---
title: "SASSy Colors"
date: 2018-08-29T23:10:20+03:00
draft: false
description: Control color using SASS functions
tags: [CSS, SASS, SCSS, stylesheet, color, CSS-tricks, frontend, FE]
keywords: [CSS, SASS, SCSS, stylesheet, Color, CSS tricks, Frontend, FE]
---

TBH, at first, I wasn't thrilled with the choice of `Sass` (or more accurate `SCSS`) for [our](https://www.bigpanda.io/) `ReactJS` component library.    
Whenever possible, I prefer going with the _'pure'_ approach, in this case `CSS`.    
But as the project matures I discover more of the useful features Sass has to offer.

Today, our legendary UX [Shabi](https://github.com/idanshabi) taught me about the Sass color functions. Together with variables, these can really speed up my development process.

#### Usage

This is an actual example from our basic button component.

Say we have a base color variable `bp-blue`, defined in our stylesheet or imported from another
variables file.

We want our button's `background-color` to have the base color by default, but alternated to a second
lighter color when hovered and a third darker color when active (pressed). This is a pretty common
behavior.

Instead of inserting two other hex values or variables we can simply utilize Sass `lighten` and
`darken` functions.

They both accept two parameters - a color and a percentage (0% - 100%) and returns a color with the lightness/darkness increased by that amount.

#### Code Sample

```CSS
.bam-button {
  background-color: $bp_blue;

  &:hover {
    background-color: lighten($bp_blue, 10); // 10% lighter
  }

  &:active {
    background-color: darken($bp_blue, 15); // 15% darker
  }
}

```
![Bam Button Example](/images/sass-colors.png)

Using Sass color functions makes future color changes much easier.

There are many other color functions you can play with, like `saturate`, `Adjust-hue` and `shade`.

If you know other Sass tricks go ahead and write them in the comments section below.

