Workshop Summary and Slides from August 2014

Post date: Tuesday, November 18, 2014 - 06:56 



Thank you to all of you participated in our GIAB workshop August 14-15.  It
was great to have discussions with many of you.  Below is a summary of talks
and discussions from the workshop.  Most of the slides are available on
slideshare at http://www.slideshare.net/GenomeInABottle, and some additional
slides may be posted in the next couple weeks.  We plan to hold the next GIAB
Consortium workshop Jan 29-30, 2015 at Stanford University, and we hope to
see many of you there then!

NIST gave an update on the Consortium’s progress since the last workshop as
well as its plans for releasing RMs and data over the next year
(http://www.slideshare.net/GenomeInABottle/aug2014-giab-intro-slides;
http://www.slideshare.net/GenomeInABottle/aug2014-giab-status-update-and-wg-charge.
    A rough timeline is available in the slides at
http://www.slideshare.net/GenomeInABottle/aug2014-nist-rm-development-plans.
The most immediate plans are to release the pilot NIST RM8398 (based on
NA12878) by the end of 2014, and to release preliminary SNP and indel calls
and ~100x PacBio sequencing for the PGP Ashkenazim trio in Q1 2015.
Don Baldwin gave an update on the proposed ABRF interlaboratory NGS
sequencing study.  This study will use the Ashkenazim trio, as well as
several mixed samples to test somatic mutation detection
(http://www.slideshare.net/GenomeInABottle/aug2014-abrf-interlaboratory-study-plans).
Several groups gave examples of how they are already using the NIST
high-confidence SNP, indel, and homozygous reference calls for benchmarking
sequencing and bioinformatics methods
(http://www.slideshare.net/GenomeInABottle/aug2014-use-cases-combined).

*RM Selection & Design Working Group*
(http://www.slideshare.net/GenomeInABottle/aug2014-working-group-report-rm-selection-and-design)
Horizon Diagnostics presented about their engineered cell lines with ~40
cancer-relevant mutations, including one translocation that is present in DNA
and RNA.  They also embed mixed cells in FFPE.
Acrometrix presented about their control material containing synthetic DNA
spiked into DNA from the cell line of the Askenazim son, which will be NIST
RM 8391. The Acrometrix control contains 504 SNVs, 2 MNVs, and 49 indels of
lengths ranging from 1 to 41 nucleotides (29 deletions, 19 insertions, and
one complex indel). Data from a multi-site study demonstrated differences in
performance between sites using the same control material.
Translocations were discussed as a challenging problem for performance
assessment, but we decided to postpone until we better understand the utility
of synthetic spike-ins with SNVs and indels.
To use existing RMs for cancer applications, they may need to be
characterized for lower frequency mutations, which would require very high
read depths at least in some locations.  This may need to be done on the
actual RM batch of DNA since new somatic mutations can accumulate in the cell
lines.
For additional families to be made into RMs, it was stated that diverse
ancestries are desired, especially an admixed Hispanic family and African
ancestry.  This may help avoid over-fitting pipelines and will be useful for
mixing experiments.
This group also discussed a potential interlaboratory study to assess whether
synthetic controls are good surrogates for DNA isolated from a clinical
sample.  Several members plan to develop a strawman proposal to distribute to
the consortium for comments.

*Characterization/Bioinformatics Working Groups*
(http://www.slideshare.net/GenomeInABottle/aug2014-working-group-report-characterization-bioinformatics)
In the last workshop, it was recommended that GIAB data be submitted to the
SRA first and then NCBI will add them to the GIAB ftp site.  However, since
most GIAB members have not submitted to the SRA, barriers to submitting data
to SRA were discussed.  Generally, experienced submitters expressed that they
find the process straightforward, but the SRA could probably have better
instructions for first-time submitters.  Any specific suggestions for
improving submission instructions are welcome.
In April 2014, NIST released v.0.2 of its calls that integrated the phased
pedigree calls from Real Time Genomics and Illumina Platinum Genomes.  NIST
has generally received positive feedback about these calls, but some
suggestions were made at the workshop that may refine them in certain cases.
NIST is reimplementing a new version of its multi-dataset integration methods
that will be on the cloud and more easily run by other interested groups.
While the concepts behind this new version are similar to the Nature
Biotechnology paper from Feb 2014, it is being redesigned to be more flexible
to better take advantage of knowledge of strengths and biases of each
sequencing method.  More details about the proposed methods are available at
http://www.slideshare.net/GenomeInABottle/aug2014-nist-integration-plans.
The PGP trios will be characterized by a number of long-read technologies to
help characterize more difficult variants and parts of the genome.
Specifically, NIST and Mt Sinai will be performing 100x PacBio sequencing of
the Ashkenazim trio (~60x of son and ~20x of each parent).  Mt Sinai has
developed methods to perform SV calling and de novo assembly with PacBio
reads alone and in combination with BioNano Genomics, which will be submitted
for publication soon.  BioNano Genomics has already mapped the Asian son and
plans to measure the Ashkenazim trio as well.  Illumina is preparing moleculo
assembled long read libraries for the Ashkenazim and Asian sons, which will
be sequenced at NIST and will result in ~10x coverage of the genome by long
reads. Complete Genomics is also preparing LFR libraries for the PGP trios.
Short read sequencing of the PGP trios by Complete Genomics, Illumina, SOLiD,
and Ion is already finished or will be completed soon and will be uploaded to
the GIAB ftp site.  Everyone is welcome to help analyze these data,
particularly the new long-read technologies, to help detect variants in more
difficult parts of the genome and SVs.
Several groups are working on developing SV calls for GIAB genomes.
Personalis has used the NA12878 pedigree to find large deletions that are
breakpoint resolved and in multiple members of the pedigree, and NIST has
developed methods to look for evidence of candidate SVs in bam files
(http://www.slideshare.net/GenomeInABottle/aug2014-nist-structural-variant-integration).
    In addition, Spiral Genetics has developed calls for NA12878 using its
unique anchored assembly approach
(http://www.slideshare.net/GenomeInABottle/aug2014-spiral-genetics-anchored-assembly).
    Harvard School of Public Health and other have collaborated to develop SV
integration and comparison methods as well, including using a set of
high-confidence SVs developed by LUMPY
(http://bcbio.wordpress.com/2014/08/12/validated-whole-genome-structural-variation-detection-using-multiple-callers/).
Transitioning to GRCh38 was also discussed, since having high-confidence
calls for this new reference assembly will help labs transition to using it.
Taking full advantage of GRCh38 requires tools that can use the alternate
haplotypes, and Deanna Church will update the group on development of these
tools after a meeting this fall.  In the meantime, it was suggested that we
remap all of the existing data to GRCh38, including the alternate haplotypes,
but then exclude as uncertain any regions in the reference that have
corresponding sequence in an alternate haplotype that does not exactly match
the reference.

*Performance Metrics Working Group*
(http://www.slideshare.net/GenomeInABottle/aug2014-working-group-report-performance-metrics)
The Performance Metrics Specification draft posted on the blog earlier this
year was discussed, and edits were suggested at
https://docs.google.com/document/d/1g8Q-6aunFmyyeS_L3xmRMqUT8PmWdIiCrzdEsn3rwUA.
    It was suggested that use cases, inputs, and outputs need to be clarified
further.  It was emphasized that a web-based interface for variant comparison
will be very helpful for many labs.  It would be useful to incorporate the
comparison tool into the GeT-RM browser and the GCAT website and both
websites have expressed interest in doing this when a comparison tool is
developed.
The Global Alliance for Genomic Health (GA4GH) has very recently formed a
Benchmarking working group to develop standardized methods and metrics for
benchmarking variant calls.  Julie Newcomb from UC Berkeley discussed the
SMaSH benchmarking tool developed by their group, which is likely going to be
adopted and further developed by GA4GH.  The Performance Metrics group
decided to continue working with GA4GH and SMaSH and ensure that the
performance assessment performed by SMaSH will be useful to clinical labs.


