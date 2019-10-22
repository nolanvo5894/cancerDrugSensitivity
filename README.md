# cancer_drug_sensitivity
As sequencing technologies make it possible to collect vast amount of data about the cellular environment
in complex diseases, the use of statistical learning techniques to integrate and analyze these data sources
and guide personalized treatment decisions has attracted great interest from the scientific community.<br>

Different kinds of features representing both the drug and the cancer cells have been used to trained predictive
models to address this challenge. While mRNA levels and mutation profiles are popular choices for representing
cancer cells, I believe protein levels offer a more accurate depiction of the cellular environment than the
two mentioned data sources. Drug molecules have often been represented by structural features (e.g. size
and topology) and physical properties (e.g molecular weight, polarity, and lipophilicity). However, the link
between these features and the drugs’ effects on the cellular environment is rarely clear.<br>

A new method for profiling small molecules’ bioactivities is morphological profiling. In this method, a library
of compounds are given to a standard cancer cell line, and changes in the cells’ morphology (e.g. size and
shape of the cell, location of the nuclei and organelles as well as their fluorescent intensities upon staining
with fluorescent dyes) after the treatment are measured from microscopic images. The molecules’ effects on
the cellular environment have been shown to manifest in these changes in morphology, and thus I believe
they could be used as effective descriptors and predictors for the molecules’ bioactivities.<br>

*My project aims to train a regression model that can take as input a query drug’s morphological profile (data collected from [GigaDB](http://gigadb.org/dataset/100351)  and a
query cell line’s protein levels (data collected from from the Cancer Cell Line Encyclopedia [CCLE](https://portals.broadinstitute.org/ccle) and predict the drug’s potency on
the cancer cell line as measured by area-under-percent-viability-curve or of that drug-cell line pair (data collected from the Cancer Therapeutics Response Portal [CTRP](https://portals.broadinstitute.org/ctrp/). *<br>

This study explored the use of drugs' morphological profile as a new, useful set of features for building predictive models of drug response in cancer cell line. The fine-tuned random forest model achived an RMSE of 1.201 (on a 0 - 30 range) and an R^2 value of 0.687. Furthermore, morphological features, when examined in parallel with -omics data from cancer cell line, revealed potential relationships between the drugs and intracellular molecules and pathways that can be validated and exploited for development of more potent and personalized cancer therapeutics.

Some future directions that I plan to pursue further are:
* Try fitting Random Forest with features selected from the LASSO. Pre-modeling feature selection might improve the model's predictive power.
* Ensemble morphology - protein model with models using other data sources (e.g. morphology - RNA expression or morphology - somatic mutation)
* Extensive mining of morphology - protein relationships in all identified drug cluster - cell line cluster pairs.
* Validation of pathways identified from the investigating the predictive model.
* Using deep neural network (e.g. convolution neural network) to directly extract morphological features for drugs from microscopic images of standard cancer cells treated with those drugs. At the moment these features come from hand-crafted, hard-defined rules. These rules may not be able to capture all the information in the images. This would require tremendous computing power and powerful algorithms, which is a major challenge.
