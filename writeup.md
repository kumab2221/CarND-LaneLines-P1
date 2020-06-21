# Finding Lane Lines on the Road

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report

---

## Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

*My pipeline consisted of 5 steps. Those steps are as follow.*

1. Convert to grayscale image  
  To get a contour image with the Canny method, we need to convert the color image to gray.
2. Convert to smoothing image  
  Get rid of noise and get a clean contour image.
3. Use Canny method  
  Create a contour image. so  determine the values for high and low threshold.
4. Region of interest extraction
  Removes lines in the contour image of areas where lanes were considered not present.
5. Detect straight lines
  Find the lines in the binary image using the modified draw_lines function and the stochastic Hough transform.
  
* How I modified the draw_lines() function
  Judge the left and right lanes from the slope. Also, if the angle exceeds the threshold value, it is excluded as noise.


### 2. Identify potential shortcomings with your current pipeline

A potential drawback is the inability to properly recognize lanes when they are turning left or right.

### 3. Suggest possible improvements to your pipeline

A possible improvement is to suppress the amount of change in the current value by using the previous frame
