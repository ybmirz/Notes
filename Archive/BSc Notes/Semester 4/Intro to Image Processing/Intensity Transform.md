> Transformation is the process of manipulating/adjusting the value of a pixel into an outputted pixel value resulting in a processed image

- Intensity transform focuses on a *target pixel value* uses this *focus source pixel* and possibly some parameters to achieve an output pixel value.
	- It focuses on each pixel's intensity!

> Intensity transforms generally produce values that are *outside* the range of the image or clustered in a small part of that range and so becomes hare to distinguish.
>	This range is known as the image's *dynamic range* and it contains a fixed number of data values that represents the image.

## Linear transforms
- The simplest forms of intensity transformation where the changes of the pixel values are *linear*; such as the use of *multiplication* or *addition* of a constant to the target pixel value.

**Gain**
The gain of an image controls the overall *contrast* of the image (this is not a specific algorithm to manipulate the contrast but a simple understanding). Usually *multiplication*

**Bias**
The bias of an image controls the overall *brightness* of the image. Usually by doing *addition* with a constant.

**Negation**
Negating an image is simply by achieving an inverse function that represents the image, or using a negation formula.

#### Contrast Stretching
- Also part of a linear transform but it combines *addition* and *multiplication* 
- It intends to *adjust* the dynamic range of the image which results in enhancing the contrast of an image.
- It converts a source image in which *intensities range* from a $min_{s}$ to $max_{s}$ to one where it ranges from $min_{t}$ to $max_{t}$
$$
g(x,y) = min_{t} + (f(x,y) - min_{s}) \times (\frac{max_{t} - min_{t}}{max_{s} - min_{s}})
$$

## Non-Linear transforms
- Intensity transformations but non-linear

**Grey level slicing**
It can be done to *highlight grey levels* or as the simplest form of image segmentation.
It highlights a specific range of intensities

**Gamma Correction**
> Context: when an image is displayed on the screen, there's a level of intensity transform due to the hardware being used, as a voltage proportional to the intensity of the pixel is used by the screen.

This can be corrected by *transforming the image so that it has a voltage to display what we want*
Somewhat by using a *corrected function* such as $g(x,y) = f(x,y)^{\frac{1}{2.5}}$
The voltage $V$ can then be taken from $g(x,y)$

> Generally, intensity transformations read and affect only an individual pixel (throughout the image) hence the manipulation power is limited.

#semester4  #image-process 