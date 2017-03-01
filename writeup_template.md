# **Finding Lane Lines on the Road**

## The Writeup

---

**Finding Lane Lines on the Road**

The goals/steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./test_images/edged_solidYellowCurve2.jpg "Grayscale"

---

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 6 steps below.   
1. Convert the images to grayscale.  
2. Apply the Gaussian smoothing.  
3. Apply the canny edge detection algorithm.  
4. Apply the mask filter with ROI.  
5. Apply Hough to detect edges, and decide the lane from the lines from the median of each coefficient.
6. Draw the line on the original image.

Here is the final result of my pipeline below.

![alt text][image1]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when the lanes covered with something. In that case, we can't detect any lanes.

Another shortcoming could be the robustness of detection with the brightness. In the real world, there are many error matters. For example the brightness of the image, e.g. evening, night or the light from the sun or the others cars.

Another shortcoming could be the shape of the lane. We assume the lane is straight, but in the real world, there are many shapes of lanes.

### 3. Suggest possible improvements to your pipeline

A possible improvement would be to interpolate the lane from one shot. If the lanes cover with something, we should assume where is the lane from lanes which we can see. This example is one workaround of an invisible lane.

Another potential improvement could be to Normalize the brightness of the image. There is the difference of the brightness with noon and midnight. So we can make it work around with normalization of brightness. And We have to take care about flashlight from the sun or the other cars. To improve from that ignores the Saturated area of the image.

Another potential improvement could be line shape. We can make it better by using Polynomial lines in particular cases which we judge the lane is not the shape of straight.
