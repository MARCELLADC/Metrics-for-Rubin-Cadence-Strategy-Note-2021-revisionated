# Cadence-Note-2021
Period and shape recovery of pulsating stars 
The input of this metric is a theoretical light-curve or a pulsating variable template 
(i.e. time/phase, magnitude in each filter $ugrizY$ and pulsation period) that is convoluted with the chosen survey strategy 
(OpSim) to obtain the ”observed” light curves in all the filters $ugrizY$ with the expected S/N for each phase point, 
filtered to exclude the saturated points for that specific OpSim and analyzed by the multiband gatspy package to obtain single filter and median periodograms. 
) the fit of the observed light curve in each band through the superposition of nHarm (in the current version of the notebook this is a parameter and it is set to 4). From this fit, we can derive, in each band, mean magnitude (averaged in intensity) and amplitude.
The differences of these quantities respect to those of the input light curve (Delta mean mag and Delta Amplitude) in each bands are additional very useful FoMs and can be plotyted in the last cell
