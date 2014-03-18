# CSS Styleguide #

## Formatting rules ##

+ Use soft tabs with two spaces for indentation.
+ Start each selector and declaration on a new line.
+ Put a space before the opening brace in rule declarations.
+ Place closing brace on a separate line.
+ Put a blank line between rules.
+ Put a space after the colon in property declarations.
+ Every comma in multi-value properties must be followed by a space.
+ Place each value, indented, on a new line when dealing with long property values such as gradients and shadows to improve readability.
+ Use a semicolon after every declaration.
+ Omit leading zeros in values.
+ Prefer lowercase hexadecimal color codes, and use the shorthand notation where possible.
+ Use double quotation marks for attribute selectors, property values, URLs, etc.

```css
/* Bad */
.panel-body, .box{
  border:1px solid rgb(47, 146, 238); color:#4455AA;
  box-shadow: 1px 1px 1px rgba(0,0,0,0.1), 2px 2px 3px #888 inset
}
.panel-input[type=text]{
  font-family: 'Open Sans', sans-serif;
  font-size: 14px
}

/* Good */
.panel-body,
.box {
  border: 1px solid #2f92ee;
  color: #45a;
  box-shadow: 
    1px 1px 1px rgba(0, 0, 0, .1),
    2px 2px 3px #888 inset;
}

.panel-input[type="text"] {
  font-family: "Open Sans", sans-serif;
  font-size: 14px;
}
```


## Selectors ##

Rules to follow:

+ Use class selectors whenever possible.
+ Do not use id selectors.
+ Avoid computationally expensive selectors like attribute and universal selectors when possible.
+ Keep selectors short and do not overqualify them.

```css
/* Bad */
#container {}
div[class="frame"] {}
div.alert h3.alert-title span {}

/* Good */
.container {}
.frame {}
.alert-title span {}
```


## Naming conventions ##

Use meaningful class names that reflect the purpose of the elements they are assigned to whenever possible. For classes that have no particular meaning use generic names to reduce the chance of needing to rename them later.

Name classes in such a way as to convey what they are about while keeping them as brief as possible.

Keep class names lowercase and separate words by a hyphen.

```css
/* Bad */
.kpp-12 {}
.title-blue {}
.panel_title {}

/* Good */
.title {}
.panel {}
.panel-title {}
.alt {}  
```

Never reference `js-` prefixed class names from CSS files as they are used exclusively from JavaScript files.

Use the `is-` prefix for state rules that are shared between CSS and JS.


## Declaration order ##

To maintain consistency declarations should follow a specific order. I recommend sticking to the order defined by Twitter in [Recess][order]. Here is an example:

```css
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 10;

  /* Box model */
  display: block;
  float: left;
  width: 100%;
  height: 100%;
  padding: 10px;
  margin: 10px;
  overflow: auto;

  /* Typography */
  font-family: sans-serif;
  font-size: 18px;
  line-height: 1.4;
  color: #333;
  text-align: center;

  /* Visual */
  background: #eee;
  border: 1px solid #444;
}
```


## Shorthand properties ##

Whenever possible, use [shorthand properties][shorthand] to improve code readability.

```css
/* Bad */
.example {
  padding-bottom: 1em;
  padding-left: 2em;
  padding-right: 2em;
  padding-top: 0;
  font-family: Helvetica, sans-serif;
  font-size: 16px;
  line-height: 1.4;
  border-bottom-style: none;
}

/* Good */
.example {
  padding: 0 2em 1em;
  font: 16px/1.4 Helvetica, sans-serif;
  border-bottom: 0;
}
```


## Vendor prefixes ##

If vendor prefixed declarations are needed make sure to align properties so that colons all end up on the same column and order them from longest to shortest. The last declaration should always come last.

```css
/* Bad */
.example {
  -ms-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
  -webkit-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
  -moz-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
  box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
  -o-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
}

/* Good */
.example {
  -webkit-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
     -moz-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
      -ms-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
       -o-box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
          box-shadow: inset 0 1px 5px rgba(0, 0, 0, .2);
}
```



## Miscellaneous ##

+ Do not use `@import`.
+ Avoid using `!important`.

[shorthand]: https://developer.mozilla.org/en-US/docs/Web/CSS/Shorthand_properties
[order]: https://github.com/twitter/recess/blob/master/lib/lint/strict-property-order.js#L36
