## Gridly **v1.2.0-rc.1**
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
* [SASS-Developers](#sass-developers)
 * [Utilizing SASS silent classes](#utilizing-sass-silent-classes)
 * [Gridly variables and aliases](#gridly-variables-and-aliases)
 * [Gridly SASS Silent Helper Classes](#gridly-sass-silent-helper-classes)
 * [Making Custom Breakpoints](#making-custom-breakpoints)


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

### SASS Developers
---
To use gridly place `gridly.scss` into your project. Then simply include:
```css
@import "<your sass folder>/gridly";
```
at the top of your SCSS or SASS stylesheet.

#### Utilizing SASS Silent Classes
To utilize sass silent classes you will first need to change `$sass-silent-classes` to `true` in the gridly.scss file.  You will then have to use `@extend` to extend each property.

```css
.my-element {
 @extend %columns;
}
```

#### Gridly variables and aliases
Gridly comes with several variables, and variable aliases. The aliases make the variable easier to call while coding.

|Variable Name               |Aliases     |Default Value|Definition                                                                                        |
|:--------------------------:|:----------:|:-----------:|:------------------------------------------------------------------------------------------------:|
|`$sass-silent-classes`      |`$silent`   |`false`      |This makes all classes created by gridly to use the sass `%` instead of `.` before the class name.|
|`$grid-max-columns`         |`$colums`   |12           |This is the total amount of columns per row that gridly will generate.                            |
|`$grid-page-gutter`         |`$gutter`   |15px         |This sets the left and right margins of the `.container` element                                  |
|`$grid-column-padding-right`|`$col-pad-r`|15px         |This sets the padding to the right of each column element.                                        |
|`$grid-column-padding-left` |`$col-pad-l`|15px         |This sets the padding to the left of each column element.                                         |
|`$grid-column-margin`       |`$col-mar`  |0            |This sets the column margins.                                                                     |
|`$grid-normal-column-name`  |`$col`      |"col"        |This sets the base column class name.                                                             |
|`$grid-xsmall-column-size`  |`$xs-size`  |480px        |This sets the first breakpoint size for the smallest column class.                                |
|`$grid-xsmall-column-name`  |`$col-xs`   |"xsmall"     |This sets the smallest column class name.                                                         |
|`$grid-small-column-size`   |`$sm-size`  |768px        |This sets the second breakpoint size for the "small" column class.                                |
|`$grid-small-column-name`   |`$col-sm`   |"small"      |This sets the second smallest column class name.                                                  |
|`$grid-medium-column-size`  |`$md-size`  |992px        |This sets the third breakpoint size for the "medium" column class.                                |
|`$grid-medium-column-name`  |`$col-md`   |"medium"     |This sets the third smallest column class name.                                                   |
|`$grid-large-column-size`   |`$lg-size`  |1200px       |This sets the final breakpoint size for the "large" column class.                                 |
|`$grid-large-column-name`   |`$col-lg`   |"large"      |This sets the largest column class name.                                                          |
|`$sticky-footer-height`     |`$sf-height`|150px        |This sets the height of the `.sticky-footer` class.                                               |
|`$sticky-footer-top-margin` |`$sf-t-mar` |15px         |This sets the margin-top spacing of the `.sticky-footer` class.                                   |

#### Gridly SASS silent helper classes
Gridly comes with a few silent classes that can be called with the `@extend` command.
* %clearfix - applies a standard clearfix to the element.
* %columns - applies columns styles to an element.

```css
.my-element {
  @extend %clearfix;
}
```

#### Making custom breakpoints
You can creat customized breakpoints by changing the 4 built in breakpoint classes or by using the `make-breakpoints` mixin

```css
@include make-breakpoints(<your column class name>, <screen min-width>, <screen max-width>);
```

Both the `min-width`, and `max-width` variables are optional simply leave them blank to create a column set without wrapping them in a media query.

