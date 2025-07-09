---
layout: post
title: PCBS
description: Principle Component BiSulfite
image: assets/images/DSC_0067.JPG
---

In 2022, I was working on a whole genome bisulfite sequencing project. I was making a figure for a collaborator and wanted a ranking metric for one of the axes that encompassed both the significance of the individual CpGs as well as the fold change of methylation at each CpG between the two conditions. The p-values alone were insufficient because they didn't capture the degree of difference between the two conditions, and the % methylation difference was a flawed because it didn't provide good protection from outlier effects. However, the PCA for that project looked something like this:
<img src="Differential_Methylation_files/figure-html/unnamed-chunk-3-1.png" width="700">

Principle Component 1 (PC1) was quite clearly driving the main variation in the dataset, and so I ranked the CpGs by their contribution to PC1. The figure ended up being quite exciting, and to make it publishable I started working on some proof of concept figures using generated data. Imagine my surprise when I compared my method to a bunch of the existing methylation softwares and found a *staggering* number of false positive and false negative calls.</p>
<p><img src="[Differential_Methylation_files/figure-html/unnamed-chunk-3-1.png](https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/bioinformatics/40/10/10.1093_bioinformatics_btae593/1/m_btae593f1.jpeg?Expires=1753937577&Signature=HBa6VQoDywXydPfopW8zXUQwBJFmsoHcRSwBtQHlzhd4q7jlzchkEkIA4FkwFKvkKFRfeG4tLsEOt2-w1G873eu71yikw~u-RASrO1rBcEu7-wDms~kIPoQL8BuJAQFjHMriNrUBBPRN9O2j0ymDAldmVqKgFDSjd7CZ8yHWWhPir1UHn~AuOkdEINpoK-7ESW-vTvzx2k6jYBCRvo~ujbk~EA-9ufKiSSdh1GRzkfsWd6jBMlOWWBVF9GK1SV8ZJc2PUWYfNEPm8dezt0U3~KrSPjdp-LoLsNWc1quKW706rIkQXp03DxNr7nRyRk~Qj7KrPLQCPY1ps9LN1~XGcg__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA)" width="700">

So began a project to improve on those existing methods, using the principle component contribution as the central metric. This work eventually became PCBS, an <a href="https://academic.oup.com/bioinformatics/article/40/10/btae593/7811138"> now published</a> R package available for download on CRAN, with a whole host of <a href="https://katlande.github.io/PCBS/"> tutorials</a> available online as well!


