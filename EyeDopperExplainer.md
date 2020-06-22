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
| <p align="center"> <img src="paint.gif"> </p> |
| The visual below depicts the eyedropper tool inside of Gimp, another desktop image editing application. Unlike Paint, Gimp is able to sample the average color of a specified radius of pixels inside the canvas. |
| <p align="center"> <img src="gimp.gif"> </p> |
| The visual to the left displays the eyedropper tool inside of Figma, an image editing web application. Uniquely, this eyedropper gives users a preview of the current color as well as the color of pixels around it. This tool is restricted to sampling colors within the canvas. |
| <p align="center"> <img src="figma.gif"> </p> |

## Goals 
- Create an Eyedropper API that returns the hex value of a pixel and the cursor coordinates when the pixel is clicked 
- The eyedropper will be able to provide a preview (in a grid format) when clicked on
- <img src= "https://github.com/SamHannat/EyeDropperExplainer/blob/master/preview.png" alt= "Preview feature of EyeDropper" max-height= "150"/>
- Allow the user to cancel eyedropper mode through ESC key as well as other methods chosen by the developer  
- Allow eyedropper access outside of the browser 
- Allow the developer to disable eyedropper mode when hovering over the toolbar

## Non-Goals
- Allow the user to have a color picker screen to choose color from 
- Allowing the developer to customize the UI of the eyedropper. This is more of a Version 2 since customers have told us that it was not their top priority currently. 
- Create a React component which can be imported as a package for Version 1 but we might implement it in Version 2 as it would prove beneficial to developers using React 
- Allow the user to select more than one pixel while in Eyedropper mode. This has been mentioned during our customer interviews as a possible addition to version 2 but "not needed for version 1".
- Disable the Eyedropper when outside of the browser screen

## Solution
 - The API will enable web developers to incorporate an eyedropper in their native web applications. The eyedropper would allow the developer to access the pixel data at a location specified by the cursor such as RGBA value, a live update preview of the pixel, radius size of the pixel area to capture, a keyboard shortcut to escape out of the eyedropper. 
 - The following code example is what a developer would use to access the eyedropper API. 
