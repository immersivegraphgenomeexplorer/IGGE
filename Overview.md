# IGGE Unity Overview
## Scripts
### GraphLoader.cs
This scripts loads a graph from a specified JSON file and sets up all of the game objects in Unity. 

Bulk of the work is done in ``LoadJSON()``. Currently, all Unity game objects are instanced in ``LoadJSON()``, right after reading the entire JSON file into memory.

### NodeData.cs
Contains the per-node metadata, attached to each ``node`` GameObject.

### Settings.cs
General global settings. Currently handles toggling between the VR and non-VR camera.

### VR scripts
#### VRInput.cs
Handles all of the input from the VR device, can easily check the state of something in other scripts.

#### VRCameraControl.cs
Controls the VR Rig and the camera connected to it. Mainly controls for movement of the VR rig.

#### VRPhysics.cs
Handles everything related to GameObject manipulation in VR. 

## Prefabs
### node
Includes all info to spawn a node. Instanced in ``LoadJSON()``. Any property that is unique to rendering (color, etc) should be added to a MaterialPropertyBlock so that all node instances could be batched. Avoid using any properties that cannot be added with MaterialPropertyBlocks.

### edge
LineRenderer prefab that is instantiated. Currently only works with LineRenderer.

## Materials
### node_mat
Node material used. Set to Unity defaults when unselected.

### selected_shader
Shader used when a node is selected. Not yet complete, something temporary added in for now.

## Streaming Assets

Currently, all JSON files are loaded from the StreamingAssets folder. Each file is loaded entirely into memory.
