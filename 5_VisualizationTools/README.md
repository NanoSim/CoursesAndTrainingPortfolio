
ParaView
=========================

[ParaView](https://en.wikipedia.org/wiki/ParaView) is a powerful visualization toolkit that is perfectly integrated with OpenFOAM(R), LAMMPS, and LIGGGHTS(R).


Hints
----------------------------
1) It recommended to use Paraview 5.0.1 or higher, since it contains a number of essential features (readers, improved visualization of point particles). You can download and unzip it from this page http://www.paraview.org/download/. It is NOT recommended to use 5.0.0, since it contains several bugs.

2) To visualize a large amount of particles (>50k), it is NOT recommended to use the glyph "sphere", because too many triangles need to be rendered. Use the "2D glyph" instead (if you use Paraview 4.4 or lower), or (the BEST OPTION) the "Point Gaussian" representation in Paraview 5.0 and higher, for details see here: https://blog.kitware.com/paraview-5-introducing-the-point-gaussian-representation/

3) It is generally recommended to render only a sub-section (e.g., clip, or threshold) of particles to keep the number small. Also, rendering a small amount of particles improves the clarity of the plot.

4) Math-text in annotation (i.e., inserting Latex-style text): ParaView 3.98.0 introduced support to add annotations with math-text. This release extends on that capability to support math-text in several annotations including Text source, chart titles, scalar bars. Simply use $ <math-text> $ as the text to use. Anything within the $ <text> $ symbols will be treated as math-text and rendered using matplotlib. Don't forget the space after/before the $!
