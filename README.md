# H and E-like-contrast
Python code to pseudo colour CH2 and CH3 Raman images to create a H&amp;E like contrast

The code requires two input files in tiff format - a CH<sub>2<sub> image and a CH<sub>3<sub>.
The exact contrast can be edited by changing the if loop to make the image more purple or more pink.


## **ImageJ alternative**
 An alternative colouring using ImageJ (Fiji) can be used - The macros is copied below:

  selectWindow("CH3.tif");
run("Apply LUT");
setMinAndMax(0, 65535);
setMinAndMax(0, 51554);
imageCalculator("Subtract create", "CH3.tif","CH2.tif");
run("Cyan");
run("Invert LUT");
selectWindow("CH2.tif");
run("Magenta");
run("Invert LUT");
run("Merge Channels...", "c5=[Result of CH3.tif] c6=CH2.tif create keep");
setMinAndMax(0, 30153);

## **HES-like contrast**
  An edited code includes the additional orange stain given by adding saffron to a normal Hematoxylin and Eosin stain. The additional colour is given by taking an image of collagen using Second Harmonic Generation.

