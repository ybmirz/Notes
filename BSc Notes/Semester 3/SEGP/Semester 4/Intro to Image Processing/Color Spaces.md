- There are a few color spaces, and each color space has it's own uses for different transformations.

## RGB
- The most common color image space where each pixel has an *intensity values* for the colors of Red, Green and Blue. This makes each pixel a *3-tuple* (R,G,B) in a 2x2 array.
	- It's inspired by how the retina perceives color and became an obvious choice for use in cameras
	- It should be noted that the intensity values are it's *light intensity* in the respective color channels

![[Pasted image 20230519154734.png]]

> RGB is additive which means that the other colors that could be represented are made by mixing the three colors.

## Gray Level
- Simply, each pixel in a grey level image contains *one value*; From 0 to 255 of it's *light intensity value*. 
> 0 to 255 because usually, these intensity values are represented using 8-bits which means that the image has a *bit depth* of 8 and a total of *256* values that could be represented (hence 0-255)

## HSV
- Instead of having three channels for *colors* within the image, HSV is based *on a colour*'s intensity rather than light.
	- **Hue**: what *general colour* is it
	- **Saturation**: how *strongly coloured* is it
	- **Value**: how *bright or dark* is it

- It separates colour from intensity values making it less sensitive to illumination changes within the image. 
	- This can be definitely useful for processing images that generally has a region of interest with a *general colour* 

> As an example, if the leaf of a plant is the region of interest in the image, then utilising HSV for the green hue can prove to be more useful. Human skin, if a region of interest, can also be better processed and identified using the HSV color space.

![[Pasted image 20230519160126.png]]

## Binary Images
- Many image processing procedures make a decision based on the pixel; with the idea of "is this the colour/object/edge that I am interested in?";
- Hence to make this decision; a resulting **binary image** is used to represent the answer.

Pixels have the values of **either 0 or 1**, but like general images it may require *noise removal*, *enhancement* or *adjustment*, etc.

#image-process #semester4 