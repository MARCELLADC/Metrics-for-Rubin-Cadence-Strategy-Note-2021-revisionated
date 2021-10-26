# Cadence-Note-2021
Here you can find our new metrics build  for Rubin Cadence Note 2021:Classical variable stars in different Galactic environments: pulsation behaviour recovery.
(https://docushare.lsst.org/docushare/dsweb/Get/Document-37629/Pulsating_stars.pdf )

***Authors***:Marcella Di Criscienzo,Vittorio Braga, Silvio Leccia
(Little changes was performed from April 2021 up to now)

Short description of files present in this directory.

***LcContructor.py*** simulate the temporal series  of a pulsating star (RR, Cepheids or LPV, template from Marconi et al. 2005 and Trabucchi et al 2019) using a given distance, reddening and OpSim. 
This metric  produce:
1)a file (cvs extension)with the temporal series and useful flags for the saturation(computed with saturation_stacker.py)  and  detection limit(the flag is set =1 when s/n<5);

2)a figure with the simulated light curves in each band, phased with the period of the model.
You can also choose to blend your star changing the parameter perc_blend which is the percentage of the mean flux of the variable itself that will add the the flux of each visit (actually we are implementing this option)


 ***LcPeriod.py*** derive the  period and the noise of Multiband periodogram  with MultibandLombscargle option of Gatspy(https://arxiv.org/abs/1502.01344) and build a figure that compare  Lombscargle in each filter with multiband analysis.  Compute differences between the true period and recovered period (also averaged on number of pulsational cycles)


***LcFitting.py***  fit the phased light curve  with a given numberOfHarmonics. This metric also compute mean magnitude of the fit, amplitudes and  chi  square of the fit. Possile FoM are the differences between the input and recoverd mean magnitudes and  amplitudes. 


***LcSampling.py*** analize the sampling of the light curve.C ompute for example  the dimension of the max distance from two consecutive phases of the light curve in each band . A possile FoM is the  number gaps larger than factorForDimensionGap*maxGapDimension.Two new measurements of the sampling was  introduced recently that use:

1)the uniformity parameter from  Barry F. Madore and Wendy L. Freedman 2005 ApJ 630 1054 (for number of point less than 20);

2)a modified version of	UniformityMetric by Peter Yoachim (https://sims-maf.lsst.io/_modules/lsst/sims/maf/metrics/cadenceMetrics.html#UniformityMetric.run). Calculate how uniformly the observations are spaced in phase (not time)using KS test.Returns a value between 0 (uniform sampling) and 1 . 


The directory also contains:

-->Notebook_example.ipynb :a notebook that  show how to use theese  metrics;

-->Notebook_iterate.ipynb :a notebook which use the three metrics described above  in a FOR cycle useful to compare results obtained with  different Opsim and number of years;

-->FILES/RRc_ra072.00dec-70.93dm18.5ebv0.08y0y2_footprint_add_mag_cloudsv1.5_10yrs.db.csv  :an  asciifile with the temporal series as computed by LcConstructor.py 

-->Multiplot figure produced by  LcConstructorLAST.py (LCnoised_RRc_ra072.00dec-70.93dm18.5ebv0.08y0y2_footprint_add_mag_cloudsv1.5_10yrs.db.pdf), LcPeriod (Period_RRc_ra072.00dec-70.93dm18.5ebv0.08y0y2_footprint_add_mag_cloudsv1.5_10yrs.db.pdf) and LcFittingLAST (LcFitting_RRc_ra072.00dec-70.93dm18.5ebv0.08y0y2_footprint_add_mag_cloudsv1.5_10yrs.db.pdf)
 
--> Allresults.csv: asciifile  produced by Notebook_iterate .

-->files with the template of 6 different variable stars (RRab.csv,RRc.csv,CEF1.csv,CEF2.csv, LPV1.csv,LPV2.csv)




Comments are welcome. 
Tested on Data Astro Lab (with Kernel LSST SIM MAF(Py3,w.2021.14)


