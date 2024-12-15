- Generally occurs when **two signals** (in our case, images) become *indistinguishable* when sampled.
- Often may happen due to *under-sampling* in an image, during [[Sampling]]
	- When it comes to an image, the aliasing that could be seen are *artefacts* within the image
- In an image case, the two signals are the **true image** and **the one reconstructed by a vision system from a sampled image**
> The true image refers to the image that would be seen if there were no [[Quantisation]]

![[Pasted image 20230208095033.png]]
> The above shows an example of *aliasing* given two signals, in an abstract manner.

- Aliasing can once again be introduced when an image is *resampled* if the sampling rate of the new image is *less than* the **Nyquist Rate** of the *original*

> Aliasing can happen at any moment that sampling is introduced, whether it's re-sampling or down-sampling. 

### Anti-Aliasing
- Anti-Aliasing is a technique done to get rid of any *inevitable* aliasing that comes from sampling or *re-sampling*
	- One of the main methods of getting this done is by **smoothing out the jagged edges**; It mainly works by *blending the colors of the pixels along the edge of an object*

> There are several different anti-aliasing techniques, including multisampling, super sampling, and font anti-aliasing. The specific technique used depends on the context and the desired results, but all anti-aliasing methods aim to achieve the same goal: to produce a smoother and more visually appealing image by reducing the visibility of jagged edges.

- Smoothing out the *high frequency* signals before sampling so its *impossible* to visually see the alias
	- Someway by adding *transparent pixels around the edges*

#semester4 #image-process 