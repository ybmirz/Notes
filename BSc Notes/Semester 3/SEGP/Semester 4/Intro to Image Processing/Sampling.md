- Sampling is the main method of *acquiring information onto an image*
- When taking images within a 3d plane, that information requires to be *digitised* and **sampling** describes
	- the *digitisation* of **spatial coordinates**
- This digitisation *determines* the **[[Resolution#Spatial Resolution]]** of a taken image.

- Generally, samples *must be taken* at a rate that is **twice** the frequency of the highest *frequency component* to be **reconstructed**.

> **Under-sampling**: sampling at a rate that is **too coarse**.
> 							but what is the *minimum rate*?
> 							We understand that it should **not** be less than the **Nyquist Rate**

- Under sampling also *may result* in **artefacts**, these are generally known [[Aliasing]]

#### Re-Sampling and Re-Sizing
- One of the most basic form of image processing, where a **group of pixel** gets its average intensity value and created into a *single pixel*
	- This is mainly when resizing into a *smaller* image size
- 
- **Down-sampling** requires you to compute a *summary pixel value* from each *local area*
	- Where we pick one, mean and weighted mean.
	- Down-sampling is **synonymous** with *compression*

- **Un-sampling** requires an *interpolation* from the *known values* to produce an estimate at the **unknow pixels**
	- Finding an average of the current *known pixels* in the local region, centered on *each unknown pixel*; to fit some kind of *function through the known values*


#semester4 #image-process 