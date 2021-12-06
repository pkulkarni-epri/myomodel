# MYOModel Toolbox Data Preparation
Version 1.0

*Note: The MYOModel Toolbox requires an ArcGIS Pro license with the 3D Analyst Extension*

## Preparing Lidar / Photogrammetry Data
Lidar and photogrammetry point cloud data must meet some requirements and undergo some pre-processing steps prior to use with the MYOModel Toolbox

### Requirements
- The file format must be LAS
- The point cloud must be in a projected coordinate system in meters, for example "NAD 1983 / UTM Zone 12N (Meters)"
- The point cloud must be sufficiently dense to represent the targets of interest and potential obstructions of concern for the targeted structure
- The point cloud should contain as few unnecessary points (e.g., ground, areas outside the UAS flight area) as possible to reduce processing time

### Pre-processing
In ArcGIS Pro an LAS file can be pre-processed and made to meet the requirements for the MYOModel Toolbox. 
1. If the LAS file is *not* in a projected coordinate system, it can be projected using the Extract LAS (3D Analyst) tool.
2. Extract LAS (3D Analyst) tool can be used to reduce the area covered by the point cloud to just the structure and likely flight paths of the UAS
3. Thin LAS (3D Analyst) tool should be used to reduce the point density substantially for the 'ground' class

## Preparing Targets Data
Like the point cloud data, the targets that are created on a structure must meet some specific requirements, but otherwise do *not* require pre-processing.

### Requirements
- Targets must be created in a PointZ shapefile. This is easiest to do in an ArcGIS Scene Map
- The 'targets' shapefile must be in the same projected coordinate system as the point cloud data
- Target points should be created near the feature of interest on a structure but should not be inside the points in the feature's point cloud or they will be obstructed
- A feature of interest that must be viewed from 360 degrees or from multiple angles will need more than 1 target point to cover the various sides that need to be imaged
- The 'targets' shapefile must contain the following attributes (columns):
    - azmin : the minimum acceptable view azimuth relative to North (0 degrees). The value is an angle, for example azmin = 5 means that any view from less than 5-degrees from North is unacceptable.
    - azmax : the maximum acceptable view azimuth relative to North (0 degrees). The value is an angle, for example azmax = 35 means that any view from greater than 35-degrees from North is unacceptable.
    - pmin : the minimum acceptable view pitch relative to straight-forward (0 degrees). The value is an angle, for example pmin = -55 means that camera pitch angles closer to 0 are unacceptable.
    - pmax : the maximum acceptable view pitch relative to straight-forward (0 degrees). The value is an angle, for example pmax = -65 means that camera pitch angles smaller than -65 (e.g. -70) are unacceptable.
    - gsd : the coarsest allowable ground sample distance for images of the target in meters. For example, a gsd = 0.01 means that images that would be larger than 1 cm per pixel (e.g. 0.03) would be unacceptable, while those finer than 1 cm per pixel (e.g. 0.005) would be acceptable.
    - ViewID : a unique integer value that represents the target's view identifier.

