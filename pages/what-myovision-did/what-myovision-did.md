---
layout: page
title: What MyoVision did
description: Web-based help for Python_MyoVision
---

### Algorithm worflow

When you ran the example, MyoVision:

+ opened a configuration file (`configuration_data.xml`) stored in `..\demos\example_A\configuration_data`.
  + looked at the task file section
    + saw one task specified with
      + an input image file `PoWer_3_Gastroc_10x_blue_cropped_small.png` stored in `..\demos\example_A\raw_image`
      + results to be written to `..\demos\example_A\results`

+ ran the task by:

  1. reading in the input image file
  
      ![raw-image.png](raw-image.png)
 
  1. converting it to gray-scale
  
     ![step_1_original-gray.png](step_1_original_gray.png)
  
  1. saturating the image
     + this step adjusts the brightness and contrast of the gray-scale image until x percent of the pixels are as dark as they can be, and x percent are as light as they can be
     + the x value, in this case 10%, is set by the `saturation percent` variable in the `<image_to_label_parameters>` of the configuration file
     
     ![step_2_saturated.png](step_2_saturated.png)
     
  1. enhancing the cell edges using a Frangi filter
       
  1. performing an initial segmentation to identify 'blobs' - regions of connected pixels
     + discarding blobs with an area below a critical size
     + the critical size, in this case 50 pixels, is set by the `min_object_size` in the `<image_to_label_parameters>` of the configuration file
  
     ![step_3_initial_segmentation.png](step_3_initial_segmentation.png)

  1. loading a classifier model (more on this later) set by `classification_model_file_string` in the `<classifier_parameters>` section of the configuration file
  1. using the classifier to mark each blob as one of the following:
     + fiber
     + potentially-connected fibers (two or more fibers separated by an incomplete cell boundary)
     + something else
     
     ![step_4_initial_classification.png](step_4_initial_classification.png)
     
  1. attempting to separate potentially-connected fibers into single fibers
     + this is done using a watershed algorithm and a `watershed_distance_parameter` (in this case, 10 pixels) defined in the `<image_to_label_parameters>` section of the configuration file
     
     ![step_5_segmention_after_initial_separation_of_connected_fibers.png](step_5_segmentation_after_initial_separation_of_connected_fibers.png)  
     ![step_6_classification_after_initial_separation_of_connected_fibers.png](step_6_classification_after_initial_separation_of_connected_fibers.png)  
     
  1. refining the edges of each cell using an adaptive contour technique which depends on the following parameters which are defined in the `<refine_fibers_parameters>` section of the configuration file:
     + max_iterations
     + sigma
     
     ![step_7_fiber_seeds.png](step_7_fiber_seeds.png)  
     ![step_8_gradient_image.png](step_8_gradient_image.png)  
     ![step_9_refined_edges.png](step_9_refined_edges.png)  
     
  1. re-segmenting the image to identify fibers with improved fidelity
  
     ![step_10_segmention_after_refined_edges.png](step_10_segmention_after_refined_edges.png)  
     ![step_11_classification_after_refined_edges.png](step_11_classification_after_refined_edges.png)  
    
  1. correcting for fibers that were inappropriately connected during the fiber refinement step
  
     ![step_12_final_segmentation.png](step_12_final_segmentation.png)  
     ![step_13_final_classification.png](step_13_final_classification.png)  
  
  1. creating the following output files in `results_folder` (which was specified for the task in the `<task_files>` section of the configuration file
  
     + an Excel file `final_results.xlsx` containing the following metrics for each fiber:
     
       + label (the id for the fiber)
       + area (in pixels)
       + eccentricity (0 is a circle, 1 is a straight line)
       + convex area (in pixels)
       + equivalent diameter (in pixels)
       + extent (ratio of pixels in the blob to the pixels in the total bounding box)
       + major axis length (in pixels)
       + minor axis length (in pixels)
       + orientation (angle between horizontal and the major axis of the equivalent ellipse - ranges from -pi/2 to +pi/2)
       + perimeter (in pixels)
       + solidity (ratio of pixels in the blob to the pixels in the convex hull image)
       
     + an image file `clean_overlay.png` showing falsely-colored fibers overlaid on the original input image
     
     + an image file `annotated_overlay.png` showing falsely-colored fibers overlaid on the original input image with text labels showing the fiber IDs
     
     + a zip file `processing.zip` which can be useful for trouble-shooting and which contains:
     
       + a folder named `blocks` with images showing processing steps for individual [blocks](analyze-a-bigger-image.html)
       + a folder named `classification_steps` with images showing the results of the processing steps outlined above
       