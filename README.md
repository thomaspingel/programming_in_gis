# programming_in_gis

These notebooks with require an installation of [ArcGIS Pro](https://apps.itpals.vt.edu/arcgis/ArcGIS_Pro_Installation_Instructions.pdf) and Anaconda with a class environment.

#### Anaconda installation instructions
* [Download and install the software](https://www.anaconda.com/products/individual).  It's free, and can install on Windows, Linux, and Mac.
* The default installation of Anaconda comes with numpy, Pandas, matplotlib, and many other useful packages.  However, it does not come with many geospatial packages.  
* Install instructions after opening an Anaconda command window (paste these three lines in, one-at-a-time).
~~~
conda create --name programming_in_gis -c conda-forge python=3.9 spyder jupyterlab numpy pandas matplotlib
~~~
From here, you should be able to close the window, and use normally except that: when you open the Anaconda command window, in addition to changing directory to your working directory you'll need to type
~~~
conda programming_in_gis
~~~ 
