# UI, Events and such

[&olt; back](../../README.md)

After creating this sample, you should be able to create 2D UI in Unity, and have it interact with the scene.

## Scene overview

Create a scene with a variety of interactions:

-   Create a cube
-   Change the cube's color
-   Delete the cube
-   Create multiple cubes, and changing the color on selection

## Prerequisites

-   Basic Unity

## Knowledge Gained

-   Prefabs
-   Scripts / Components
-   Canvas
-   Raycasting
-   Basic materials
-   Sounds

## Expected time to complete

-   Beginner: 1-2 days
-   Expert: 1-2 hours

## Simple guide

1.  Create an empty scene
2.  Add a button that creates a cube every time it is pressed [1]
3.  Add a button that cycles the most recently created cube between a handful of colours (or create a button for each color)
4.  Add a button that destroys the most recently created cube
5.  Instead of relying on the most recent cube, require the cube to be tapped to confirm the deletion (ie. "Choose a cube to delete")
6.  When creating, require a "placement" of the cube by building a virtual environment and putting the cubes on a wall
7.  Add sounds to the button presses (use ZapSplat or FreeSound for quick sounds)

## Tips

-   The Button component works with 2D UI components to make button states and dispatch simple and easy - use this for 2D UI (buttons)
-   The Event Trigger component is a simple component that listens to events and dispatches them to your own methods. Use this for 3D UI (e.g. tapping on a cube)

## Useful Resources to complete

* [1] <https://learn.unity.com/tutorial/ui-components#5c7f8528edbc2a002053b4d0>