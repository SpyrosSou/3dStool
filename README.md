**Note that this repo is under construction, and data handling functions have not been added as of yet. 
Functions for data handling, splitting, etc will be added and the raw data will be uploaded on Zenodo. 
Until then, the prepared data are solely available using Zenodo.**

# 3dStool
The 3D surgical tool dataset (3dStool) has been constructed with the aim of
assisting the development of computer vision techniques that address the
operating room. It can be downloaded [here](https://zenodo.org/record/7635563).

Specifically, even though laparoscopic scenes have received a lot of attention
in terms of labelled images, surgical tools that are used at initial stages of
an operation, such as scalpels and scissors, have not had any such datasets
developed... until now.

3dStool includes 5370 images, accompanied by manually drawn polygon labels,
as well as information on the 3D pose of these tools in operation. Four
surgical tools have been collected for now:

1. Scalpel
2. Scissors
3. Forceps
4. Electric Burr

An example of the manual masks is shown below for each tool:

![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/scalpel.jpg?raw=true)
![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/scissors.jpg?raw=true)
![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/forceps.jpg?raw=true)
![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/burr.jpg?raw=true)

An annotation json file (in the format of COCO) exists for the images,
containing the masks, boxes, and other relevant information. Furthermore,
pose information is provided in two different manners.

Firstly, a csv in the following format:

| Column  | #1    | #2    | #3    | #4    | #5    | #6    | #7    | #8    | #9   |
| :---:   | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---:|
| Seconds | X (m) | Y (m) | Z (m) | q<sub>i</sub>| q<sub>j</sub>| q<sub>k</sub>| q<sub>l</sub>| Class   | Image Name  |

Position and orientation are both provided in the coordinate axes of the camera
used to obtain the data (Realsense D415, Intel, USA). Pose is provided in the
form of quaternions, however it is possible to convert this format into other
available notations.

The pose data can also be combined with the masks in the form of a final json
file, in order to obtain a final COCO-format json with object poses as well.

The 3D poses can be visualised in 2D images using the intrinsic calibration
matrix, K. The results of this are shown below:

![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/pose_scalpel.jpg?raw=true)
![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/pose_scissors.jpg?raw=true)
![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/pose_forceps.jpg?raw=true)
![alt text](https://github.com/SpyrosSou/3dStool/blob/main/example_images/readme_images/pose_burr.jpg?raw=true)

TODO:

1. Upload the code for visualisation, data handling etc
2. Create instructions on use of code
