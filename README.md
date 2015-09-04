# Specification for HTML-based adverts

## 1. Files
* Avoid use of subfolders.
* Require all media files under index document, resolving local file paths is restricted.
* External JavaScript documents may be loaded using a JavaScript function and/or copy/pasted within the index document. We recommend using our [Script Loader](http://www.github.com) function.
* All local (uploaded) files must be included using our `_ADPATH_` variable within the index document.

```html
<img src="_ADPATH_image.png">
```

Important: ad server variable `_ADPATH_` (as well as all others) can only be used within the index document.

## 2. Click Counter

```html
<a href="_ADCLICK_http://domain.com">
```

Important: ad server variable `_ADCLICK_` (as well as all others) can only be used within the index document.

## 3. Client Side

Recommendations for advert designers and developers:

* Avoid including any `<html>`, `<head>`, `<meta>` and/or `<body>` elements, creative code will be embedded within an existing website structure.
* Avoid applying any styles on common website elements, ID's and/or class names to prevent conflicts with existing website structure. We highly recommend using unique ID's and class names!

Remember, this code will be embedded within an existing website structure!
