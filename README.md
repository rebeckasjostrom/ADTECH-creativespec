# Specification for HTML based adverts

## 1. Ad Server Side

### Files and Folders
* Avoid use of subfolders.
* Require all media files under main HTML document, resolving local file paths is restricted.

### Ad Server Variables

Local file path

```
<img src="_ADPATH_image.png">
```

Click Through URL

```
<a href="_ADCLICK_http://domain.com">
```

Note: ad server variables can only be used within the main HTML document.

## 2. Client Side
