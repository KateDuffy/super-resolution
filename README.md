# Super-resolution of satellite datasets

## Datasets:
- MODIS (in-progress)
- Himawari-8 (in-progress)
- GOES-16 (not started)

## How to run:

The procedure is as follow:

1. Download MODIS data using the included `download_modis.py` script. Right now the tiles
being used are `h23v03` to `h32v13`. The download should be in `.hdf` format.
1. Run `warp_modis.py` to warp MODIS to the `EPSG:3857` projection and store it in geoTIFF files.
1. Download the Himawari-8 data for the day(s) that you are compositing to MODIS.
(You're on your own for this one)
1. Run `process_himawari.py` to turn the binary files into usable geoTIFF files.
1. Run `warp_himawari.py` to warp the geoTIFF to `EPSG:3857`.
1. Run `himawari_to_modis.py` to composite the Himawari-8 data into a similar
dataset as MODIS.
1. Run `split_composite.py` to split the data into chunks for the network.
1. ???
1. **Deep learning!**