# RocketSim
A rocket control system simulator using the [bullet3](https://github.com/bulletphysics/bullet3) physics engine.

### Building this project
This project relies on [vcpkg](https://learn.microsoft.com/en-gb/vcpkg/get_started/overview) and cmake. Once you've pulled the repository, assuming they are both installed, it _should_ just work and pull the required packages when running cmake.  
To build this project, first make sure to change the value of `VCPKG_ROOT` in `CMakeUserPresets.json` to your local install of vcpkg.

This project has been tested to build on Windows x86-64 with VS2022. 

 --- 

 Made for SUSF Starworks' software team