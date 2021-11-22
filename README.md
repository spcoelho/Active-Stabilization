# Active-Stabilization
LabVIEW code and ImageJ plugin

# LabVIEW
The LabVIEW code here was developed for active stabilization/ 3D Focus locking using a GPU

To run the Simulation and Hardware software:

Necessary hardware:
1.	Windows PC with 64-bit architecture 
2.	CUDA enabled Nvidia graphics card (e.g. GTX 1080)

Additional optional hardware:
1. LED and LED controller box (Mightex, BLS-SA02-US)
2. Nanopositioning Piezo Stage with USB 20-bit connection  (Mad City Labs, Nano-LP50-200)

Necessary software:
1.	LabVIEW 64-bit (2014 or above) including:
  a.	Vision and Motion 
  b.	Vision Acquisition Software
  c.	Ni-DAQmx
2.	CUDA 7.5 (https://developer.nvidia.com/cuda-75-downloads-archive)

To run the simulation software:

1. Download and unzip the folder
2. Open the software (Simulation and Hardware Test.exe)
Ensure the DLL's remain in the path structure
3. Select the approriate tab and run


To install all necessary hardware, full software and troubleshooting:
Follow steps found at Coelho et al Nature Protocols 2021 (https://www.nature.com/articles/s41596-020-00426-9)
  
# ImageJ / Micromanger plugin (developed by James Walsh, james.walsh@unsw.edu.au)

This here is a CPU based approach to perform focusing locking.
To install here are two files -  a Jar and the parameters file. 

To install it, place these two files into the micromanager plugin folder (for me this is C:\Program Files\Micro-Manager-2.0gamma\mmplugins). In micromanager, you then need to have 3 things:
1) The camera you want to use installed and running as the primary camera
2) The pixel size set correctly for the camera
3) The xy and z stages that you want to control installed and set as the Core-XY stage in the device property browser.

To run it in micromanager go Plugins->Feedback Focus lock
The main GUI will then come up.
Using the ImageJ panel draw a box over the fiducial that you want to track then click select bead. If you want to track a second fiducial to measure errors draw a second box on the live screen then click select second box.
Click calibrate to generate the calibration zstack. The correlation plot that is made at the end should look like a smooth inverted parabola. If it is jagged you probably need to increase the delta zslices in the options and rerun calibrate.
Click lock and then it should hold the position.
When you're finished stop live to stop focus locking. It should give you an option to save a csv that plots the XYZ position of the stage at each move point as well as the measured position of Fiducial 1 and Fiducial 2.

Contact: s.pereiracoelho@unsw.edu.au
