# Opening WRF files in xarray
#til/python/xarray

I work with the MarsWRF general circulation model, which is part of the [planetWRF](http://planetwrf.com) climate model family.  This model is based on the [NCAR Weather Research and Forecasting Model](https://www.mmm.ucar.edu/weather-research-and-forecasting-model). The model results are output in the [NetCDF](https://www.unidata.ucar.edu/software/netcdf/) format. To read the files, I use the [xarray](http://xarray.pydata.org/en/stable/index.html) Python module. However, there’s a trick to simultaneoulsy reading multiple NetCDF files produced by MarsWRF.

Generally, to read multiple NetCDF files into one array using `xarray`, one just uses the command `xarray.open_mfdataset`. However, the MarsWRF output requires a few flags to get the concatenation correct. Here’s a minimal example:
```python
import xarray as xr

array_variable = xr.open_mfdataset('/path/to/output/file/wrfout_*', concat_dim='Time', combine='nested')
```
The `concat_dim=‘Time’` and `combine=‘nested'` are required so that `xarray` can properly concatenate the files together into a single variable.