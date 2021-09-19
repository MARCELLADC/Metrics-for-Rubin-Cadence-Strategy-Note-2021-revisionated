# Cadence-Note-2021
Metrics used in Cadence Note 2021:Classical variable stars in different Galactic environments: pulsation behaviour recovery.
Little changes was performed from April 2021 to now

Description:
The input of this metric is a theoretical light-curve or a pulsating variable template 
(i.e. time/phase, magnitude in each filter $ugrizY$ and pulsation period) that is convoluted with the chosen survey strategy 
(OpSim) to obtain the temporal series and  the ”observed” light curves if the period of the model is used in all the filters $ugrizY$ with the expected S/N for each phase point and  filtered to exclude the saturated points for that specific OpSim and analyzed by the multiband gatspy package to obtain single filter and median periodograms. 
Lcperiod use gatpsy to recover the period of the temporal series and LcfittingLAST perfor  the fit of the observed light curve in each band through the superposition of nHarm (in the current version of the notebook this is a parameter, we suggest 2 for RRC and 4 for RRabm CEF1,CEF2,LPV1,LPV2). From this fit, we can derive, in each band, mean magnitude (averaged in intensity) and amplitude.
This last metric gives The differences of the quantities  computed by the fitting with respect to those of the input light curve (Delta mean mag and Delta Amplitude) andd other important parameters useful, in our consideration, to judge the simulation
Tested on AstroDataLab.

Comments are welcome.


