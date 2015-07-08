Meshing Toools that Interface with OpenFOAM
=======================================
Note
-------
Zhis list is based on a discussion held at the PFAU X meeting (Graz, July 8th, 2015) and summarizes a number of meshing tools that might (or might not) be useful to OpenFOAM users.

blockMesh
-------------------
standard tools, good experience

foamyHexMesh – Oliver, Alexander
-------------------------
Oliver had problems with foamyHexMesh generating 10 cells. For larger domain it failed. To run it needs a special library. Case of Oliver would be simpler than test case, but just gets some 10 cells. No experience in the audience using foamyHexMesh. User error probably.
foamyMesh – no experience in the audience
Polyeders, 2D meshes
CFMesh der Uni Zagreb – Jozsef
----------------------------
Extend project. Joszef has some experience. Automatic, control by dictionary, similar to snappyHexMesh but boundary layers are better.

Blender - Jozsef
-------
Längere Einarbeitungszeit. Vergleichsweise zu OpenFOAM. Tool for artists. Tutorials on rendering. Ca. first 10 minutes are on creating an surface. You can move around the nodes in blender.
SwiftBlock and SwiftMesh
------------------
Funktioniert schlecht. Swift Block takes a geometry and creates a blockMesh input file. Not up-to-date, works with a old version of blender. So first blender make stl, swift block generates a blockMeshdict which can be used by OPenFOAM then.
snappyHexMesh
Jozsef uses blender for the geometry as nice input for snappy.
3 Cut
-------------------
For simple geometries

ENGrid
------------
STL file with 1M triangles, it needs days to make mesh. Problem with small cells created by EN Grid, and periodic bouandary conditions. Face on one side simply had no face on the other side. Works fine for small geometries. Newer version has hex elements.
meshLab – Alexander
fills holes in a stl file.


Problem with dense particle bad with small distance between particles. Case raphi. Any id how to solve. AVL is meshing in India, but computing in Austria. Way of Stefan was castelate, layer for fluid and than layer extrusion for particle. Snappy has a problem with layer extrusion to singular point. If gap between spheres is small, problems. Look at pair of particles and do a neck around those. Tool to generate cylinders.
Idea mesquite, comes with extend project. Improves mesh quality after mesh is completed. Come from sandia. Sandia has project, collaborating all their meshing tools to one tool. Tool is opensource.

Good commercial tool for meshing, spyder from AVL bought by Numecka. ViF has a licence. Used when snappy failed, spyder was used. Works quiet nice. Tool called hexpress. Mesh is good enough for acoustic, giving a fine enough mesh for pressure.

Hyper mesh
----------------------
Commercial. Used for structure analysis by ().

Ansa – Jozsef
---------------------
For abacus, openfoam, good but pricy. Post processing tool for analyzes of data

Netgen
-------------------
For openFoam, tetrahedras, now with boundary layer extrusion

Pointwise (company, software name)
----------------------
They want to create a test case where everybody can benchmark the meshing tools. On CFD wiki, it will be announced in the next days.

Solid Edge
-----------------
CAD software allowing meshing. You can inport it to fluent. From fluent to foam.

Gambit
-------------------
Fluent to foam only works for one region. It could be combined in fluent. But needs experience.


