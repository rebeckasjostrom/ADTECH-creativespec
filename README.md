# Specification for HTML-based creatives

This document provides general requirements for HTML/HTMl5 creatives. Please note that this document is updated frequently. Please note that the client and/or site may have extended requirements in addition to this document.

## 1. Requirements & Limitations

* Subfolders not supported.
* All media files must be loaded using server variables.
* External JavaScript documents must be initialized using our [Script Loader](https://github.com/fredrikborggren/ADTECH.load) method.


## 2. Server Variables

This section describes server variables identifiable by the adserver. These variables are partly employed in the banner code by default or may be used as additional options. Please note that these variables may only be used within the main HTML document.

List of common server variables

Variable | Description
---------|------------
`_ADPATH_` | Replaced by ADTECH file server path URL.
`_ADCLICK_` | Replaced by ADTECH click counting URL.
`_ADTIME_` | Replaced by ADTECH random millisecond value.


### HTML

CSS

```css
#foo { background: url('_ADPATH_image.png') no-repeat 0 0 scroll; }
```


Style Sheets

```html
<link href="_ADPATH_styles.css" rel="stylesheet" type="text/css">
```

Links

```html
<a href="_ADCLICK_http://clickthrough.com" target="_blank"></a>
```

Images

```html
<img src="_ADPATH_image.png">
```


### JavaScript

Define global variables within `index.html` document:

```javascript
window.adpath = '_ADPATH_';
window.adclick = '_ADCLICK_';
window.adtime = '_ADTIME_';
```

Resolve global variables within external documents:

```javascript
var imagePath = window.adpath + 'image.png';
```
```javascript
var clickPath = window.adclick + 'http://clickthrough.com';
```

## 3. Client Side

Recommendations for advert designers and developers:

* Avoid including any `<html>`, `<head>`, `<meta>` and/or `<body>` elements, creative code will be embedded within an existing website structure.
* Avoid applying any styles on common website elements, ID's and/or class names to prevent conflicts with existing website structure. We highly recommend using unique ID's and class names!

Remember, this code will be embedded within an existing website structure!
