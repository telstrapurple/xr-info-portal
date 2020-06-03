# MonoBehaviour and GameObject basics

[&olt; back](../../README.md)

After this, you should have a simple 3d app that spawns objects, destroys objects and runs scripts on those

## Scene overview

Create a scene that deals with dynamic object lifecycles:

-   Create a "spawner" object - say, a gun firing bullets, a tap dripping water, or a beehive spawning bees
-   At a regular time interval, spawn the objects and have them move somewhere
-   At some point, destroy the objects (either via a collider, or a timer or whatever)
-   Rinse and repeat
-   Extra points: have the destruction occur based on user input (eg. spraying the bees)

## Prerequisites

-   Really, this is Unity 101

## Knowledge Gained


-   Prefabs
-   Scripting (components)
-   Creating and destroying components

## Expected time to complete

-   Beginner: 4 hours
-   Expert: 30 mins

## Simple guide

This guide will use a simple dripping tap approach

1.  Create an empty scene
2.  Create a game object with a small sphere in it.  This will be the water droplet - call it "water droplet".
3.  Drag the sphere to the project window to make a "prefab" out of it, then delete the water droplet
4.  Make another game object with a cube. This will be a tap (feel free to find a 3d model)
5.  Create a script called "SpawnInterval"- this is a monobehaviour, and is the basis for components that add game logic to your game objects
6.  Give this script 2 fields - one for the spawn interval (float), one for the object to spawn (GameObject)
7.  Write the logic to instantiate the object every interval seconds.  (Hint: Coroutines)
8.  Add the new behaviour to the tap, and wire it up.  Hit play - you should see things spawn (but alas, you should also never see them disappear)
9.  Open up the water drop prefab and give it a RigidBody behaviour - so it reacts to gravity
10. Give the water drop a behaviour that destroys itself either

    1.  After a specific time period
    2.  After its height goes below 0 (assume that's the ground?)
    3.  When colliding with something

## Useful Resources to complete

* [1] <https://learn.unity.com/>
* [2] <https://www.youtube.com/user/Unity3D/featured>