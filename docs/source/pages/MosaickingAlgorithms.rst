.. _mosaic_algos:

#####################
Mosaicking Algorithms
#####################

Input to the mosaicking process are surface reflectance values, from the so-called Level 2A product.
Level 2As are operationally produced by the Copernicus (ESA) ground segment.
Currently ESA is using the Sen2Cor atmospheric correction processor for the generation of Level 2A products.
These Level 2A contain directional surface reflectances in 10 spectral bands (i.e. not BRDF corrected),
a scene classification layer (SCL) providing information on cloudiness, snow and other pixel classification information,
as well as aerosol and water vapour used during the atmospheric correction process.
The S2GM mosaicking algorithm has to rely on this information for its processing.
The S2GM processing chain to calculate the mosaic image products is fully automated and is based on a modular design -
see see :numref:`processingChainMainSteps`. The three following main modules form the basis of the chain.

1.	Quality assurance/ quality check (QA/QC) of the input products
2.	Composite/Mosaic algorithm
3.	Quality assurance/ quality check (QA/QC) of the input products

.. _processingChainMainSteps:
.. figure:: images/ProcessingChainMainSteps.png
   :name: processingChainMainStepsName
   :scale: 80%
   :alt: Processing Chain - Main Steps
   :align: center

   Processing Chain - Main Steps

General overview
****************

The basis of the main module of the processing chain (:numref:`mosaickingScheme`) consists of the following steps (see also :ref:`mosaic_hub`):
1.	Selection of the region of interest or the whole globe (typically a user option)
2.	Selection of the spatial resolution and the aggregation period of the composite (typically a user option)
3.	The processing system identifies all observations in space and time which lie within the region and aggregation period definitions of the user. These are then submitted to the composite algorithm, which also includes the pre-processing.
4.	The compositing algorithm selects the best pixel observation in time, depending on statistical characteristics of the spectral measurements and other corresponding information like geometry; pixel identification is included in the composite regarding the chosen spatial resolution
5.	Mosaicking in the region of interest
The algorithm used here for the generation of Sentinel-2 mosaics selects the original pixel from the Sentinel-2 L2A product
that is supposed to be most representative for the mosaicking period.
The only manipulation of actual measured values may come from the resampling required to arrive at a common spatial resolution of the output format.
There are two distinct methods used for selection of the best pixel, namely the MEDOID and the Short-Term Composite (STC).
They are briefly introduced below, and all steps are described in full detail in the ATBD document.
While both methods are sufficiently simple and robust for automated large-scale application,
the quality of the resulting mosaics are sensitive to errors in Sen2Cor’s scene classification and to an optional pre-filtering of input products based on the scene classification.


.. _mosaickingScheme:
.. figure:: images/MosaickingScheme.png
   :name: mosaickingSchemeName
   :scale: 80%
   :alt: Mosaicking Scheme
   :align: center

   Mosaicking Scheme


The mosaic processing is organized in two distinct modules (see :numref:`mosaickingScheme`):
- the pre-processing module
- and a combined mosaicking module based on Medoid and Short-Term Composite approaches.

A threshold related to the number of valid observations is defined and applied in the processing chain for the selection of the mosaicking approach. In case of sufficient valid observations, the Medoid approach is selected otherwise the Short-Term composite is chosen. The threshold has been set to 4 for Mosaics V1.


