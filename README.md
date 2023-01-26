<div align="center">
          
[![GitHub issues](https://img.shields.io/github/issues/uml-marine-robotics/MassMIND)](https://github.com/uml-marine-robotics/MassMIND/issues)
[![GitHub forks](https://img.shields.io/github/forks/uml-marine-robotics/MassMIND)](https://github.com/uml-marine-robotics/MassMIND/network)
![GitHub all releases](https://img.shields.io/github/downloads/uml-marine-robotics/MassMIND/total)

</div>

# **MassMIND: Massachusetts Maritime INfrared Dataset** [1](#references)

MassMIND is an exhaustive dataset of real-life Long Wave Infrared (LWIR) images geared towards development of deep learning algorthms specifially for the Maritime domain. The dataset consists of 2916 diverse LWIR images captured in and around the Boston Harbor in Massachusetts, USA over a span of 2 years. The images have been recorded in a busy marine area as well as in not so busy ocean waters during various seasons and times of the day creating seasonal and temporal diversity. Each image has been segmented with pixel level instance segmentation and labeled across 7 different classes. This is the first publicly available dataset for LWIR maritime images. 

## Dataset 
**LWIR Images:** 
| Category                                      | 
| :---:                                         | 
| [LWIR Images](https://drive.google.com/file/d/1T572f0oqy5JmuTvVEwkSUeXLWOSHl4hL/view?usp=sharing)|
| [LWIR Semantically segmented annotated masks]|(https://drive.google.com/file/d/1pHp480_Q-s72RoDf1nD7ERzsv9yZTDE1/view?usp=sharing)
| [LWIR Instance segmented annotated masks]|(https://drive.google.com/file/d/16rPWhV8OEocyLLpT1-LSCALt757P_h0N/view?usp=sharing)|



## Dataset Overview 

LWIR images are independent of visible light and depend on thermal radiation emitted from surfaces or heat. Some of the patterns described below especially those of extreme light conditions & horizon detection pose a challenge to the optical images. LWIR therefore help a lot in these situations as seen below. The first row is during the dark, while the 2nd one has a lot of glitter that presents problem to the optical image. The deep learning algorithms can be enhanced by training them against such LWIR images.  

**Comparison of Optical and LWIR**
          
|  | Optical  | LWIR   |
| :---:| :---:    | :---:  |
| Nighttime | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/Night-opt.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/night-ir.png" width = "150" > |
| Daytime | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/day-opt.png" width = "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/day-ir.png" width ="150" >|
          

### **Scene Coverage**
- [x] Night time images with little or no light 
- [x] Day time images 
- [x] Foggy or cloudy weather 
- [x] Rough waters 
- [x] Coastal clutter with humans, ships, buoys 
- [x] Images in the far seas with horizon
- [x] Construction commonly found in a urban setting 
- [x] Adequate coverage of obstacles in the water 

**Segmentation Samples** 

|  Category    | Image 1  | Image 2 | Image 3       |Image 4       |
| :---:| :---:    | :---:  | :---:  | :---: |
| LWIR Image | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1635452627_010979.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1571161484_881385.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1603391664_499289.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1571167609_333506.png" width= "150" > |
|Ground truth semantic segmentation| <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1635452627_010979_label_ground-truth_semantic_colored.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1571161484_881385_label_ground-truth_semantic_colored.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1603391664_499289_label_ground-truth_semantic_colored.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1571167609_333506_label_ground-truth_semantic_colored.png" width= "150" > |
|Ground truth instance segmentation| <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1635452627_010979_label_ground-truth_instance_colored.png" width= "150" > |<img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1571161484_881385_label_ground-truth_instance_colored.png" width= "150" > |<img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1603391664_499289_label_ground-truth_instance_colored.png" width= "150" > | <img src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/a1571167609_333506_label_ground-truth_instance_colored.png" width= "150" > |


### **Image size and volume**
All images and their labeled annotations are 640x512 (widthxheight) in the dataset. There are 2916 such images in the dataset. 

### **Diversity**
Intrinsically maritime scenes have a significant imbalance in their class distribution as sky and water occupy major portions of the scene. An effort has been made to reduce this imbalance so that sky and background do not undermine the obstacles and living obstacles in the water that are critical for training. We also focused on bridges as they are relevant for path navigation, and at the same time are part of the scene background. Since the images are instance segmented, multiple occurance of a class within an image is counted seperately (2 boats in an image will be counted as 2 separate instances), except for sky, water and self. These are always counted one per image. The distribution of instances across various classes has been depicted below. 

<p align="center">
<img width="400" height="250"  src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Piechart_class_instances.png" width ="100">
</p>
          
### **Class Definitions**

All images have been labeled using pixel wise instance segmention for the below classes. More on instance segmentation can be found at - 

| Class Name | Class ID | Labeling guidelines | 
| :---:      | :---:    | :---                |
| Sky        | 0        | Skies including birds, sun/moon, clouds, airplanes, trees or any other object in the sky.|
| Water      | 1        | Areas that contain water and associated ripples, waves, wakes, reflection in water, any miniscule objects that cannot be separated, such as leaves | 
| Bridge     | 2        | Bridges that are in water and pertinent to the navigation path. Includes foundation block, piers,arches that can obstruct navigation Portion of the bridge that is on land or construction on the deck / arches of the bridge will be considered background | 
| Obstacle   | 3        | Non Living entities that are in water and pertinent to the navigation path. Partially submerged or visible on the surface of water E.g. ships, buoys, wooden pillars, construction |
| Living Obstacle | 4   | Living entities in water. Partially submerged or visible on the surface of water. E.g. humans in kayaks or in sailboats, a swimmer, animals, birds on the water surface |
| Background |     5    | Entities outside of water, or adjacent to water. Land, walls, lights / people on bridges, buildings, roads, vehicles on road, bridges on land, construction on land that extends in water 
| Self       |     6    | This is the self return of our boat. This is typically seen on the lower right or left hand corner of the pictures.  The boat also has a hood that comes on the top left or right corner of the pictures. Both the hood and the boat will be marked as self | 

[1] Instance annotation is done for each image. E.g. if an image has multiple boats, each boat will have it's own instance id.  
[2] Sky is annotated as 1 instance per image.   
[3] Water is annotated as 1 instance per image.   
[4] Self is annotated as 1 instance per image. If an image has 2 self returns in an image, they have the same instance id.    

## Inferences
We evaluated the MassMIND dataset against 3 popular acchitectures and the table below depicts (Precision/Recall) some of the quantitative measures obtained. F1 score is really good for sky, water, background and self class as expected. Despite their tiny size, obstacles give a satisfactory recall. 

| Architecture | Class-Sky | Class-Water| Class-Bridge| Class-Ob| Class-living Ob| Class-Backgnd| Class-Self|
| :---:        | :---:     | :---:      | :---:       | :---    | :---:          | :---:        | :---:     |
| UNet         | 99.4/96.6 | 100/100 | 61.4/85 | 76.5/58.6 | 75.5/42.7 | 97.8/88 | 92.8/96.9 |
| DeepLabv3    | 99.8 / 97.6|100/100 | 72.9/89.5 |82.7/72.8 | 80.9/60.9 |99.2/92.4 |97.7/97.6 |
| PSPNet       | 99.6/98.4 |100/100 | 76.5/91.9 |82.9/73.6 |93.4/11.4 |98.8/95.3 |99.2/97.9 |




## Copyright
  
  
<img align="left" src="https://github.com/uml-marine-robotics/MassMIND/blob/main/Images/Copyright.png">
All datasets and benchmarks on this page are copyrighted by us and published under the Creative Commons Attribution-NonCommercial-ShareAlike 4.0 License. This means that you must attribute the work in the manner specified by the authors, you may not use this work for commercial purposes and if you alter, transform, or build upon this work, you may distribute the resulting work only under the same license.

## Cite
If you find this dataset useful, please cite our work as below: 
```
@misc{Nirgudkar_MassMIND_Massachusetts_Marine,
title = {{MassMIND: Massachusetts Marine INfrared Dataset}}
author = {Nirgudkar, Shailesh and DeFilippo, Michael and Sacarny, Michael and Benjamin, Michael and Robinette, Paul},
journal = {Under review} 
doi = { },
pages = { }
Issue = { } 

}
```
  
## References 
[1] Nirgudkar, Shailesh and DeFilippo, Michael and Sacarny, Michael and Benjamin, Michael and Robinette, Paul, MassMIND: Massachusetts Marine INfrared Dataset, Under review  
[2] Shailesh Nirgudkar and Paul Robinette, Beyond visible light: Object Detection Using Long Wave Infrared Images in Maritime Environment, 2021 20th International Conference on Advanced Robotics (ICAR), 2021, pp. 1093-1100, doi: 10.1109/ICAR53236.2021.9659477  
[3] MIT AUV Raw Dataset  https://seagrant.mit.edu/auvlab-datasets-marine-perception-1/  
[4] Image Segmentation platform: https://segments.ai

  
## Credits 
We are grateful to Brunswick® Corporation for their support. The views, opinions and/or findings expressed are those of the authors and should not be interpreted as representing the official views or policies of Brunswick® Corporation. We also thank the team at segments.ai for providing early access and for providing dashboard for tracking the progress of the labeling work.
