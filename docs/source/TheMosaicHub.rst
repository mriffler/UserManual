.. _mosaic_hub:

##############
The Mosaic Hub
##############


.. note::
   The content will be provided by UK

The Mosaic Hub front-end is the main tool for S2GM users.
It allows for the specification of S2GM products in terms of the spatial extent as well as the compositing period and the format of the output products.
The front-end guides the user through the process of this product specification. A registration is required before requesting and downloading mosaics.


Registration
************
For the registration process, guide your browser to: https://services.sentinel-hub.com/oauth/subscription
After you have filled out the form (see :numref:`mosaicHubRegistration`), you will receive an e-mail to confirm your
mail address. Click on the verification button and you will receive the confirmation that your account has been created.

.. _mosaicHubRegistration:
.. figure:: MosaicHubRegistration.png
   :name: mosaicHubRegistrationName
   :scale: 50%
   :alt: Mosaic Hub Registration
   :align: center

   Mosaic Hub Registration



Mosaic Ordering
***************
This page describes the process of ordering  mosaics, from defining the conditions to the download of the processed product.
The ordering of Time Series are described below.

Mosaic Hub
==========

The Mosaic Hub is located here: https://webdev.sentinel-hub.com/mosaic-hub/#/

However, in order to download the processed products, you will have to install the "Mosaic Downloader" App.
In fact, this App has the same functionality like the browser instance. In order to not have to switch between browser and
Mosaic Downloader, it might be more convenient to work with the App from the beginning.


Mosaic Downloader
=================
In the Mosaic Hub, click on the drop-down menu item "Mosaic Downloader" like in :numref:`mosaicDownloaderMenu`.

.. _mosaicDownloaderMenu:
.. figure:: MosaicDownloaderMenu.png
   :name: mosaicDownloaderMenuName
   :scale: 50%
   :alt: Mosaic Downloader Menu Item
   :align: center

   Mosaic Downloader Menu Item

From there, you are able to download the App for your specific OS, or even launch the App from the browser menu.
When you launch the App, you will see a window like in :numref:`mosaicDownloaderAppBase`.

.. _mosaicDownloaderAppBase:
.. figure:: MosaicDownloaderAppBase.png
   :name: mosaicDownloaderAppBaseName
   :scale: 50%
   :alt: Mosaic Downloader App Window (Base view)
   :align: center

   Mosaic Downloader App Window (Base view)

.. _mosaicDownloaderAppS2:
.. figure:: MosaicDownloaderAppS2.png
   :name: mosaicDownloaderAppS2Name
   :scale: 50%
   :alt: Mosaic Downloader App Window (Sentinel view)
   :align: center

   Mosaic Downloader App Window (Sentinel view)

The menu of the App has menu buttons in the top; clicking on them brings up the following functionality:

+------------------------+------------------+
| Menu Button            |  Functionality   |
+========================+==================+
| Home                   | TBD              |
+------------------------+------------------+
| User Manual            | This document    |
+------------------------+------------------+
| User Area              | Status of Orders |
+------------------------+------------------+
| Mosaic Hub             | Configuration    |
|                        | of Mosaics       |
+------------------------+------------------+
| Time Series            | Configuration    |
|                        | of Time Series   |
+------------------------+------------------+
| Mosaic Downloader      | Configuration    |
|                        | and Execution    |
|                        | of Downloads     |
+------------------------+------------------+
| Resources              | TBD              |
+------------------------+------------------+
| About S2GM             | TBD              |
+------------------------+------------------+


The App Window is separated vertically with the dynamic map on the right and the temporal and spatial
configuration options on the left. Users can scroll and zoom into the map to focus on an area of interest.
There are different options to define the area for which the mosaic product will be generated:

* Drawing a rectangular on the map after selecting the corresponding icon in the menu on the upper right of the map.
* Drawing a polygon of arbitrary geometry after selecting the corresponding icon in the menu on the upper right of the map.
* Uploading a kml or kmz shape file. The upload button is located on the second tab in the area selection menu of the configuration menu.
* Selection of a pre-defined area, i.e. a country or a continent, in the dropdown menus of the configuration menu.



Area Selection
--------------


Compositing Periods
-------------------
The definition of the compositing period is done in the temporal period section of the configuration menu. There are five different compositing lengths to choose from: year, season, month, 10-day, day. For each of these compositing lengths, pre-defined periods can be selected by selecting the desired option in the corresponding tabs (see ).

.. _compositing10Days:
.. figure:: Compositing10Days.png
   :name: compositing10DaysName
   :scale: 50%
   :alt: Compositing Dialog (10 days)
   :align: center

   Compositing Dialog (10 days)

Once area of interest and compositing period have been selected, users must define further properties in the Order Panel dialogue.

Order Preparation
-----------------



Time Series
===========

Compositing Periods
-------------------

Pixel Selection
---------------

User Area
*********
