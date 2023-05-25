> This is a means of applying a *filter* onto the original image!

As a comparison towards general transformation, filtering uses a *local processing* on the window, which means it looks at *target pixel and its surrounding*. This then can be used to create a *filter* and *applying it* results in an outputted pixel value.

> More on filtering:
> Images are *spatially organised data structure* with many important attributes spread across the image. 
> It intends to process the image to be restricted to a small and compact area but have access to more information from the rest of the image. Still likely to consider a single object, surface or illumination patter.

Highly useful to do [[Image Noise#Noise Reduction]]! Ideally, because choosing the region to only include pixels that *should* have the same values.

---
### Convolution
The main method of *applying* a filter onto the image is by multiplication with the image. 
Many filters follow a similar patter where you **multiply each image value** by **a corresponding filter entry** and then **summing the results**.
- Convolution is the summing of the results

> Convolution can be used for various operations such as feature extraction, noise reduction, image enhancements, frequency analysis etc. 

---
## Linear Filters
- Intended to smooth sharp image changes and reduce noise! 
- Generally, convolution with a mask of weights compute a *linear function* of a set of pixel values.

### Mean Filtering
- Mean filters are created by taking the the *average value of its neighbouring pixels*.

> A filtering window or a **kernel** or **mask** (a small matrix of predetermined size) and this window is used to determine the *size of the neighbourhood* considered for calculating the average

Using this *mean mask*, the target pixel's value would be replaced by the *computed average pixel value*. This process is repeated throughout the image. Usually with a mask size of *3x3,5x5,7x7*

### Gaussian Filtering
- Filtering with a *mask whose weights are determined by a 2D Gaussian function*; 
	- *higher weights* is given to pixels near the source pixel
	- hence more likely to lie on the same object as the source pixel.
- The kernel or mask for this filter is used to apply the gaussian filter with a specified gaussian parameter $\sigma$
	- As an example; centre of the window has x=y=0, then sample the Gaussian at each point and normalise it. Example:
	- ![[Pasted image 20230519172345.png]]

**Normalised Gaussian Function**
$$
GB[I]_{p} = \sum_{q\in S} G_{\sigma}(\mid p-q|)I_{q}
$$
> This function shows how the gaussian filter is generated, where the difference between source and neighbour pixel is used for the Gaussian distribution and applied to the image.

### Separable Filtering
> Gaussian filters are separable too!

Separable filters are basically filters that can be *separated* into two distinct filters. Gaussian is separable because a 2D Gaussian is equivalent to *two* 1D Gaussians.
	- In this case, filtering with a *horizontal Gaussian* then *vertical Gaussian*

- Generally, separable filters are more efficient as given an $N \times N$ image and an $n \times n$  filter mask; we do $O(N^{2}n^{2})$ operations
- However, applying two $n\times_{1}$ filter to an $N \times N$ image takes $O(2N^2n)$ operations

---

## Non-Linear Filters
- Intends to preserve or even enhance sharp image changes and overall reduce noise!

### Median Filtering
Median is statistically the *middle value* in a set. It takes the *median value of its neighobouring pixels*.
- The neighbours are determined based on the filter mask or kernel. Each pixel is then set to this median value which results in a *real pixel value* and not *combination*

> This filtering bases off the idea that *noise pixels are outliers* and it would have to affect >1/2 of the general pixels in the local window to appear in the output of the filter.

> Median filtering is often good given small regions of speckle noises, but less if edges are important within the image; as there's an explicit edge preserving smoothing operation

### Anisotropic Diffusion/Filtering
This filtering works where median filter falls off, by making *each pixel more like those neighbours* (like mean and Gaussian) BUT *only neighbours that ARE similar to the pixel*.

> Anisotropic means to *be not the same in all directions* and diffusion defines *spreading out*. It can even be noted that Mean and Gaussian Filters are also diffusion processes

**The function**
$$
p' = \frac{\sum q \times s(p,q)}{\sum s(p,q)}
$$
- The new pixel value $p$ is based on *all of its neighbours* $q$ where $s(p,q)$ (the smoothing or similarity function) has a value of \[0,1\]; 
	- if the pixels $p$ and $q$ are similar, $s(p,q)$ is close to $1$
	- if the pixels $p$ and $q$ are different, $s(p,q)$ is close to $0$

**Smoothing Function**
- There are various ways to retrieve the smoothing function:
	- if $d$ is the difference between $p$ and $q$, $D$ is the maximum possible difference where $\frac{D-d}{D}$
	- There are also functions where a constant $K$ defining the *amount of smoothing*
		- $s(p,q) = e^{(\frac{p-q}{K})^{2}}$
		- $s(p,q) = \frac{1}{1+(\frac{p-q}{K})^2}$

> Anisotropic similar to Mean filtering! Because if the similarity function is 1, we basically get a mean filter!

### Bilateral Filtering

> Bilateral Filtering similar to Gaussian Filtering! It modifies Gaussian filtering in a similar way to Anisotropic with Mean filtering.

**Bilateral Function**
$$
BF[I]_{p} = \frac{1}{W_{p}} \sum_{q \in S} G_{\sigma_{s}}(|p -q|) G_{\sigma_{t}}(I_{p} - I_{q}) I_{q}
$$
- It modifies the Gaussian function by taking the *dynamic range* of the source and neighbouring pixels as a factor on the bilateral filtered image. This range is taken from $I_{p} - I_{q}$. Not just the spatial difference.


#image-process #semester4 