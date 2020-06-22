# EyeDropper API 
Authors: [Sidhika Tripathee](https://github.com/t-sitri), [McKinna Estridge](https://github.com/t-saestr), [Sammy Hannat](https://github.com/samhannat)

## Introduction
Currently on the web, creative application developers are unable to implement eyedropper functionality. This explainer proposes a web-based API that enables developers to build eyedropper-like tools in their web apps. 

## Problem

Several creative applications would like to utilize the ability to pick a color from pixels on the screen. Many cross-platform applications, e.g. Powerpoint, have eyedroppper functionality on their native app but are unable to carry it over the web.      
   
Although some browsers have built-in eyedropper functionality into color input tags. This limits customizability and can be seen as being out of place for many applications. 

## Motivation

Currently, desktop versions of apps with eyedroppers have many different features which have motivated our solution. Some of them are: preview of pixel color, averaging of surrounding pixels, and adding eyedropper colors to a queue inside of a color box.

| Feature Explanation |
| ------------- |
| The visual below highlights the eyedropper feature inside of Paint, a desktop image editing application. The eyedropper is able to select pixels within the canvas and queue them in color boxes. |
| <img src = "https://github.com/SamHannat/EyeDropperExplainer/blob/master/paint.gif" height="550"/>|
| The visual below depicts the eyedropper tool inside of Gimp, another desktop image editing application. Unlike Paint, Gimp is able to sample the average color of a specified radius of pixels inside the canvas. |
|  <img src = "https://github.com/SamHannat/EyeDropperExplainer/blob/master/gimp.gif" height="550"/> |
| The visual to the left displays the eyedropper tool inside of Figma, an image editing web application. Uniquely, this eyedropper gives users a preview of the current color as well as the color of pixels around it. This tool is restricted to sampling colors within the canvas. |
|  <img src = "https://github.com/SamHannat/EyeDropperExplainer/blob/master/figma.gif" height="550"/>|

## Goals 
- Create an Eyedropper API that returns the hex value of a pixel and the cursor coordinates when the pixel is clicked 
- The eyedropper will be able to provide a preview (in a grid format) when clicked on
- <img src= "https://github.com/SamHannat/EyeDropperExplainer/blob/master/preview.png" alt= "Preview feature of EyeDropper" max-height= "150"/>
- Allow the user to cancel eyedropper mode through ESC key as well as other methods chosen by the developer  
- Allow eyedropper access outside of the browser 
- Allow the developer to disable eyedropper mode when hovering over the toolbar

## Non-Goals
- Return a Color object rather than hex value when pixel is clicked. This will be implemented as soon as a Color object is avaiable in HTML to implement. 
- Allowing the developer to customize the UI of the eyedropper. This is more of a Version 2 since customers have told us that it was not their top priority currently. 
- Allow the user to select more than one pixel while in Eyedropper mode. This has been mentioned during our customer interviews as a possible addition to version 2 but "not needed for version 1".
- Allowing the developer to restrict the Eyedropper when in certain areas

## Solution
 - The API will enable web developers to incorporate an eyedropper in their native web applications. The eyedropper would allow the developer to access the pixel data at a location specified by the cursor such as hex value, and the cursor position.  

### EyeDropper Object

We propose the addition of an eyedropper object with the following functionality:

#### Methods
- EyeDropper(): Constructor for the eyedropper object
- enable():  Replaces the cursor with predefined magnifying preview. When the mouse is clicked, the value attribute of the eyedropper object is updated with the color of the pixel where the user clicked. Calling enable on an eyedropper when one is already enabled throws an error.  

- disable(): Exits the magnifying preview and the cursor returns to its regular functionality. 

#### Attributes 
- value: The hex value of the color of the last pixel chosen by the eyedropper. Defaults to #000000  

- IsEnabled: Whether the magnifying preview of the eyedropper is enabled.  

### Proposed Events

We propose two events that a developer can utilize in their applications

#### colorselect
This event is fired when a user using the eyedropper selects a colour. 

The value attribute of the eyedropper object is replaced by the hex value of the color of the pixel the user selected. After the event is fired, the eyedropper is disabled.

The screenX, screenY attributes of the event are populated with the (x,y) coordinates of where the user clicked. The ID attribute of the event is populated with that of the eyedropper object that triggered the event. 

#### exit

This event is fired when the eyedropper is exited manually by the user by pressing escape. This event allows developers to graciously handle such a scenario. 

## Example Usage
```javascript
document.getElementById().addEventListener('click', event => {
   EyeDropper.enable()
 });;
 ```
## Metrics
- User studies
- Length of time of each use
- Length of time between pixel selection
- Number of uses per browser session
- Desktop vs browser usage146
