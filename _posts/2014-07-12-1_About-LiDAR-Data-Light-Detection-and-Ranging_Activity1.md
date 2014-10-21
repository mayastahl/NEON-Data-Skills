---
layout: post
title:  "LiDAR Data Basics"
date:   2014-07-11 20:49:52
categories: [LiDAR Links]
tags : [measuring vegetation,remote sensing, laser scanning]
description: "Learn the basics of how a LiDAR works and what a LiDAR system measures. Explore some LiDAR data using free online tools."

---


## Overview ##

LiDAR or **Li**ght **D**etection **a**nd **R**anging is an active remote sensing system that can be used to measure vegetation height across wide areas. This page will introduce you to the fundamental concepts needed to understand:

1. What LiDAR data are 
2. The key attributes of LiDAR data
3. How LiDAR data are used to measure trees. 


{% include _images.html url="https://farm4.staticflickr.com/3913/14532371197_a17d52e010.jpg" description="LiDAR data collected at the Soaproot Saddle site by the National Ecological Observatory Network Airborne Observation Platform (NEON AOP) - available on https://www.flickr.com/photos/126239263@N04/sets" %}


#Some Background on LiDAR


##The Story of LiDAR Data video - On YouTube
<iframe width="560" height="315" src="//www.youtube.com/embed/m7SXoFv6Sdc?rel=0" frameborder="0" allowfullscreen></iframe>

##How LiDAR Works ##
<iframe width="560" height="315" src="//www.youtube.com/embed/RR1QFE-mB0k?rel=0" frameborder="0" allowfullscreen></iframe>


## Let's Get Started - Key Concepts to Review ##

### Why LiDAR ###

As ecologists, we often want to characterize vegetation over large regions. Because we don’t have the resources to measure each and every tree - we use tools that can estimate key characteristics over large areas. These tools often use remote methods - that is to say, we aren’t actually physically measuring things with our hands and eyes, we are using sensors which capture information about a landscape and record things that we can use to estimate conditions and characteristics.


{% include _images.html url="/minimal-mistakes/images/ScalingTrees_NatGeo.jpg" description="Conventional on the ground methods to measure trees are resource intensive and limit the amount of vegetation that can be characterized! Photo: National Geographic" %}

To measure vegetation across large areas we need remote sensing methods that can take many measurements, quickly using automated sensors. These measurements can  be used to estimate forest structure across larger areas. LiDAR, or light detection ranging (sometimes also referred to as active laser scanning) is one remote sensing method that can be used to map vegetation height, density and other characteristics across a region.

### How Scientists Use LiDAR Data ##
There are many different uses for LiDAR data. 


- LiDAR data classically have been used to derive high resolution elevation data <image: low vs high resolution DEM>
- LiDAR data have also been used to derive information about vegetation structure including
	- Canopy Height
	- Canopy Cover 
	- Leaf Area Index
	- Vertical Forest Structure
	- Species identification (in less dense forests with high point density LiDAR)

{% include _images.html url="//farm4.staticflickr.com/3883/14718736222_190e498006.jpg" width="500" height="354" description="LiDAR data have historically been used to generate high resolution elevation datasets." %}

{% include _images.html url="//farm6.staticflickr.com/5584/14696841986_586d180bee.jpg" width="500" height="354" description="Cross section showing LiDAR data and an example profile of a landscape." %}


### How A LiDAR System Works (video review) ##

LIDAR is an **active remote sensing** system. An active system means that the system itself generates energy - in this case light - to measure things on the ground. In a LiDAR system, light is emitted from a rapidly firing laser. You can imagine, light quickly strobing from a laser light source. This light travels to the ground and reflects off of things like buildings and tree branches. The reflected light energy then returns to the LiDAR sensor where it is recorded.

**Plane Flying Animation will go here**
 

Now remember from the video that the LiDAR system times the travel of the light to the ground and back and that time is used to in turn calculate distance traveled. Distance traveled is then converted to elevation. Also remember that a LiDAR system contains a GPS and an IMU that help it accurately identify the location of reflected light energy, on the ground.

<iframe width="960" height="720" src="//www.youtube.com/embed/OPgsL79eoBE?rel=0&vq=hd720" frameborder="0" allowfullscreen></iframe>


##The Distribution of Reflected Light Energy in terms of Photons

Light energy is a collection of photons. As photons that make up light moves towards the ground, they hit objects such as branches on a tree. Some of the light reflects off of those objects and returns to the sensor. If the object is small, and there are gaps surrounding it that allow light to pass through, some light continues down towards the ground. Because some photons reflect off of things like branches but others continue down towards the ground, multiple reflections may be recorded from one pulse of light. 

The distribution of energy that returns to the sensor creates what we call a waveform. The amount of energy that returned to the LiDAR sensor is known as "intensity". The areas where more photons or more light energy returns to the sensor create peaks in the distribution of energy. Theses peaks in the waveform often represent objects on the ground like - a branch, a group of leaves or a building. 

{% include _images.html url="/minimal-mistakes/images/Waveform.PNG" description="An example LiDAR waveform. Image: National Ecological Observatory Network, Boulder, CO" %}


### Discrete vs Full Waveform LiDAR ###
LiDAR data may be recorded in two ways.


1. A **Discrete Return LiDAR System** records individual (discrete) points for the peaks in the waveform curve. Discrete return LiDAR systems, identify peaks and record a point at each peak location in the waveform curve. These discrete or individual points are called returns. A discrete system may record 1-4 (and sometimes more) returns from each laser pulse.
2. A **Full Waveform LiDAR System** records a distribution of returned light energy. Full waveform LiDAR data are thus more complex to process however they can often capture more information compared to discrete return LiDAR systems.

##LiDAR File Formats **
Whether it is collected as discrete points or full waveform, most often LiDAR data are available as discrete points. A collection of discrete return LiDAR points is known as a LiDAR point cloud.

The commonly used file format to store LIDAR point cloud data is called .las which is a format supported by the Americal Society of Photogrametry and Remote sensing (ASPRS). Recently, the [.laz](http://www.laszip.org/) format has been  developed by Martin isenberg of LasTools. Laz is a highly compressed version of .las.


### Exploring 3D LIDAR data in a free Online Viewer
You can LiDAR data in the [plas.io website](plas.io)   develped by Martin Isenberg of Las Tools and his colleagues.


##Summary
*	A LiDAR system uses a laser + a gps and IMU to estimate the heights of objects on the ground.
*	Discrete LiDAR data is generated from waveforms - and each point represent peak energy points along the returned energy.
*	Discrete LiDAR points contain an x, y and z value. the z value is what is used to generate height.
*	LiDAR data can be used to estimate tree height and even canopy cover using various methods.


----------
----------



###Additional Resources:
*	What is the  [las file format](http://www.asprs.org/Committee "las file format: ")-*
*	General/LASer-LAS-File-Format-Exchange-Activities.html
*	What is Discrete Return lidar (ppt)
*	What is full waveform LiDAR (ppt)
*	[las: python ingest](http://laspy.readthedocs.org/en/latest/tut_background.html)
*	[las v1.3 specs](http://www.asprs.org/a/society/committees/standards/asprs_las_spec_v13.pdf)



## Check out our gallery on Flikr! ##




#THE END 
