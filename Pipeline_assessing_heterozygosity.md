<p align="center">
H2020-MSCA-ITN-2017 Plant.ID 		 Project No. 765000  
</p>


<p align="center">
 <img src="Aspose.Words.5dd3bc34-8607-489b-aa09-63efc51540ac.001.png"  alt="drawing" width="200" 
 <img src="Aspose.Words.5dd3bc34-8607-489b-aa09-63efc51540ac.002.jpeg" alt="drawing" width="200"/> 
</p>





# Plant.ID.  Molecular Identification of Plants 



# 1. Summary

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project's purpose is to check the variation of genetic health in endemic begonia populations over time. The allele diversity within different populations will be linked to their genetic health for conservation purposes. We will assess if a single specimen can provide an estimation of the allelic variation at a population-level. The bioinformatic pipeline will be used as well to confirm the identity of New-Guinean single specimens and follow their evolutionary history, and to track the introgression of Socotran alleles in horticultural varieties of winter flowering Begonia.



# 2. Purpose

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Begonia is one of the ten largest genera [(Frodin 2004)](https://www.zotero.org/google-docs/?0NpAwE) with the 2,000th species due to be described in early 2021. New species are published at a higher rate than in any other genus   [(Moonlight et al. 2018)](https://www.zotero.org/google-docs/?Ea5wDy). Correctly identifying species and understanding the relationships between them is therefore a moving target.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Furthermore, many of these species are threatened. More than half of the Begonia species known have been classified as threatened by the Global IUCN assessment. Like many other tropical herbaceous plants, Begonias commonly have restricted and isolated populations, and this may lead to poor genetic health caused by genetic drift. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;This project's purpose is to build a bioinformatic pipeline to identify species, reconstruct the evolutionary history of a population, and estimate its genetic health. For wide applicability this pipeline will be optimised to work with herbarium specimens as well as fresh samples, as many Begonia species are known only from type collections, or are inaccessible in the wild. Furthermore, present-day genome-wide diversity is a poor predictor of population size and conservation status in endangered species. Historical specimens collections include samples pre-dating the demographic declines that have occurred in populations history, and therefore can be used as a reference for the baseline levels of diversity, inbreeding, and genetic load. The comparison of specimens in a sequence time series of genomes can estimate genomic erosion of populations and used as a criteria to assess the IUCN Red List threat level of a species [(Díez-del-Molino et al. 2018)](https://www.zotero.org/google-docs/?5Neo7E)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The first batch of samples analysed was a mapping population which is being used to calibrate the pipeline.  The second set of samples we are working with are populations from two species endemic to the Socotra archipelago, which have already been genetically characterized with microsatellites.  This will test the pipeline.  The first experimental set we will work with will be sequences from New-Guinean specimens including several new species.  These sequences have already been obtained.  A final set of sequencing is planned for the spring.  This will include restricted and widespread species from Malaysian to test for demographic variations.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;We have also developed a side-project analysing the contribution of alleles from the rare B. socotrana to horticultural varieties of winter flowering Begonia. We will use the pipeline and the list of Socotran SNPs we have developed to search for introgressed Begonia socotrana alleles in the hybrid genomes. We hope to place the original specimen collected by Sir Isaac Bayley Balfour in 1880, and used for the groundbreaking “Gloire de Lorraine'' hybrids in the context of B. socotrana populations.  We will also identify if some of the allelic diversity lost from B. socotrana natural populations over the past 140 years has been retained in the horticultural varieties.

# 3. Material and methods

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Begonia samples were collected from silica-dried specimens for present-day populations and herbarium sheets capsule for historical specimens. Genomic libraries were made from extracted DNA , and Hyb-Seq RNA baits designed by Dr. Catherine Kidner have been used to select the library reads matching the bait set following the protocols of [(Nicholls et al. 2015)](https://www.zotero.org/google-docs/?S4MrcL). The baits were designed on the transcriptome of B. luzhaiensis, and a limited amount of B. conchifolia sequences and match single copy key developmental genes, differentially expressed genes and neutral genes. The selected libraries have been amplified and sequenced with an Illumina NovaSeq 6000.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;In parallel with the Hyb-Seq laboratory work, DNA from horticultural varieties of Begonia has been extracted and sequenced with an Illumina MiSeq PE150 for the Masters project of Philippa Stone, focused on introgression of B. socotrana alleles into horticultural Begonia varieties.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Hyb-Seq reads have been aligned using Paleomix [(Schubert et al. 2014)](https://www.zotero.org/google-docs/?6snhN0), a High-Throughput Sequencing (HTS) data pipeline specialized in ancient DNA analysis. The aligner selected was BWA. The MapDamage module of the pipeline has provided information on the DNA damage level of herbarium specimens, and edited the quality score of the alignment BAM files, for increasing the confidence of variants calling on historical samples.

To estimate the success of the target capture method, the Hyb-Seq reads have been first trimmed and aligned to the baits sequence, allowing to check the ratio of specific libraries captured. We tested different Burrows-Wheeler transform aligners (Bowtie2, BWA) and a range of parameters to optimise the alignment.

Furthermore, the Hyb-Seq reads have been aligned to the *B. conchifolia* plastids genome to check the abundance of plastid sequences in the a-specific captured reads and the possible use of plastids markers for phylogenetic inference. It is usually not considered for population-level studies and taxons with high rate of speciation, as plastid markers are not recombinant, and the mutation rate is low, which could cause incomplete lineage sorting [(Nicholls et al. 2015)](https://www.zotero.org/google-docs/?IEzjpA). But the same set of baits has been used successfully in the work of Hannah Wilson (UoE PhD thesis 2021)  to retrace the species phylogeny of non-identified New Guinean specimens.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;A mapping population of Begonia section Gireoudia (*B. conchifolia*, *B. plebeja*) has been included in the samples batch to set up parameters to exclude paralogs from the analysis.  A robust genome of *B. conchifolia* (Campos-Dominguez UoE Phd 2020) has been used to identify possible paralogs and the problematic loci examined under different mapping parameters to determine which produce the most reliable SNP calls.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;To select species-specific sequences, a genome version of the baits have been produced using blast and original scripts. This method has been notably used for the mapping population, producing a conchifolia version of the baits on which the Hyb-Seq reads have been mapped.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;SNP genotyping along long stretches of chromosome are required for demographic inference For this we need to use baits which are conserved in synteny across species. To investigate the shared synteny between samples of different taxa, the mapping of the baits with BLAST has been realized on different genomes, the genomes statistics have been produced with SAMtools, and heatmap with ggplot2.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The present stage of the project is to discriminate paralogs from orthologs using homemade scripts. The mapping population will be used to check the result using the expected allele frequency ratios of hybrids F1 and Backcross. The homemade scripts are based on detecting loci with high heterozygosity levels, which might indicate paralogy. A consensus sequence of the orthologs and paralogs haplotypes are then produced using a phasing tool. 


# 4. Results

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The Hyb-Seq dataset has been submitted to a series of tests to assess the efficiency of the target capture and library amplification process. Due to several technical  issues involving target capture, over-amplification of libraries post capture, and to the problematic sequences of several target capture baits, 11% of the reads on average were mapped to the reference bait set. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The mapping population displays a low bait coverage of 2.7 on average, with an uneven repartition of the reads along the baits reference sequence. The selection of conchifolia-specific sequences has allowed to reach better sequencing depth, and to call alleles with higher confidence in the mapping population.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The next step of the project will be to determine and compare the loss of diversity over time in the different B. socotrana populations that have been sampled. The loss of diversity can be assessed with several genomic parameters, using the time series of samples to calculate the differential (Δ) between present and historical specimens. These delta estimators will be representative of genetic change over time: Heterozygosity level (Δh), inbreeding level (ΔF), genetic load (ΔL), and level of genomic deletions (Δd).

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The **genome-wide heterozygosity** (**h**), calculated as the number of heterozygous sites divided by the total number of sites [(Díez-del-Molino et al. 2018)](https://www.zotero.org/google-docs/?Qd7lms). It is a whole-genome statistic that can be used to describe and summarize the genomic diversity in a sample. However, its estimation can be biased with low or uneven coverage, and ancient DNA (aDNA) damages. To deal with the low-depth of the read, a specific method implying an expectation-maximization (EM) algorithm will be used to estimate the proportion of loci that are heterozygous in the target individual [(Bryc, Patterson, and Reich 2013)](https://www.zotero.org/google-docs/?xCqknJ). Another trial will include the suite of methods ATLAS that will be used to process the low-depth and herbarium-dried historical DNA and estimate the genetic diversity of ancient samples [(Link et al. 2017)](https://www.zotero.org/google-docs/?yL6nV0). 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The level of homozygosity in an individual will be assessed by estimating the amount of **Runs Of Homozygosity** (**ROH**) in an individual genome, and will be used to calculate the **inbreeding level** (**F**). On diploid organisms, ROH are  genomic intervals where nucleotides are identical on both chromosomes at every position of the interval. Several selection events as well as  genetic drift can generate ROH, but longer ROH can indicate the level of recent inbreeding in the population [(Magi et al. 2014)](https://www.zotero.org/google-docs/?Qa6I1a).  The number and length of ROH can be used to calculate the individual inbreeding coefficient (F), and provide information on the evolutionary history of a population [(McQuillan et al. 2008)](https://www.zotero.org/google-docs/?Ux4oWU). We will be using present and historical samples to discriminate ancient bottleneck events, that will be in the genomic baseline of all samples, and recent declines that will be short ROHs in the genome of present samples, and include them in the calculation of ΔF. 

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The calculation of the **genetic load** (**L**), and its change through time can provide information about the inbreeding and the strength of purging applied to a population. To calculate the genetic load, the **Loss-of-Function variants** (**LoF**) number can be compared to the number of synonymous variants. LoF, or most commonly deleterious mutations, are caused by mutations that disrupt the function of a gene and reduce the individual fitness [(Lynch, Conery, and Burger 1995)](https://www.zotero.org/google-docs/?nfMoUE). Their classification can be challenging on non-model organisms, and it is unknown if we may use this parameter.

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;The frequency of **genomic deletions** (**d**) is a genetic variation that may increase in frequency or even be fixed in a declining population [(Rogers and Slatkin 2017)](https://www.zotero.org/google-docs/?KOMu5J). It can be studied if functional annotations are available for the genome studied to estimate to what extent the deletion of functionally important genes has increased as a consequence of population decline. Once again the feasibility of this option has to be explored. 



# 5. Litterature


[Bryc, Katarzyna, Nick Patterson, and David Reich. 2013. ‘A Novel Approach to Estimating Heterozygosity from Low-Coverage Genome Sequence’. ](https://www.zotero.org/google-docs/?Ddciwq)[*Genetics*](https://www.zotero.org/google-docs/?Ddciwq)[* 195 (2): 553–61. https://doi.org/10.1534/genetics.113.154500.](https://www.zotero.org/google-docs/?Ddciwq)

[Díez-del-Molino, David, Fatima Sánchez-Barreiro, Ian Barnes, M. Thomas P. Gilbert, and Love Dalén. 2018. ‘Quantifying Temporal Genomic Erosion in Endangered Species’. ](https://www.zotero.org/google-docs/?Ddciwq)[*Trends in Ecology & Evolution*](https://www.zotero.org/google-docs/?Ddciwq)[* 33 (3): 176–85. https://doi.org/10.1016/j.tree.2017.12.002.](https://www.zotero.org/google-docs/?Ddciwq)

[Frodin, David G. 2004. ‘History and Concepts of Big Plant Genera’. ](https://www.zotero.org/google-docs/?Ddciwq)[*TAXON*](https://www.zotero.org/google-docs/?Ddciwq)[* 53 (3): 753–76. https://doi.org/10.2307/4135449.](https://www.zotero.org/google-docs/?Ddciwq)

[Link, Vivian, Athanasios Kousathanas, Krishna Veeramah, Christian Sell, Amelie Scheu, and Daniel Wegmann. 2017. ‘ATLAS: Analysis Tools for Low-Depth and Ancient Samples’. Preprint. Bioinformatics. https://doi.org/10.1101/105346.](https://www.zotero.org/google-docs/?Ddciwq)

[Lynch, Michael, John Conery, and Reinhard Burger. 1995. ‘Mutation Accumulation and the Extinction of Small Populations’. ](https://www.zotero.org/google-docs/?Ddciwq)[*The American Naturalist*](https://www.zotero.org/google-docs/?Ddciwq)[* 146 (4): 489–518. https://doi.org/10.1086/285812.](https://www.zotero.org/google-docs/?Ddciwq)

[Magi, Alberto, Lorenzo Tattini, Flavia Palombo, Matteo Benelli, Alessandro Gialluisi, Betti Giusti, Rosanna Abbate, et al. 2014. ‘H 3 M 2 : Detection of Runs of Homozygosity from Whole-Exome Sequencing Data’. ](https://www.zotero.org/google-docs/?Ddciwq)[*Bioinformatics*](https://www.zotero.org/google-docs/?Ddciwq)[* 30 (20): 2852–59. https://doi.org/10.1093/bioinformatics/btu401.](https://www.zotero.org/google-docs/?Ddciwq)

[McQuillan, Ruth, Anne-Louise Leutenegger, Rehab Abdel-Rahman, Christopher S. Franklin, Marijana Pericic, Lovorka Barac-Lauc, Nina Smolej-Narancic, et al. 2008. ‘Runs of Homozygosity in European Populations’. ](https://www.zotero.org/google-docs/?Ddciwq)[*The American Journal of Human Genetics*](https://www.zotero.org/google-docs/?Ddciwq)[* 83 (5): 658. https://doi.org/10.1016/j.ajhg.2008.10.009.](https://www.zotero.org/google-docs/?Ddciwq)

[Moonlight, Peter W, Wisnu H Ardi, Luzmila Arroyo Padilla, Kuo-Fang Chung, Daniel Fuller, Deden Girmansyah, Ruth Hollands, et al. 2018. ‘Dividing and Conquering the Fastest-Growing Genus: Towards a Natural Sectional Classification of the Mega-Diverse Genus Begonia (Begoniaceae)’, 57.](https://www.zotero.org/google-docs/?Ddciwq)

[Nicholls, James A., R. Toby Pennington, Erik J. M. Koenen, Colin E. Hughes, Jack Hearn, Lynsey Bunnefeld, Kyle G. Dexter, Graham N. Stone, and Catherine A. Kidner. 2015. ‘Using Targeted Enrichment of Nuclear Genes to Increase Phylogenetic Resolution in the Neotropical Rain Forest Genus Inga (Leguminosae: Mimosoideae)’. ](https://www.zotero.org/google-docs/?Ddciwq)[*Frontiers in Plant Science*](https://www.zotero.org/google-docs/?Ddciwq)[* 6 (September). https://doi.org/10.3389/fpls.2015.00710.](https://www.zotero.org/google-docs/?Ddciwq)

[Rogers, Rebekah L., and Montgomery Slatkin. 2017. ‘Excess of Genomic Defects in a Woolly Mammoth on Wrangel Island’. Edited by Gregory S. Barsh. ](https://www.zotero.org/google-docs/?Ddciwq)[*PLOS Genetics*](https://www.zotero.org/google-docs/?Ddciwq)[* 13 (3): e1006601. https://doi.org/10.1371/journal.pgen.1006601.](https://www.zotero.org/google-docs/?Ddciwq)

[Schubert, Mikkel, Luca Ermini, Clio Der Sarkissian, Hákon Jónsson, Aurélien Ginolhac, Robert Schaefer, Michael D Martin, et al. 2014. ‘Characterization of Ancient and Modern Genomes by SNP Detection and Phylogenomic and Metagenomic Analysis Using PALEOMIX’. ](https://www.zotero.org/google-docs/?Ddciwq)[*Nature Protocols*](https://www.zotero.org/google-docs/?Ddciwq)[* 9 (5): 1056–82. https://doi.org/10.1038/nprot.2014.063.](https://www.zotero.org/google-docs/?Ddciwq)
