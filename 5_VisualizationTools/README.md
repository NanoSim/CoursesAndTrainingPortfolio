
1 - ParaView
=========================

[ParaView](https://en.wikipedia.org/wiki/ParaView) is a powerful visualization toolkit that is perfectly integrated with OpenFOAM(R), LAMMPS, and LIGGGHTS(R).


Hints
----------------------------
1) It recommended to use Paraview 5.0.1 or higher. You can download and unzip it from [this page](http://www.paraview.org/download/)
Note, that Paraview 5.0.1 has ALREADY a simple LAMMPS/LIGGGHTS file reader that will automatically read in files with the extension ".dump". If you want to use the (better) plugin reader, install the plugin, and use the extension ".liggghts"!

Paraview 4.3.1. is also an option. It can be installed (for OpenSUSE) here (preferred option):
http://software.opensuse.org/
or downloaded from [here](http://www.paraview.org/)
If you have a previous paraview version installed, it might be necessary to remove the old one, and set an alias (in your .bashrc file) that points the command "paraview" to the Paraview 4.3.1 executable (check in Yast where the executable is placed on the computer).

2) It is STRONGLY recommended to install a plugin to read data directly from source (e.g., for LIGGGHTS; OpenFOAM is available by default in the latest versions, same as for LAMMPS files). See the LIGGGHTS folder for instructions, or search the web.
The latest version of the plugin can be found here:
https://github.com/sradl1981/ParaView_Reader_for_LIGGGHTS
The required reader is already compiled for Paraview 4.3.1 and 5.0.1, and can be found here (needs to be added as a plugin in Paraview):
https://github.com/sradl1981/ParaView_Reader_for_LIGGGHTS/blob/master/pre_compiled/4.3.1/libliggghts_reader.so
https://github.com/sradl1981/ParaView_Reader_for_LIGGGHTS/blob/master/pre_compiled/5.0.1/libliggghts_reader.so

3) Check out the quick intro [here](http://www.openfoam.org/docs/user/paraview.php)

4) Math-text in annotation (i.e., inserting Latex-style text): 
ParaView 3.98.0 introduced support to add annotations with math-text. This release extends on that capability to support math-text in several annotations including Text source, chart titles, scalar bars. Simply use $ <math-text> $ as the text to use. Anything within the $ <text> $ symbols will be treated as math-text and rendered using matplotlib. Don't forget the space after/before the $!

5) To visualize a large amount of particles (>50k), it is NOT recommended to use the glyph "sphere", because too many triangles need to be rendered. Use the "2D glyph" instead (if you use Paraview 4.4 or lower), or (even better!!) the "Point Gaussian" representation in Paraview 5.0 and higher, for details see here:
https://blog.kitware.com/paraview-5-introducing-the-point-gaussian-representation/

6) It is generally recommended to render only a sub-section (e.g., clip, or threshold) of particles to keep the number small. Also, rendering a small amount of particles improves the clarity of the plot.

7) LIGGGHTS users: when dumping scalar quantities (made available by a fix), you MUST NOT use [0] to correctly visualize it in ParaView, e.g., use  “dump            dmp all custom ${dumpFrequency} ../DEM/post/dump*.liggghts id type x y z vx vy vz fx fy fz f_dragforce[1] f_dragforce[2] f_dragforce[3] radius 
