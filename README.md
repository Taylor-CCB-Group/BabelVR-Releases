# BabelVR-Releases
This is a repository for releases of BabelVR executables.

# Abstract

Biological objects both at the macro and micro level often have complex 3D architectures that can be difficult to interpret, measure and manipulate using traditional 2D software. In geometric morphometric analysis, understanding shape variation in 3D images generated from different anatomical structures requires time-consuming landmarking procedures before such analyses can be undertaken.  We present BabelVR as a novel application allowing interaction with 3D images, which has specific enhancements to aid measurement and landmarking of biological object(s) using Virtual Reality.

# Overview
BabelVR is a general purpose method for visualising 3D volumetric data using either HTC Vive or Oculus Rift / Quest. 
More recently we have been focusing on use cases for the process of landmarking complex 3D images. Using Virtual Reality allows you to place these pointers very accurately on the surface or even inside the object you are working with, which can be more difficult using traditional 2D workflows. You can then export these landmarks to packages such as [MorphoJ](https://morphometrics.uk/MorphoJ_page.html)



<a href="https://www.youtube.com/watch?v=XzY7f1UY25o">
<img alt="Doing landmarking" src="https://img.youtube.com/vi/XzY7f1UY25o/0.jpg">
</a>

Figure 1: Introductory video showing landmarking using BabelVR. Click on the image above to see a video.

# Getting started
When you first run BabelVR, a folder is created in your user Documents `"%UserProfile%\Documents\Babel"`.

This contains various subfolders with data to be loaded into the program (`Nii` format volumetric data, `Obj` meshes...), configuration files (which in most cases you are unlikely to need to be aware of), and any saved or exported data (such as landmark data created from within the app).

# Image files

In order to bring new data into the program, you copy files into the `Nii` or `Objects` folders, which will be scanned when the program starts and used to populate the "Volumes" GUI. The Nii files can be generated from DICOM or any 3D stack images (including colour) using software such as [Fiji](https://imagej.net/software/fiji/) via "Save as" using the [Nii plugin](https://imagej.nih.gov/ij/plugins/nifti.html)


# Interacting in VR

There are two controllers with the Vive or Oculus headset. 
VR is a relatively new way of interacting with 3D objects. Instead of mouse you use controllers. We will refer to controller 1 and 2. Both controllers allow activation of a laser pointer to point and select menu items using the trigger. You can close down menus by clicking on the X in the top left corner of the panel. 

Each controller has a "grab zone" (the downward facing pyramid) which when you move over the object and then press the grab buttons(s) it allows you to grab the object (the outline of the selected object will highlight). This means to you can then move it around in the 3D space as long as you hold on to it.

Controller 1 is used to activate the function via the circular menu and the Menu bar is used to access settings for each button and 
other settings and functions.

# Controllers HTC Vive

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/ViveControllers.png" width="50%" height="auto">

Is in the dominant hand (left or right). Image shows a Vive controller. 

The circular menu (accessed via track pad on Vive and thumbstick on Quest) activates the function. See the Quest diagram below that shows the icons on the controllers. 

# Controllers Meta Quest 2
Here is a schematic of the Meta Quest controllers

***

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Quest2Controllers.png">

***
In the software they look like this. Access the different functions by moving the thumbsticks on the controller and clicking on the top of the thumbstick.

<img src="https://user-images.githubusercontent.com/10518908/175566807-71ee7eb8-0b10-4cc7-b5ee-cb343b5576c9.png">

# More On Folders
As discussed a `BabelVR` folder in `My Documents` will be created. In this folder are various subfolders. The following folders are relevant to end-users:
## Nii
Place all your Niftii (Nii) images here and they will be accessible from the Volumes menu.
## Objects
Place any Mesh (OBJ format) objects in this folder and they will be accessible from the Volumes menu.
## Exports
Any data that is saved via the Export function is put here. For example, morphoJ files. 
## Screenshots
The snapshot tool creates timestamped PNG images when activated and these are stored in here.

It is advised *NOT* to tamper with the other folders in the `BabelVR` directory as they are used internally by the software. 

# Menus
These icons are ways of getting access to properties of the different functions of BabelVR. The functions are mostly accessed from the right controller by the trackpad (HTC Vive) or thumbstick (Meta Quest).

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/BabelVRArcMenuFigure.png">

# Volumes 
Nii files can be accessed here.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Volumes.png">
There are various settings that you can apply to the loaded volume which can be accessed buy the COG icon on the menu bar.

## Settings

<a href="https://youtu.be/I_Uh4zqGcK8">
<img alt="Overview of settings / volume info menu" src="https://img.youtube.com/vi/I_Uh4zqGcK8/0.jpg">
</a>

Figure 2: Video showing an overview of settings / volume info menu functionality

### Manipulation

This allows you to directly interact with one volume. If you have loaded more that one volume in the space you can separate out these into multiple objects.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo1.png" width="50%" height="auto">

## Data
This is very useful for rescaling the values of the voxels of the volume.

_value_ has a range associated with it (valueRangeMin and valueRangeMax)

`valueRangeMin: Rescale values according to the formula:
(max(voxel.rgb) - valueRangeMin) / (valueRangeMax - valueRangeMin).
valueRangeMax: Rescale values according to the formula:
(max(voxel.rgb) - valueRangeMin) / (valueRangeMax - valueRangeMin)`

and similarly _cutValue_

`cutValueRangeMin: Before rescaling, set values below cutValueRangeMin to 0.
cutValueRangeMax: Before rescaling, set values above cutValueRangeMax to 0.`

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo2.png" width="50%" height="auto">

## Properties
Allows the adjustment of contrast, brightness and opacity of the volume.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo3.png" width="50%" height="auto">

## Light
when Enabled activates light simulation / ray tracing. You will see a torch that can be picked up and positioned anywhere in the scene to adjust the light flow. This is useful to create a more realistic appearance or to resolve certain features. Surface threshold (opacity), alpha, shininess and colouring of the light (ambient / diffuse / specular) can be adjusted. 

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo4.png" width="50%" height="auto">


## Exclusion
This is used to be able to slice or exclude part of object. For example you want to partially exclude a skull so you can look inside. If you check the _Excluder_ _Active_ box (by default) a grey cube will appear that can be picked up and positioned to exclude regions of the volume.
Checking _Invert_ _Culling_ only shows the volume when it is contained inside the cube, so the visible surface is the side of a cube.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo5.png" width="50%" height="auto">

## Colour
Allows you to upload a 256 x 256 pixel transfer gradient PNG (these should be placed in the Babel > Transfers directory. This allows colouring of certain densities with colour which can be useful for highlighting features.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo6.png" width="50%" height="auto">

## Label
Turns the labelling of the volume on / off and also can vary it's size.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo7.png" width="50%" height="auto">

## Scale 
Resize the voxels of the image on the x, y, or z axis. Useful if the image has been imported with incorrect relative dimensions.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo8.png" width="50%" height="auto">

## Rendering
Increase the number of samples on the ray cast which can improve the volume rendering quality and avoid colour fringing.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_VolumeInfo9.png" width="50%" height="auto">

# Reference Annotations
You can upload landmark reference annotations as a csv file defining the name, colour and description of each landmark in Babel > Groups directory.
Colour is helpful as aide for left / right positioning. In this case we have used red for right, green for left based markers and white for everything else.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Groups.png" width="50%" height="auto">

# Lines
Show the distances between each landmark as it is drawn.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Lines.png" width="50%" height="auto">

# Save
Allows the saving of the scene. *Does it allow saving of the reference images*

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Saves.png" width="50%" height="auto">

# Objects - do we need to keep this if it is available from the volumes directory
You can load .obj format 3D meshes into BabelVR. Place any objects in the Babel > Objects folder and they will appear here. These objects can also be used as an excluder.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Objects.png" width="50%" height="auto">

# Landmarks
* Ray Based draw - the landmark will be constrained to move across the surface of the object. This experimental feature in theory makes it easier to position a landmark on the surface.
* Pyramid Mesh Style - landmark will be a downward shaped pyramid, the point of which is the exact landmark position. The alternative is a low poly sphere.
* Add Labels - Shows the label based on the reference file
* Continuous Draw - Draws points continuously when the trigger is held down
* Snap to excluder - Landmarks will follow excluders contours where available

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Brushes.png" width="50%" height="auto">

# Delete
<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Delete.png" width="50%" height="auto">

# Slow down speed
This allows the volume movement to be dampened to allow very fine operations / movements. Adjusting the _Factor_ increases / decreases the dampening effect. 

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Movement.png" width="50%" height="auto">

# Tape measure
Properties of the measuring tool. 
* Single Handed - uses one controller
* Double Handed - uses both controllers to do the measurement
* Stay after release - means just that, otherwise it disappears quickly

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Tape.png" width="50%" height="auto">

# Snapshot
This allows you to take pictures within BabelVR of your volume from different angles. 

* Enabled - start the Snapshot function
* Attached to active volume - the Camera will move when you move the volume
* Attach light to camera - attach the torch to the camera 

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Camera.png" width="50%" height="auto">

# Object creator -----? Get rid of this
A way of creating custom meshes.
<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Mesh.png" width="50%" height="auto">

# Eraser
Erase allows removal of parts of the volume (voxels). It works in the same way as the "Excluder" function but draws continuous metaballs to exclude parts of the volume.
* Size - size of the metaball
* Alpha - Opacity of the metaball 
* Show Outline - shows a yellow outline around the excluded area

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Eraser.png" width="50%" height="auto">

# Undo
Shows a history if all the operations that can be undone / redone

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_UndoRedo.png" width="50%" height="auto">

# Reference image
if PNGs or JPGs are place in the folder Babel > References these will be seen as a list in this panel. Activating the check boxes will bring show the reference image in the virtual world. 

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_RefImages.png" width="50%" height="auto">

# Debug console
This is good way of reporting errors. If you see a problem checking this the row(s) will send an email to the developers.

<img src="https://github.com/Taylor-CCB-Group/BabelVR/blob/master/Assets/Resources/Menu_Debug.png" width="50%" height="auto">


