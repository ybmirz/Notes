- There's often an overlap between *image processing*, *image analysis*, *computer vision*, and *computer graphics*. 
	- **Image Analysis**: mainly concerned with quantitative *measurements* on images; an image acquisition is constrained so that image measurements are a proxy for some real world value
		It sits between processing and computer vision, as computer vision focuses on using AI ontop of a processing and analysis
		- Uses a generic operation where possible, but takes an *engineering approach* more than *specific approach*
	- **Computer Vision**: aims to *invert* image formation or *recover* information about the viewed world: such as 3D shapes, motions and identity.
	- **Computer Graphics**: it focuses on creating images from an object model, hence an image (or graphic) is computer generated.
	- **Image Processing**: uses and extract information from an image, to some degree, manipulating said information.
		- Fundamentals of digital image processing, in theory or practice

### The steps
1. Describing the **image formation**
2. Creating an **acquisition of information**
3. Annotating the **color representation** of the image, based on the acquisition

> It should note that Pixel values represent the *brightness* and *colour* of the viewed objects, but give no indication of what object the numbers refer to - hence low-level

**Image Manipulation**
- From noise reduction, smoothing, sharpening, constrast enhancement,, changing the appearance of an image, etc.

> **How do we image process vector images?**
> 	*question came up due to an understanding of logically, using pixels to move through an image, but vector images does not have pixels*
> Answer: Most of the time, the traversal of the image is done by the pixel and an analysis of each pixel

> **What about upscaling an image? Is it algorithmically similar to enlarging an image?**
> Answer: Upscaling ensures that when the image is enlarged, the pixels around one *significant* pixel by value, should be kept in a similar value (colour ratio)

> **Can we algorithmically determine whether an image has been manipulated or not?**
> Answer: It is difficult to reverse, but can be done through the colour historgram or comparison

### Image Compression
- Given a large data of information, there should be some sort of *redundancy and image compression* such that we can **efficiently** represent image data for storage (minimise space) and communication (minimise network bandwidth) 

### Domains of Image Processing
There's alot of domains that could be looked at within image processing, and it highly depends on **what** or **how** we're manipulating an image, hence;
	- [[Geometric Operation]]
	- Finding **geometric objects**
	- [[Spatial Domain]]
	- [[Frequency Domain]]
	- [[Content-based Image Retrieval]]

### An Application of Image Processing
There's alot of applications of image processing, whereby it could be used in a real world manner, rather than simply a mathematical sense.
As an example; 
	- **[[Painterly Rendering]]**, used to *reproduce* a particular artist or *movement*'s style
		- such as Impressionism
	- **[[Interactive Tools and Compositing]]**, creating a composite of images in a way to create new information (albeit maybe false)

#semester4 #image-process