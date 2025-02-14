# programming_in_gis

These notebooks with require an installation of [ArcGIS Pro](https://apps.itpals.vt.edu/arcgis/ArcGIS_Pro_Installation_Instructions.pdf) and Anaconda with a class environment.

#### Anaconda installation instructions
* [Download and install the software](https://www.anaconda.com/products/individual).  It's free, and can install on Windows, Linux, and Mac.
* The default installation of Anaconda comes with numpy, Pandas, matplotlib, and many other useful packages.  However, it does not come with many geospatial packages.  
* Install instructions after opening an Anaconda command window (paste these three lines in, one-at-a-time).
~~~
conda create --name gis --file https://nearearthimaginglab.org/python/neil.20220730.txt
conda activate gis
pip install opencv-python 
pip install pypdf2==2 pyppeteer==0.2.2 
~~~
From here, you should be able to close the window, and use normally except that: when you open the Anaconda command window, in addition to changing directory to your working directory you'll need to type
~~~
conda activate gis
~~~ 
# Manual Install (for mac?)
~~~
conda create --name gis -c conda-forge python=3.10 spyder jupyter jupyterlab numpy pandas matplotlib
conda activate gis
pip install nbconvert[webpdf]
# To convert your first notebook using webpdf, you'll need to run on the python/gis environment commandline:
# jupyter nbconvert --to webpdf --allow-chromium-download path/to/any_notebook.ipynb
# After this, you can do it in the browser as normal.
~~~

# Key Packages and Software
* [Anaconda](https://www.anaconda.com/distribution) is an aggregation of many of the tools we use, including Python, Jupyter, Numpy/SciPy, etc.  It's worthwhile to learn to [use and manage environments](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html), which are sort of firewalled/separated installations so that dependencies don't clash.
* Pandas is best for column/vector/attribute/tabular manipulation.  [Vaex](https://www.kdnuggets.com/2021/05/vaex-pandas-1000x-faster.html) may be a newer, faster alternative?
* A number of visualization packages, including [matplotlib](https://matplotlib.org/3.1.0/#) and [seaborn](https://seaborn.pydata.org/).  We'd like to branch more into [Bokeh](https://bokeh.pydata.org/en/latest), [Datashader](https://datashader.org) [[more](https://anitagraser.com/2020/12/13/spatial-data-exploration-with-linked-plots/), [Holoviews](http://holoviews.org), and [Folium](https://python-visualization.github.io/folium).
* IDEs and IDE-like environments, including [Spyder](https://www.spyder-ide.org/), [Jupyter Notebooks](https://jupyter.org), and [JupyterLab](https://jupyterlab.readthedocs.io/en/stable)
## Key Scientific Packages
* From [SciPy](https://www.scipy.org): [ndimage](https://docs.scipy.org/doc/scipy/reference/ndimage.html) and [stats](https://docs.scipy.org/doc/scipy/reference/stats.html)
* [scikit-learn](https://scikit-learn.org/stable/) for statistical and machine learning applications
# Image Processing
* SciPy's [ndimage](https://docs.scipy.org/doc/scipy/reference/ndimage.html) package
* [OpenCV](https://github.com/thomaspingel/neil/wiki/OpenCV) for many image processing operations
* [scikit-image](https://scikit-image.org) for image processing operations
* [Pillow](https://pillow.readthedocs.io/en/stable) - a PIL fork, useful sometimes for image reading and writing.
* [tifffile](https://pypi.org/project/tifffile/) - A quick, handy utility for reading and writing large (or any) TIF file.
* For very large image processing, we'd like to use [xarray](http://xarray.pydata.org/en/stable) and [dask](http://xarray.pydata.org/en/stable/dask.html) more often.

## Geospatial
* [Rasterio](https://rasterio.readthedocs.io/en/stable/) provides a front-end for GDAL and various types of raster processing
* [Geopandas](http://geopandas.org) (and [Pandas](https://pandas.pydata.org)) for vector GIS operations and general Excel-like manipulation of data tables.
* [Neilpy](https://github.com/thomaspingel/neilpy) - a collection of tools (including SMRF) useful for lab-related point cloud and raster processing.
* [GDAL and GDALDEM](https://gdal.org/programs/gdaldem.html) for raster processing.
* [PDAL](https://pdal.io) for point cloud processing.
* [PySAL](https://pysal.org/) and [Tobler](https://pysal.org/tobler/)
* A number of supporting geospatial packages including [shapely](https://shapely.readthedocs.io/en/stable/manual.html), [pyproj](https://pyproj4.github.io/pyproj/stable), and [fiona](https://fiona.readthedocs.io/en/latest/manual.html)
* [PyKriging](https://pykriging.com/)
* [Colour](https://colour.readthedocs.io/en/latest/index.html#) for scientific color analysis
* [Open3D](http://www.open3d.org/) and [PyViz3D](https://github.com/francisengelmann/PyViz3D) for visualization of point clouds.
* [xarray](https://docs.xarray.dev/en/stable/) and [rioxarray](https://corteva.github.io/rioxarray/html/index.html) and [geocube](https://corteva.github.io/geocube/html/index.html)

## Mapping
* [geoplot](https://residentmario.github.io/geoplot/)
* [Python Maps](https://twitter.com/PythonMaps)
* [CARTOframes](https://carto.com/developers/cartoframes)
* [Contextily](https://contextily.readthedocs.io/en/latest/)
* [Cartopy](https://scitools.org.uk/cartopy/docs/latest) is a bit outdated
* [Basemap](https://basemaptutorial.readthedocs.io/en/latest) is super outdated

## Geodesy
* [Navpy](https://pypi.org/project/NavPy/)
* [Nvector](https://pypi.org/project/nvector/)

# Exporting Notebooks
     * For simple export, the GoFullPage screengrabbing extension for Chrome is pretty good.
     * The new [notebook-as-pdf](https://pypi.org/project/notebook-as-pdf/) package makes this much easier than before.  Install with "pip install notebook-to-pdf".  As of this writing, it is best to downgrade pypdf2 after that: "pip install pypdf2==2".  Then, Use File -> Download -> PDF via HTML.  You can also export notebooks to PDF via the commandline, and in batches.
~~~
jupyter-nbconvert --to PDFviaHTML *.ipynb
~~~
