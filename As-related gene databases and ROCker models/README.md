# As-related gene databases and ROCker models

This repository contains As-related gene databases and ROCker models, including ***aioA***, ***arxA***, ***arrA***, ***arsC1***, ***arsC2***, ***arsM***, ***arsI***, and ***arsP*** genes. If you have any other questions or needs related to the ROCker models, please don't hesitate to contact us (syzhang@des.ecnu.edu.cn). The databases and ROCker models provided here may only be used for academic exchange and are not permitted for commercial use.

The papers are out at ***Microbiome*** (https://doi.org/10.1186/s40168-024-01952-4) and ***Environ Sci Technol*** (https://doi.org/10.1021/acs.est.4c08620). Please cite the following if you find POCker models helpful for your analyses. 

If you use the databases of ***aioA***, ***arxA***, ***arrA***, ***arsC1***, and ***arsC2*** genes or the ROCker models, please cite the first paper; if you use the databases of ***arsM***, ***arsI***, and ***arsP*** genes or the ROCker models, please cite the second paper.

## Citation
1. Zhao, XD., Gao, ZY., Peng, JJ. et al. Various microbial taxa couple arsenic transformation to nitrogen and carbon cycling in paddy soils. *Microbiome* **12**, 238 (2024).
2. Gao, ZY., Zhao, XD., Chen, Chuan. et al. Paddy Soil Flooding and Nonflooding Affect the Transcriptional Activity of Arsenic Methylation and Demethylation Communities. *Environ Sci Technol* (2025).

## For the rocker file (*based on diamond blastx, used for filtering the blastout files*)
aioA.150.ROCker.txt: sensitivity: 99.43%; specificity: 99.99%; accuracy: 99.99%
arrA.150.ROCker.txt: sensitivity: 99.16%; specificity: 99.98%; accuracy: 99.97%
arxA.150.ROCker.txt: sensitivity: 99.85%; specificity: 99.99%; accuracy: 99.99%
arsC1.150.ROCker.txt: sensitivity: 97.90%; specificity: 99.56%; accuracy: 99.50%
arsC2.150.ROCker.txt: sensitivity: 92.03%; specificity: 99.83%; accuracy: 99.61%
arsM.150.ROCker.txt: sensitivity: 95.63%; specificity: 99.92%; accuracy: 99.87%
arsI.150.ROCker.txt: sensitivity: 95.13%; specificity: 99.83%; accuracy: 99.74%
arsP.150.ROCker.txt: sensitivity: 97.48%; specificity: 99.81%; accuracy: 99.71%

## Usage 
Please remember that all rocker commands need to run in your directory! (*not any mount points, such as shared, data_name...*)
gene=***aioA***/***arxA***/***arrA***/***arsC1***/***arsC2***/***arsM***/***arsI***/***arsP***
ROCker=$gene.150.rocker.txt (*the ROCker file*)
input=$SAMPLE.$gene.blastout (the blastout file against the corresponding gene database)
## Run
singularity exec ~/shared/apps/ROCker.sif ROCker filter -k $ROCker -x $input -o $SAMPLE.$gene.ROCker (*Please install ROCker before use according to https://doi.org/10.1093/nar/gkw900*)
