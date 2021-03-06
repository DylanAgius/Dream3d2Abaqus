# Dream3d2Abaqus
## Main Function
Convert microstructure information generated by Dream3d (opensource software which can be used to synthetically build different microstructure which can be found [here](http://dream3d.bluequartz.net/)) to construct an Abaqus input file containing periodic boundary conditions.

The generated microstructure features and orientations are assigned to element sets in Abaqus with the corresponding material definition assigned via sections.
## Dream3D Requirements
The minimum filter construction required is as follows:

<img src="/Images/minimum_filter_pipeline.png" width="200" height="200">

Centroid information will be stored in the *csv* file (created using the *Export Feature Data as CSV File* filter), while node/element/orientation information is stored in the *.vox* file (created using the *Export Los Alamos FFT File* filter).
## Required informtion for Matlab function
To use the Matlab function, the *xlsx* file included here should be updated with the material parameters in the sheet (with the corresponding name) in the order provided in the pdf found [here](http://www.columbia.edu/~jk2079/Kysar_Research_Laboratory/Single_Crystal_UMAT.html). 

The location of the centroid of each grain can be extracted from the generated *csv* file.  These values should be transferred to the *centroid* sheet in the *xlsx* file (inputfile_info)

## Installation
Simply copy files in the folder titled *Dream3d2Abaqus* into the MATLAB file path.

## Running the MATLAB function
Run from the command prompt the following:
*dream2abq('nameofvoxfile.vox','nameofinputfile.inp')*
where:
* nameofvoxfile = name of the vox file included in the same directly and which is exported using the *Export Los Alamos FFT File* filter
* nameofinpfule = is the name of the Abaqus input file you would like to create
