# Project Proposal

By [Lukasz Spiewla]

## Summary

To develop a flexible code for transforming raw spectral data into a rasterized, analyzable output suitable for software import and statistical analysis.

## Overview

Soil spectral data often contains various, dense, nuanced information concerning microbial, plant, and molecular interaction. This particular spectral dataset contains microscale XANES K-edge soil surface information across multi-channeled layering, creating a heatmap of elemental presence and fine-scale energy excitation graphs. In simpler terms, a dense mess of elemental data that requires transformation for transferable data usage. In developing a workflow to transform variable raw spectral datasets into exportable, multilayer-compatible data outputs, the data production pipeline becomes streamlined for incorporating future datasets. Downstream, understanding the microscale nuance of elemental speciation allows for greater accuracy in digital soil twin models and improved understanding of upscaled effects on elemental transitions in broader ecology and resource management needs.

## Software or Project Description

I seek to transform this raw spectral data into a layered-raster output suitable for software analysis. This data was collected through synchrotron accelerator hand-coded software which operates by a variable X-Y serpentine scanline pattern across subsets of the scanned samples. Additional datasets were collected for site-specific scans at greater resolution and more precise energy readouts. By developing a package that can transform both variable-limited datasets into exportable, rasterized outputs, my expectation is to flexibly adjust across individual scans at differing resolutions to minimize the need to make adjustments across larger datasets and have a strong basis for developing this data into a versatile base architecture for further datasets to build on for visual data modeling in software more capable than ImageJ.

## Project Goals and Timeline

The primary objective for this semester is to develop a flexible code package which can accurately translate a variable serpentine-scanline pattern as a formatted raster output which successfully preserves raw channel data. Additional objectives will seek to incorporate collected site-specific scans into the same or adjacent workflow. Longer term goals include the development of these outputs as a foundational baseline for a broader data model incorporating elemental and soil feature associations together. The over-arching objective for this data is the capability to utilize this scanned data for classification and prediction of subsurface chemical architecture. Ideally over a multi-year timeline, I would like to see these broader data sets unified into a microscale digital soil twin. 

- Phase 1 -
Developing framework code to intake, read, and organize the raw data from different data formats.

- Phase 2 -
Developing an algorithmic code to re-assemble a serpentine-patterned scan divided across 4 quadrants of a scanned sample.

- Phase 3 -
Normalizing the scanned energy readout to convert raw intensity data into chemical concentrations / oxidation state data arrays.

- Phase 4 -
Developing a custom, local spatial metadata to affix the array into a GeoTiff file as a multiband raster.

## Methods and Workflow

This workflow will seek to develop a python architecture for a lightweight data pipeline to transform raw synchrotron XANES spectral data into spatially reconstructed, multilayer raster products. The software must accommodate scan resolution variability, energy-channel configurations, and acquisition geometry while preserving the original spectral data. This particular XANES dataset was collected via serpentine scanline acquisition, so an algorithm to appropriately repackage this data will be a high priority.

Phase 1 will utilize h5py, NumPy, Pandas, struct, and xarray to parse scans, extract detector data, align spectral returns to their coordinates, and organize the raw data into a standardized multidimensional structure suitable for downstream processing.

Phase 2 will develop an algorithm-based tool to correct serpentine scanline acquisition patterns, reconstruct spatial coordinates, and merge the four sample quadrants into a single sample grid. Development will utilize GeoPandas, NumPy, and SciPy to support coordinate handling, interpolation, and spatial alignment while maintaining consistency with the original scan geometry.

Phase 3 will develop mathematical procedures to transform raw detector intensity measurements into usable variables through spectral processing and normalization methods using NumPy, SciPy, and xarray.

Phase 4 will convert reconstructed spatial and spectral datasets into multilayer raster outputs suitable for GIS and scientific analysis software. Rasterio and GDAL will be used to generate multiband GeoTIFF products, create custom spatial metadata, and preserve relevant info for downstream analysis and visualization.

Development will utilize Git for version control, handled through PyCharm IDE and Python 3.14 interpreter for dependency. Software development will produce subset modules to split logic segments into manageable script for individual-phase code testing and validation. Documentation will be produced to support reproduction and future development for this data pipeline.

## Anticipated Challenges

My greatest challenges will be in algorithm development. I do not have an extensive programming or mathematics background, so I expect I will need to lean on AI in order to resolve a varying input-dependent script. I have had issues with Github in the past, so it will be a slight hurdle in familiarizing myself with effective versioning. Ideally, I would like to have the biggest hurdles in this project cleared before I travel in November for additional data scans. My aggressive pacing ambitions might cause me some grief.

## Expected Outcomes

By the end of this semester, I would ideally like to have a functioning, scalable, hands-free program to transform raw XANES input folders into clean GeoTiff product ready for GIS import. If I can't have all three objectives met, then at least 2 out of 3 would be good, 1 out of 3 would be my low-bar. 
