# **Finding Lane Lines on the Road** 

---

**Finding Lane Lines on the Road**

The goals / steps of this project are the following:
* Make a pipeline that finds lane lines on the road
* Reflect on your work in a written report


[//]: # (Image References)

[image1]: ./examples/grayscale.jpg "Grayscale"
[image2]: ./report/blur.png "Blur"
[image3]: ./report/canny.png "Canny"
[image4]: ./report/hough.png "Hough"
[image5]: ./report/image.png "Lines on Image"

### Reflection

### 1. Describe your pipeline. As part of the description, explain how you modified the draw_lines() function.

My pipeline consisted of 5 steps. First, I converted the images to grayscale for more generic solution over different images with different lane line colors, Second, I smoothed the image using a gaussian filter with a kernel of 5, Third I used Edge detection algorithm (Canny) to get the elements which has different colors than their neighbourings, Fourth I used hough transform to connect the edges with lines, Lastly I used draw_lines function to draw the lines onto the image 

In order to draw a single line on the left and right lanes, I made the max_gap parameter for hough transform relatively big so that it could connect the cut lane lines which resulted in more unneeded lines to be connected with hough so I modified the draw_lines() function to exclude any line that has a slope less than 0.4


![To Grey][image1]
![Blurred][image2]
![Cannied][image3]
![Houghed][image4]
![Added lines to image][image5]


### 2. Identify potential shortcomings with your current pipeline


One potential shortcoming would be what would happen when The car goes onto a bridge or be in a crowded street which will result for both cases to no lane lines to be found

Another shortcoming could be if a sharp curve is to be taken the algorithm may fail to identify the lane lines



### 3. Suggest possible improvements to your pipeline

A possible improvement would be to make hough lines draw not only a straight lines but also curves to detect curves as the non linear regression method in ML

Another potential improvement could be to using other sensors to detec cars & other objects, also using gbs could help
