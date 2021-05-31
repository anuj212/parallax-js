# parallax-js
True parallax scrolling, not just fixed backgrounds. Done simply with (lightweight) vanilla JavaScript.

# How to Use
parallax-js uses HTML, CSS, and JavaScript togeather to create the desired effect. Here's how to set up each:

## HTML
```HTML
<div class="parent-element">
  <!-- Your content -->
  <div class="parallax" data-depth="4"></div>
</div>
```
- Give your background element a class of "parallax"
- Give your background element a `dataset-property` of 'depth' with a value between 1 and 10 (higher values are also okay, you just won't see much movement)
- Link your parallax-js script (or include it in another JavaScript file)

## CSS
```SCSS
.parent-element {
    //give the element relitive positioning (this is required to keep the absolute positioned chidren contained)
    position: relative;
    //keep the child element from overflowing oustide of the parent
    overflow: hidden;
}
.parallax {
  //let JS move the element
  position: absolute;
  //stretch the element to fit it's parent (the parent must have relitive positioning)
  width: 100vw;
  height: 100%;
  //center the element in it's parent (the parent must have relitive positioning)
  top: 50%;
  left: 50%;
  //transform the element to have it's origin at the center and to be scaled (to avoid visible edges. If visible edges are present, up the scaling to 1.2 - 1.5)
  transform: translate(-50%, -50%) scale(1.15);
  //place the element in the background
  z-index: -99;
  //background prep
  background-position: bottom;
  background-size: cover;
  //background image
  background-image: url('your-background-image.png')
}
```
