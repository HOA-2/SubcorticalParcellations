[![DOI](https://zenodo.org/badge/521466842.svg)](https://zenodo.org/badge/latestdoi/521466842)

# Harvard-Oxford Atlas 2.0: Subcortical parcellations

## Release version: 2.2.0

Version 2.1.1 added the subcortical probablistic atlas corrsesponding to 2.1.0.

Version 2.1.0 adds parcellation of the cerebellum, adding the following labels:
* 29 Cerebellar_Cortex_Left
* 30 Cerebellar_Cortex_Right
* 31 Cerebellar_White_Matter_Left
* 32 Cerebellar_White_Matter_Right

Version 2.0.1 corrects the mispelling of file 192540_dseg.nii.gz .

Version 2.0.0 increases the number of subjects for the discrete brain 
segmentation to 100. The probablistic segmentation still includes only the 
first 50 subjects; it will be updated in the next minor release.

## Introduction

The Harvard-Oxford Atlas 2.0 project is developing a state-of-the-art,
high-resolution full brain MR atlas consisting of 200 high definition
MR data sets from the Human Connectome Project (HCP) parcellated into
392 gray and white matter PUs using structural MRI and 189 white
matter fascicles using diffusion MRI. Manual parcellation will be
performed based on a developed neuroanatomical ontology using a
principled and well-defined parcellation methodology.

## Dataset

This dataset consists of 50 manual parcelations of MRI datasets from
The Human Connectome Project (HCP).

Files in the `dseg` directory are discrete parcelations of the subject data. Image files are in nifti format and GZIP compressed. File numbers correspond to the HCP subject number from the HCP1200 dataset.

In the `lut` directory, the `dseg.tsv` file describes the label values,
structure names, and suggested colors using the BIDS standard format. The
same file is stored in ctbl format for use with 3D Slicer.

The `probseg` directory contains a probablistic segmentation of the atlas. See the README in that directory for more information.

## Software

Datasets have been authored using 3D Slicer using custom modules developed
by the [Center for Morphometric Analysis](https://cma.mgh.harvard.edu) (CMA)
at Massachusetts General Hospital and Brigham and Women's Hospital in Boston.

## Source files

The parcellation files are derived from 3D Slicer MRB file. Because
of HCP data use agreements covering the underlying datasets, we cannot publicly
post the MRB files that contain that data. They are available by request.

## Citation

Rushmore R.J., Sunderland, K., Carrington H., Chen J., Halle M., Lasso A., Papadimitriou G., Prunier N., Rizzoni E., Vessey B., Wilson-Braun P., Rathi Y., Kubicki M., Bouix S., Yeterian E. and Makris N. (2022) Anatomically curated segmentation of human subcortical structures in high resolution magnetic resonance imaging: An open science approach. Front. Neuroanat. 16:894606. doi:10.3389/fnana.2022.894606

## Sponsorship

[NIH NIMH 5R01MH112748-04 High Resolution, Comprehensive Atlases of the Human Brain Morphology](https://reporter.nih.gov/search/QhVboFoXdUe_XiAriH9B5w/project-details/10053340)

## License

This data is licensed under the 3D Slicer license, part B.

https://raw.githubusercontent.com/Slicer/Slicer/main/License.txt

## Past version history

* v1.0.0: Initial release of the discrete segmentation of 50 subjects.
* v1.1.0: Initial release of the probability atlas for the subjects in v1.0.0.
* v1.1.1: Minor update of this README, no data files have changed.
