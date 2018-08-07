#############
Product Guide
#############

General
*******

All products provide surface reflectance in eleven bands. The surface reflectance is computed using the “Sentinel-2 Atmospheric Correction” (L2A_AtmCorr) algorithm and based on reference radiative transfer code. Look Up Tables (LUTs) are based on LibRadtran.

**Table #: Surface reflectance bands**

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

All products additionally provide quality indicator bands.

**Table #: Quality Indicator bands**

+------------------------------+------------------------------------------------+------+
| Band name                    |  Description                                   | Unit |
+==============================+================================================+======+
| quality_aot                  | Aerosol Optical Thickness (AOT)                | %    |
+------------------------------+------------------------------------------------+------+
| quality_cloud_confidence     | Ranging from 0 for high confidence no snow/ice | %    |
|                              | to 100 for high confidence snow/ice.           | None |
+------------------------------+------------------------------------------------+------+
| quality_scene_classification | Scene classification map                       | %    |
|                              | (see Figure # & Table ##)                      | None |
+------------------------------+------------------------------------------------+------+

**Figure #: Scene classification map classes**

.. image:: ClassificationMap.png

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
