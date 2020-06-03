# First AR Project

[&olt; back](../../README.md)

Use an AR framework to spatially place a cube and interact with it

> **Note**: You may be better served by https://github.com/xwipeoutx/ar-grad-workshop

## Scene overview

Spatially anchor the previous scene:

-   Create a cube

## Prerequisites

-   "UI, Events and Such" script

## Knowledge Gained

-   ARCore/Kit/Foundation
-   Image targets

## Expected time to complete

-   Beginner: 2-3 days
-   Expert: 2-4 hours

## Simple guide

1.  Add ARCore/ARKit/ARFoundation (choose your poison) to the existing project
2.  Use the AR Library to link the camera to the device and pass-thru the camera background
3.  Enable the "point cloud" visualisation, so you can prove your room scanning is working
4.  Use the AR framework's ray casting to place the cube
5.  Add an anchor[4] to ensure it stays in place
6.  Create an image target and have a sphere stick to it
7.  Make cube creations animate from the image-target centered cube to the manually placed location [3]

## Useful Resources to complete

* [1] <https://www.youtube.com/watch?v=ml9qVRdEH4k> - AR Foundation Overview
* [2] <https://www.youtube.com/watch?v=Ml2UakwRxjk> - A useful basic project settings and game objects with AR Kit tutorial
* [3] <https://docs.unity3d.com/ScriptReference/Animator.html>
* [4] <https://developers.google.com/ar/develop/developer-guides/anchors>