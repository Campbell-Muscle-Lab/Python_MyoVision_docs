---
layout: page
title: How to organize your data
description: Web-based help for Python_MyoVision
---
### Overview

If you are using Python_MyoVision, you probably have a lot of files, and some of the raw image files might be very big. It can be difficult to keep track of them, and it takes a long time to copy them from place to place. This page outlines a potential strategy that might help.  


### Tips

+ Keep your data files and your results separate from Python_MyoVision  
  + Note the demos in this tutorial keep the source code, the raw images, and the results close together in the file structure, but this is only to simplify the installation and maintainance of the software package. It's not a good idea for normal purposes.  
  
+ For example, if you have installed Python_MyoVision in  
  `c:\users\your_username_here\GitHub\Python_MyoVision`  
  
  + you could put your raw images in  
  `c:\users\your_username_here\Documents\Project_1\raw_images`
    + When you create your configuration files, just replace  
    `<raw_image_file_string>..\demos\example_A\raw_image\image_1.png</raw_image_file_string>`  
    with  
    `<raw_image_file_string>c:\users\your_username_here\Documents\Project_1\raw_images\image_1.png</raw_image_file_string>`  
    
  + and your results in  
  `c:\users\your_username_here\Documents\Projects_1\results`  
  using configuration inputs like  
  `<results_folder>c:\users\your_username_here\Documents\Project_1\results\image_1</results_folder>`  
 
