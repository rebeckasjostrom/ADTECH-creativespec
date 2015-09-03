# Specification for HTML based adverts

## 1. Ad Server Side

### Files and Folders
* Avoid use of subfolders.
* Require all media files under main HTML document, resolving local file paths is restricted.
* A

### Ad Server Variables

Local file path

```
_ADPATH_
```

Click Through URL

```
_ADCLICK_
```

Click Through URL (escaped)

```
_ADCLICKESC_
```

Note: ad server variables can only be used within the main HTML document.

## 2. Client Side
