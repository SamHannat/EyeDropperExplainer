# Hi 

## Motivation

Currently, desktop versions of apps with eyedroppers have many different features which have motivated our solution. Some of them are: preview of pixel color, averaging of surrounding pixels, and adding eyedropper colors to a queue inside of a color box.
![Alt Text](paint.gif)
| Automated Example | Feature Explanation |
| ------------- | ----------- |
| <img src="paint.gif" alt="paint" width="500"/> | The visual to the left highlights the eyedropper feature inside of Paint, a desktop image editing application. The eyedropper is able to select pixels within the canvas and queue them in color boxes. |
| ![Alt Text](gimp.gif) | The visual to the left depicts the eyedropper tool inside of Gimp, another desktop image editing application. Unlike Paint, Gimp is able to sample the average color of a specified radius of pixels inside the canvas. |
| ![Alt Text](figma.gif) | The visual to the left displays the eyedropper tool inside of Figma, an image editing web application. Uniquely, this eyedropper gives users a preview of the current color as well as the color of pixels around it. This tool is restricted to sampling colors within the canvas. |

## Goals 
- Create an Eyedropper API that returns the hex value of a pixel when the pixel is clicked 
- The eyedropper will be able to provide a preview (in a grid format) when clicked on 
- Allow the user to cancel eyedropper mode  

## Non-Goals
- Allow the user to have a color picker screen to choose color from 
- Developing the UI and functionality of an eyedropper 
