# Shaders and Lighting

[&olt; back](../../README.md)

Learn how to write a basic shader

## Scene overview

-   Create a few models and materials with various basic lighting effects
-   Note this will not touch on PBR, environment maps, reflections - it's a basic LIGHTING model, not IBL or PBR model

## Prerequisites

-   Modelling experience is very useful to understand textures, UV Maps, normals, vertices etc.

## Knowledge Gained

-   ShaderLab
-   Cg
-   Basic lighting techniques

## Expected time to complete

-   Beginner: 2 days
-   Expert: 1 hour

## Simple guide

1.  Import a model into the scene (or use the sphere)
2.  Create a new shader based on the unlit shader
3.  Add a material with this shader to your model and see it render
4.  Modify the shader to have an "Albedo" input
5.  Multiply the albedo by the texture result to make it a "tint" to the texture
6.  Add Lambert[1] shading to give it a diffuse look
7.  Add Phong[1] to give us a shiny look (include a shininess/roughness parameter)
8.  Convert to BlinnPhong[1] and try to get similar looking results to Phong (performance optimisation)
9.  Add a fresnel[2,3] effect to the model to approximate the phenomenon where light reflects more at shallow angles
10. Extend the shader to use a texture for shininess/roughness instead of a number
11. Add support for a normal  map, instead of relying on the mesh's normals

## Useful Resources to complete

* [1] Lighting models in Unity: <https://www.jordanstevenstechart.com/lighting-models> (don't just copy paste!)
* [2] Fresnel (in a surface shader) - <https://www.ronja-tutorials.com/2018/05/26/fresnel.html>
* [3] Fresnel again: <http://kylehalladay.com/blog/tutorial/2014/02/18/Fresnel-Shaders-From-The-Ground-Up.html>
* [4] John Carmack (iD Software) blowing your mind about lighting. Very good video. [Principles of Lighting and Rendering with John Carmack at QuakeCon 2013](https://www.youtube.com/watch?v=IyUgHPs86XM)
* [5] Steve's implementation of some or all of these: <https://github.com/xwipeoutx/unity-bits>

### Videos

[Principles of Lighting and Rendering with John Carmack at QuakeCon 2013](https://www.youtube.com/watch?v=FxvO0iWHtxQ)

[![Principles of Lighting and Rendering with John Carmack at QuakeCon 2013](https://img.youtube.com/vi/FxvO0iWHtxQ/0.jpg)](https://www.youtube.com/watch?v=FxvO0iWHtxQ)