Input Data- Sentinel-2 L2A processed with Sen2Cor
*************************************************
The Sentinel-2 L2A products produced with Sen2Cor and delivered by ESA via the two Copernicus hubs serve as input for the mosaic service.
The Sen2Cor processor [#f1]_,
which generates the L2A products has been analysed in the Atmospheric Correction Inter-Comparison Exercise (ACIX) exercise
and was found to provide reasonable results regarding the aerosol optical depth, water vapour and surface reflectance values.
The scene classification was not part of the assessment in the ACIX exercise [Doxani et al., 2018 [#f2]_].
The processing methodology for the mosaicking algorithm relies on quality of the input data in terms of surface reflectance values,
on the absence of artefacts and on a correct pixel classification, in particular for clouds and cloud shadows.
Despite the high accuracy and quality of the L2A images reported in the sen2cor documentation,
we encountered several issues concerning remaining haze, cloud omission errors and commission errors for bright surfaces.
In particular, urban areas are systematically flagged with the low probability flag.
This has a significant influence on the quality of the mosaic. The erroneous S2 L2A scene classification has a direct
impact on the quality of the resulting mosaics. The configuration of the pre-filtering based on the L2A flags has different
effects on the resulting mosaics depending on the compositing method (Medoid or STC) applied.
In summary, a very strict pre-filtering leads to systematic removal of numerous valid observations while undetected
cloud pixels are still present. In turn, a weak pre-filtering results in numerous occurrences of cloud spectra (Medoid)
or even remaining clouds in the final mosaic products (STC).


Pre-processing - filtering
==========================
The pre-processing module analyses all input spectra and identifies all pixel which should be used in the compositing/mosaicking approach that are defined as valid observation.
As explained before, the unreliability of the S2 L2A scene classification requires this pre-processing of the Sen2Cor data.
Furthermore, unflagged artefacts on the swath border in the Sen2Cor data have been also filtered out by the pre-processing to ensure the quality of the mosaics.
This filtering is done by using the view zenith, because the swath border can be identified through the view zenith angle.
Additionally, all input spectral bands containing any Not-a-Number (NaN) or infinite value have been also identified and filtered out by the pre-processing regarding the quality of the mosaics.
The pre-processing of the input spectra has been applied to perform the mosaicking only for valid observations.
The definition of a valid pixel is based on the spectra, the viewing geometry, and also of the Sen2Cor scene classification layer (SCL).


Temporal Resampling
===================
Image compositing aims at identifying the best suited observation in a given period of time on the basis of pre-defined criteria at the pixel-level or image-level [#f3]_.

Short Term Composite - STC – adaption of the WELD algorithm regarding Sentinel-2
--------------------------------------------------------------------------------
The STC approach has been motivated by the Web-enabled Landsat Data –WELD method [#f4]_ method and is, like WELD,
based on a decision tree regarding the surface reflectance values, the scene classification, and the different indices.
The compositing approach has been designed to preferentially select valid land surface observations with minimum cloud,
snow, and atmospheric contamination. Therefore, the composited mosaics are not for studies of cloud, snow or the atmosphere.
Compared to WELD, the STC has to work without the thermal bands available on Landsat 8, and is adapted to the spectral characteristics,
as well as the Scene Classification available in the Sentinel 2 Level 2A product.
STC is part of the S2GM processing chain. The ATBD provides a detailed description of this algorithm.

Medoid Composite [#f5]_
-----------------------
The Medoid composite is part of the combined mosaicking algorithm to produce the composites in the S2GM service.
The approach determines the medoid of a set of observations which can be considered as a representative value in a period.
The algorithm is described in detail in the ATBD.

Spatial resampling
==================
The S2GM service produces Sentinel-2 surface reflectance composites at global/regional scale at spatial resolutions of
10m, 20m and 60m, which include all bands except B9 and B10. The Sentinel L2A input products do not include all bands
in all three spatial target resolutions; a spatial resampling is thus necessary prior to the production of composites. It should be recalled here that:
Terminology:
Up-sampling is used when measurements with a larger spatial resolution (e.g. S2 band 1 with 60m) are resampled onto a grid with higher spatial resolution grid (e.g. to a grid at 10m resolution).
Down-sampling is used when measurements with a higher spatial resolution (e.g. S2 band 2 with 10m) are resampled onto a grid with lower spatial resolution (e.g. to a grid with 60m resolution).
The following list summarizes the different approaches to spatial re-sampling and compositing in the different spatial resolutions:

* for the 10m composite:

  * up-sampling to 10m via nearest neighbour method for B01_60m, B05_20m, B06_20m, B07_20m, B8A_20m, B11_20m, B12_20m and SCL_20m
  * selection of the best representative spectra based on all original and up-sampled bands in 10m
  * Consequently, all bands of lower spatial resolution, may exhibit spatial (artificial) variability below the spatial resolution of the detector, because several values from different observation times may be used to generate the spatial composite in the higher resolution.

* for the 20m composite

  * down-sampling via mean aggregation or via wavelet down-sampling method required for B08_10m
  * up-sampling via nearest neighbour method required for B01_60m
  * selection of the best representative spectra based on all original and down- and up-sampled bands in 20m

* for the 60m composite

  * down-sampling via mean aggregation or via wavelet down-sampling method required for B08_10m
  * selection of the best representative spectra based on all original and down-sampled bands in 60m

The method delivers the requested mosaic in the desired spatial resolution as a composite of genuine observations within
the aggregation period, albeit at (potentially) different observation times for each pixel. As a consequence,
a later spatial aggregation, in particular a down-sampling to lower resolution is not advisable,
because of the different selected observation time in the spatial grid.



.. rubric:: Footnotes

.. [#f1] ESA 2018: `sen2cor Configuration And User Manual <http://step.esa.int/thirdparties/sen2cor/2.5.5/docs/s2-pdgs-mpc-l2a-sum-v2.5.5_v2.pdf>`_
.. [#f2] Doxani et al., 2018: Doxani, G.; Vermote, E.; Roger, J.-C.; Gascon, F.; Adriaensen, S.; Frantz, D.; Hagolle, O.; Hollstein, A.; Kirches, G.; Li, F.; Louis, J.; Mangin, A.; Pahlevan, N.; Pflug, B.; Vanhellemont, Q. Atmospheric Correction Inter-Comparison Exercise. Remote Sens. 2018, 10, 352.
.. [#f3] Frantz et al., 2017: Frantz, D., et al. (2017). "Phenology-Adaptive Pixel-Based Compositing Using Optical Earth Observation Imagery." Remote Sensing Of Environment 190: 331-347
.. [#f4] Roy et al., 2011: Roy, D. P., Ju, J., Kommareddy, I., Hansen, M., Vermote, E., Zhang, C., Kommareddy, A. (2011). Web-Enabled Landsat Data (WELD) Products – Algorithm Theoretical Basis Document, February 2011, 63 PP
.. [#f5] Flood 2013: Flood, N. (2013). Seasonal Composite Landsat TM/ETM+ Images Using The Medoid (A Multi-Dimensional Median). `Remote Sensing, 5(12), 6481–6500. <http://doi.org/10.3390/rs5126481>`_
