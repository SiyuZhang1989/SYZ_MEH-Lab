#@Author Xin-Di Zhao, Zi-Yu Gao
#@Data Feb 23rd 2025

##For the rocker file (based on diamond blastx, used for filtering the blastout files)
aioA.150.ROCker.txt: sensitivity: 99.43%; specificity: 99.99%; accuracy: 99.99%
arrA.150.ROCker.txt: sensitivity: 99.16%; specificity: 99.98%; accuracy: 99.97%
arxA.150.ROCker.txt: sensitivity: 99.85%; specificity: 99.99%; accuracy: 99.99%
arsC1.150.ROCker.txt: sensitivity: 97.90%; specificity: 99.56%; accuracy: 99.50%
arsC2.150.ROCker.txt: sensitivity: 92.03%; specificity: 99.83%; accuracy: 99.61%
arsM.150.ROCker.txt: sensitivity: 95.63%; specificity: 99.92%; accuracy: 99.87%
arsI.150.ROCker.txt: sensitivity: 95.13%; specificity: 99.83%; accuracy: 99.74%
arsP.150.ROCker.txt: sensitivity: 97.48%; specificity: 99.81%; accuracy: 99.71%

#Usage: Please remember that all rocker commands need to run in your own dircetory!(not any mount points, such as shared, data_name...)
gene=aioA ## or arxA, arrA, arsC1, arsC2, arsM, arsI, arsP
ROCker=$gene.150.rocker.txt ## the ROCker file
input=$SAMPLE.$gene.blastout ## the blastout file (your short-read metagenomic and metatranscriptomic data can do diamond blastx aganist the corresponding gene database)

singularity exec ~/shared/apps/ROCker.sif ROCker filter -k $ROCker -x $input -o $SAMPLE.$gene.ROCker
