New High-Confidence NA12878 Genotypes Integrating Phased Pedigree Calls

Post date: Friday, April 18, 2014 - 17:21 



We have recently been working to integrate the phased pedigree calls for NA12878 (from Real Time Genomics and Illumina Platinum Genomes) with the multiple dataset arbitration calls (from NIST and others in GIAB). Our integration process takes advantage of the strengths of each of these callsets to give a larger, more accurate set of phased high-confidence SNP, indel, and homozygous reference genotypes. An initial beta version 0.2 of these calls and the corresponding bed file of high-confidence regions is available on the NCBI GIAB ftp site at (ftp://ftp-trace.ncbi.nih.gov/giab/ftp/data/NA12878/variant_calls/GIAB_in.... These calls will continue to be refined, but we wanted to give everyone the opportunity to test these and give us feedback about how they can be improved. For more information about the calls, see the README in the ftp directory and below:

Genome in a Bottle NA12878 vcf/bed file repository (www.genomeinabottle.org)

This is a repository of integrated snp and indel calls for NA12878, along with bed file that includes regions in which we believe our genotype calls are highly accurate (including homozygous reference calls if no snp or indel is called). To develop these calls, we have integrated v.2.19 of the NIST-GIAB multiple-platform arbitrated calls (http://www.nature.com/nbt/journal/v32/n3/full/nbt.2835.html) with the phased "gold standard" pedigree calls from Real Time Genomics (http://biorxiv.org/content/early/2014/01/24/001958) and Illumina Platinum Genomes (http://www.illumina.com/platinumgenomes/).

This is a preliminary beta version of these calls, which is designed to take advantage of the strengths of multiple dataset arbitration from a simple genome with the phased genotypes of NA12878, her husband, and their 11 children. The multiple dataset arbitration gives high-confidence snp, indel, and homozygous reference genotypes, whereas the phased pedigree calls are most accurate for sites where at least one family member is heterozygous. In the phased pedigree calls, systematic sequencing errors like motif-specific or homopolymer errors generally will not be inherited properly and will be correctly filtered. In contrast, some alignment and mapping errors around complex or structural variants may be incorrect even if they inherit correctly. The integrated calls use phasing information from RTG. We are in the process of writing a description of the methods for integrating these calls, but we wanted to give others a chance to test and use these calls now.

The integrated calls include more SNPs and indels than v2.18 of the NIST-GIAB arbitrated calls, and appear to be more accurate based on preliminary examinations. The vcf file NIST_RTG_PlatGen_merged_highconfidence_v0.2_Allannotate.vcf.gz contains highly confident heterozygous and homozygous variant calls. Any bases that are in the union13callableMQonlymerged_addcert_nouncert_excludesimplerep_excludesegdups_excludedecoy_excludeRepSeqSTRs_noCNVs_v2.19_2mindatasets_5minYesNoRatio_AddRTGPlatGenConf_filtNISTclustergt9_RemNISTfilt_RemPartComp_RemRep_RemPartComp_v0.2.bed.gz bed file intervals and not in the vcf should be considered highly confident homozygous reference (for snps and short indels). This bed file excludes regions/variant locations that are uncertain due to low coverage, genotypes called in < 2 datasets, locations with unresolved discordant genotypes, locations where most datasets have evidence of bias (systematic sequencing errors, local alignment problems, mapping problems, or abnormal allele balance), variants inside possible deletions, known segmental duplications, and structural variants reported in dbVar for NA12878. In all, this excludes ~23% of the non-N bases in the GRCh37 reference assembly. To assess false positive and false negative rates, it is important to compare only variants inside the bed file regions.

GATK's CombineVariants can be used with the bed file to assess performance of individual datasets, but other new methods can be used that give more information, such as David Nix's VcfComparator at http://sourceforge.net/projects/useq/. Examples of different types of comparisons using USeq are described below. We also worked with GCAT to host interactive comparisons with these integrated calls at www.bioplanet.com/gcat, which is available, though currently from v2.18 of the NIST-GIAB arbitrated calls.

IMPORTANT NOTE: Some differences between the integrated calls and your datasets are likely due to different representations of the same complex variants, so be careful about this. In our experience, for some datasets, over half of the putative false positive snps and indels can be due to different correct representations of complex variants. Running vcflib vcfallelicprimitives (https://github.com/ekg/vcflib) on your vcf should allow proper comparison of all homozygous complex variants, but not all heterozygous complex variants since our calls are currently unphased. Real Time Genomics has freely released their vcf comparison algorithm vcfeval, which can properly compare most unphased heterozygous complex variants (http://genomeinabottle.org/blog-entry/availability-phase-consistent-gold...). Currently for complex variants, our calls generally use the representation from Real Time Genomics caller.

If you find any places where you think the integrated calls are incorrect, please post these to the forum on the GIAB website (http://genomeinabottle.org/forum-topic/nist-na12878-integrated-highly-co...). These calls will likely continue to improve as the integration methods improve and additional datasets are incorporated, and we will periodically post new versions of the calls.

Developers:
Justin Zook and Marc Salit - National Institute of Standards and Technology
Brad Chapman, Oliver Hofmann, and Winston Hide - Harvard School of Public Health
Jason Wang and David Mittelman - Arpeggi/Virginia Bioinformatics Institute
Francisco De La Vega - formerly at Real Time Genomics
Michael Eberle - Illumina

Contact:

Justin Zook

