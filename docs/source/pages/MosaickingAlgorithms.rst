.. _mosaic_algos:

#####################
Mosaicking Algorithms
#####################

.. note::
   The content needs to be provided/edited by GK

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


Medoid
======

STC
===

QA / QC
*******

Processing System
*****************
