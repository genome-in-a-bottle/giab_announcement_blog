With sequencing technologies and bioinformatics rapidly evolving, want to highlight some interesting use cases for our high-confidence calls for the pilot NIST Genome in a Bottle (GIAB) Reference Material, based on NA12878 (see ftp://ftp-trace.ncbi.nih.gov/giab/ftp/data/NA12878/variant_calls/NIST).  Our recent Nature Biotechnology paper (http://www.nature.com/nbt/journal/v32/n3/full/nbt.2835.html) provided some examples of performance metrics for a few different exome and genome sequencing variant callsets.  We used the GCAT website (www.bioplanet.com/gcat), a platform for interactively calculating performance metrics.  The example comparisons shown in the paper were intended to demonstrate how our high-confidence calls can be used rather than as a platform comparison.  Since the publication process is slow and the state-of-the-art evolves rapidly, the high-confidence benchmark variant calls described in the paper are primarily intended to provide a resource for anyone to measure the performance of any sequencing and bioinformatics pipeline.  We would like to continue to collect examples of groups comparing new variant call sets to our high-confidence calls, and we welcome others to submit ideas for posts related to how they have used our Reference Materials.

 

In this blog post, Srinka Ghosh and Keyan Zhao from Ion Torrent have compared their current exome sequencing and bioinformatics variant calls to our high-confidence calls.  Compared to the demonstration Ion Torrent calls used in our paper, they show that their current sequencing protocol and bioinformatics gives much better results, particularly for indels. Their analyses further highlight the importance of variant calling algorithms.  Specifically, for Ion data a variant caller that uses flow information is critical, as it provides the most accurate model for the Ion platforms – PGM and Proton. As part of this work, the GCAT website has also been updated to include a more recent Ion AmpliSeq exome sequencing dataset, and an example comparison is available at http://www.bioplanet.com/gcat/reports/3062-dauqsiflwh/.

 

 

Variant caller matters!

Based on their analysis, TMAP for alignment followed by flow-aware TVC (Torrent Variant Caller) for variant calling is the best pipeline for Ion data. Significant variability in variant performance metrics – benchmarked against the GIAB truth set - is observed when non-flow aware callers, such as FreeBayes (Sensitivity ~83%) and  GATK (42%-77%) are used. The analysis also contrasts the differential performance characterization obtained when the GATK best practices are implemented under the Haplotype Caller versus Unified Genotyper pipelines. TMAP+TVC on the new Ion data (123x) greatly increased the overall sensitivity, as demonstrated in the table below.

orrent Variant Caller (TVC) is a genetic variant caller for Ion Torrent™ Sequencing platforms, and is specially optimized to utilize the underlying flow signal information in the statistical model to evaluate variants. TVC will be available as a standalone open source release in June as part of TSv4.2. - See more at: http://ioncommunity.lifetechnologies.com/community/products/torrent-variant-caller

 

 

 

Genome in a bottle for platform characterization

The variant comparison toolsets (vcflib/vcfallelicprimitives and USeq/VCFComparator), as recommended in the NIST v2.18 README provide a simple, standardized way for variant comparison utilizing the high-confidence NIST reference set.  A pseudo-code for variant comparison is provided below. Using the new Ion exome data, their analysis showed high performance of SNPs (comparable with Illumina 150x exome data) and great improvement of False Positives for indels.  The publication figures are shown only for reference purposes.


Detailed command used for variant comparison:

 

vcfallelicprimitives  test.vcf  > regularizedtest.vcf

vcfallelicprimitives  test.vcf  > regularizedtest.vcf

 

vcftools --vcf regularizedtest.vcf --remove-indels --recode --recode-INFO-all --out SNP_variants

vcftools --vcf regularizedtest.vcf --keep-only-indels --recode --recode-INFO-all --out indel_variants

 

java -jar -Xmx4g $VCFComparator \

 -a $NISTvcf -b $NISTbed \

 -c SNP_variants.vcf -d $TARGETBEDFILE \

 -g -e -s -p compare_NIST_test_geno_SNP/

 

 

java -jar -Xmx4g $VCFComparator \

 -a $NISTvcf  -b $NISTbed \

 -c indel_variants.vcf -d $TARGETBEDFILE \

 -g -e -n -p compare_NIST_test_geno_indel/

 [JZ1]Since there were several non-NIST authors, it might be better to say "Nature Biotechnology paper" rather than "NIST publication"


