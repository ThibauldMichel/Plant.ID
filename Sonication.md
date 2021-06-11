# Processing unde-fragmented and low-concentration samples


## Starting material requirement

In the Illumina libraries guide:

**Starting Material: 500 pg–1 μg fragmented DNA. We recommend that DNA
be sheared in 1X TE. If the DNA volume post shearing is less than 50 μl, add
1X TE to a final volume of 50 μl. Alternatively, samples can be diluted with
10 mM Tris-HCl, pH 8.0 or 0.1X TE.**

Range starting material:
- *Concentration: 0.5ng-1000ng*
- *Volume: 55uL*

The selection of 2ng/uL (110ng) for the input solution was adapted for horticultural samples (high concentrated), but not adapted for silicate_storage/herbarium low concentrated samples.



## Low-concentrated samples

The low-concentrated samples 16-24 have not been correctly diluted at 2ng/uL in reason of poor measurement of the nanodrop at low concentration (0-20ng/uL). The resulting solutions were very diluted and not usable for library processing. 

Calculation of final concentration of samples 16-24 with remaining first extraction.  

	Ve = volume first elution remaining (uL)
	
	
	Ce = Bioanalyzer estimation (ng/uL) 
	ne = quantity DNA first elution remaining (ng)
	Vf = volume final solution (55uL)
	
	ne = Ve * Ce
	Cf = ne/Vf = (Ve * Ce) / Vf


Problem: 
> the yield is really poor for samples 13, 14, 17-21.  

One way to optimize the material recovered: **using the second elution for the dilution**.  
As the second elution concentration has only been estimated with nanodrop, the final concentration is unknown before another QC. 

> What is the detection limit for the HS Bioanalyzer chips?  

**NGS sheared DNA or libraries: For accurate determination of DNA concentration, the total DNA in the samples must be between 100pg/μL to 10 ng/μL.**  
0.1 ng/uL to 10 ng/uL => The most concentrated sample is Sample_16 with 5.63 ng/uL.  
It is unlikely that any sample will be more concentrated than 10ng/uL.


## Second sonication for all present-day samples

> Warning! Sample 20 is only 38uL with First_elution+Second_elution.
> The fragmented sample 20 from the first batch will be added to complete is to 55uL.

This second batch of samples 13-24 have been made from "First elution" + "Second_elution" to maximize the quantity of sample available.


 