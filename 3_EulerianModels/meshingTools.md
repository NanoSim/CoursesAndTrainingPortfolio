Meshing Toools that Interface with OpenFOAM
=======================================
Note
-------
This list is based on a discussion held at the PFAU X meeting (Graz, July 8th, 2015) and summarizes a number of meshing tools that might (or might not) be useful to OpenFOAM users.

blockMesh
-------------------
standard tools, good experience

foamyHexMesh – Oliver, Alexander
-------------------------
To run it needs a special library. Oliver had problems with foamyHexMesh generating 10 cells. For larger domain it failed.  Case of Oliver would be simpler than test case, but just gets some 10 cells. User error probably. No experience in the audience using foamyHexMesh. 

foamyMesh – no experience in the audience
-------------------------
Polyeders, 2D meshes

CFMesh der Uni Zagreb – Jozsef
----------------------------
Provided by [Creative Fields, Ltd.](http://www.c-fields.com/) Extend project. Joszef has some experience. Automatic, control by dictionary, similar to snappyHexMesh but boundary layers are better.

Blender - Jozsef
-------
As OF, Blender needs some training time to get it. Tool developed for artists – so most of the tutorials online focus on rendering, however there is always a mesh generation step first. You can move around the nodes in blender (to improve mesh quality, correct mesh).

SwiftBlock and SwiftMesh
------------------
Swift Block takes a geometry and creates a blockMesh input file. Not up-to-date, works with an old version of blender. The way is to (i) create a surface in Blender, (ii) generate a blockMeshDict in Swift Block, and (iii) generate the mesh in OF. Statement is, that it is not functioning that well.

snappyHexMesh
------------------
Jozsef uses blender for the geometry as nice input for snappy. Everybody nows about snappy and uses it / used it for a problem.

3 Cut - Oliver
-------------------
For simple geometries

ENGrid - Oliver
-------------------
For large STL files (1m triangles) it takes days to generate a mesh. Problems occurred generating a mesh with small cells for simulation having periodic boundary conditions. Face on one side simply had no face on the other side. Works fine for small geometries.
Next version will have hex elements.

meshLab – Alexander
-------------------
Repair mesh - fills holes in a stl file.

AutoMesh / Hexpress
---------
Commercial, provided by [numeca](http://www.numeca.com/), product info [here](http://www.numeca.com/en/products/automeshtm).
Good commercial tool for meshing, spider from AVL bought by Numecka. ViF has a licence. Used when snappy failed, spyder was used. Works quiet nice. Tool called hexpress. Mesh is good enough for acoustic, giving a fine enough mesh for pressure.

Hyper mesh
----------------------
Commercial. Used for structure analysis by (guy from Viennese company - sry for missing the name).

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

IPPT Problem Statement
-------------------
Problem with dense particle bad with small distance between particles (as reference, look figure at Pfau X invite).
IPPT (Stefan R.) approach: castelate mesh, add layers for fluid and than add layers for particle. Snappy has a problem with layer extrusion to singular point. If gap between spheres is small, problems. Look at pair of particles and do a neck around those. Tool to generate cylinders.
Idea / Solution to problem: mesquite, which comes with extend project. Improves mesh quality after mesh is completed. Produced by sandia. Sandia has project, collaborating all their meshing tools to one tool. Tool is opensource.
Note: AVL approach for meshing complicated stuff: source it out to India. Computation then is done in Austria.

Outlook / Future in Meshing
-------------------
Jozsef attended meshing BoF session at OpenFOAM Workshop 10 in Ann Arbor, Michigan, US.
As we did, they counted all the existing meshing tools. Idea there and here is, to provide test cases and benchmark the meshing tools available. Put it on a public webpage for industry and researchers to be found.
In a survey, attending people are asked weather they prefer top-down solution (like snappy) or bottom-up solutions (like blockMesh). The favor was for top-down.
In Pfau X BoF session, Oliver and Jakob stated to feel more confortable having more control as in bottom-up solutions (like blockMesh).
