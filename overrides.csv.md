In some cases you may find that volumes loaded into Babel do not have complete or accurate metadata relating voxel size to real-world measurements.

If there is a file `override.csv` in the `nii` folder, it will be used to override the metadata used for scale etc of corresponding objects within the system.

We may add more user-friendly ways of editing this data in future. If correct metadata is present in the file headers of any loaded data, it is not necessary to use this file, but it can be useful in instances where that is not the case if it isn't practical to fix the files themselves.

# Format
Columns are: `filename, pixelWidth, pixelHeight, pixelDepth, unit, imageWidth, imageHeight, channels, slices, frames`.

## filename
The name of the `nii` file to which this line refers. This does not require the full path. If a file with the given name does not exist in `%UserProfile%\Documents\Babel\Nii` when the program starts, the entry will be ignored.

## pixelWidth, pixelHeight, pixelDepth
Floating point (decimal) values for the physical size of an individual pixel (voxel) in the original model.

## unit
A string (text) indicating what physical units the above measurements are in.

Any of `µm` `um` or `microns` will be interpreted as micrometers. Other valid inputs are `meter`, `milimeter`, `mm`.

## imageWidth, imageHeight, channels, slices
Integer values for the image size. Channels should be 1 for scalar data, 3 for rgb, etc.

## frames
This relates to a currently unsupported feature relating to multi-frame video data that. Can be set to `-1` in normal circumstances.

# Example
For a file `STACK_3_2021_Rec.nii` with 762 slices of 500x500px, where each voxel should be 35.16µm³:

```
STACK_3_2021_Rec.nii,35.16,35.16,35.16,um,500,500,1,762,-1
```

## warning
If the `override.csv` file is open in another program (particularly OpenOffice, VSCode seems ok) when running Babel, then it will cause an error that means the file can't be loaded (and possibly other issues causing the program not to initialise correctly at all).