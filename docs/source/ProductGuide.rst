.. _prod_guide:

#############
Product Guide
#############

General
*******

All products provide surface reflectance in eleven bands. The surface reflectance is computed using the “Sentinel-2 Atmospheric Correction” (L2A_AtmCorr) algorithm and based on reference radiative transfer code. Look Up Tables (LUTs) are based on LibRadtran.

.. _surface_reflectance_bands:

Surface reflectance bands
=========================

+------------------------+-----------------+---------------+
| Band name              |  Central        | Spatial       |
|                        |  Wavelength (nm)| Resolution (m)|
+========================+=================+===============+
| B01                    | 443             | 60            |
+------------------------+-----------------+---------------+
| B02                    | 490             | 10            |
+------------------------+-----------------+---------------+
| B03                    | 560             | 10            |
+------------------------+-----------------+---------------+
| B04                    | 665             | 10            |
+------------------------+-----------------+---------------+
| B05                    | 705             | 20            |
+------------------------+-----------------+---------------+
| B06                    | 740             | 20            |
+------------------------+-----------------+---------------+
| B07                    | 783             | 20            |
+------------------------+-----------------+---------------+
| B08                    | 842             | 10            |
+------------------------+-----------------+---------------+
| B8A                    | 865             | 20            |
+------------------------+-----------------+---------------+
| B11                    | 1610            | 20            |
+------------------------+-----------------+---------------+
| B12                    | 2190            | 20            |
+------------------------+-----------------+---------------+

.. _quality_indicator_bands:

All products additionally provide quality indicator bands.

**Table #: Quality Indicator bands**

+------------------------------+------------------------------------------------+------+
| Band name                    |  Description                                   | Unit |
+==============================+================================================+======+
| quality_aot                  | Aerosol Optical Thickness (AOT)                | None |
+------------------------------+------------------------------------------------+------+
| quality_cloud_confidence     | Ranging from 0 for high confidence clear sky   | %    |
|                              | to 100 for high confidence cloudy.             |      |
+------------------------------+------------------------------------------------+------+
| quality_snow_confidence      | Ranging from 0 for high confidence no snow/ice | %    |
|                              | to 100 for high confidence snow/ice.           |      |
+------------------------------+------------------------------------------------+------+
| quality_scene_classification | Scene classification map                       | None |
|                              | (see :numref:`sceneClassifMap` & Table ##)     |      |
+------------------------------+------------------------------------------------+------+


.. _sceneClassifMap:
.. figure:: pages/images/ClassificationMap.png
   :name: ClassificationMapClassesName
   :scale: 100%
   :alt: Scene classification map classes
   :align: center

   Scene classification map classes


The following figure gives an example of an applied classification map:


.. _sceneClassifMapExample:
.. figure:: SceneClassificationMapExample.png
   :name: SceneClassificationMapExample
   :scale: 100%
   :alt: Scene classification map example
   :align: center

   Scene classification map example

The products provide view and sun geometry information.

.. _view_sun_geometry_bands:

**Table #: View and sun geometry bands**

+--------------------+--------------------------------------+--------+
| Band name          |  Description                         | Unit   |
+====================+======================================+========+
| view_zenith_mean   | Mean view zenith angle of all bands  | Degree |
+--------------------+--------------------------------------+--------+
| view_azimuth_mean  | Mean view azimuth angle of all bands | Degree |
+--------------------+--------------------------------------+--------+
| sun_zenith         | Sun zenith angle                     | Degree |
+--------------------+--------------------------------------+--------+
| sun_azimuth        | Sun azimuth angle                    | Degree |
+--------------------+--------------------------------------+--------+

The products provide information on the validity of an observation (pixel).

**Table #: Validation bands**

+--------------------+-----------------------------------------------+--------+
| Band name          |  Description                                  | Unit   |
+====================+===============================================+========+
| source_index       | Index of the product used for this pixel. See | None   |
|                    | 'SourceProductIndices' element in metadata.   |        |
+--------------------+-----------------------------------------------+--------+

Finally, a quality measure for the Medoid compositing algorithm is included.

**Table#: Medoid quality band**

+------------+-----------------------------------------------+--------+
| Band name  |  Description                                  | Unit   |
+============+===============================================+========+
| medoid_mos | The measure of spread of the medoid algorithm.| None   |
|            | Defined as sum of distances divided by number |        |
|            | of observations.                              |        |
+------------+-----------------------------------------------+--------+

The products additionally hold two bands with latitude and longitude information.

INSPIRE
*******

Coordinate Reference Systems
****************************

Software
********

SNAP
====

ArcGIS
======

QGIS
====


GeoTiff / Jpeg2000
******************

General
=======

Naming Convention and File Structure
====================================

Data Content
============

GeoTiff / Jpeg2000 Data Files
-----------------------------

Metadata
--------

NetCDF
******

General
=======

Naming Convention and File Structure
====================================

Data Content
============

NetCDf Data File
----------------

Metadata
--------

Time Series
***********

File Format
===========
