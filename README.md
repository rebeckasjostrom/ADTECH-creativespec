# Specification for HTML based adverts

## Files and Folders
* Avoid use of subfolders.
* Require all media files under main HTML document, resolving local file paths is restricted.

Locating files with help of variable

```html
<img src="_ADPATH_image.png">
```

## Click Counter

```html
<a href="_ADCLICK_http://domain.com">
```

Note: ad server variables can only be used within the main HTML document.

## Client Side
