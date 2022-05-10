# Image Carousel

This is the template I built for the component we use with Slick Image Carousel. 
Using a CDN/API (ImgIX) I was able to set up a template that would take one image from the CMS and auto generate 37 different versions of the same image.

**The triggers for the variations of images:**
- Screen Size of Device: Reduce image size (dimensions) and quality
- Pixel Density of Device: Reduce quality at various stages
- Best Image Format for Browser: avif, webp, jpg which impacts the compression/speed of load time
- Placeholder Image for slow loads: Drastically reduced image size (dimensions), quality, and heavy blur. This was inserted via inline styles to make it the first thing to load.
- I combined the Placeholder Image with native width and height dimensions to make sure there was no CLS and ensure that some image would be in place to indicate to users something is loading.
- Portrait or Landscape: I designed the template to be able to switch between a landscape or portrait, and this is chosen by the user. If it is portrait it will cover/fill the background with a copy of the image with a heavy blur to keep it from being hard to see the original.

The template also notes which is the first image in the loop and separates it (again dependent on if it is Landscape or Portrait) and will include Native Eager Loading on it only since it is the first one to be displayed above the fold.

**Resources:**
- [Ken Wheeler's Slick Repo](https://github.com/kenwheeler/slick)
- [ImgIX](https://imgix.com/)
- [Smashing Mag - Humble img](https://www.smashingmagazine.com/2021/04/humble-img-element-core-web-vitals/)


**Note:** I initially had native lazy loading on all subsequint images after the first image but I found this actually slowed everything down. Instead I stuck with decode='async' on all images other than the first and it made a substantial improvement.

Here is a repository for the [whole template](https://github.com/Gruffel/Jekyll-Template#jekyll-template-work).

If you would like to learn more here is [my portfolio website](https://turtonic.com).
