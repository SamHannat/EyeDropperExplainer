# Hi 

## Motivation

Currently, desktop versions of apps with eyedroppers have many different features which have motivated our solution. Some of them are: preview of pixel color, averaging of surrounding pixels, and adding eyedropper colors to a queue inside of a color box.

| Automated Example | Feature Explanation |
| ------------- | ----------- |
| ![Alt Text](paint.gif) | The visual to the left highlights the eyedropper feature inside of Paint, a desktop image editing application. The eyedropper is able to select pixels within the canvas and queue them in color boxes. |
| ![Alt Text](gimp.gif) | The visual to the left depicts the eyedropper tool inside of Gimp, another desktop image editing application. Unlike Paint, Gimp is able to sample the average color of a specified radius of pixels inside the canvas. |
| ![Alt Text](figma.gif) | The visual to the left displays the eyedropper tool inside of Figma, an image editing web application. Uniquely, this eyedropper gives users a preview of the current color as well as the color of pixels around it. This tool is restricted to sampling colors within the canvas. |

## Goals 
- Create an Eyedropper API that returns the hex value of a pixel when the pixel is clicked 
- The eyedropper will be able to provide a preview (in a grid format) when clicked on 
(will insert pic of eyedropper we already have)
- Allow the user to cancel eyedropper mode  
- Allow eyedropper access outside of the browser unless disabled
- Allow the developer to disable eyedropper mode when hovering over the toolbar and outside the browser screen

## Non-Goals
- Allow the user to have a color picker screen to choose color from 
- Allowing the developer to customize the UI of the eyedropper. This is more of a V2 since customers told us that it was not their top priority currently. 
- Create a React component which can be imported as a package for V1 but we might implement it in V2 as it would prove beneficial to developers using React 

