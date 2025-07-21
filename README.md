# machinelearning

Abstract
This study investigates the differential gene expression profiles of  pancreatic islet cells from nondiabetic, Type 1 diabetic (T1D), and Type 2 diabetic (T2D) donors, and how these differences correlate to the disease’s physiologic effects.  Using data from GEO dataset GSE12472, single-cell RNA-sequencing was used to analyze transcriptomic variations.  The data was processed to remove irrelevant entries as well as standardize diabetes-related labels.  Differential gene expression analysis was conducted using DESeq2 to identify key genes and pathways distinguishing between different donor groups.  The findings from this study aim to better amplify our understanding of molecular mechanisms underlying diabetes and to potentially guide the development of targeted therapy.
 
Introduction
Diabetes is a group of chronic diseases affecting the metabolism. It causes issues with insulin production, action, or both, resulting in hyperglycemia. This causes long term damage and dysfunction to several organs, especially affecting the eyes, kidney, nerves, and heart. It is divided into Type 1 (T1) and Type 2 (T2) variants, with T1 being an autoimmune disorder resulting from the immune system attacking the islet cells that produce insulin, and T2 resulting from the pancreas producing less insulin overall, and/or the body becoming resistant to insulin. While both are affected by genetic factors, Type 2 is more influenced by diet and lifestyle, although the onset of either can also be triggered by external factors.  
 
Dataset
GSE124742, the dataset used in our project, was collected from combined single-cell RNAseq of human pancreatic islet cells. It consists of 1,369 pancreas patch-seq cells (nondiabetic and type II diabetes), 348 cryopreserved patch-seq cells (nondiabetic and type I diabetes), and 3,518 FACS islet cells from the same donors.  In total, cells from 18 nondiabetic, 7 T2D donors, 3 T1D (cryopreserved) and 3 nondiabetic donors (cryopreserved) were used.
 
Methods
 
The Dataset was first cleaned by removing n/a values and then sampled from the categories of Nondiabetic, Type 1 Diabetes, and Type 2 Diabetes for the first factor (diabetes status), and neither, FACS, and Patch-Seq for the second factor (sequencing method). Unfortunately, the dataset is lacking T1 FACS samples as the T1 samples were only obtained from cryopreserved patch-seq cells.
Differential analysis was performed using DESeq2 tuned using single-cell dataset parameters. (LRT over Wald test with the reduced model examining only diabetes status, minimum replicates for replacements at infinite)
The results of the model were then examined for the T1 diabetic vs nondiabetic and T2 diabetic vs nondiabetic groups, with results that passed an adjusted p-value of 0.5 after FDR correction. These two models were shrunk for LFC analysis using apeglm, and results with a resulting LFC < -1 or > 1 were pulled to create our list of differentially expressed genes. The resulting overlap was compared via Fisher’s exact test using the GeneOverlap library to determine significance.
 
PCA plotting was used to visualize the variance of the different categories.
 
The differentially expressed genes were searched for significant Gene Ontology term results with a p-value cutoff of 0.1 using GOStats hypergeometric tests.  
