# Cadence-Note-2021
Here you can find three  new metrics build for Cadence Note 2021:Classical variable stars in different Galactic environments: pulsation behaviour recovery.
(https://docushare.lsst.org/docushare/dsweb/Get/Document-37629/Pulsating_stars.pdf )

Authors:Di Criscienzo,Braga, Leccia

(Little changes was performed from April 2021 up to now)

Short description of files in this directory.


-->LcConstructorLAST.py

The input of this metric is a theoretical light-curve or a pulsating variable template 
(i.e. time/phase, magnitude in each filter $ugrizY$ and pulsation period) that is convoluted with the chosen survey strategy 
(OpSim) to obtain the temporal series and  the ”observed” light curves if the period of the model is used in all the filters $ugrizY$ with the expected S/N for each phase point and  filtered to exclude the saturated points for that specific OpSim and analyzed by the multiband gatspy package to obtain single filter and median periodograms. The output is a file with the temporal series and some useful flags.


-->Lcperiod.py


This metric uses GATSPY to recover the period of the temporal series and compute the difference bewteen the period of the model and the recovered one.


-->LcfittingLAST.py

This metric perform  the fit of the observed light curve in each band through the superposition of nHarm (in the current version of the notebook this is a parameter, we suggest 2 for RRC and 4 for RRabm CEF1,CEF2,LPV1,LPV2).The output are  mean magnitudes (averaged in intensity), amplitudes, chi,dimension of the largest gap in phase, and the number of gaps larger than half of 
This last metric gives The differences of the quantities  computed by the fitting with respect to those of the input light curve (Delta mean mag and Delta Amplitude) andd other important parameters useful, in our consideration, to judge the simulation
Tested on AstroDataLab.

The directory also contains:

-->Notebook_example.ipynb :a notebook that  show how to use theese three metrics;

-->Notebook_iterateipynb :a notebook which use the three metrics described above  in a FOR cycle useful to compare results obtained with  different Opsim and number of years;

-->FILES/XXXXX:an  asciifile with the temporal series as computed by LcConstructorLAST.py 

-->Multiplot figure produced by  LcConstructorLAST.py (XXXXX), LcPeriod (XXXXX) and LcFittingLAST (XXXXX)
 
--> All_results.csv: asciifile  produced by Notebook_iterate with all the results for two different Opsim and finish year.

-->files with the template of 6 different variable stars (RRab.csv,RRc.csv,CEF1.csv,CEF2.csv, LPV1.csv,LPV2.csv)


Comments are welcome. 
Tested on Data Astro Lab


