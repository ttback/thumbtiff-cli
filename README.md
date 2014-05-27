# thumbtiff-cli 
> The command line interface for generating thumbnails via sharp.


Goal
---------
Leverage the sharp module for quick tiff thumbnail generation in the command line.


Prerequisites:
---------
sharp: libvips wrapper for node.js
Please see https://www.npmjs.org/package/sharp for more information on how to install libvips.


Installation
---------
```
npm install -g thumbtiff-cli
```

Options
---------
  Usage: thumbtiff [options]

  Options:

    -h, --help                        output usage information
    -V, --version                     output the version number
    -h, --height <n>                  autoscale image to height. Default: 480
    -q, --quality <n>                 set thumbnail quality. Default: 80
    -s, --sharpen                     shapren the image
    -t, --template <template string>  template the output file name, supported %n-filename, %h-height, %q-quality
    -e, --extension <string>          set output file extension. Default: png
    -o, --output <file>               output to a file

Note: output option will override template and extension options.


Examples
---------

Quick run
```
thumbtiff Sample.tiff
```
Output: Sample.png, autoscaled to 480px in height.


Resize to 360px in height, use name_height filename template
```
thumbtiff Sample.tiff -h 360 -t %n_%h

```
Output: Sample_360.png


Resize to 360px in height for two tiff files at once.
```
thumbtiff Sample1.tiff Sample2.tiff -h 360

```
Output: Sample1.png, Sample2.png
