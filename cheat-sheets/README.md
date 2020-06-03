# Tool cheat cheet

[&olt; back](../README.md)

A bunch of lists and descriptions for good controls / libraries / etc. for XR development

## 3D map viewer

### Bing Maps SDK for Unity

HoloLens, VR

<https://github.com/Microsoft/MapsSDK-Unity/wiki/Getting-Started>

-   Good extensibility - terrain layers and elevation
-   Free license is wonderful for PoCs and dev - it's something like 500 app launches a month

### MapBox SDK for Unity

Any platform

<https://www.mapbox.com/unity/>

-   Reasonably good out-of-the-box experiences
-   Mapbox services can be consumed for custom data

-   (eg. add a custom tileset with building outlines of your client)
-   Supports automatic texture generation to make buildings look more like buildings

-   Open source
-   Unfortunately, the control itself is clearly for immersive scale or static view, not interactive room scale - so it's not too polished for the usual map use case on AR

## Shared anchor - image target

### ARFoundation - out of the box

iOS, Android

<https://docs.unity3d.com/Packages/com.unity.xr.arsubsystems@2.1/manual/image-tracking.html>

-   Very fast, stable and accurate across devices
-   Can add images at run time (often sub-frame speed)

### Vuforia

HoloLens

[https://developer.vuforia.com](https://developer.vuforia.com/pricing)

-   Vuforia is really bad and annoying. But sometimes the only option (until MS put decent image tracking on the HoloLens)

See: HALIA

### QR Code

HoloLens

<https://docs.microsoft.com/en-us/windows/mixed-reality/qr-code-tracking>\
See: None

## Shared Anchor, Wayfinding - No Markers,

### Azure Spatial Anchors

iOS, Android, HoloLens

<https://docs.microsoft.com/en-au/azure/spatial-anchors/> 

-   Uses point cloud and colours to correlate the location 
-   Even works well for anchoring labels to an object, if it's visually distinctive enough 

### Google Cloud Anchors

iOS, Android

<https://developers.google.com/ar/develop/java/cloud-anchors/overview-android> 

-   ARCore supporting ARKit means this is cross platform, even if google only 
-   Didn't seem as accurate as azure spatial anchors, but alternatives are good, right? 

### Just manually send the serialized anchors

HoloLens

<https://docs.unity3d.com/ScriptReference/XR.WSA.Sharing.WorldAnchorTransferBatch.html>

-   Serialize the anchors using this batch

## Multiplayer

### Photon

Any Platform

<https://doc.photonengine.com/en-us/pun/v2/demos-and-tutorials/pun-basics-tutorial/intro> 

-   There is a Photon Server option if cloud-hosting isn't suitable for your client
-   This stuff is way easier than you might expect.  Join a room, and sync variables or send RPCs. Worth trying out 
-   Photon Server is great for low connectivity or data sovereignity circumstances 
-   Licensing is wonderful for dev and pocs (free, basically) 
-   Supports voice as well (it's designed for games)

## Authentication (OAuth2 / AAD)

### IdentityModel.OidcClient2

Android / iOS

<https://github.com/peterhorsley/Unity3D.Authentication.Example>

-   Gotta understand the platform and native tools pretty well - e.g. uses activities for message passing between browser and app

### ADAL

HoloLens

-   Never done it
-   Documentation is scarce
-   Theoretically easy though
-   Best example - azure spatial anchor documentation. Strange.
-   TBD - confirm this stuff

## Share video and audio
---------------------

### Web RTC

Any Platform

<https://github.com/microsoft/MixedReality-WebRTC> 

-   Basic demo is easy to get going and works well
-   Anything real and you have to build or buy a signalling server - suddenly not easy!

Build Automation
----------------

### Unity Cloud

Any non-UWP platform

<https://unity3d.com/unity/features/cloud-build> 

-   Easy to set up
-   Fast
-   Integrates with source control for CI / CD
-   Can sign the outputs
-   Provides link to download (except iOS)

### VM in Azure

-   Yeaaah

## Real Time Data (e.g. IoT)

### Photon Server + Plugins

Any platform

<https://doc.photonengine.com/en-us/server/current/plugins/manual>

-   Nice to have a single deployable for sharing and data
-   It's .NET!
-   API is similar to client->client comms within Unity

### HTTP Polling

Any platform

### Web Sockets? SignalR?

Any platform

Up for grabs - I believe SignalR support works everywhere now, but I haven't tried it recently

## GIS Processing

### GDAL

-   Raster and vector tooling for GIS
-   <https://gdal.org>

### PDAL

-   Point cloud library
-   <https://pdal.io/pipeline.html>

### LASTools

-   More point cloud tools (beware of licensing)
-   Best thing is the lasview tool - fast view of lidar files
-   <https://www.cs.unc.edu/~isenburg/lastools/> 

### TURFjs

-   If you can get your GIS into GeoJSON format, this is a powerful spatial processing library
-   Example - you can convert GeoJSON points into a TIN or convex / concave hull, which you can then load into MapBox and visualise.  Handy for building layers!

-   Consider pairing with an exporter (<https://threejs.org/docs/#examples/en/exporters/GLTFExporter>) or extruder (<https://github.com/pissang/geometry-extrude>) for mesh processing

-   <https://turfjs.org/>

### Blender

-   If you need to manually tweak
-   <https://blender.org>

### QGIS

-   Free GIS viewer (everything but point clouds)
-   <https://qgis.org/>

### Some notes on all these:

-   GDAL and PDAL are both available as docker images 
-   Mostly scriptable end-to-end, maybe some final tweaking in Blender 
-   Pretty steep learning curve 
-   Eg. for buildings from LiDAR -  
-   PDAL: extract building points, cluster by distance, triangulate 
-   Blender: Decimate, extrude down to ground 
-   Unity: Import, add a clipping volume for the ground level 
-   It's GIS - so it's very complicated 

## Custom mesh processing (C#)

### geometry3sharp

<https://github.com/gradientspace/geometry3Sharp> 

Because sometimes you just need to automate some mesh operations (eg. decimation)

-   If you need to automate script stuff, this is a powerful and fast mesh library in a familiar language. 
-   But you gotta learn some mesh theory 

See: DNRME engagements

### Various node tools

Several tools are available in nodejs for this

-   <https://github.com/pissang/geometry-extrude> - extrude geometry (good for buildings)
-   <https://threejs.org/> - it's a 3d engine, sure, but it has mesh tools and reader/writers (eg. GLTF) as well

## Video and Audio

### WebRTC

All platforms

<https://github.com/microsoft/MixedReality-WebRTC>

-   It's in a usable state for PoCs right now (Dec 2019), but not for production
-   Specifically, the signaling server uses node-dss, which is very 1-to-1, so you can't have a team. Just a pair.

### Photon Audio

Yes, Photon does audio as well

## CI / CD

See [dedicated learning page](../learning-resources/topics/unity/cicd.md)