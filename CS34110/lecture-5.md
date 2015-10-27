###Two Problems

* The edge signal is noisy
    * Solution: A 3x3 kernel instead of 1x3 has a helpful local averaging effect
 * Looking for vertical edges with horizontal kernel
    * Use a 3x1 kernel as well to look for horizontal edges
* **Sobel edge detector**

###Sobel edge detector

It is customary to combine the h and v responses
*Get notation from slides*

Then threshold it, and that gives actual edges

Issues with Sobel:
    * Thickening
    * Choice of threshold

###Formal definition

If the image intensity function is *l(x,y)*, the Sobel edge detector computes approximations to:
*Get notation*

*Edge Strength* is then the RMS of these estimates, and *edge direction*....

##Smarter Issues In Edge Detection

###Zero crossings
* Second differential of the intensity signal shows a sharp up-down, and crosses zero at the edge
* Zero crossings of the second derivative are powerful edge detectors

###Problems
* Don't know the direction of the edges in the image
