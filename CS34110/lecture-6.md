#Edge Grouping - From Edges to Lines and Contours
*Hannah Dee - Physics A*

##Creating Contours
###Creating Contours From Edge Pixels
* Edge detection only extracts pixels or small groups of pixels belonging to Edges
* These need to be grouped into higher-level features
    * Straight Lines
    * Curves
    * Blobs
    * Ribbons
    * Etc
* Can be done *bottom up* or *top down*
    * *Bottom Up*
        * Find edges and trace them through the scene
    * *Top Down*
        * You have a model, that you are looking for in the world
###Bottom Up Approaches
* Edge pixels are grouped by edge following: from an edge pixel, move along the edge direction until the next edge pixel is encountered etc.
* Problems are
    * Camera noise
    * Digitisation noise
    * Gaps
    * Complex topology
    * Starting point dependent
    * Multiple "garden paths"
###Top Down Approaches
* A model of what is sought is available and is "projected" on the image, and matched with the edge pixels
* Problems are:
    * We need to know what we are looking for
    * Projection
    * Noise
    * Matching complexity
###Line Fitting
**See Diagram On Slides**

* Fitting a model of the form *y = mx + c*
    * *x,y* Pixel Coordinates
    * *m,c* The parameters of the line
* The problem: Finding the parameters providing the best fit
* For edge pixel *(Xi, Yi)*, *di* is the distance between pixel and line
* Best fit: find *(m,c)* so that *di = 0* for all *i*

###Line Fitting: Multiple Lines
* Might need more than one line
* Fir of current solution measured using the global distance between edge pixels and line
* If fit not good enough, solution must be broken into 2 parts
* Where to break is determined using individual distances

##Hough Transform
###Finding Lines: The Basic Idea
* Line equation we know *y = mx +c*
* Contraints on the line parameters
* All lines going through a pixel will create a curve in line space, and we can do this in an accumulator array
* Voting from all edge pixels
* High values in the accumulator indicate lines (threshold)
* Can be applied to other geometric shapes
* Problem with lines in this context:
    * A vertical line has a high gradient
###Practicalities
* New line equation: **See slides**
* Quantisation of the accumulator/feature space (similar to a histogram)
* Can be used for anything where you can come up with an accumulator space

###Pros and Cons
| Pros | Cons |
| ---- | ---- |
| A nice solution to geometrical feature matching | Can group widely separated edge pixels |
| Can group widely separated edge pixels | Depends on a number of parameters (grid size, threshold) that depend on noise levels |
| Good for finding parallel lines and circles | Needs enough evidence to work |

##RANSAC
* **See Slides For Line Fitting**
* Outliers will pull the solution away from the inlying points
* **RAN**dom **SA**mple **C**onsensus

###The Process
* Repeat Many Times
    1. Fit a model to a random subset of points (samples)
    2. Build a consensus set: other points that fit the model
    3. Evaluate quality of the model: size or total error of the consensus set
* Rebuild model with best consensus set
* Can estimate number of iterations needed based on probability of outliers, acceptable error and size of samples set
* Like the Hough Transform, can be used for more general
model fitting (not just lines)

## Conclusion..
* Edge detection finds pixels where there are discontinuities
* You need something on top of that to find structure
    * Lines
    * Circles
* Problems include outliers, noise and gaps
* Going from pixels to structures is where it starts to get interesting
