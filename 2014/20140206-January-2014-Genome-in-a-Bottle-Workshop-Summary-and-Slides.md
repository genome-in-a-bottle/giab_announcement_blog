January 2014 Genome in a Bottle Workshop Summary and Slides

Post date: Thursday, February 6, 2014 - 00:00 



Thank you to all of you who attended our workshop January 27-28, 2014 at Stanford University. Your contributions to Genome in a Bottle are very much appreciated! Below, we have a summary of the topics discussed at the workshop, including links to slides with more details.

Update and Consortium Progress
- NIST plans to release its pilot whole genome Reference Material (RM 8398), based on a large batch of ~8000 vials of 10ug of NA12878 DNA from Coriell, by May 2014

    o Consortium members have developed several high-confidence SNP and indel callsets for NA12878
        • Zook et al have integrated and arbitrated between 14 callsets from 5 sequencing platforms to develop high-confidence SNP, indel, and homozygous reference calls (see http://www.slideshare.net/GenomeInABottle/140127-zook-giab-update and http://genomeinabottle.org/blog-entry/new-version-manuscript-and-highly-...)
        • Vega et al have used phased variant calls for NA12878 and her 11 children to develop a larger set of high-confidence SNP and indel calls with the RTG pipeline that are inherited as expected by phasing the family (see http://www.slideshare.net/GenomeInABottle/140127-rtg-phased-pedigree-ana... and http://genomeinabottle.org/blog-entry/availability-phase-consistent-gold...)
        • Eberle et al have used phased variant calls for NA12878 and her 11 children to develop a larger set of high-confidence SNP, indel, and (in progress) SV calls with several variant calling pipelines that are inherited as expected by phasing the family (see http://www.slideshare.net/GenomeInABottle/140127-platinum-genomes-pedigr... and ftp://ftp.1000genomes.ebi.ac.uk/vol1/ftp/technical/working/NA12878_Illum...)
        • NIST plans to integrate these callsets together to form a larger high-confidence callset, along with Complete Genomics LFR for phasing integration
        • Data is available on the GIAB ftp site and Amazon S3

    o NIST and some consortium members are also starting to develop structural variant integration methods
    o Consortium members have generated data from the NIST RM 8398 DNA, including 50x 100bp Illumina, 200x 150bp Illumina, Complete Genomics, 100x 75bp SOLiD, and 25x Ion Proton whole genome sequencing, and Illumina and Ion Proton exome sequencing. Some of this data is already on the GIAB ftp site.
    o NIST is analyzing the homogeneity of RM8398 by sequencing 6 vials of DNA and comparing allele fraction and coverage differences between the vials to determine if the vials may contain different cell line mutations, though no detectable differences are expected since the DNA was well-mixed before aliquotting.
    o NIST is measuring the stability of RM8398 after shipping, vortexing, freeze-thaw cycles, and storage at 4°C or 37°C for 2 and 8 weeks. Because the size distribution of DNA is expected to be the least stable attribute, Pulsed-field gel electrophoresis is being used to measure size distribution changes
    o Several labs gave examples of how they are already using the NIST high-confidence calls and regions for NA12878 (see http://www.slideshare.net/GenomeInABottle/140128b-use-cases-of-giab-rms)
        - NIST is receiving DNA in Jan-Feb 2014 from large batches of cells of the father, mother, and son in an Ashkenazim Jewish trio and of the son in an Asian trio. These DNA will be available to anyone in the Consortium interested in helping to characterize them (see http://genomeinabottle.org/blog-entry/want-help-characterize-first-4-pgp...). These individuals are consented to allow many types of applications, including commercial redistribution.

RM Selection and Design Working Group
- See summary slides at http://www.slideshare.net/GenomeInABottle/140127-rm-selection-wg-summary
- For selecting future genomes, it was proposed that finding a large family is prioritized over additional trios, because the large number of children of NA12878 has been very useful for understanding sequencing errors
- There was significant interest is selecting a tumor-normal cell line pair, and ATCC will look into producing a tumor cell line from the father of the Ashkenazim trio, as well as the consents of its existing tumor-normal pairs
- ABRF presented about their proposed interlaboratory study using the Ashkenazim Jewish trio candidate NIST RM, which will provide valuable data from multiple sequencing technologies in Phase 1

Measurements for RM Characterization Working Group
- See summary slides at http://www.slideshare.net/GenomeInABottle/140127-measurements-for-rm-cha...
- For more expensive technologies, measurements should be prioritized on the child of the trios.
- Representatives from Complete Genomics LFR, Illumina moleculo, PacBio, and BioNano Genomics presented about how their technologies can help with phasing and characterizing more difficult regions of the genome and structural variants. All are interested in working with GIAB, and we will likely rely on their help and methods developed by their early collaborators to use their data.

Bioinformatics Working Group
- See summary slides at http://www.slideshare.net/GenomeInABottle/140127-bioinformatics-wg-summary
- Future submissions of data for GIAB should be submitted to the NCBI SRA if possible so that they can be properly accessioned and appropriate metadata is collected. Chunlin Xiao will then transition the data to the GIAB ftp site
- Developing reproducible pipelines was discussed, and the consensus was that it is less important to have easily reproducible pipelines for characterizing the RMs, but very important to have reproducible and standardized methods to compare calls to the GIAB high-confidence genotypes (which falls under the Performance Metrics Working Group). However, there was also discussion of developing an automated pipeline to utilize new data as it is generated for the RMs.
- Justin Zook, Francisco De La Vega, and Mike Eberle will work to integrate the NIST arbitrated high-confidence calls with the phased pedigree calls to develop a more comprehensive callset.

Performance Metrics Working Group
- see summary document at http://www.slideshare.net/GenomeInABottle/140127-performance-metrics-wg
- GIAB will develop a draft document containing a specification for tools to compare calls to GIAB high-confidence callsets
- The issues around comparing complex variants (i.e., nearby indels or nearby SNPs and indels) were discussed, including methods like vcfeval (see http://www.slideshare.net/GenomeInABottle/140127-rtg-vcfeval-vcf-compari...) to compare them properly. Justin Zook will collect examples of complex variants that are difficult to compare, and GIAB may propose a challenge of methods to compare these.



