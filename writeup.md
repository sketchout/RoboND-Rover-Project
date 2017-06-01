# Proejct : Search and Sample Return


The goals / steps of this project are the following:
--------------------------------

Training / Calibration

- Download the simulator and take data in "Training Mode"
- Test out the functions in the Jupyter Notebook provided
- Add functions to detect obstacles and samples of interest (golden rocks)
- Fill in the 'process_image()' function with the appropriate image processing 
  steps (perspective transform, color threshold etc.)   to get from raw images to a map. 
  The output_image you create in this step should demonstrate that your mapping pipeline works.
- Use moviepy to process the images in your saved dataset with the 'process_image()' function. 
  Include the video you produce as part of your submission.

Autonomous Navigation / Mapping

- Fill in the 'perception_step()' function within the perception.py script with the 
  appropriate image processing functions to create a map and update Rover() data 
  (similar to what you did with process_image() in the notebook).
- Fill in the 'decision_step()' function within the decision.py script with 
  conditional statements that take into consideration the outputs of the 'perception_step()' 
  in deciding how to issue throttle, brake and steering commands.
- Iterate on your perception and decision function until your rover does a reasonable 
  (need to define metric) job of navigating and mapping.


Writeup :
--------------------------------

Notebook Aanlysis

1. Run the functions provided in the notebook on test images

  - First just run each of the cells in the notebook, examine the code and the results of each.
    ![warped](/misc/0601warped.png)
  - Run the simulator in "Training Mode" and record some data. 
  - Change the data directory path (path = '../log_dataset/IMG/*') to be the directory where saved data
  - Test out the functions provided on new data
  - Write new functions to report and map out detections of obstacles and rock samples
  - Populate the process_image() function 
  
2. Populate the process_image() function

  - Populate with the appropriate steps/functions to go from a raw image to a worldmap.
  - Run the cell that calls process_image() using moviepy functions to create video output
    ![process](/misc/0601process.png)

Autonomous Navigation and Mapping

1. Modify code to allow rover to navigate

  - Fill in the 'perception_step()' function within the perception.py script
  - Fill in the 'decision_step()' function within the decision.py script
  - Run the simulator in "Autonomous Mode"

2. Iterate on perception and decision function
  
  - modify code and run the simulator until  rover does a reasonable job of navigating and mapping
  

