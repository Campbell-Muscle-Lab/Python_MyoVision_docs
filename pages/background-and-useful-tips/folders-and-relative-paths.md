---
layout: page
title: Folders and relative paths
description: Web-based help for Python_MyoVision
---
### Overview

You are probably used to arranging your files in folders, and navigating between folders using a mouse.  

When you use Python_MyoVision from the command line, as we are in this tutorial, you need to know about paths, because you have to type them into your configuration file. This page should get you started. If you want more details, try [this page](http://desktop.arcgis.com/en/arcmap/10.3/tools/supplement/pathnames-explained-absolute-relative-unc-and-url.htm).


### Primer

Imagine your hard drive just has two directories: data and code. Each contains a single file. We can draw that like this:  

````
-c-
   |-data
   |  |- image_1.png
   |
   |-code
      |- test.py   
````

We can always refer to image_1.png using the full path `c:\data\image_1.png`.  

If we are the `data` folder, we can refer to it just using the file name `image_1.png`.  

If we are in the `code` folder, we can refer to it using a relative path `..\data\image_1.png`. Here, the `..` means go up a level, so the relative path goes up to `c:\` and then down into `data\image_1.png`.  


### Background for demos

This documentation doesn't know which directory you installed Python_MyoVision in.

That's because, if you followed [the instructions](../clone-the-python-myovision-repository/clone-the-python-myovision-repository.html), you cloned the code to  
`c:\users\your_user_name\github\Python_MyoVision`  
where _your_user_name_ is something specific to you.

The demos use relative paths to overcome the fact they don't know the directory structure on your computer.  
+ `..\` means go up a directory
+ `..\..\` means go up 2 directories
+ `..\demos` means go up a directory, and then into the `demos` directory
+ `..\demos\example_A` means go up a directory, and then into the `example_A` subdirectory of `demos`
+ and so on
