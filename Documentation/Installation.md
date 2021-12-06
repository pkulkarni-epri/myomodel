# MYOModel Toolbox Installation
Version 1.0

## Prerequisites
The MYOModel Toolbox installation has a couple prerequisites. The following is a list of prerequisites:
1. ArcGIS Pro 2.7 (or newer) with 3D Analyst license, and all patches and updates installed.
2. A PC with >= 16 GB RAM
3. Administrative account access on Windows (needed only during installation of the ArcGIS Pro Python Environment)

## Setting Up the ArcGIS Pro Python Environment
This is arguably the most complex part of the MYOModel Toolbox Installation. MYOModel makes use of a couple Python modules that are not included in the default ArcGIS Pro Python environment. This means the default environment must be cloned, the cloned environment activated, and finally the required modules installed.

### Cloning and Activating the ArcGIS Pro Python Environment
1. Follow the guide from ESRI here: [ESRI: Work with Python Environments] (https://pro.arcgis.com/en/pro-app/latest/arcpy/get-started/work-with-python-environments.htm)
2. From the guide, "Create an environment" will show you how to create the new cloned environment. **Note: record the new environment name somewhere for later**
3. From the guide, "Activate an environment" will show you how to activate the newly created environment. 

Additional note: The newly activated environment should be available by default as already active for any new ArcGIS Pro Projects; if you wish to revert to the original, default environment you must activate that environment using the same process as above for activating an environment.

### Installing Python Modules
This section explains how to install the required Python modules. It is important to follow these steps in order.
1. Open the ArcGIS Pro "Python Command Prompt" from the Windows Start Menu.
2. The currently active Python environment should be listed in parentheses at the beginning of the prompt, for example (arcgispro-py3-clone)
3. If the currently active environment is not the new one you created, activate it by entering the below command in the prompt and pressing the 'enter' kay
    - activate clone | where "clone" is the name of your newly cloned environment
4. Next, install the needed python modules with the following commands, in order:
    - conda install -c conda-forge fiona=1.8.20
    - conda install geopandas=0.6.1
    - conda install laspy=1.7.0
5. If the above succeeded, you can close the Python Command Prompt

**A note about the above packages**

*Fiona* is a spatial data management library for Python and is required by many Python modules including geopandas. The version specification is to ensure that the installed version of fiona is compatible with Arcgis Pro 2.7 or newer.

*Geopandas* is a spatial data capable extension of pandas, and is used for the analysis of spatial data frames.

*Laspy* is an LAS point cloud tool useful for reading/loading point clouds into data frames and arrays.

## Installing the MYOModel Toolbox
The MYOModel Toolbox is an ArcGIS Pro Python Toolbox. This means that it can be used in ArcGIS Pro similarly to any Geoprocessing Tool / Toolbox. Installation is simple.
1. Copy the "MYOModel Toolbox.pyt" file from the GitHub repository to any sensible place on your local hard drive.
2. In an ArcGIS Pro Project, using the Catalog, navigate to where you have saved the "MYOModel Toolbox.pyt" file. It will appear as a Toolbox.
3. Expanding the MYOModel Toolbox will show the available tools ("Run MYOModel" and "Use Waypoints on Similar Structure")