[![DOI](https://zenodo.org/badge/521466842.svg)](https://zenodo.org/badge/latestdoi/521466842)


# Harvard-Oxford Atlas 2.0: Subcortical parcellations

## Release version: 1.0

## Introduction

The Harvard-Oxford Atlas 2.0 project is developing a state-of-the-art,
high-resolution full brain MR atlas consisting of 200 high definition
MR data sets from the Human Connectome Project (HCP) parcellated into
392 gray and white matter PUs using structural MRI and 189 white
matter fascicles using diffusion MRI. Manual parcellation will be
performed based on a developed neuroanatomical ontology using a
principled and well-defined parcellation methodology.

## Dataset

This dataset consists of 50 manual parcellations of MRI datasets from
The Human Connectome Project (HCP). Files in the nii directory are in 
nifti format and GZIP compressed.

File numbers correspond to the HCP subject number from the HCP1200 dataset.

in the `lut` directory, the `dseg.tsv` file describes the label values,
structure names, and suggested colors using the BIDS standard format. The 
same file is stored in ctbl format for use with 3D Slicer.

Datasets have been authored using 3D Slicer using custom modules developed
by the [Center for Morphometric Analysis](https://cma.mgh.harvard.edu) (CMA) 
at Massachusetts General Hospital and Brigham and Women's Hospital in Boston.

## Source files
The parcellation files are derived from 3D Slicer MRB file. Unfortunately, becaue
of HCP data use agreements covering the underlying datasets, we cannot publicly
post the MRB files that contain that data. They are available by request.

## Sponsorship

[NIH NIMH 5R01MH112748-04 High Resolution, Comprehensive Atlases of the Human Brain Morphology](https://reporter.nih.gov/search/QhVboFoXdUe_XiAriH9B5w/project-details/10053340)

## License

This data is licensed under the 3D Slicer license, part B.

https://raw.githubusercontent.com/Slicer/Slicer/main/License.txt

