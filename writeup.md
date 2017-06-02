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
        1) Change the data directory path (path = '../log_dataset/IMG/*') to be the directory where saved data.
        2) Test out the functions provided on new data.
      - Write new functions to report and map out detections of obstacles and rock samples.
          ![rock_tresh](/misc/0601rock_tresh.png)
          1) Add 'obstacle_thresh()'' to check the obstacles
          2) Add 'rock_thresh()'' to check the rocks
      - Define the functions used to do coordinate transforms.
          ![polar](/misc/0601polar.png)

  2. Populate the process_image() function

      - Populate with the appropriate steps/functions to go from a raw image to a worldmap.
      - Run the cell that calls process_image() using moviepy functions to create video output
          ![process](/misc/0601process.png)
          1) Define source and destication points
          2) Apply perspective transform with 'perspect_transform()'
          3) Apply color threashold to navigable/obstacles/rock with 'color_thresh(),obstacle_thresh(),rock_thresh()'
          4) Convert image pixel to rover-centric coords with 'rover_coord()'
          5) Convert rover-centric coords to world coords with 'pix_to_world()'
          6) Update worldmap

Autonomous Navigation and Mapping

  1. Modify code to allow rover to navigate

      - Fill in the 'perception_step()' function within the perception.py script

          1) 'rotate_pix()' : convert yaw to radian and apply to rotation
          2) 'translate_pix()' : apply a scaling and a translation
          2) perception_step() : apply code which tested in the notebook
              (1) Define source and destication points for perspective transform
              (2) Apply perspective transform
              (3) Apply color threashold to navigable/obstacles/rock
              (4) Update Rover.vision_image (Rover.vision_image[:, :, 2] = threshed * 245)
              (5) Convert image pixel to rover-centric coords
              (6) Convert rover-centric coords to world coords
              (7) Update Rover worldmap (to be displayed on right side of screen)
              (8) Convert rover-centric pixel positions to polar coordinates

      - Fill in the 'decision_step()' function within the decision.py script

          1) check condition with 'if Rover.near_sample:'
          2) set Rover.mode ='stop' and set Rover.send_pickup = True

      - Run the simulator in "Autonomous Mode"

          1) activate RoboND & execute 'python drive_rover.py'
          2) Screen resoultion : 800 x 600 Windowed
          3) Graphics quality : Fantastic

  2. Iterate on perception and decision function

      - modify code and run the simulator until  rover does a reasonable job of navigating and mapping


