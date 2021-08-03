# Frontend Mentor - 3-column preview card component solution

This is a solution to the [3-column preview card component challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/3column-preview-card-component-pH92eAR2-). Frontend Mentor challenges help you improve your coding skills by building realistic projects.

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot Desktop](#screenshot-desktop)
  - [Screenshot Mobile](#screenshot-mobile)
  - [Links](#links)
- [My process](#my-process)
  - [What i Learned](#what-I-learned)
  - [Built with](#built-with)
  - [Useful resources](#useful-resources)
- [Author](#author)

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot desktop

![](./screenshots/screenshots/screenshot-desktop.jpg)

### Screenshot mobile

![](./screenshots/screenshots/screenshot-mobile.jpg)

### Links

- Solution URL: [Add solution URL here](https://your-solution-url.com)
- Live Site URL: [Add live site URL here](https://your-live-site-url.com)

## My process

### Built with

- Semantic HTML5 markup
- SCSS and with a custom formula to convert px into rem.
- CSS Grid
- Mobile-first workflow

### What I learned

I made a function in SCSS to convert pixels into rem:

```
$base-font-size: 15px;

// Function to strip the units from a number. See https://stackoverflow.com/questions/12328259/how-do-you-strip-the-unit-from-any-number-in-sass
@function strip-units($number) {
  @return math.div($number, $number * 0 + 1);
}

// Function that converts any pixel measure into rem.
// Is there a way to strip units from a number?
@function pxrem($px) {
  $foo: math.div($px, strip-units($base-font-size));

  // Only two digits after the decimal point. Thanks to https://stackoverflow.com/questions/10369643/rounding-numbers-in-sass-and-adjusting-the-amount-of-decimals/38449536
  $result: round($foo * 100) / 100;

  @return $result + rem;
}
```

`$base-font-size` is the `font-size` of the html tag. If `$base-font-size` is 15px, that would be 1rem. If for example I want a `padding` of 26px, but I want to use the rem equivalent, I will write: `padding: pxrem(26)`. When compiled in css that will become `padding: 1.7333333333rem`.

### Useful resources

- [This function](https://stackoverflow.com/questions/12328259/how-do-you-strip-the-unit-from-any-number-in-sass) to strip the units from a number in SCSS.
- Function to [limit the number of decimals in SCSS](https://stackoverflow.com/questions/10369643/rounding-numbers-in-sass-and-adjusting-the-amount-of-decimals/38449536)

## Author

- Frontend Mentor - [@yourusername](https://www.frontendmentor.io/profile/Filippo-B)
