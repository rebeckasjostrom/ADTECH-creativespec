# Specification for HTML-based creatives

This document provides general requirements for HTML/HTML5 creatives. Please note that this document is updated frequently. Please note that the client and/or site may have extended requirements in addition to this document.

## Contents

1. [Folder Structure]()
	2. [Introduction]()
	3. [Properties and Restrictions]()
10. [HTML Structure]()
	11. [Introduction]()
	3. [Properties and Restrictions]()
2. [Ad Server Variables]()
	3. [Properties and Restrictions]()
	4. [Variables]()
	5. [Global Scope]()
	6. [Usage]()
		9. [Images]()
		8. [Hypertext Links]()
		7. [Cascading Style Sheets (CSS)]()
		9. [JavaScript]()
		9. [JavaScript Override]()
10. [Identifiers]()
	2. [Introduction]()
	3. [Properties and Restrictions]()
	11. [Elements]()
	12. [Cascading Style Sheets (CSS)]()
	13. [JavaScript]()

## 1. Folder Structure

###Introduction

Generally, an HTML5 banner consists of an index.html file and additional files in subfolders. This typical use case is supported as long as the creative have an index.html in the root folder, additional files can be stored on the same level or in subfolders.

###Properties and Restrictions

* Root folder must contain initial `index.html` document.

##2. HTML Structure

###Introduction

Some extra recommendations/suggestions for advert designers and developers.

###Properties and Restrictions

* Avoid applying any styles on `html`,  `body` and any other common website identifiers.
* Avoid including `<html>`, `<head>`, `<meta>` and `<body>`.

## 3. Ad Server Variables

###Introduction

A list of global ad server variables identifiable by the ad server. These variables are partly employed in the banner code by default or may be used as additional options.

###Properties and Restrictions

* Ad Server variables may only be used within initial HTML document.

###Variables

The following variables are available:

Variable | Description
---------|------------
`_ADPATH_` | Replaced by the server path URL.
`_ADCLICK_` | Replaced by the click counting URL.
`_ADCUID_` | Replaced by the placement identifier.
`_ADADID_` | Replaced by the campaign/flight identifier.
`_ADBNID_` | Replaced by the banner identifier.
`_ADTIME_` | Replaced by a random value (current time in milliseconds).

###Global Scope

As previously mentioned, ad server variables may only be used within initial HTML document. However, in some cases it might be very useful to reach these externally. Achieving this generally very simple by registering global DOM variables from within the initial HTML document, making all variables available for any JavaScript dependencies with custom variable names.

Example:

```javascript
window.adpath = '_ADPATH_';
```

OR

```javascript
window.parent.adpath = '_ADPATH_';
```
###Usage

####Cascading Style Sheets (CSS)

```html
<style type="text/css">

	#foo {
		background-image: url('_ADPATH_image.png');
	}
	
</style>
```

####Images

The ad server will generally append `_ADPATH_` for attribute `src` automatically.

```html
<img src="_ADPATH_image.png">
```

####Hypertext Links

The ad server will generally append `_ADPATH_` for attribute `href` automatically.

```html
<a href="_ADCLICK_http://domain.com" target="_blank"></a>
```

####JavaScript

The ad server will generally append `_ADPATH_` for attributes `src` and `href` automatically. 

```javascript
var link.href = '_ADCLICK_http://domain.com';
```

```javascript
var img.src = '_ADPATH_image.png';
```

####JavaScript Override

Override automatic appending for media hosted elsewhere by adding `'' + ` before the path string.

```javascript
var img.src = '' + 'http://domain.com/image.png';
```

##4. Identifiers

###Introduction

Using unique identifiers, classes, variables and function names is a good way of avoiding conflicts, such as two ads with the same code interfering with one another.

###Properties and Restrictions

* Use unique identifiers for elements, styles, variables and methods.
* Ad Server variables may only be used within initial HTML document.

###Elements

Using campaign and banner ID as element identifier

```html
<div id="foo__ADADID___ADBNID_"></div>
```

Example result:

```html
<div id="foo_1234567_1"></div>
```

###Cascading Style Sheets (CSS)

Using campaign and banner ID as element identifier

```css
#foo__ADADID___ADBNID_ {
	background-color: #000;
}
```

Example result:

```css
#foo_1234567_1 {
	background-color: #000;
}
```

###JavaScript

Using campaign and banner ID as element identifier

```javascript
document.getElementById('foo__ADADID___ADBNID_');
```

Example result:

```javascript
document.getElementById('foo_1234567_1');
```
