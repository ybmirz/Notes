> Noise is the *small errors* in an image's value

Usually is a result of imperfect sensors that introduces it, and image compression methods as repeated coding and decoding adds noise. Small errors can happen all the time when manipulating an image.
- Often times, noise is used as an *additive* such as Recorded value = true value + random noise value

There are several types of noise that can be identified within an image. The most common is known as the [[#Gaussian Noise]]

### Noise Reduction
Generally, we can reduce noise by taking mean value of each pixel. This can work if there are *multiple similar images*, as noise is randomly added to each value. (AKA Mean Filtering)
- If you have an *average* of a *large set* of estimates of the same pixel, the random noise values will cancel out!

How about if there is only *one image*, hence we need to have an *average over the local region of a pixel* and use this average to reduce the noise. It results in a similar effect, and one of the most common ways is to apply a **Spatial Filter**

---

### Gaussian Noise
- Sensors often give a measurement *a little off* the true value. Hence, on *average* they give the right true value of the pixels.
	- They tend to give values near the right value rather than far from it. Sounds familiar?
- These noises can then be modelled off of the **Gaussian Distribution** hence known as the Gaussian noise.
	- Hence calculations of noise follows the distribution, with the mean taken as the  **Gaussian Parameter** $\sigma$ . It is used to indicate the *level of Gaussian noise* within the image.

### Salt and Pepper Noise
- Sensors can sometimes either fail to respond or saturate in error; which results in a *false saturation* which gives a **white spot (salt)** or *failed response* which gives a **black spot (pepper)**. AKA Speckle Noise
- When trying to reduce this type of noise using *linear filters* such as Gaussian or Mean filtering, the noise still exists; which means that linear functions do not help reduce this type of noise, which is where **Non-Linear Filters** come in such as Median Filtering!


#semester4 #image-process 