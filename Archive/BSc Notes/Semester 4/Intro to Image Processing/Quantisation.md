- Refers to the digitisation of the *light intensity function*
- It shall determines the *grey level*, *colour or [[Resolution#Radiometric Resolution]]*

> Similar to the an affect of *under-sampling*, we should also somehow determine the amount of *grey level to store*

- This *grey level* can also be taken as the *number* of levels of **colour/intensity** to be represented at each pixel.
	- This level of intensity is known as **Quantisation**, and often is determined per pixel

### Re-Quantisation
- Pixel values are integers in a *fixed range*
	- The grey level resolution of an image *can be dropped* by *dividing each pixel value by a constant*
	- *cannot increase* the grey level
- Super resolution methods can combine *multiple exposures* of the same scene and so have more than one measurement of each pixel.

#semester4 #image-process 