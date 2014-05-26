# Readme #

This readme provides a short description on c++ pointclouds alignment software and its dependencies installation

## Installation ##

On a fresh Ubuntu 12.04 (amd64) install PointCloud Library from the ppa

`sudo add-apt-repository ppa:v-launchpad-jochen-sprickerhof-de/pcl`

`sudo apt-get update`

`sudo apt-get install libpcl-1.6-all`

`cd path/to/software`

`make`

## Usage ##

You have to provide the directory with the .ply files as first argument and the true volume of the object (in square meters) as second:

`./kinect path/to/ply/dir 0.028800`

The .ply files must follow this name convention

`capture-mesh-N.ply` 

### Example ###

* ply/files/directory
    + capture-mesh-1.ply
    + capture-mesh-2.ply
    + capture-mesh-3.ply
    + capture-mesh-4.ply
    + capture-mesh-5.ply

where N increments for every view of the object

## Output ##

In the .ply files directory two files will be written:

* output-aligned-clouds.ply: will contain the aligned point clouds

* output-convex-hull.ply: will contain the convex hull points plus the mesh indices

