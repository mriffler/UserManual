.. _prod_guide:

#############
Product Guide
#############

General
*******
All Mosaic Hub products provide 22 raster bands selectable by the user
during the order process (see section :ref:`Order Panel <orderPanel>`). Available
raster bands comprise:

- 11 surface reflectance bands
- 4 quality indicator bands
- 4 sun/view geometry bands
- 2 validation bands
- 1 quality band

Additionally two raster bands comprising latitude/longitude information are provided with each product.

The following chapter give more detailed information for the available bands.

.. _surface_reflectance_bands:

Surface reflectance bands
=========================
The Mosaic Hub delivers products with reflectance bands chosen by the user in
the **Band selection** section of the Mosaic Hub order panel
(see section :ref:`Order Panel <orderPanel>`).
The surface reflectance is computed using the “Sentinel-2 Atmospheric Correction”
(L2A_AtmCorr) algorithm and based on reference radiative transfer code.
Look Up Tables (LUTs) are based on LibRadtran.

The following :ref:`table <surface_reflectance_bands_table>` lists the available bands and corresponding native
resolutions of the Sentinel-2 L2A input products.

.. _surface_reflectance_bands_table:
.. csv-table:: Sentinel-2 bands
   :file: csv/S2_bands.csv
   :header-rows: 1

.. _quality_indicator_bands:

Quality indicator bands
=======================
All products additionally provide quality indicator bands, if selected.

.. _quality_indicator_bands_table:
.. csv-table:: Quality Indicator bands
   :file: csv/quality_indicator_bands.csv
   :delim: ;
   :widths: 30, 60, 10
   :header-rows: 1

|

The following figure shows a list of all quality_scene_classification classes

.. _sceneClassifMap:
.. figure:: images/ClassificationMap.png
   :name: ClassificationMapClassesName
   :scale: 100%
   :alt: Scene classification map classes
   :align: center

   Scene classification map classes


The following figure gives an example of an applied classification map:


.. _sceneClassifMapExample:
.. figure:: images/SceneClassificationMapExample.png
   :name: SceneClassificationMapExample
   :scale: 100%
   :alt: Scene classification map example
   :align: center

   Scene classification map example

.. _view_sun_geometry_bands:

View and sun geometry bands
===========================
The products additionally provide view and sun geometry information, if selected.

.. _view_and_sun_geometry_table:
.. csv-table:: View and sun geometry bands
   :file: csv/view_sun_geometry.csv
   :delim: ;
   :widths: 25, 45, 10
   :header-rows: 1

.. _validation_bands:

Validation bands
================
The products provide information on the validity of an observation (pixel), if selected.

.. _validation_bands_table:
.. csv-table:: Validation bands
   :file: csv/validation_bands.csv
   :delim: ;
   :widths: 10, 45, 10
   :header-rows: 1

.. _medoid_bands:

Medoid quality bands
====================
Finally, a quality measure for the Medoid compositing algorithm is included, if selected.

.. _medoid_bands_table:
.. csv-table:: Medoid quality bands
   :file: csv/medoid_quality_bands.csv
   :delim: ;
   :widths: 10, 45, 10
   :header-rows: 1

Resolution
**********
All Mosaic Hub raster products are provided in uniform resolution. Three different resolutions are available:

- 10m
- 20m
- 60m



Coordinate Reference Systems
****************************
The Mosaic Hub raster products are provided either projected in UTM(WGS84) or unprojected WGS84

UTM
====
Universal Transverse Mercator (UTM) conformal projection is not a single map projection.
The system instead divides the Earth into sixty zones, each being a six-degree band of longitude,
and uses a secant transverse Mercator projection in each zone. WGS84 is used as ellipsoid for UTM.

WGS84
=====
WGS84 is an Earth-centered, Earth-fixed terrestrial reference system and geodetic datum.
WGS84 is based on a consistent set of constants and model parameters that describe
the Earth's size, shape, and gravity and geomagnetic fields.

File Formats
************
The Mosaic Hub raster products are available in three different file formats:

- GeoTiff
- Jpeg2000
- NetCDF

GeoTiff / Jpeg2000
==================

General
-------

Naming Convention and File Structure
------------------------------------

Data Content
------------

GeoTiff / Jpeg2000 Data Files
+++++++++++++++++++++++++++++

Metadata
++++++++

NetCDF
======

General
-------

Naming Convention and File Structure
------------------------------------

Data Content
------------

NetCDf Data File
++++++++++++++++

Metadata
++++++++

INSPIRE
*******



Software
********

SNAP
====

ArcGIS
======

QGIS
====




Time Series
***********

File Format
===========
