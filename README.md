## Gridly **v1.0.0-rc.1**
a simple grid framework for sass and css developers.
 
If this framework is useful for you, you might want to buy me a cup of coffee to keep me fresh.

[![Buy me a cup of coffee via PayPal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_LG.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=PGTACGX86MG82)

## Features

 * SASS by [nex3] (https://github.com/nex3/sass.git)
 
## Using Gridly
**Table of contents**
* [CSS Developers](#css-developers)
 * [Creating the grid structure](#creating-the-grid-structure)
 * [Media queries](#media-queries)
 * [Push, pull, and offsets](#push-pull-and-offsets)
 * [Using the sticky footer](#using-the-sticky-footer)


### CSS Developers
---
To use gridly place `gridly.min.css` into your project. Then simply include: 
```html
<link rel="stylesheet" href="<your css folder>/gridly.min.css">` 
```
in your `head` tag.

#### Creating the grid structure

You can wrap the entire grid in the `.container` class to provide a 15px page margin around your entire grid element.  The grid comes with a total of **12** colums.  Each 12 column set must be wrapped in a `.row` classed element.
 ``` html
 <div class="container">
   <div class="row">
     <div class="col-6">
       ...
     </div>
     <div class="col-6">
       ...
     </div>
   </div>
 </div>
 ```
 
#### Media queries
Gridly comes with 4 breakpoints installed as well as a simple column structure not wrapped in a `media query`.

|Column name | min-width | max-width |
|:----------:|:---------:|:---------:|
|`col`       |           |           |
|`xsmall`    |           | **480px** |
|`small`     | **481px** | **768px** |
|`medium`    | **769px** | **992px** |
|`large`     | **993px** |           | 

You can call on these by adding them to you `div`, `section`, `span`, or any other elements:

```html
<div class="row">
  <div class="col-8 xsmall-12">
    ...
  </div>
  <div class="col-4 xsmall-6">
    ...
  </div>
</div>
```

The example above will create two columns.  On a desktop the first column will span 8 spaces, and the second will span 4 spaces.  On a mobile device the first column will span the entire width of the device screen, and the second column will span half of the screen.

#### Push, pull, and offsets
Gridly comes with several `.push`, `.pull`, and `.offset` classes.  Each breakpoint class also has these classes.

```html
<div class="container">
  <div class="row">
    <div class="offset-6 xsmall-offset-4">
      ...
    </div>
    <div class="col-6 xsmall-8">
      ...
    </div>
  </div>
  <div class="row">
    <div class="push-9 small-push-6">
      ...
    </div>
    <div class="pull-3 small-pull-6">
      ...
    </div>
  </div>
</div>
```

#### Using the sticky footer
Gridly comes installed with a sticky footer class, which will allow you to create a footer element at the absolute bottom of the page.  You can use this by applying the `.sticky-footer` class to the `body` tag of your html and placing a `footer` element or a `div` with the `.footer` class at the bottom of your html.

```html
<body class="sticky-footer">
 <div class="container">
   <div class="row">
     <div class="col-6">
       ...
     </div>
     <div class="col-6">
       ...
     </div>
   </div>
 </div>
 <footer>
   ...
 </footer>
</body>
```
