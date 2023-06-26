# rna_breast-cancer

## Introduction:
Breast Cancer is the most common cancer maligancy in women around the world and is curable in 70-80% of patients with early detection<sup>1</sup>.  In the U.S. alone, 12% of women will be diagnosed with breast cancer in their lifetime<sup>2</sup>  with an estimated cost to treat each individual in the range of 16,000-100,000 USD<sup>13</sup> .  Even a conservative estimate places the cost in the range of 4.5 billion dollars annually.  

The development of gene microarray technologies has allowed the detection of gene expression levels of thousands of genes simultanously.  Technological insights could help patient outcomes as well as save costs in poor diagnosis and ineffective treatments. This technology, in concert with the migration to electronic health records can now be utilitzed to help understand the underlying pathways of various disease states and enhance patient outcomes.

The goal of this study is to create a machine learing model that can identify patients with poor outcomes (death from cancer) from gene expression profiles (GEP).  Additionally, gain insights into genes that influence those predictions.

## Data Source

The [cBioPortal hosted by the Center of Molecular Oncology at Sloan Kettering Cancer Center](https://www.cbioportal.org/datasets) <sup>3</sup> holds an open source website with various datasets in the field of cancer research.  This analysis will focus on the METABRIC Dataset. Due to privacy and HIPAA regulations, information is anonymous and preformatted.

## Exploratory Data Analysis

The Molecular Taxonomy of Breast Cancer International Consortium (METABRIC) is an organization hosting a database  with clinical and genetic data from 1,904 patients and primary breast cancer samples.   A list of 489 genes are listed as feature columns and Z-scores of mRNA expression levels are listed as values from RNA-seq collection. In this study, we will be focusing on the mRNA expression levels which is exclusively numerical. The catagory of patient outcomes (living, death from other causes, and death from cancer) was recatagorized as 1:deceased due to cancer, 0:all other cases.

Of the 1,904 patients, 622 were classfied as deceased due to cancer, and as a group had a lower time of survival after diagnosis.

## Modeling 

Baseline Model: Logistic Regressor
    untuned model performs poorly


Best Parameters for Model: penalty = l1, class weight = 'balanced', C = 0.03077
Best Score for LogisticRegression: 0.6678

### With threshold value lowered to 0.3, recall score climbs to 94%