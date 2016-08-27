# laser-cutter
Support files for the HackRVA laser-cutter build

This repository contains the configuration files necessary to run HackRVA's laser cutter.  The CamBam configuration files are required when using CamBam to generate gcode specific to the HackRVA laser.  These files have been tested with CamBam Plus Version 0.9.8.  

The Mach3 configiration files are used when controlling laser operation with Mach3.

CamBam
Installation of the files:
You will need to work in the C:\ProgramData directory, which is usually hidden.  If you don't see this directory in the File Explorer, you may need to change the folder options for C:\ to "show hidden files, folders, and drives". 
The configuration files need to be installed in the "C:\ProgramData\CamBam plus 0.9.8\" directory.  This directory should already be present and contain the default configuration - if it appears empty or doesn't exist, check that you are looking in the proper location.  The files in the *styles* and *tools* folders will overwrite the default files.  The *post* folder contains only one file containing the critical HackRVA-specific gcode configuration.
