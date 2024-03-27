
# Libre Engineer
A FOSS alternative to many industry-standard engineering solutions.
Highly extensible through the [Wren](https://wren.io/) scripting language.
Custom engineering kernels/libraries for CAD, CAM, & CAE.

## Goals
The primary goal of Libre Engineer is to bring industry level engineering solutions to the open source ecosystem.
Because of that, it is organized such that you can easily include it's libraries into your own projects.

## Design
Libre Engineer is primarily designed for the power user in mind.
It has first class support for the Wren programming language as well as Wasm plugins.
The UI is broken up into workspaces, not unlike [FreeCAD](), but all of the computationally expensive algorithms are handled by Zig instead of a (relatively slow) scripting language.
All custom file formats are saved as XML data and are designed to be accessed by Wren.
Documents such as blueprints and setup sheets are generated through markdown templates, typically abstracted by a GUI.

### Core Libraries
The engineering kernels are built off of a few core libraries that provide reusable pieces of code.

#### Geometry Library
This is the Heart of Libre Engineer. The hope is that it is adopted all around the open source engineering ecosystem.
It provides a few new standardized file formats for representing geometry.
1. '\*.3dpath' format, is extended by the toolpath and cad drawing formats
2. '\*.brepxml' = xml representation of OCCT's [brep format](https://dev.opencascade.org/doc/overview/html/specification__brep_format.html)
3. '\*.cad' xml format, provides a design timeline, standardized features like unmodeled threads, and a reliable way to access geometry through code
    - it also includes other metadata like [PMI](https://www.capvidia.com/blog/what-is-pmi-product-manufacturing-information)

#### Physics Libraries
This is a group of libraries with a standardized api for simulating physics. It is primarily used in the CAM & CAE engineering kernels.
