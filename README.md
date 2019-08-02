# Rare Disease Workflows
This repo contains a list of workflows designed for accerating the interpretation of rare-disease data, currently applied to data within the NF-OSI.

The goal of this repository is to faciliate harmonization across rare-disease datasets that are deposited onto [Synapse](http://synapse.org). These workflows will be centered around various stages of analysis, shown below.

![Alt text](doc/workflowCats.png?raw=true "Workflows")

## Data Harmonization workflows
We have built a number of workflows that re-process raw data uploaded to Synapse to create a single data repository.

| Data Type | Description | Location | Destination | Status
| --- | --- | --- | --- | --- | 
| RNA-Seq | This workflow runs Salmon alignment from FASTQ files to populate a both a public and private Synapse table that stores all NF-related gene expression data. | [rna-seq-workflow/](rna-seq-workflow) | [Synapse Table]() | Complete 
| Exome/WGS-Seq | This workflow *currently* runs `vcf2maf` on uploaded `vcf` files and stores them on Synapse.  | [gene-variant-workflow](gene-variant-workflow) | Table TBD | Currently processed files, needs to be updated to store data on synapse.|
| Somatic variant caller | This workflow should take the raw data and call somatic variants. | TBD | TBD | Not yet built|
| Drug-Sensitivity Data | This workflow takes drug-sensitivity data and combines it to a single file. | [drug-screening-workflow](drug-screening-workflow) | Table TBD | Still requires table update |

As more data types are added we will continue to add more workflows. 

## Research projects/workflows
Building upon these standardized datasets are workflows that take the data generated by the data harmonization steps above to identify new scientific hypotheses.

| Project name | Description | Data Type | Results Tables | Status | 
| --- | --- | --- | --- | --- |
| [DTEN](http://github.org/sage-bionetworks/dten) | Drug-target expression network takes gene expression data and identifies relevant drug targets. | RNA-Seq | [DTEN Nodes](https://www.synapse.org/#!Synapse:syn18779013/tables/), [DTEN Terms]() |Currently required update to do analysis of network results. |
| [CDOM](https://github.com/aabaker99/cdom) | Combinatorial domain mutation analysis | Exome/WGS-Seq | TBD | Under development | 
| [Latent variable analysis]() | We are comparing various latent variable approaches to characterize gene expression data | RNA-Seq || Under development |
| [Gene mutation feature selection]() | This project evaluates the ability of specific genes to predict tumoe type | | Under development |
| [Drug sensitivity analysis]() | This project looks to identify difference in drug sensitivy across cell lines representing different tumor types || Under development  


## Results extraction workflows
This  is a placeholder for tool we develop to transfer the data into a more visualizable format, such as shiny apps or ETL tools.
