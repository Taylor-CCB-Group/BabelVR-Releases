# Workflow for landmarking multiple volumes in a session

## 'Autosave'
This is a mode that is intended to facilitate efficiently landmarking several volumes in a single session. Once the "Start Autosave" button in the GUI is pressed, it will enter a mode where, as volumes are loaded, information relating to the previously open volume(s) will be saved:
- As a file in Babel's 'scene' format with the name `auto_<volume_name>.sce`, which contains all information about any landmarks that have been created, as well as most other aspects of the application state such as rendering settings, panel layout etc. (If multiple volumes are open simultaneously, the `volume_name` for the file will be that of the 'active' volume, but information relating to all open volumes will be included.)
- Landmark coordinates for each volume opened throughout the session will be accumulated, to be exported as a single morphoJ file `morphoJ_auto_YYYY-mm-dd_hh-mm.txt` when the "Finish Autosave" button is pressed. This file contains one line per volume, with the name of the volume followed by `x, y, z` coordinates of each landmark in order, separated by tabs.

## Preload / volume cache
Babel maintains a cache of volume data, such that it is often possible to switch instantly between volumes. If you anticipate that you will be working on another volume in the near future, it is possible to load its data into the cache in the background by pressing the 'preload' button that appears on the bottom-right of each entry in the volume loading palette[^1]. If you do this while working on landmarking a particular volume, you can ensure that the data for the next volume is already loaded by the time you're ready to use it.

When 'preload' is pressed, the button will be replaced with a circular progress indicator as the data is loaded, and then a 'tick' to indicate that the data is available in the cache. Least-recently-used items will be automatically removed if the cache becomes full (in which case, 'preload' buttons will be shown again for corresponding items).


[^1] Note that OBJ files do not currently support this preloading feature, and indeed when loading cause the interface to freeze briefly - which can be unpleasant in VR. They do get cached, though, so switching to an OBJ file that has previously been loaded in a given Babel session should be instantaneous.



# Groups

## CSV 'GroupSet'

## Auto-advance
When using the landmarking tool with this option enabled, the software will automatically switch to the next group every time a new landmark is placed. When the final group from the list is reached, there will be 'no active group' and it is not possible to input further landmarks until a group is explicitly selected in the groups palette.

## Show only empty
In the 'Groups' panel, it is possible to display only those groups that do not contain any landmarks. In cases where you expect to input a value for each group, this can be used as a way of checking whether more input is still needed.