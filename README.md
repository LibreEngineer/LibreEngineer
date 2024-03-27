
# Libre Engineer
A FOSS alternative to many industry-standard engineering solutions.
Highly extensible through the [Wren](https://wren.io/) scripting language.
Custom engineering kernels for CAD, CAM, & CAE.

## Goals
The primary goal of Libre Engineer is to bring industry level engineering solutions to the open source ecosystem.
Because of that, it is organized such that you can easily include it's libraries into your own projects.

## Design
Libre Engineer is primarily designed for the power user in mind.
It has first class support for the Wren programming language as well as Wasm plugins.
All custom file formats are saved as XML data and are designed to be accessed by Wren.

### Core Libraries
The engineering kernels are built off of a few core libraries that provide reusable pieces of code.

#### Geometry Library
This is the Heart of Libre Engineer. The hope is that it is adopted all around the open source engineering ecosystem.
It provides a few new standardized file formats for cad & 3d modeling.
1. '\*.3dpath' file, used for representing toolpaths and sketches (as a child of that parent file format)
    - the parent drawing file for instance, provides other things like constraints (defined in the CAD engineering library)
3. '\*.cad' file, provides a design timeline for a product and standardized features like unmodeled threads
    - it also includes other metadata like [PMI](https://www.capvidia.com/blog/what-is-pmi-product-manufacturing-information)
