![](WCM_MB_LOGO_HZSS1L_CLR_RGB.png)

# Bioinformatic methods (RNA-seq) for Guo al.

The quality of the sequenced reads was assessed with FastQC and QoRTs. Unless stated otherwise, plots involving high- throughput sequencing data were created using R and ggplot2.

## RNA-SEQ data analysis
Raw reads were quality checked with FastQC v0.11.7 (http://www.bioinformatics.babraham.ac.uk/projects/fastqc/), and adapters were trimmed using Trim Galore v0.6.7 (http://www.bioinformatics.babraham.ac.uk/projects/trim_galore/). Reads were aligned to the mouse reference genome (GRCm38.p6) using STAR v2.6.0c with default parameters. Gene abundances were calculated with featureCounts v1.6.2 using composite gene models from Gencode release vM17. Principle component analysis was performed using the plotPCA function from DESeq2 v1.32.0 (Love et al., 2014). Differentially expressed genes were determined with DESeq2 v1.32.0 with a two-factor model incorporating batch as a covariate, with significance determined by Wald tests (q < 0.05). Gene set enrichment analysis was performed using fgsea v1.18.0 with gene sets from the Broad Institute’s MSigDB collections; genes were ranked by the DESeq2 Wald statistic. Only pathways with an adjusted P value < 0.05 were considered enriched. Expression heatmaps were generated using variance-stabilized data, with the values centered and scaled by row.


## Software used

| Software           | Version    | Authors           | URL                                                               |
|--------------------|------------|-------------------|-------------------------------------------------------------------|
| STAR               | v2.6.0c    | Dobin et al.      | [GitHub](https://github.com/alexdobin/STAR/releases)             |
| featureCounts     | v1.6.2      | Liao et al.       | [Subread](https://subread.sourceforge.net/featureCounts.html)    |
| R                  | v4.1.0      | R Core Team       | [CRAN](https://cran.r-project.org)                               |
| DESeq2             | v1.32.0     | Love et al.       | [Bioconductor](https://bioconductor.org/packages/release/bioc/html/DESeq2.html) |
| ggplot2            | v3.4.1      | Wickham           | [CRAN](https://cran.r-project.org/web/packages/ggplot2/index.html) |
| pheatmap           | v1.0.12     | Kolde             | [CRAN](https://cran.r-project.org/web/packages/pheatmap/index.html) |
| fgsea              | v1.18.0     | Korotkevich et al.| [Bioconductor](https://bioconductor.org/packages/release/bioc/html/fgsea.html) |
