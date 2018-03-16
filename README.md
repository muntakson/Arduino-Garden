# Weed-Detection

The following program detects weeds and plants, implementing OpenCV 
to threshold and find the edges of green objects. As of right now, 
the largest object is considered a plant while any other object above 
a certain size is considered a weed. One of the advantages of this 
program is that it performs under a range (albeit small) of lighting 
conditions. However, one of the disadvantages of using this program is 
that it does not implement any kind of machine learning. I aim to add 
in the future a neural network to identify plants regardless of size.

## Requirements
1. Python 3.x
2. OpenCV 3.4
3. numpy (latest available version preferred)

Optional:
4. matplotlib (if you would like to display results, mostly for testing)
5. serial (if you want to communicate with an Arduino, will add extension later)

## How to use this repo
detect = ImageDetection()
The project overall has a class from which you call methods from other classes.

detect.image_grab()
This function must be called in order to initialize the image. Can use a given
image in the folder Capture or can take an image with a given camera.

detect.find_plant()
This function finds the plant, which is (for now) the object that has the 
largest size after thresholding and normalizing. Some of the thresholds have 
defaults, but others are currently fixed.

detect.find_weeds()
This function labels all other regions as weeds.

detect.draw_weeds()
Using matplotlib, one can outline the contour of all weeds. 
The color is currently fixed to magenta.

detect.draw_plant()
Using matplotlib, one can outline the contour of the plant detected. 
The color is currently fixed to green.

detect.display_drawings()
Displays the original image, the image after the initial threshold, and the 
original image with all outlines drawn.

## Future Edits
I will later add arduino communication capabilities to allow one to implement 
the weed detection in an Arduino garden.