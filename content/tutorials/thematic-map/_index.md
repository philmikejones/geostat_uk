+++
title = "Thematic maps"
date =  2018-01-13
weight = 20
draft = true
+++


## Purpose

Perhaps the most common function of GIS software, particularly in the social sciences, is to produce thematic or choropleth maps.


## Getting started

{{% notice info %}}
We recommend [QGIS](https://www.qgis.org/en/site/) for most GIS tasks, especially for beginners. You should download and install this before continuing.
{{% /notice %}}


## Overview

Creating a thematic map usually involves the following steps:

1. Obtain and load the outline of the geographical area of interest. See our [boundary files](../../boundary-files) for suitable files.
1. Obtain and load data about the areas about a topic of interest.
1. ‘Join’ these data sets using a unique key in both files.
1. Set the shading of the map based on the joined dataset.

This is easily achieved in QGIS.


## Obtain and load boundary files

I use shapefiles as these appear to be the de facto standard among GIS applications. Load a shapefile with SHIFT+CTRL+V or by clicking the ‘Add Vector Layer’ icon (bottom left of this screenshot, looks like a ‘V’):
QGIS: Add Vector Layer

QGIS: Add Vector Layer (bottom left icon)


## Obtain and load theme data

To add data about the geography you’ve loaded – and join it to the shapefile – click ‘Add Delimited Text Layer’ (icon looks like a comma). I’m assuming here you’re using a text delimited file (probably comma delimited, like .csv) because this is the most common format data is shared in, or at least can be easily converted to. Other data formats are supported, but for now lets load a .csv:
QGIS: Add csv layer

QGIS: Add CSV Layer

You should get the following dialogue box:
Load CSV file

QGIS: Load CSV File

The main thing to remember when loading a .csv file is to tell QGIS if your file contains geometry data or not. Most of the time when I download .csv files relating to a geography (like LSOA) it contains the LSOA code for referencing, but the file doesn’t include any geometry data per se. I would therefore select ‘No geometry (attribute only table)’ from the dialogue box.


## ‘Joining’ the boundary and theme data

Once the data is loaded, it’s time to ‘join’ it to the shapefile or other layer we loaded earlier. Right-click on the layer and press ‘Properties’:
Performing a join in QGIS

QGIS: Joining a csv file to a layer

From there, select Joins, then the green plus:
Joining in QGIS

QGIS: Joins dialogue

Select your csv file (‘Join layer’), the unique code you’re using to join, which is probably an LSOA code or similar (‘Join field’), and the target field in your vector layer. Like a key in a relational database, the codes for the join field and target layer must match exactly, or QGIS won’t know which area’s which!


## Plotting and styling

Once the join is completed you can create a thematic map by modifying the ‘Style’ tab of the layer properties. I typically change ‘Single Symbol’ to ‘Graduated’ and selecting an appropriate colour gradient:
Producing a thematic map

QGIS: Applying styles to layer

The finished result should look something like this. If you want to reproduce this map you can obtain the Townsend Scores and shapefile map layer.
Sheffield thematic map (Townsend Deprivation Scores depicted)

Sheffield Townsend Deprivation Scores 2011 – darker areas are more deprived
Sources

The csv data is based on my analysis of the 2011 Census. The boundary files was obtained from the UK Data Service:

Office for National Statistics, 2011 Census: Aggregate data (England and Wales) [computer file]. UK Data Service Census Support. Downloaded from: http://infuse.mimas.ac.uk. This information is licensed under the terms of the Open Government Licence [http://www.nationalarchives.gov.uk/doc/open-government-licence/version/2].

Office for National Statistics, 2011 Census: Digitised Boundary files (England and Wales) [computer file]. UK Data Service Census Support. Downloaded from: http://edina.ac.uk/census
