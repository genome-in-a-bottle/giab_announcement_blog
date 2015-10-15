
Availability of phase-consistent gold standard variant set for NA12878 and rtgTools software

Post date: Wednesday, January 22, 2014 - 21:16 



I wanted to let you know of the availability of a gold standard variant data set for NA12878, NA12877 and their 11 offspring developed by RTG based on their consistency with the haplotype phases inferred for this family. Also available now is the free rtgTools package to allow comparisons of VCF calls with a gold standard.

The haplotype phases were inferred by a new method to identify recombination cross-overs, identify haplotype blocks, and linking them in an optimal path leveraging the large number of offspring in this pedigree. The starting data for this were the WGS sequencing BAMs for the entire pedigree produced by Illumina as part of their Platinum project (ENA Acc. Nos. ERA172924 and ERA185981). Reads were aligned and variants called with rtgVariant 1.2 providing relationships for NA12878 and its parents; offspring where treated as independent. Only good quality calls (including good reference calls) were used as input for the phasing process. Once the haplotype framework is inferred, raw variant calls across the pedigree can then be checked for consistency to this haplotype framework and aggregated to build a gold standard. If phase consistency fails due to a single sample, the benefit of the doubt can be given to this variant and the single offending genotype corrected. This rescues a few percent of the variants in the pedigree. Obvious errors where removed as well, such as all heterozygous calls and those from problematic regions with missing data.

The segregation phasing consistent gold standard (aka SP standard) is delivered as a multi-sample VCF and it is available at the GiaB repository at:
ftp://ftp-trace.ncbi.nih.gov/giab/ftp/data/NA12878/variant_calls/RTG/pha...

Please look at the README file in the subdirectory for details on the custom annotations on the SP gold standard.
I am also glad to announce that RTG has released a set of tools to analyze VCF files freely available to the community. This rtgTools software package includes vcfeval, a tool to compare a set of calls in a VCF file to a gold standard VCF (baseline) such as the SP standard. Vcfeval has a novel algorithm is to deal with the different representation issues of indel and MNPs across call sets, and provides and output ready to draw ROC curves. rtgTools is a java program available for Linux, Mac OS, and Windows, and can be obtained here:
ftp://ftp-trace.ncbi.nih.gov/giab/ftp/tools/RTG/

You can use these tools to compare variant call sets with the SP standard and obtain ROC curves.
Finally, all the methods used in the construction of the SP standard, the mapping, alignment, and joint variant calling algorithms, and how vcfeval compares VCFs are part of a manuscript that is available online as of today at the BioRxiv pre-print server:
http://biorxiv.org/content/early/2014/01/22/001958

Hope this new data and tools are useful to the GiaB community to construct a reference data set for NA12878 and subsequent reference samples. I will discuss the strategy for constructing the SP standard and some of the results at the GiaB workshop at Stanford new week. Hope to see you all there.

Francisco De La Vega



