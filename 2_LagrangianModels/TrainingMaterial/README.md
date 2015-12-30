Training Material Guide
======================
(c) Stefan Radl, TU Graz, 2015

Preface
--------
The documents in this folder should be used for training students, researchers, engineers in practice to become familiar with the tools. 
The documents are **NOT** meant to re-iterate or copy available documentation, tutorials, or source code. Instead, a connect to these documents should be established in this training material. If necessary, examples of documentation, tutorials, or source code should be included in the training material, but this should be reduced to a minimum.

Document Format
---------------
All documents should be prepared in PPT or PPTX format (for exceptions see below). In case equations need to be embedded, MathType should be used.

Screencast Recording
--------------------
Please use the software [RECORDMYDESKTOP](http://recordmydesktop.sourceforge.net/about.php) to record *.OGV files.

Document Categories and File Naming
---------------------
In order to keep track of the files, as well as to provide a clear structure to the user of the training material, files must be named in a structured way. Therefore , 6 different document categories should be used:

### Overview Document 
- File name starts with "1_Overview_"
- only one document allowed per tool
- should summarize make clear why and for which purpose the tool is used, ideally with a small example.
- This document should be short, and **MUST NOT** provide an overview of the individual components of the software.
- After reading this document, the user should be aware of problems that can be solved with the tool.

### Usage Documents
- File name starts with "2_Usage_"
- should introduce the user to the concept used for interfacing with the software tool, ideally with a small example. Also, an overview of the individual components of the software (e.g., documentation, source code, tutorials) should be provided.
- After reading this document, the user should be able to understand how to interact with the software tool.

### Theory Documents
- File name starts with "3_Theory_"
- should introduce the user to the underlying theory that is not already covered in the online software documentation. Ideally the theory should be explained using a small example, or a journal publication. In contrast t othe online software documentation (which may also contain theory), the theory documents in the training material should be designed for class lectures. Hence, there is no need to discuss every detail, but to rather train core aspects that are needed to understand the online software documentation.
- After reading this document, the user should be able to explain the main theoretical concepts that are used in the software tool, and should be able to efficiently use the theory manual of the software tool.

### Hands On Documents
- File name starts with "4_HandsOn_"
- should guide the user through one or more tutorials provided with the software tool.
- After reading this document, the user should be able to efficiently run a tutorial. Also, the user should be able to set up a new simulation case (or apply to the tool to a new situation).

### Screencasts
- File name starts with "5_Screencasts"
- The file contains links to web resources (e.g., cloud repositories) that allow the user to view and/or retrieve movies (with text) of the training material.


### Appendix (optional)
- Files must be place in the folder "6_Appendix"
- Preferably, PDFs should be placed there.


Miscellaneous
--------------------
- In order to avoid conflict with copyright, please cite documents (or parts of documents) in the training material
- the training material cannot cover a basic introduction to Linux, C/C++, git and Matlab/octave. It is expected that a potential user is familiar with the basic concepts of these tools. 
- it is expected that the user has a basic understanding of numerical techniques, e.g., discretization and integration algorithms.
- the training documents will not be tracked with git, hence a version number and date should be displayed in the document to avoid confusion.
