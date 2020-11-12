---
layout: page
title: Blendemoji
genre: An interactive Plugin
permalink: /blendemoji/
---

### Project Overview

2020.09 - 2020.11

This is a research project advised by Professor Brian A. Barsky at University of California, Berkeley

Tools: Blender, Python, OpenCV

<div class="w3-container w3-center">
  	<img src="/img/blendemoji.gif" alt="1" class="center" width="500"/>
</div>

<p style="text-align:center">Blendemoji, used on Vincent, an Opensource Blender Model available on Blender Cloud</p>

Blendemoji is a Python scripted plugin for Blender which reads the user’s facial expression through Webcam and simulates it on a 3d rigged model.

### Technical Overview

we are essentially extracting data from the user's face input, and we then interpret the data and apply it onto our model.

#### Haar Cascade

Haar Cascade is a machine learning object detection algorithm used to identify objects in an image or video and based on the concept of features proposed by Paul Viola and Michael Jones in their paper "Rapid Object Detection using a Boosted Cascade of Simple Features" in 2001.

<div class="w3-container w3-center">
  	<img src="/img/haarcascade.png" alt="1" class="center" width="500"/>
</div>

And if we look at the picture on the right. Top row shows two good features. The first feature selected seems to focus on the property that the region of the eyes is often darker than the region of the nose and cheeks. The second feature selected relies on the property that the eyes are darker than the bridge of the nose. 

####