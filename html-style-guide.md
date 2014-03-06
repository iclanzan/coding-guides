# HTML style guide #

_Strive to maintain HTML standards and semantics, but not at the expense of practicality. Use the least amount of markup with the fewest intricacies whenever possible._

## Syntax ##

+ Use soft tabs with two spaces for indentation.
+ Always use double quotes for wrapping attribute values.
+ Mark tags of [void elements][void-elements] as self-closing.
+ Do not declare a value for [boolean attributes][boolean-attributes].

```html
<!DOCTYPE html>
<html>
  <head>
    <title>Page title</title>
  </head>
  <body>
    <h1 class="heading">Welcome!</h1>
    <input type="text" disabled />
  </body>
</html>
```

[void-elements]: http://www.whatwg.org/specs/web-apps/current-work/multipage/syntax.html#void-elements

[boolean-attributes]: http://www.whatwg.org/specs/web-apps/current-work/multipage/common-microsyntaxes.html#boolean-attributes


### Doctype ###

Enforce standards mode and more consistent rendering in every browser by including `<!DOCTYPE html>` at the beginning of every HTML page.


### Attribute order ###

HTML attributes should come in the following order for easier reading of code.

- `class`
- `id`
- `data-*`
- `src`, `for`, `type`, `href`

Classes make for great reusable components, so they come first. Ids are more specific and should be used sparingly (for in-page bookmarks for example), so they come second.
