---
layout: post
title: SED predictor
permalink: 'sedpredictor'
---

[<img src="/images/sed_sketch.png" class="fit image">](/sedpredictor)


## Link to the tool

This tool predictions SEDs of protoplanetary disk using neural networks.
If this tool is useful to your work, please cite 
[Kaeufer et al. 2023](){:target="_blank"}.

[Go to the prediction webpage](https://arxiv.org/abs/2302.04629){:target="_blank"}

## Disclaimer

The SEDs displayed in this tool are created by a neural network introduced in Kaeufer et al. (in prep). The network will predict SED for every combination of input parameters. This does not mean that the predictions are reasonable in all cases. This can be because the chosen settings are physically not possible, or because the neural network has trouble finding good predictions for it. The latter is especially the case if you increase the inclination to look at the disk close to edge-on. If the NN is outside of its comfort zone, warnings pop up. Please do not ignore them.

The tool should be used to get a feeling for the influence of different disk parameters or to get rough estimations for model parameters that can explain an observation.

## Instructions

You can change all parameters using the sidebar (left side). To unfold this sidebar, you might need to click on the arrow at the top left. First decide if you want to use a single zone or two-zone model. Two-zone models consist of two zones with possibly a gap in between. The additional number of parameters is often used to fit SEDs better. The parameters can be input using sliders or text input. The first one will be on a logarithmic scale for the parameters noted as logarithmic. However, the text input will always be on a linear scale. 

On the main panel the settings can be chosen. If you like to get a feeling for the influence of different parameters choose the 'simplified faster plotting'. This will return the SED faster in a simplified plot. If you would like to compare an observation to a model choose 'compare to observation'. Note that this does not work for the simplified plotting routine. You can select observational data for a list of objects that were fitted in DIANA (Woitke et al., 2019) and re-analysed in Kaeufer et al. (in prep.). Alternatively, you can upload your own observational file (example below). By writing the Chi-value, the value of Chi-squared, the reduced chi, or the chi introduced in DIANA is written. Uploading your own parameter file allows you to save data of a session and use it again. For saving the data, scroll below the SED plot and export the SED or parameter file. The parameter file can be downloaded and used as an input in later sessions or as a ProDiMo input file. If the SED is outside the plotted window, the limits for the x- and y-axis can be adjusted using 'Adjust plot limits'. Have fun!

Additionally, you can visualise the 2D density and column density of the model using the respective bottoms.
The stellar parameters can be used to place the star in the Hertzsprung-Russell diagram. This will be automatically done, when the star is outside the training set of the NN, otherwise it can be plotted using the 'Plot HRD' bottom. You will see that the temperature and luminosity are the only stellar parameters to describe the star. We use a Neural Network trained on pre-main-sequence tracks from Siess et al. 2000 to calculate the corresponding stellar mass. This is displayed as: predicted stellar mass.



## Example files

The parameter input file should contain the parameter value (not on a logarithmic scale) followed by the parameter name (as shown in the example). View the example input parameter file for a [single zone model](https://raw.githubusercontent.com/tillkaeufer/SEDpredictor/main/Example_input.txt){:target="_blank"}
or a [two-zone model](https://raw.githubusercontent.com/tillkaeufer/SEDpredictor/main/Example_input_two.txt){:target="_blank"}.

The SED file should contain at least 3 columns. The first one displaying the wavelength in micrometre, the second one listing the flux in Jy at this wavelength, and the third one listing the uncertainty in Jy. Optionally, a fourth column can be added to include the name of the used instrument. This is not yet used in the online tool but might be added in the future. [View example input SED file](https://raw.githubusercontent.com/tillkaeufer/SEDpredictor/main/Example_observation/49Cet/SED_to_fit.dat){:target="_blank"}
