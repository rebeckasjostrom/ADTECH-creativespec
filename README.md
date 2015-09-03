# Specification for HTML-based adverts

## 1. Files
* Avoid use of subfolders.
* Require all media files under index document, resolving local file paths is restricted.
* External JavaScript documents may be loaded using a JavaScript function and/or copy/pasted within the index document. We recommend using our [Script Loader](http://www.github.com) function.

###### Sidenote
All local (uploaded) files must be included using our `_ADPATH_` variable within the index document.

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

* Do not include any HTML `<html>`, `<head>` and/or `<body>` structure.
* Rembember to use unique ID and/or classnames to avoid style conflicts with websites. 
