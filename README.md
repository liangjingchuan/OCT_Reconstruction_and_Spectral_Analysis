# OCT_Reconstruction_and_Spectral_Analysis
A MATLAB code for reconstruction and spectral analysis of spectral domain OCT images. 
This code can be used as part of a platform for molecular imaging with OCT, which we call MOZART.

This code was created to read raw interferograms from Thorlabs OCTs (SW version 4 works best, but version 3 is also supported).
It reconstructs the raw interferograms into OCT images, and supports both 2D and 3D.
In addition to reconstructing the images this code:
- Calculates the normalized spcekle variance (useful for detecting blood vessels)
- Calculates dispersion compensation
- Calculates a map of spectral contras, based on dual-band spectral analysis
- Calculates spectral-depth compensation
- Creates images that combine the OCT image, spectral analysis and speckle variance.
- and more features...

This code was used to create analysis and images for: "Contrast-enhanced optical coherence tomography with picomolar sensitivity for functional in vivo imaging"
O Liba, ED SoRelle, D Sen, A de La Zerda - Scientific reports, 2016.
Please cite our paper if you use our code.

I would like to acknowledge the support of Thorlabs' team in Lubeck, Germany, for their support in working with the OCT systems and reconstructing the raw signals.

----------------------------------------------------------------------------------------------------------------------------
Usage of the code:

0. If you use Thorlabs spectral domain OCTs, export your data as raw interferogram.
This code supports Ganymede HR and Telesto.
If you use a different system you'll need to update the chirp file, and perhaps other parameters, such as size of buffer.
If you use an OCT from a different manufacturer, you'll also need to update the functions that read the raw data.

1. Update the parameter files according to your system and the type of scans you acquired.
The parameter file should be readable enough. Feel free to contact me if you have any questions.
If you ran 3D volumes, use spectralParamsV3_3D. It will save your results as a .mat buffer file, and not png images.

2. run the file called runSpectralV3.m

3. If you have a 3D volume, you'll now need to create it into a Tiff file. To do this, run one of the createTiff functions in the display_functions folder.
This allows stitching of multiple files into one volume, and also choosing the type of output (OCT log signal, spectral signal, speckle variance...).
You can also change the colormap using the display functions.
If you saves a 2D .mat buffer, you can also play with the display parameters using createPngBscanFunction.m
