# Characterization of the chromatin landscape surrounding the Il17f gene locus in γδ T-cells
## Overview

- [Research Questions and Methods](#research-questions-and-methods)
    - [Psoriasis: IL17 driven inflammation](#psoriasis-il17-driven-inflammation)
- [Results](#results)
    1. [Enhancers show more variability across cell types than promotors](#1-enhancers-show-more-variability-across-cell-types-than-promotors)
    2. [γδ T-cells cluster by differentiation stage (ATAC-seq and RNA-seq data)](#2-γδ-t-cells-cluster-by-differentiation-stage-atac-seq-and-rna-seq-data)
    3. [Cell type specific genes cluster together in hierarchical clustering](#3-cell-type-specific-genes-cluster-together-in-hierarchical-clustering)
    4. [Ridge regression links ATAC-seq peaks to γδ T‑cell lineage‑specific gene expression](#4-ridge-regression-links-atac-seq-peaks-to-γδ-tcell-lineagespecific-gene-expression)
    5. [OCRs can be linked to gene expression via correlation](#5-ocrs-can-be-linked-to-gene-expression-via-correlation)
    6. [OCRs around the IL17f gene locus](#6-ocrs-around-the-il17f-gene-locus)
- [Conclusion](#conclusion)
- [References](#references)
- [Additional results](#additional-results)

## Research Questions and Methods

Genome-wide association studies have shown that many genetic variants linked to autoimmune disease lie in non-coding regions of the genome, making it difficult to investigate how they influence gene regulation and cell identity (Calderon et al. 2019). To address this, our project combines ATAC-seq and RNA-seq data from the mouse immune system atlas of Yoshida et al., to examine how chromatin accessibility and gene expression relate to each other in  γδ T-cell lineages. ATAC-seq captures open chromatin regions that may act as promoters or enhancers, while RNA-seq measures gene expression but does not reveal the upstream regulatory mechanisms driving it.
We investigated how the chromatin landscape changes during γδ T-cell differentiation regulating the expression of cell type specific genes and establishing cell identity. Therefore 13 different cell types from stem cells to fully differentiated were analysed. 

<div style="text-align: center">
  <img src="plots_for_poster/cell%20lineage.jpg" alt="Cell lineage of γδ T-cells from stem cells (grey) over αβ progenitor T-cells to fully differentiated cell types (Yoshida et al, 2019)" width="60%" />
  <p><b>Fig. 1.</b> Cell lineage of γδ T-cells from stem cells (grey) over αβ progenitor T-cells to fully differentiated cell types (Yoshida et al, 2019).</p>
</div>

<div style="text-align: center">
  <img src="plots_for_poster/Methodes Figure.png" alt="Overview of the ATAC-seq and RNA-seq Datasets: Chromatin accessibility and gene expression were profiled across 86 mouse immune cell types" width="60%" />
  <p><b>Fig. 2.</b> Overview of the ATAC-seq and RNA-seq Datasets: Chromatin accessibility and gene expression were profiled across 86 mouse immune cell types.</p>
</div>

---
<div style="background-color:#f5f5f5; padding:10px; border-radius:4px;">
### Psoriasis: IL17 driven inflammation

Psoriasis is one of the most widespread autoimmune inflammatory skin diseases (Man et al, 2023). It is characterized by increased proliferation of keratinocytes, resulting in impaired maturation and loss of function. Chronic inflammation leads to the constant release of proinflammatory cytokines like IL17, because of misregulated immune cells. In affected skin, γδ T-cells are increased and are potent producers of IL17 (Veras et al, 2022).
The focus is on IL17f, the member of the IL17 family that is predominantly expressed by IL17 producing γδ T-cells. We asked, how the Il17f expression is regulated in immune cell populations through cis-regulatory elements at the gene locus and which open chromatin regions may contribute to γδ T-cell specific regulation.

<div style="text-align: center">
  <img src="plots_for_poster/table_Il17_expr.png" alt="Il17 expression in different cell types" width="60%" />
  <p><b>Fig. 3.</b> Il17 expression in different cell types.</p>
</div>
</div>

## Results
### 1. Enhancers show more variability across cell types than promotors
Enhancer OCRs show sharper distinctions between differentiated immune cell types than promoter OCRs, as evidenced by the more heterogeneous correlation structure. These results are consistent with the established role of distal enhancers as primary determinants of cell type identity.

<div style="text-align: center">
  <img src="plots_for_poster/enhancer_promoter ATAC heatmap all cells.png" alt="A: Matrice of Pearson correlation between cell types, based on ATAC signal intensity at promoter OCRs.
B: Matrice of Pearson correlation between cell types, based on ATAC signal intensity at distal enhancer OCRs." width="60%" />
  <p><b>Fig. 4.</b> <b>A:</b> Matrice of Pearson correlation between cell types, based on ATAC signal intensity at promoter OCRs.
<b>B:</b> Matrice of Pearson correlation between cell types, based on ATAC signal intensity at distal enhancer OCRs.</p>
</div>

Promoter OCRs show higher mean chromatin accessibility, while enhancer OCRs exhibit greater signal variability. This supports a model, where promoters provide accessibility and enhancers drive specificity.  

<div style="text-align: center">
  <img src="plots_for_poster/Boxplot CV Enhancer_promoter all cells.png" alt="Comparison of mean chromatin accessibility and signal variability between promoter and enhancer OCRs across all 90 immune cell types." width="60%" />
  <p><b>Fig. 5.</b> Comparison of mean chromatin accessibility and signal variability between promoter and enhancer OCRs across all 90 immune cell types.</p>
</div>

### 2. γδ T-cells cluster by differentiation stage (ATAC-seq and RNA-seq data)
With both data sets, the clustering closely resembles the cell lineage. Cell types of similar differentiation stages tend to cluster together, rather than differentiated cells with their progenitors. IL17-producing γδ T-cells have quite little correlation with related cell types in both their ATAC and RNA signals. The ATAC signal shows a more gradual change, whereas the RNA signal shows a harsh difference between cell groups, especially between γδ T-cells and Tab progenitors.

<div style="text-align: center">
  <img src="plots_for_poster/Pearson correlation clustermap of ATAC-seq cell types (average linkage).png" alt="A: Matrix of Pearson correlation between cell types, based on ATAC-seq signal intensity and hierarchical clustering of cell types" width="45%" style="vertical-align: middle; margin-right: 10px;" />
  <img src="plots_for_poster/Pearson correlation clustering of RNA-seq cell types (average linkage).png" alt="B: Matrix of Pearson correlation between cell types, based on RNA-seq signal intensity and hierarchical clustering of cell types" width="45%" style="vertical-align: middle;"/>
  <p><b>Fig. 6.</b> <b>A:</b> Matrix of Pearson correlation between cell types, based on ATAC-seq signal intensity
 and hierarchical clustering of cell types. <b>B:</b> Matrix of Pearson correlation between cell types, based on RNA-seq signal intensity and hierarchical clustering of cell types.</p>
</div>

### 3. Cell type specific genes cluster together in hierarchical clustering
Using the Gini score, genes specifically expressed in certain cell types were identified. Many cell type-specific genes are predominantly expressed in myeloid cell types. Distinct gene clusters are visible for B cells, ILCs, NK cells, and stem cells, whereas Tgd cells do not show such clustering. Treg cells exhibit a highly specific gene set. In our cell lineage, large clusters of specific genes are visible for stem cells and IL17-producing γδ T-cells. Characteristic genes were also determined for the cell groups. For γδ T-cells, eight specific genes were identified and used in further analysis.

<div style="text-align: center">
  <img src="plots_for_poster/hierarchical clustering of genes based on expression profile (highest gini genes).png" alt="A: Matrix of Pearson correlation between cell types, based on ATAC-seq signal intensity and hierarchical clustering of cell types." height="450px" width="45%" style="vertical-align: middle; margin-right: 10px;" />
  <img src="plots_for_poster/hierarchical clustering of genes based on expression profile (highest gini genes and only Tgd cells).png" alt="B: Matrix of Pearson correlation between cell types, based on RNA-seq signal intensity and hierarchical clustering of cell types." height="450px" width="45%" style="vertical-align: middle;"/>
  <p><b>Fig. 7.</b> <b>A:</b> Matrix of Pearson correlation between cell types, based on ATAC-seq signal intensity
 and hierarchical clustering of cell types. <b>B:</b> Matrix of Pearson correlation between cell types, based on RNA-seq signal intensity and hierarchical clustering of cell types.</p>
</div>

### 4. Ridge regression links ATAC-seq peaks to γδ T‑cell lineage‑specific gene expression
A ridge regression model was built to predict gene expression from ATACseq peaks. Because few peaks are strongly associated with Il17f and the variance is low, the model tends to overfit, so it is useful only for comparative evaluation of Il17f, not precise prediction. A second ridge model was trained specifically on γδ T-cell development and compared with the all-cell-type model to identify lineage-specific CREs by comparing regression coefficients and selecting the top peaks for different genes.

Rorc, selected among genes with the highest Gini in γδ T-cells, shows a broad pattern, playing a bigger role in late γδ T-cell differentiation rather than a single subset.

<div style="text-align: center">
  <img src="plots_for_poster/top_peaks_ATAC_RNA_Rorc.png" alt="Regression coefficients of the top OCRs associated with Rorc expression in γδ T-cells." width="60%" />
  <p><b>Fig. 8.</b> Regression coefficients of the top OCRs associated with Rorc expression in γδ T-cells.</p>
</div>

For Il17f, the top peaks shown in the plot are top candidate CREs associated with Il17f expression. They show accessibility almost entirely restricted to Tgd.g2+d17.LN, the same subset with detectable Il17f expression. This points to Tgd.g2+d17 specific CREs, but is also limited by the instability of the model.

<div style="text-align: center">
  <img src="plots_for_poster/top_peaks_ATAC_RNA_Il17f.png" alt="Regression coefficients of the top OCRs associated with IL17f expression in γδ T-cells." width="60%" />
  <p><b>Fig. 9.</b> Regression coefficients of the top OCRs associated with IL17f expression in γδ T-cells.</p>
</div>

### 5. OCRs can be linked to gene expression via correlation
To link OCRs to their target genes, ATAC-seq accessibility and RNA-seq expression were correlated for all OCR-gene pairs within a 100 kb genomic window across γδ T cell types. Of the tested pairs, 9,776 passed FDR correction. Correlated OCRs are densely clustered near the transcription start site, indicating that chromatin accessibility at regulatory elements is tightly coupled to gene expression.

<div style="text-align: center">
  <img src="plots_for_poster/single Barplot DIstance of correlated OCRs to TSS.png" alt="Distribution of correlated OCRs relative to TSS." width="60%" />
  <p><b>Fig. 10.</b> Distribution of correlated OCRs relative to TSS.</p>
</div>

Applying the correlation approach to the Il17f locus, a key cytokine in psoriatic inflammation, shows strong correlation between local chromatin accessibility and Il17f expression. γδ T-cells and ILC-cells display elevated OCR accessibility and expression, while other immune lineages remain low (r = 0.730, FDR < 0.05).

<div style="text-align: center">
  <img src="plots_for_poster/scatterplot IL17f- OCR accessibility vs gene expression.png" alt="Chromatin accessibilty versus IL17f expression." width="60%" />
  <p><b>Fig. 11.</b> Chromatin accessibilty versus IL17f expression.</p>
</div>

### 6. OCRs around the IL17f gene locus
The depicted ATAC-seq peaks matches the more detailed chromatin accessibility data from Yoshida et al., which is available in the UCSC Genome Browser. It can also be linked to the correlation analysis. The strongest correlated OCR with Il17f across all immune cell types is a promoter (peak-id: 2095), showing moderate accessibility across expressing cell types. Therefore Il17f seems to be largely driven by promoter activity in most cell types. In contrast, the γδ T-specific analysis identifies a distal enhancer (peak-id: 2086) with highly restricted, elevated accessibility almost exclusively in Tgd.g2+d17 cells (p-value of 1.331e-131). Additionally, this region contains multiple potential binding sites for transcription factors as recognized by JASPAR, suggesting a regulatory function. Some of these predicted transcription factors are also expressed in the Tgd.g2+d17 cells, suggesting that this lineage-specific enhancer cooperates with the promoter to drive elevated Il17f expression specifically in this IL17-producing γδ T-cell subset.

<div style="text-align: center">
  <img src="plots_for_poster/ATAC-peaks around the IL17f gene locus.png" alt="ATAC-seq peaks around the IL17f gene locus for 7 different cell types (displayed is peak summit of 250 bp range). Transcription direction is from right to left, because gene lies on the - strand. Arrows point to peak 2086 (distal enhancer) & peak 2095 (TSS)." width="60%" />
  <p><b>Fig. 11.</b> ATAC-seq peaks around the IL17f gene locus for 7 different cell types (displayed is peak summit of 250 bp range). Transcription direction is from right to left, because gene lies on the - strand. Arrows point to peak 2086 (distal enhancer) & peak 2095 (TSS).</p>
</div>

## Conclusion
<b>Cellular identity</b> is mostly <b>determined by change in distal enhancer</b> regions rather than differences in promotor activity.

IL17-producing γδ T-cells have <b>very different chromatin signatures</b> in comparison with related cell types.

The <b>chromatin landscape changes gradually</b> during differentiation, whereas the gene expression changes abruptly.

Il17f expression is <b>mainly driven by promotor and enhancer activity.</b>

γδ T-cells expressing Il17f have a <b>unique OCR at the Il17f gene locus</b> likely to bind transcription factors and to have regulatory function.

## References

[1] Buenrostro JD, Giresi PG, Zaba LC, Chang HY, Greenleaf WJ (2013)
    Transposition of native chromatin for fast and sensitive epigenomic
    profiling of open chromatin, DNA-binding proteins and nucleosome position.
    Nat Methods 10(12):1213–1218.

[2] Cai Y, Shen X, Ding C, Qi C, Li K, Li X, Jala VR, Zhang H, Wang T, Zheng J, et al. (2011)
    Pivotal role of dermal IL-17-producing γδ T cells in skin inflammation.
    Immunity 35(4):596–610.

[3] Calderon D, Nguyen MLT, Mezger A, Kathiria A, Müller F, Nguyen V, Lescano N, Wu B,
    Trombetta J, Ribado JV, et al. (2019)
    Landscape of stimulation-responsive chromatin across diverse human immune cells.
    Nat Genet 51(10):1494–1505.

[4] Casper J, Speir ML, Raney BJ, Perez G, Nassar LR, Lee CM, Hinrichs AS, Gonzalez JN,
    Fischer C, Diekhans M, et al. (2026)
    The UCSC Genome Browser database: 2026 update.
    Nucleic Acids Res 54(D1):D1331–D1335.

[5] Conesa A, Madrigal P, Tarazona S, Gomez-Cabrero D, Cervera A, McPherson A, Szcześniak MW,
    Gaffney DJ, Elo LL, Zhang X, et al. (2016)
    A survey of best practices for RNA-seq data analysis.
    Genome Biol 17:13.

[6] Hu Y, Hu Q, Li Y, Lu L, Xiang Z, Yin Z, Kabelitz D, Wu Y (2023)
    γδ T cells: origin and fate, subsets, diseases and immunotherapy.
    Sig Transduct Target Ther 8:434.

[7] Kukurba KR, Montgomery SB (2015)
    RNA sequencing and analysis.
    Cold Spring Harb Protoc 2015(11):951–969.

[8] Man A-M, Orăsan MS, Hoteiuc O-A, Olănescu-Vaida-Voevod M-C, Mocan T (2023)
    Inflammation and psoriasis: a comprehensive review.
    Int J Mol Sci 24:16095.

[9] Sun L, Su Y, Jiao A, Wang X, Zhang B (2023)
    T cells in health and disease.
    Sig Transduct Target Ther 8:235.

[10]  Veras FP, Publio GA, Melo BM, Prado DS, Norbiato T, Cecilio NT, Hiroki C, Damasceno LEA,
      Jung R, Toller-Kawahisa JE, et al. (2022)
      Pyruvate kinase M2 mediates IL-17 signaling in keratinocytes driving psoriatic skin inflammation.
      Cell Rep 41(13):111897. doi:10.1016/j.celrep.2022.111897.

[11] Yoshida H, Lareau CA, Ramirez RN, Rose SA, Maier B, Wroblewska A, Desland F, Chudnovskiy A,
     Mortha A, Dominguez C, et al. (2019)
     The cis-regulatory atlas of the mouse immune system.
     Cell 176(4):897–912.e20.

[12] Zhu W, Xu X, Nagarajan V, Guo J, Gupta A, Peng Z, Zhang A, Liu J, Mattapallil MJ,
     Jittayasothorn Y, et al. (2025)
     TLR2 supports γδ T cell IL-17A response to ocular surface commensals by metabolic
     reprogramming.
     J Exp Med 222(10):e20251046.

[13] Claude Sonnet 4.6 (Anthropic AI model)
     Used for Python code refinement and language refinement in writing.

## Additional Results
