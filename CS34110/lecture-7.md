# Features
*Hannah Dee, Physics B*

* Features of Features
    * textures
    * Corners
    * ellipses
    * projection of rectangles

## What Makes A Good Feature?
* Repeatability - can we find it again?
* Distinctiveness - is it different to other bits, or distinctive in terms of general image stats?
* Locality - features should not be the size of the image, local
* Easy to find - enough of them to use for matching?
* Accuracy - do they pinpoint a thing with precision?
* Efficiency - can we compute them quickly?

## Generalised Cylinders and Ribbons
* See slides, Hannah flew

## Corner detection
* If we want to find a "thing" in an image, and the same "thing" in the next image, the feature has to be repeatedly findable
* Because corners have 2 edges meeting, more changes in intensity and therefore fast to find
* Key thing about Harris corner detection:
    * Don't just look at patch, look at surrounding patches as well
    * Use it to ensure that the patch is relatively unique
* Neighbourhoods of corners are fairly unique

## From Description To matching
* Harris corners are good at finding things that are easy to find again
* Other methods: Harris was improved on in 1994 by Shi and Tomasi, "Good Features To Track"
    * Main difference is scoring function
    * Use Harris corners and KLT features all the time - perform very similarly
* Actually matching the corners is called Feature Tracking

## Scale Invariant Feature Transform (SIFT)
* Features that:
    * are invariant to scale
    * are invariant to rotation in the image plane
    * are invariant to small translations/rotations in depth
    * contain a local description of the image
* Features can be used in object recognition, correspondence, etc
* This algorithm and it's variants are considered state-of-the-art
* Depends on **many** more or less arbitrary parameters
* Expensive to run, but many "tricks" to make it faster

## SIFT: Scale invariance
* Gaussian pyramid
* Difference between successive images gives the DoG (Difference of Gaussians)

## SIFT: feature selection
* Features selected if
    * Good enough contrast#
