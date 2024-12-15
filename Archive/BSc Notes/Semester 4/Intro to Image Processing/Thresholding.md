The process of thresholding is closely linked with *binarisation* where a threshold value $T$ is used to consider each pixel in the image as the region of interest.
- This assumes that a *dark object* in a *light background* is the region of interest, and the input image has to be of *grey-level color space*
- [[Color Spaces#Gray Level]] $\to$ [[Color Spaces#Binary Images]]

If the *brightness* at a pixel is *less than* ($<$) $T$ , then the pixel is *object* or *part of the region of interest*. Otherwise, it is part of the background.

> This region can then be further used to be processed, such as colouring or defining the sets of colours values to the objects.

This *simplicity* relies on the value of the threshold; if too high than the background pixels may be classified as the foreground, or too low that the object pixels can be considered background.

## Adaptive Thresholding
An adaptive threshold is when the *threshold value is based on image properties*;
These values are determined by using automatic methods based on image properties; most commonly is the image histogram.

### Otsu Thresholding
- This method assumes the histograms are *bimodal*; where two regions can be separated by *one threshold*. See below;
![[Pasted image 20230519194918.png]]

Otsu realises that we should find the *threshold* which *minimises a weighted a sum of the variations of the two regions* 
- Weights are the areas of the histogram assigned to each region.
- It is particularly effective when there is a clear bimodal distribution of pixel intensities within the image. 

**Steps**
1. Consider all possible threshold values (0,255)
2. Compute the weighted sum
3. Pick $t$ with the smallest value.

### Rosin Thresholding
- This method assumes that the histograms are *uni modal*. Many histograms are not bimodal, and there often only one peak (like textual images where it is mainly white with a small amount of black.)

- Extremely useful in uneven illumination and varying local contrast.

**Steps**
1. Find the peak of the histogram
2. Draws a line from there to the top of the furthest bin
3. Finds the top of the bin that is the furthest from the line, and uses it as the threshold

### Local Adaptive Methods
- Imaging conditions and object properties can vary within a single image as well as across sets of images
- In this case, we select a threshold by dividing the image into 

#semester4 #image-process 
