# Hi 

## Motivation

Currently, desktop versions of apps with eyedroppers have many different features which have motivated our solution. Some of them are: preview of pixel color, averaging of surrounding pixels, and adding eyedropper colors to a queue inside of a color box.


| Syntax | Description |
| ----------- | ----------- |
| Feature Explanation | Automated Example |
| The visual to the right highlights the eyedropper feature inside of Paint, a desktop image editing application. The eyedropper is able to select pixels within the canvas and queue them in color boxes.  | ![Alt Text](paint.gif) |
| The visual to the right depicts the eyedropper tool inside of Gimp, another desktop image editing application. Unlike Paint, Gimp is able to sample the average color of a specified radius of pixels inside the canvas. | ![Alt Text](gimp.gif) |
| The visual to the right displays the eyedropper tool inside of Figma, an image editing web application. Uniquely, this eyedropper gives users a preview of the current color as well as the color of pixels around it. This tool is restricted to sampling colors within the canvas. | ![Alt Text](figma.gif) |

## Goals 

- Allow image editing applications to implement eyedropper functionality which can pick color from one pixel and is customizable for the user 
- The eyedropper will be able to provide a preview when clicked on (all info contained within the browser) 
- Allow the user to cancel selection via Escape key 
- Create a tool that is secure and will prevent privacy issues (only send info to site when clicked) 
## Non-Goals
- Allow the user to have a color picker screen to choose color from 
- Developing the UI and functionality of an eyedropper 
