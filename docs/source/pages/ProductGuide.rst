.. _prod_guide:

#############
Product Guide
#############

Data
****
All Mosaic Hub products provide 22 raster bands selectable by the user
during the order process (see section :ref:`Order Panel <orderPanel>`). Available
raster bands comprise:

- 11 surface reflectance bands
- 4 quality indicator bands
- 4 sun/view geometry bands
- 2 validation bands
- 1 quality band

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

.. _crs:

Coordinate Reference Systems (CRS)
**********************************
The Mosaic Hub raster products are provided either projected in UTM(WGS84) or unprojected WGS84

.. _utm:

UTM
===
Universal Transverse Mercator (UTM) conformal projection is not a single map projection.
The system instead divides the Earth into sixty zones, each being a six-degree band of longitude,
and uses a secant transverse Mercator projection in each zone. WGS84 is used as ellipsoid for UTM.

.. _wgs:

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

File format properties are described in the following chapter. Where needed a
distinction is made between the different formats.

File Structure
==============
File structures are mainly identical for GeoTiff,
Jpeg2000 and NetCDF. Therefore, no explizit chapters for the single formats
exist. Differences are indicated within the single chapter.

.. _folders:

Folders
-------
The Mosaic Hub products are organized in a folder structure. The product's structure
consists of a base folder, containing all data of one order, a sub/tile folder
containing one or multiple folders, holding single product or tiles if a tiling is needed.
Within these sub folders the actual data is stored.

Structure example for GeoTiff format:

.. [Base folder]
   [Sub/tile folder]
      raster.tif

..      ...

..      raster.tif

..      metadata.xml
   [Sub/tile folder]
      raster.tif

..      ...

..      raster.tif

..      metadata.xml

.. _fileStructExample:
.. figure:: images/FileStructure.png
   :name: FileStructureExample
   :scale: 75%
   :alt: File structure example
   :align: center

   File structure example example

.. _files:

Files
-----
Depending on the format the number of files varies.

GeoTiff/Jpeg2000:
    The product is delivered in 23 separate files. 22 GeoTiff/Jpeg2000 files
    contain the raster bands described in the :ref:`'General' <general>` section, and one JSON file containing

NetCDF:
    The product is delivered in 2 seperate files. One NetCDF file containing
    all raster bands

.. _tiling:

Tiling
------
The product is split into the area of original Sentinel-2 granules.
For a detailed description of the Sentinel-2 tiling scheme please
visit the `official website`__. A tiling of the products is only done
if :ref:`UTM <utm>` projection is chosen as :ref:`CRS <crs>` and the
chosen area exceeds a certain size.

 .. _s2_tiling: https://sentinel.esa.int/web/sentinel/missions/sentinel-2/data-products

__ s2_tiling_
|

.. _naming_conventions:

Naming conventions
==================
Naming conventions are mainly identical for GeoTiff,
Jpeg2000 and NetCDF. Therefore, no explicit chapters for the single formats
exist. Differences are indicated within the single chapter

The product name (folders & files) contains key information on its content. Product names
support easy identification of relevant files and support meaningful sorting.
The Mosaic Hub product names are constructed according to the following naming convention:

Base folder
-----------

S2GM_{TemporalIdentifierSpatialIdentifier}_{PeriodStart}_{PeriodEnd}_{OrderName}_[ConfIndicator] _v{Version}_[{uniqueID}].{FileExtension}

In short, and with the correct length indicated by placeholders:

S2GM_{TSS}_{SSSSSSSS}_{EEEEEEEE}_{AA...AA}_[CCC]_v{X.Y.Z}_[DDD}.{ext}

Two examples:
    S2GM_Q10_20171001_20171230_MyPersonalRequest_STD__v1.0.0_385.tiff
    S2GM_M60_20170401_20170430_SPAIN_STD__v1.0.0_420.netCDF

.. _base_folder_table:

.. csv-table:: Base folder naming convention
   :file: csv/base_folder_naming_convention.csv
   :delim: ;
   :widths: 10, 60, 30
   :header-rows: 1

|


Sub folder
----------

The sub folder naming differs for tiled and none-tiled products (see :ref:`tiling <tiling>`).

*Non-tiled products*: The sub-folder name is equal to your order name (see {AA...AA} in :ref:`base folder table <base_folder_table>`)

*Tiled products*: The sub folder names are equal to Sentinel-2 granule names (see :ref:`tiling <tiling>`)

Files
-----
The file naming differs for GeoTiff/Jpeg2000 and NetCDF due to the structuring of the files.

**GeoTiff/Jpeg2000:**

In GeoTiff and Jpeg2000 format all raster bands are stored in separate files (see :ref:`Files <files>`)

{RasterBandIdentifier}_{TemporalIdentifierSpatialIdentifier}_{PeriodStart}_{OrderName}.{FileExtension}

In short, and with the correct length  indicated by placeholders (if not variable; variability indicated by ...):

{BB...BB}_{TSS}_{SSSSSSSS}_{AA...AA}.{ext}

*Example: B04_M60_20170701_Northern_Germany.jp2*

|


.. _file_naming_tif_jpg_table:

.. csv-table:: File naming convention GeoTiff/Jpeg200
   :file: csv/file_naming_convention_tif_jpg.csv
   :delim: ;
   :widths: 9, 32, 59
   :header-rows: 1

|

**NetCDF**

In NetCDF format all raster bands are stored in a single NetCDF (.nc) file (see :ref:`Files <files>`)

{TemporalIdentifierSpatialIdentifier}_{PeriodStart}_{OrderName}.{FileExtension}

In short, and with the correct length  indicated by placeholders (if not variable; variability indicated by ...):

{TSS}_{SSSSSSSS}_{AA...AA}.{ext}

*Example:*
    *M60_20170701_Northern_Germany.nc*

    *metadata_20170701_Northern_Germany.json*

|


.. _file_naming_netcdf_table:

.. csv-table:: File naming convention NetCDF
   :file: csv/file_naming_convention_netcdf.csv
   :delim: ;
   :widths: 9, 32, 59
   :header-rows: 1

The metadata file is prefixed with 'metadata/_'

Metadata
============

GeoTiff / Jpeg2000
------------------
json + xml

NetCDF
------
NetCDF internal + xml

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
