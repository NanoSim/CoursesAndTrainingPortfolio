
1 - ParaView
=========================

[ParaView](https://en.wikipedia.org/wiki/ParaView) is a powerful visualization toolkit that is perfectly integrated with OpenFOAM(R), LAMMPS, and LIGGGHTS(R).

Version
-------------
It recommended to use Paraview 5.0.1 or higher. You can download and unzip it from this page
http://www.paraview.org/download/
Note, that for Paraview 5.0.1 and 5.4.1 a reader (via plugin, see below) is available that will automatically read in files with the extension ".liggghts"!

Paraview 4.3.1. is also an option. 

Paraview can be installed (for OpenSUSE) here (preferred option):
http://software.opensuse.org/
or downloaded from here
http://www.paraview.org/

If you have a previous paraview version installed, it might be necessary to remove the old one, and set an alias (in your .bashrc file) that points the command "paraview" to the Paraview 4.3.1 executable (check in Yast where the executable is placed on the computer). Note, compiling ParaView from source takes long, and necessitates expertise (e.g., ensure that matplotlib is available, in order to have nice equation rendering).

The PVReader Plugin (relevant for OpenFOAM 5.x users that work with lagrangian data )
-------------
This plugin is important for OpenFOAM versions 5 and up, since the way how particle positions is saved by OpenFOAM has changed fundamentally (i.e., barycentric coordinates are used!). Native Paraview CANNOT understand this format when using (the standard) Paraview OpenFOAM reader (file extension ".foam").
These plugins are located in the source code of OpenFOAM here: ~OpenFOAM-5.x/applications/utilities/postProcessing/graphics/PVReaders
After compilation of these plugins, the user can use "paraFoam" (or "paraview" in case the plugins are loaded) to load files with the extension ".OpenFOAM". Then, barycentric coordinates of Lagrangian data points are correctly understood by this plugin, and can be displayed.
WARNING: As noted here:
https://www.openfoam.com/documentation/user-guide/paraview.php
the PVReader CANNOT read decomposed OpenFOAM data. Thus, it is impossible to display decomposed Lagrangian data dumped from OF 5.x with ParaView directly! Either: reconstruct first (e.g., by using 'reconstructPar -noFields'), or use the vtkWrite function object.

The LIGGGHTS(R) Reader Plugin (relevant for LIGGGHTS users only)
-------------
It is STRONGLY recommended to install a plugin to read data directly from source (e.g., for LIGGGHTS(R); a reader for OpenFOAM files is available by default in Paraview). 
The latest version of the plugin can be found here:
https://github.com/sradl1981/ParaView_Reader_for_LIGGGHTS
The required reader is already compiled for Paraview 4.3.1, 5.0.1 and 5.4.1, and can be found here (needs to be added as a plugin in Paraview):
https://github.com/sradl1981/ParaView_Reader_for_LIGGGHTS/blob/master/pre_compiled/4.3.1/libliggghts_reader.so
https://github.com/sradl1981/ParaView_Reader_for_LIGGGHTS/blob/master/pre_compiled/5.0.1/libliggghts_reader.so
https://github.com/sradl1981/ParaView_Reader_for_LIGGGHTS/blob/master/pre_compiled/5.4.1/libliggghts_reader.so

A Very Quick Start
-------------
Check out the quick intro here:
https://cfd.direct/openfoam/user-guide/paraview/

A less complete, but useful quick start is also available here:
https://www.openfoam.com/documentation/user-guide/paraview.php

Complete Books, User Guides and Tutorials
======================
https://www.paraview.org/Wiki

Math-text in Annotations etc. (i.e., inserting Latex-like text)
-------------
ParaView 3.98.0 introduced support to add annotations with math-text. This release extends on that capability to support math-text in several annotations including Text source, chart titles, scalar bars. Simply use $ <math-text> $ as the text to use. Anything within the $ <text> $ symbols will be treated as math-text and rendered using matplotlib (note: while the binary version of Paraview downloadable from https://www.paraview.org/download/ has the matplotlib package bundled, you have to provide it in case you compile Paraview from source!). Don't forget the space after/before the $ (for newer versions of ParaView this space is not important)!

Handling large Amount of Lagrangian data
-------------
To visualize a large amount of particles (>50k), it is NOT recommended to use the glyph "sphere", because too many triangles need to be rendered. Use the "2D glyph" instead (if you use Paraview 4.4 or lower), or (even better!!) the "Point Gaussian" representation in Paraview 5.0 and higher, for details see here:
https://blog.kitware.com/paraview-5-introducing-the-point-gaussian-representation/

It is generally recommended to render only a sub-section (e.g., clip, or threshold) of particles to keep the number small. Also, rendering a small amount of particles improves the clarity of the plot.

Important data from LIGGGHTS (relevant for LIGGGHTS users only!)
-------------
LIGGGHTS users: when dumping scalar quantities (made available by a fix), you MUST NOT use [0] to correctly visualize it in ParaView, e.g., use  “dump            dmp all custom ${dumpFrequency} ../DEM/post/dump*.liggghts id type x y z vx vy vz fx fy fz f_dragforce[1] f_dragforce[2] f_dragforce[3] radius 

