# **Finding Lane Lines on the Road** 

## Writeup Template

### You can use this file as a template for your writeup if you want to submit it as a markdown file. But feel free to use some other method and submit a pdf if you prefer.

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. 
Step 1. I converted the images to grayscale
Step 2. I applied gaussian blur to reduce image noise.
Step 3. I have applied canny edge detection along with region of interest to get only the lane lines.
Step 4. I applied hough transform to get correct left/right lanes
Step 5. I combined the lines with original image using weighted_img function.

I modified the draw_lines() function by using slope and X/Y values of them to draw left and right lanes, tweaked line's slope - positive for right lane and negative for left lane
For creating a single line for left/right, I have used polyfit to get slope and intercept values for both left/right lists. 
Then, line is drawn with fixed Y positions and X positions are found using slope and intercept values.


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when there is different/curved surface/shadows in the video and the lanes are not mapped properly.


Another shortcoming could be when there is curved lanes or any other objects(car) or no lanes found in the image.


### 3. Suggest possible improvements to your pipeline

A possible improvement would be to tune hough transform parameters to handle shadows,curved lines, shakiness of lines and also ability to draw default lines