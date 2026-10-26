# Annual kRSEI and four ecological components for China, 2001–2025

Processed annual rasters used as the ecological outcome inputs for the study of
China's Shan-Shui Initiative. This deposit contains **125 single-band GeoTIFFs**:
25 years each of kRSEI, kNDVI, WET, NDBSI and daytime LST.

## Download

Download the ZIP assets from the [version v1.0.0 release](https://github.com/NOOB304/shanshui-ecological-quality-data/releases/tag/v1.0.0).
The GitHub repository's automatic **Source code** ZIP contains metadata, not the raster assets.

| Variable | Years | Raster count | Download |
|---|---|---:|---|
| kRSEI | 2001–2025 | 25 | [kRSEI GeoTIFFs](https://github.com/NOOB304/shanshui-ecological-quality-data/releases/download/v1.0.0/China_kRSEI_2001-2025.zip) |
| kNDVI | 2001–2025 | 25 | [kNDVI GeoTIFFs](https://github.com/NOOB304/shanshui-ecological-quality-data/releases/download/v1.0.0/China_kNDVI_2001-2025.zip) |
| WET | 2001–2025 | 25 | [WET GeoTIFFs](https://github.com/NOOB304/shanshui-ecological-quality-data/releases/download/v1.0.0/China_WET_2001-2025.zip) |
| NDBSI | 2001–2025 | 25 | [NDBSI GeoTIFFs](https://github.com/NOOB304/shanshui-ecological-quality-data/releases/download/v1.0.0/China_NDBSI_2001-2025.zip) |
| LST | 2001–2025 | 25 | [LST GeoTIFFs](https://github.com/NOOB304/shanshui-ecological-quality-data/releases/download/v1.0.0/China_LST_2001-2025.zip) |

## File format and spatial grid

- GeoTIFF, one Float32 band per file; internally ZSTD-compressed.
- CRS: WGS 84 / EPSG:4326.
- Cell size: 0.008333333333333333 degrees (30 arc-seconds), the study's nominal 1-km grid.
- Dimensions: 7,392 columns × 5,969 rows.
- Bounds (west, south, east, north): 73.49166666666666, 3.8249999999999997, 135.09166666666667, 53.56666666666666.
- NoData: -9999. Source missing cells are retained in these main analysis-input files.
- Filenames: `VARIABLE/China_VARIABLE_YEAR.tif`.
- Temporal coverage: 2001–2025, with one June–August composite per year, not a full-year average.
- kRSEI, kNDVI, WET and NDBSI are dimensionless; LST is in degrees Celsius.
- GIS software must support GeoTIFF ZSTD compression (for example, recent GDAL/QGIS or Rasterio).

## Processing and provenance

kNDVI, WET and NDBSI were derived from MODIS MCD43A4 Version 6.1 reflectance;
daytime LST was derived from MODIS MOD11A2 Version 6.1. The processing used
June–August composites and the common study grid. kRSEI was calculated with
full-period standardization, a single PCA, ecological-direction correction of PC1,
and a common full-period min–max transformation. Numerical PCA parameters are
provided in `metadata/global_pca_parameters.json`.

The released GeoTIFFs are byte-for-byte copies of the five annual outcome-input
series used in the manuscript analysis. Packaging does not recalculate, fill,
resample or otherwise change their pixel values. Separately generated trend maps,
DID effect maps, CATE predictions, and temporally gap-filled map derivatives are
different products and are not substitutes for these five input series.

Public source-product records:

- [MODIS MCD43A4 Version 6.1](https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MCD43A4)
- [MODIS MOD11A2 Version 6.1](https://developers.google.com/earth-engine/datasets/catalog/MODIS_061_MOD11A2)

Sources and access links for other public input datasets are specified in the main
text of the associated study; those third-party datasets are not redistributed here.

## Metadata and integrity

- `file_manifest.csv`: variable, year, archive, byte size and SHA-256 of all 125 GeoTIFFs.
- `data_dictionary.csv`: variable names, definitions and units.
- `metadata/grid.json`: spatial reference, shape, transform and NoData.
- `metadata/global_pca_parameters.json`: numerical global standardization/PCA parameters.
- `SHA256SUMS.txt`: SHA-256 for the five downloadable archives.
- Each archive also includes SHA-256 checksums for its 25 GeoTIFFs.

## License and citation

Data are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
Cite this versioned repository release and the associated article when available;
retain the MODIS source-product citations. See `CITATION.cff` and `LICENSE`.

Version: 1.0.0. Release date: 2026-10-26. Maintainer: [NOOB304](https://github.com/NOOB304).
This release currently has a GitHub version URL; no DOI has been assigned.
