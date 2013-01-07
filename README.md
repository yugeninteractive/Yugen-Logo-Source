## Example
<http://yugen.ca/lab/yugenlogo/source/index.html>


## Authors
- Hakim El Hattab - Development - <http://hakim.se>
- Garus Booth - Founder / Art Direction / Design - <http://bythebooth.com>
- Ram Puvanesasingham - Founder -  <http://yugen.ca>
- Kuhan Puvanesasingham - Founder - <http://yugen.ca>


## Yugen Logo Documentation

This document outlines the functionality built into the Yugen logo animation project and aims to explain the source architecture on a high level.


### Fallback
The primary logo animation is rendered on the HTML5 canvas element but there are also two levels of degraded experiences depending on what level of support is detected. Layer by layer:


1. If JavaScript is not available a static image is shown.

2. If JavaScript is available BUT support for canvas is not detected, a rotation of still images is shown. The image changes whenever the mouseover event is dispatched by the container DOM element. The list of images to rotate through can be configured via the initialization object on the YugenLogo class (more on that later).

3. If Javascript is available AND canvas support is detected, we run the intended canvas animation. Bells. Whistles. The works!


### JavaScript Structure
The core of the logo animation logic and display is in the source/js/yugenlogo.js file. Any type of interaction input that affects the logo is stored in a separate plug-in JavaScript file. This decoupling enables a flexible architecture that simplifies the process of adding new, or removing old, types of input. Input files are stored in the source/js/input/ folder.


### Configuration
The index.html file delivered with this project contains some debug elements which help test the configuration values of the logo.

The logo has an extensive range of options available to configure the properties of shapes, fallback images, framerate, colors and much more. The default options with inline documentation can be found in source/js/yugenlogo.js, note that not all of these are exposed in the debug panel. Options can be overridden when calling the YugenLogo.initialize method, see the bottom of index.html for an example of this.


### Build script
There are Ant build scripts available in the build/ folder to help simplify the deployment process. This script takes everything in the source/ folder, minifies it, and moves it to the deploy folder.

## Changelog
0.1 Initial release


## License
MIT licensed

Copyright (C) 2013  
Yugen Inc. http://yugen.ca