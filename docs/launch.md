# Launch Setup

## Pre-Built Template vs Float CLI vs MMCloud Air



!!! Note "Differences"

    === "Pre-Built Template"

        For this course, we have already set up the full configuration for the pipleines. To submit, go to the MMCloud Opcenter and and launch your designated pipeline.

    === "MMCloud Air"

        Launching in [MMCloud Air](https://air.mmcloud.io/) is fully web-based allowing users to launch the pipeline from the web in a GUI. 
    
    === "Float CLI"

        Launching from the Float CLI gives you the most control. You have full control of the launch, but need to be familiar with the float cli.


## `nf-core/scrnaseq` Setup


#### Run Command

```sh
nextflow run nf-core/scrnaseq -r 2.7.0
```

---

```
[spotOnly=true,retryLimit=10,retryInterval=300s]
```

#### Staged Mounts
```
https://mdibl-cloud-workshop.s3.us-east-1.amazonaws.com
```


### Sample Sheet
!!! info  
     *Young_Y1_lung_29w* sample has been removed. The authors found batch effects in this sample and excluded it in downstream analysis. Might be good to keep in as a teaching tool, but their method of batch detection would need to be incorporated into our workflow, so we're leaving it out.


> Data Location: https://mdibl-cloud-workshop.s3.amazonaws.com/scRNAseq-2024/data/
```txt
sample,fastq_1,fastq_2
Young_Y1_kidney_29w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320581/Y1K1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320581/Y1K1_R2_001.fastq.gz
Young_Y1_kidney_29w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320582/Y1K2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320582/Y1K2_R2_001.fastq.gz
Young_Y1_spleen_29w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320585/Y1S1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320585/Y1S1_R2_001.fastq.gz
Young_Y3_kidney_31w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320586/Y3K1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320586/Y3K1_R2_001.fastq.gz
Young_Y3_kidney_31w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320587/Y3K2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320587/Y3K2_R2_001.fastq.gz
Young_Y3_lung_31w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320588/Y3RL1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320588/Y3RL1_R2_001.fastq.gz
Young_Y3_lung_31w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320589/Y3RL2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320589/Y3RL2_R2_001.fastq.gz
Young_Y3_spleen_31w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320590/Y3S1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320590/Y3S1_R2_001.fastq.gz
Young_Y3_spleen_31w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320591/Y3S2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320591/Y3S2_R2_001.fastq.gz
Young_Y4_kidney_34w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320592/Y4K1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320592/Y4K1_R2_001.fastq.gz
Young_Y4_kidney_34w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320593/Y4K2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320593/Y4K2_R2_001.fastq.gz
Young_Y4_lung_34w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320594/Y4RL1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320594/Y4RL1_R2_001.fastq.gz
Young_Y4_lung_34w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320595/Y4RL2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320595/Y4RL2_R2_001.fastq.gz
Young_Y4_spleen_34w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320596/Y4S1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320596/Y4S1_R2_001.fastq.gz
Young_Y4_spleen_34w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320597/Y4S2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320597/Y4S2_R2_001.fastq.gz
Young_Y5_kidney_34w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320598/Y5K1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320598/Y5K1_R2_001.fastq.gz
Young_Y5_kidney_34w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320599/Y5K2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320599/Y5K2_R2_001.fastq.gz
Young_Y5_lung_34w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320600/Y5RL1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320600/Y5RL1_R2_001.fastq.gz
Young_Y5_lung_34w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320601/Y5RL2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320601/Y5RL2_R2_001.fastq.gz
Young_Y5_spleen_34w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320602/Y5S1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320602/Y5S1_R2_001.fastq.gz
Young_Y5_spleen_34w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320603/Y5S2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320603/Y5S2_R2_001.fastq.gz
Old_O1_kidney_88w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320604/O1K1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320604/O1K1_R2_001.fastq.gz
Old_O1_kidney_88w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320605/O1K2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320605/O1K2_R2_001.fastq.gz
Old_O1_lung_88w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320606/O1RL1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320606/O1RL1_R2_001.fastq.gz
Old_O1_lung_88w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320607/O1RL2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320607/O1RL2_R2_001.fastq.gz
Old_O1_spleen_88w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320608/O1S1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320608/O1S1_R2_001.fastq.gz
Old_O1_spleen_88w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320609/O1S2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320609/O1S2_R2_001.fastq.gz
Old_O2_kidney_91w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320610/O2K1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320610/O2K1_R2_001.fastq.gz
Old_O2_kidney_91w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320611/O2K2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320611/O2K2_R2_001.fastq.gz
Old_O2_lung_91w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320612/O2RL1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320612/O2RL1_R2_001.fastq.gz
Old_O2_lung_91w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320613/O2RL2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320613/O2RL2_R2_001.fastq.gz
Old_O2_spleen_91w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320614/O2S1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320614/O2S1_R2_001.fastq.gz
Old_O2_spleen_91w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320615/O2S2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320615/O2S2_R2_001.fastq.gz
Old_O3_kidney_93w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320616/O3K1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320616/O3K1_R2_001.fastq.gz
Old_O3_lung_93w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320617/O3RL1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320617/O3RL1_R2_001.fastq.gz
Old_O3_spleen_93w_rep1,/staged-files-1/scRNAseq-2024/data/SRR9320618/O3S1_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320618/O3S1_R2_001.fastq.gz
Old_O3_spleen_93w_rep2,/staged-files-1/scRNAseq-2024/data/SRR9320619/O3S2_R1_001.fastq.gz,/staged-files-1/scRNAseq-2024/data/SRR9320619/O3S2_R2_001.fastq.gz
```

### Params
```
multiqc_title: 'scRNAseq-workshop'
aligner: 'cellranger'
protocol: '10XV2'
fasta: 'https://ftp.ensembl.org/pub/release-112/fasta/mus_musculus/dna/Mus_musculus.GRCm39.dna.primary_assembly.fa.gz'
gtf: 'https://ftp.ensembl.org/pub/release-112/gtf/mus_musculus/Mus_musculus.GRCm39.112.gtf.gz'
skip_emptydrops: true
```

!!! danger "Cost Summary"

    | **onDemand/Spot** | Time | Cost |
    | -------- | -------- | -------- |
    | **OnDemand**     | 3h43m22s     | $54.773     |
    | **SpotFirst** | 3h42m56s | $20.473 | 


---

## `mdibl/scscape` Setup

### Github Repository Address
```
https://github.com/mdibl/scscape
```

### Run Command
```sh
nextflow run nf-core-scscape/main.nf -c mmcloud.config -params-file parameters.json -profile docker
```

### Sample Sheet
```
id,data_directory,mt_cc_rm_genes
Old_O1_kidney_88w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O1_kidney_88w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O1_lung_88w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O1_lung_88w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O1_lung_88w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O1_lung_88w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O1_spleen_88w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O1_spleen_88w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O1_spleen_88w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O1_spleen_88w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O2_kidney_91w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O2_kidney_91w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O2_kidney_91w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O2_kidney_91w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O2_lung_91w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O2_lung_91w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O2_lung_91w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O2_lung_91w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O2_spleen_91w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O2_spleen_91w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O2_spleen_91w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O2_spleen_91w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O3_kidney_93w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O3_kidney_93w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O3_lung_93w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O3_lung_93w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O3_spleen_93w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O3_spleen_93w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Old_O3_spleen_93w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Old_O3_spleen_93w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y1_kidney_29w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y1_kidney_29w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y1_kidney_29w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y1_kidney_29w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y1_spleen_29w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y1_spleen_29w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y3_kidney_31w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y3_kidney_31w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y3_kidney_31w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y3_kidney_31w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y3_lung_31w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y3_lung_31w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y3_lung_31w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y3_lung_31w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y3_spleen_31w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y3_spleen_31w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y3_spleen_31w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y3_spleen_31w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y4_kidney_34w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y4_kidney_34w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y4_kidney_34w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y4_kidney_34w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y4_lung_34w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y4_lung_34w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y4_lung_34w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y4_lung_34w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y4_spleen_34w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y4_spleen_34w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y4_spleen_34w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y4_spleen_34w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y5_kidney_34w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y5_kidney_34w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y5_kidney_34w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y5_kidney_34w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y5_lung_34w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y5_lung_34w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y5_lung_34w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y5_lung_34w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y5_spleen_34w_rep1,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y5_spleen_34w_rep1/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
Young_Y5_spleen_34w_rep2,s3://mdibl-cloud-workshop/scrnaseq_output/cellranger/count/Young_Y5_spleen_34w_rep2/outs/filtered_feature_bc_matrix/,s3://mdibl-cloud-workshop/scscape_input/AuxillaryGeneList_mm.csv
```

### Parameters
```json
{

    "sample_sheet": "s3://mdibl-cloud-workshop/scscape_input/Samples.csv",
    "segmentation_sheet":"s3://mdibl-cloud-workshop/scscape_input/segmentation.csv",
    "outdir": "s3://mdibl-cloud-workshop/scscape_output/",

    "gene_identifier": "gene_name",
    "min_cells": 3,
    "min_features": 200,

    "nfeature_lower": 10,
    "nfeature_upper": 0,
    "ncount_lower": 10,
    "ncount_upper": 0,
    "max_mito_pct": 10,

    "vars_2_regress": "nCount_RNA,nFeature_RNA,percent.mt,S.Score,G2M.Score",

    "features_2_scale": "VF",
    "scale_method": "SCT",

    "pcMax": null,

    "integration_method": "Harmony",

    "resolutions": "0.05,0.1,0.3,0.5,0.7,0.9,1.2,1.5",

    "makeLoupe": true,
    "eula_agreement": "Agree"

}
```

### Segmentation Sheet
```csv
id,kidney,spleen,lungs,all
Old_O1_kidney_88w_rep1,true,false,false,true
Old_O1_lung_88w_rep1,false,false,true,true
Old_O1_lung_88w_rep2,false,false,true,true
Old_O1_spleen_88w_rep1,false,true,false,true
Old_O1_spleen_88w_rep2,false,true,false,true
Old_O2_kidney_91w_rep1,true,false,false,true
Old_O2_kidney_91w_rep2,true,false,false,true
Old_O2_lung_91w_rep1,false,false,true,true
Old_O2_lung_91w_rep2,false,false,true,true
Old_O2_spleen_91w_rep1,false,true,false,true
Old_O2_spleen_91w_rep2,false,true,false,true
Old_O3_kidney_93w_rep1,true,false,false,true
Old_O3_lung_93w_rep1,false,false,true,true
Old_O3_spleen_93w_rep1,false,true,false,true
Old_O3_spleen_93w_rep2,false,true,false,true
Young_Y1_kidney_29w_rep1,true,false,false,true
Young_Y1_kidney_29w_rep2,true,false,false,true
Young_Y1_spleen_29w_rep1,false,true,false,true
Young_Y3_kidney_31w_rep1,true,false,false,true
Young_Y3_kidney_31w_rep2,true,false,false,true
Young_Y3_lung_31w_rep1,false,false,true,true
Young_Y3_lung_31w_rep2,false,false,true,true
Young_Y3_spleen_31w_rep1,false,true,false,true
Young_Y3_spleen_31w_rep2,false,true,false,true
Young_Y4_kidney_34w_rep1,true,false,false,true
Young_Y4_kidney_34w_rep2,true,false,false,true
Young_Y4_lung_34w_rep1,false,false,true,true
Young_Y4_lung_34w_rep2,false,false,true,true
Young_Y4_spleen_34w_rep1,false,true,false,true
Young_Y4_spleen_34w_rep2,false,true,false,true
Young_Y5_kidney_34w_rep1,true,false,false,true
Young_Y5_kidney_34w_rep2,true,false,false,true
Young_Y5_lung_34w_rep1,false,false,true,true
Young_Y5_lung_34w_rep2,false,false,true,true
Young_Y5_spleen_34w_rep1,false,true,false,true
Young_Y5_spleen_34w_rep2,false,true,false,true
```

### Auxillary Feature File
```csv
MTgenes,G2Mgenes,Sgenes,RMgenes
mt-Atp6,Hmgb2,Mcm5,
mt-Atp8,Cdk1,Pcna,
mt-Co1,Nusap1,Tyms,
mt-Co2,Ube2c,Fen1,
mt-Co3,Birc5,Mcm7,
mt-Cytb,Tpx2,Mcm4,
mt-Nd1,Top2a,Rrm1,
mt-Nd2,Ndc80,Ung,
mt-Nd3,Cks2,Gins2,
mt-Nd4,Nuf2,Mcm6,
mt-Nd4l,Cks1b,Cdca7,
mt-Nd5,Mki67,Dtl,
mt-Nd6,Tmpo,Prim1,
mt-Rnr1,Cenpf,Uhrf1,
mt-Rnr2,Tacc3,Cenpu,
mt-Ta,Pimreg,Hells,
mt-Tc,Smc4,Rfc2,
mt-Td,Ccnb2,Polr1b,
mt-Te,Ckap2l,Nasp,
mt-Tf,Ckap2,Rad51ap1,
mt-Tg,Aurkb,Gmnn,
mt-Th,Bub1,Wdr76,
mt-Ti,Kif11,Slbp,
mt-Tk,Anp32e,Ccne2,
mt-Tl1,Tubb4b,Ubr7,
mt-Tl2,Gtse1,Msh2,
mt-Tm,Kif20b,Rad51,
mt-Tn,Hjurp,Rrm2,
mt-Tp,Cdca3,Cdc45,
mt-Tq,Jpt1,Cdc6,
mt-Tr,Cdc20,Exo1,
mt-Ts1,Ttk,Tipin,
mt-Ts2,Cdc25c,Dscc1,
mt-Tt,Kif2c,Blm,
mt-Tv,Rangap1,Casp8ap2,
mt-Tw,Ncapd2,Usp1,
mt-Ty,Dlgap5,Clspn,
,Cdca2,Pola1,
,Cdca8,Chaf1b,
,Ect2,Mrpl36,
,Kif23,E2f8,
,Hmmr,,
,Aurka,,
,Psrc1,,
,Anln,,
,Lbr,,
,Ckap5,,
,Cenpe,,
,Ctcf,,
,Nek2,,
,G2e3,,
,Gas2l3,,
,Cbx5,,
,Cenpa,,
```

Sateesh cost breakdown for scrnaseq


| **onDemand/Spot** | Time | Cost |
| -------- | -------- | -------- |
| **OnDemand**     | 3h43m22s     | $54.773     |
| **SpotFirst** | 3h42m56s | $20.473 | 

