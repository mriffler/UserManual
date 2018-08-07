############
Introduction
############

The objective of the S2GM service is the provision of mosaic surface reflectance products derived from Sentinel-2 A and B platforms. Input to the processing are Level 2A products provided by the Copernicus Ground Segment, i.e. ESA Sentinel 2 core products. The S2GM service will generate regional and temporal composites at global scale and produced on-demand over specific areas of interest. The generated products will directly support international policy agreements to which the EU committed, e.g., the Paris agreement of the United Nations Framework Convention on Climate Change (UNFCC) and its activities for Reducing Emissions from Deforestation and forest Degradation (REDD+). These mosaicked surface reflectance products shall serve as input to further thematic processing, i.e. the generation of higher level products, and analyses. Thus, the overarching requirement for the mosaicking is the selection of the most representative spectrum for a given pixel, selected from the set of observations made during the temporal compositing period and to provide this information as Analysis Ready Dataset (ARD).

The Sentinel-2 mission includes a twin-satellite constellation covering all Earth’s land surfaces, large islands, inland and coastal waters every five days at the equator with even higher observation frequencies in mid- and high-latitude regions with the primary aim to support the monitoring of vegetation, land cover, and the environment in general. The Sentinel-2 Multispectral Instrument (MSI) provides multi-spectral information from 13 spectral bands ranging from visible and near-infrared to shortwave infrared wavelengths along a 290-km orbital swath. The MSI sensor data are complementary to data acquired by the U.S. Geological Survey Landsat 8 Operational Land Imager and Landsat 7 Enhanced Thematic Mapper Plus. Sentinel-2A was launched in June 2015 and Sentinel-2B in April 2017.

Input to the mosaicking process are surface reflectance values, from the so-called Level 2A product. Level 2As are operationally produced by the Copernicus (ESA) ground segment. Currently ESA is using the Sen2Cor atmospheric correction processor for the generation of Level 2A products. These Level 2A contain directional surface reflectances in 10 spectral bands (i.e. not BRDF corrected), a scene classification layer (SCL) providing information on cloudiness, snow and other pixel classification information, as well as aerosol and water vapour used during the atmospheric correction process. The S2GM mosaicking algorithm has to rely on this information for its processing.

The S2GM processing chain to calculate the mosaic image products is fully automated and is based on a modular design - see Figure #. The three following main modules form the basis of the chain.
1.	Quality assurance/ quality check (QA/QC) of the input products
2.	Composite/Mosaic algorithm
3.	Quality assurance/ quality check (QA/QC) of the input products

**Figure #: Processing chain - main steps**

.. image:: ProcessingChain.png

S2GM Project
************

Motivation
==========

Scope
=====

Team
====

Organisation of the Manual
**************************

Problem Reporting
*****************

Webinterface + Software Installation
************************************
