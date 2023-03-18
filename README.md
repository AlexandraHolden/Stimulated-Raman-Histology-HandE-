# H-E-like-contrast
Python code to pseudo colour CH2 and CH3 Raman images to create a H&amp;E like contrast

The code requires two input files in tiff format - a CH2 image and a CH3.
The exact contrast can be edited by changing the if loop to make the image more purple or more pink.



An alternative colouring using ImageJ (Fiji) can be used - The macros is copied below:
  selectWindow("CH3.tif");
//run("Brightness/Contrast...");
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
