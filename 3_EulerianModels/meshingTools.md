Meshing Toools that Interface with OpenFOAM
=======================================
Note
-------
This list is based on a discussion held at the PFAU X meeting (Graz, July 8th, 2015) and summarizes a number of meshing tools that might (or might not) be useful to OpenFOAM users.

[blockMesh] (http://cfd.direct/openfoam/user-guide/blockmesh/)
-------------------
User: all

standard tools, good experience

[foamyHexMesh] (http://www.openfoam.org/version2.3.0/foamyHexMesh.php)
-------------------------
User: Oliver, Alexander

To run it needs a special library. Oliver had problems with foamyHexMesh generating 10 cells. For larger domain it failed.  Case of Oliver would be simpler than test case, but just gets some 10 cells. User error probably. No experience in the audience using foamyHexMesh. 

[foamyMesh] (https://github.com/OpenFOAM/OpenFOAM-dev/tree/master/applications/utilities/mesh/generation/foamyMesh)
-------------------------
User: no experience

Polyeders, 2D meshes

[CFMesh] (http://www.c-fields.com/cfmesh)
----------------------------
User: Jozsef

Provided by [Creative Fields, Ltd.](http://www.c-fields.com/) Extend project, University Zagreb. Joszef has some experience. Automatic, control by dictionary, similar to snappyHexMesh but boundary layers are better.

[SALOME](http://www.salome-platform.org/)
--------------------------------------
Open, and a number of youtube videos are provided (e.g., see [HERE](https://www.youtube.com/watch?v=1zQbU-E4k1U)). Salome also features mesh cleaning tools.

[Blender] (https://www.blender.org/)
----------------------------
User: Jozsef

As OF, Blender needs some training time to get it. Tool developed for artists – so most of the tutorials online focus on rendering, however there is always a mesh generation step first. You can move around the nodes in blender (to improve mesh quality, correct mesh).

[SwiftBlock and SwiftMesh] (https://openfoamwiki.net/index.php/Contrib/SwiftBlock)
------------------
User: Jozsef

Swift Block takes a geometry and creates a blockMesh input file. Not up-to-date, works with an old version of blender. The way is to (i) create a surface in Blender, (ii) generate a blockMeshDict in Swift Block, and (iii) generate the mesh in OF. Statement is, that it is not functioning that well.

[snappyHexMesh] (http://cfd.direct/openfoam/user-guide/snappyhexmesh/)
------------------
User: all

Jozsef uses blender for the geometry as nice input for snappy. Everybody nows about snappy and uses it / used it for a problem.

3 Cut
-------------------
User: Oliver

For simple geometries

[enGrid] (http://engits.eu/en/engrid)
-------------------
User: Oliver

For large STL files (1m triangles) it takes days to generate a mesh. Problems occurred generating a mesh with small cells for simulation having periodic boundary conditions. Face on one side simply had no face on the other side. Works fine for small geometries.
Next version will have hex elements.

[meshLab] (http://meshlab.sourceforge.net/)
-------------------
User: Alexander

Repair mesh - fills holes in a stl file.

[AutoMesh / Hexpress] (http://www.numeca.com/en/products/automeshtm)
---------
Commercial, provided by [numeca](http://www.numeca.com/), product info [here](http://www.numeca.com/en/products/automeshtm).
Good commercial tool for meshing, spider from AVL bought by Numecka. ViF has a licence. Used when snappy failed, spyder was used. Works quiet nice. Tool called hexpress. Mesh is good enough for acoustic, giving a fine enough mesh for pressure.

[Hyper mesh] (http://www.altairhyperworks.de/%28S%2804tbws45ludcdmbr3egcbi45%29%29/Product,7,HyperMesh.aspx)
----------------------
User: guy from Vienna

Commercial. Used for structure analysis by (guy from Viennese company - sry for missing the name).

[Ansa] (http://www.beta-cae.gr/ansa.htm)
---------------------
User: Jozsef

For abacus, OpenFOAM, good but pricy. Post processing tool for analyzes of data

[Netgen] (http://www.hpfem.jku.at/netgen/)
-------------------
For OpenFOAM, tetrahedras, now with boundary layer extrusion

[Pointwise] (http://www.pointwise.com/)
----------------------
They want to create a test case where everybody can benchmark the meshing tools. On CFD wiki, it will be announced in the next days.

[Solid Edge] (www.siemens.com/SolidEdge)
-----------------
CAD software allowing meshing. You can inport it to fluent. From fluent to foam.

[Gambit] (http://www.ansys.com/Products/Workflow+Technology/ANSYS+Workbench+Platform/ANSYS+Meshing)
-------------------
Fluent to foam only works for one region. It could be combined in fluent. But needs experience.

Outlook / Future in Meshing
-------------------
Jozsef attended meshing BoF session at OpenFOAM Workshop 10 in Ann Arbor, Michigan, US.
As we did, they counted all the existing meshing tools. Idea there and here is, to provide test cases and benchmark the meshing tools available. Put it on a public webpage for industry and researchers to be found.
In a survey, attending people are asked weather they prefer top-down solution (like snappy) or bottom-up solutions (like blockMesh). The favor was for top-down.
In Pfau X BoF session, Oliver and Jakob stated to feel more confortable having more control as in bottom-up solutions (like blockMesh).
