---
title: Unity Info Dump
draft: false
tags:
  - game-dev
date: 2026-10-03
unlisted: false
publish: true
---
This is a page of random Unity knowledge that may be useful in the future. There won't be much in-depth stuff here, this is mainly to push things I either don't want to make into a reusable script and/or the resourced links below should provide enough context to work with. In case they became outdated, I'll provide my own notes/explanations for them.

# 2D Sorting Orders
Sorting groups define the render order an object is given. This is useful for placing objects either in front or behind one another (Ex. Background objects in the back, player in the foreground). Typically, you can assign a [sorting layer](https://docs.unity3d.com/6000.6/Documentation/ScriptReference/SortingLayer.html) to sprites, and if the sorting layers are the same you can even define an int-based order in layer to manage how objects are ordered in the same layer. 

However, this poses a problem: Prefabs or GameObjects under the same sorting layer all render at different times, so this causes a weird mixing effect when layering objects over each other. To fix this, use [sorting groups](https://docs.unity3d.com/6000.6/Documentation/Manual/sprite/sorting-group/use-sorting-groups.html) on your parent object in order to treat the whole object itself as one whole layer.

Furthermore, you can dynamically change the sorting order based on distance. For 2D games, we can update the [Renderer 2D Data](https://docs.unity3d.com/Manual/2d-renderer-sorting.html) and set its **Transparency Sort Mode** to **Custom Axis**. By setting a vertical axis (0,1,0), you can have objects with a higher y-axis be behind those with a lower y-axis. This helps create a depth effect for 2D scenes.