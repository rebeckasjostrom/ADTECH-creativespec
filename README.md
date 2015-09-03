# Specification for HTML-based adverts

## 1. Files
* Avoid use of subfolders.
* Require all media files under main HTML document, resolving local file paths is restricted.

#### Sidenote
All local (uploaded) files must be included using our `_ADPATH_` variable within the index document.

```html
<img src="_ADPATH_image.png">
```

## 2. Click Counter

```html
<a href="_ADCLICK_http://domain.com">
```

Note: ad server variables can only be used within the main HTML document.

## 3. Client Side
