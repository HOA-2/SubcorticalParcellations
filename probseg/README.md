# CMA Subcortical Probabilistic Atlas

The probabilistic atlas was created using Advanced Normalization Tools (ANTs) (Avants et al., 2009; Avants et al., 2011) (https://github.com/ANTsX/ANTs) in two stages. First, a T1w MRI image template was created from the fifty segmented T1w MRI images using antsMultivariateTemplateConstruction2 (Avants et al., 2011). A probabilistic atlas was then created using antsJointLabelFusion2 (Wang et al., 2013). This used the output of the above template creation command in conjunction with the T1w MRI images and associated labelmaps to create an atlas labelmap (`malf2Labels.nii.gz`) as well as individual probability maps for each region of interest (`malf2Posterior0001.nii.gz – malf2Posterior0028.nii.gz`) 

`malf2` stands for "mulitatlas label fusion" produced by the `antsJointLabelFusion2` command, the Posterior indicates probability files, and each of the numbers from 1-28 represent the segment labels in order the color tables in the lut directory. The exact commands used are detailed below, with the parameters identified in the cited papers and repository.


```
antsMultivariateTemplateConstruction2.sh \
    -d 3 \
    -g 0.2 \
    -t BSplineSyN \
    -n 0 \
    -r 1 \
    -k 1 \
    -c 2 \
    -j 12 \
    -f 8x4x2x1 \
    -o ants50 \
    *.nii.gz


antsJointLabelFusion2.sh \
    -d 3 \
    -c 2 \
    -j 12 \
    -t ants50template0.nii.gz \
    -o malf2 \
    -p malf2Posteriors%04d.nii.gz \
    -g Brain1_T1w.nii.gz -l Brain1_labelmap.nii.gz \
    -g Brain2_T1w.nii.gz -l Brain2_labelmap.nii.gz  \
    -g Brain3_T1w.nii.gz -l Brain3_labelmap.nii.gz ...
```


Note 1: Application of the atlas does not necessarily assure anatomically correct segmentation of target brain. This is especially true for regions subject to high amounts of inter-individual variability (e.g., posterior horn of the lateral ventricle, fifth ventricle). Be sure to review the result and adjust output according to CMA guidelines (see Rushmore et al., 2022)

Note 2: Please reference Rushmore et al. Frontiers in Neuroanatomy 2022 when using these data.

## References

Avants, B. B., Tustison, N., and Song, G. (2009). Advanced normalization tools (ANTS). Insight J. 2, 1–35. Available at: https://scicomp.ethz.ch/public/manual/ants/2.x/ants2.pdf.

Avants, B. B., Tustison, N. J., Song, G., Cook, P. A., Klein, A., and Gee, J. C. (2011). A reproducible evaluation of ANTs similarity metric performance in brain image registration. Neuroimage 54, 2033–2044. doi: 10.1016/j.neuroimage.2010.09.025.

Rushmore R.J., Sunderland, K., Carrington H., Chen J., Halle M., Lasso A.,
Papadimitriou G., Prunier N., Rizzoni E., Vessey B., Wilson-Braun P., Rathi Y.,  Kubicki M., Bouix S., Yeterian E. and Makris N. (2022) Anatomically curated segmentation of human subcortical structures in high resolution magnetic resonance imaging: An open science approach.
Front. Neuroanat. 16:894606. doi: 10.3389/fnana.2022.894606

Wang, H., Suh, J. W., Das, S. R., Pluta, J. B., Craige, C., and Yushkevich, P. A. (2013). Multi-Atlas Segmentation with Joint Label Fusion. IEEE Trans. Pattern Anal. Mach. Intell. 35, 611–623. doi: 10.1109/TPAMI.2012.143.
