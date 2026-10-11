# GPUOpen-radeon_gpu_analyzer - AMD Direct3D 11 GSA shader compile extension C++ headers

This is a `build2` package repository for
[`radeon_gpu_analyzer`](https://github.com/GPUOpen-Tools/radeon_gpu_analyzer),
the Radeon GPU Analyzer (RGA) compiler and code analysis tool. It packages
the headers of the GSA shader compile extension of the AMD Direct3D 11 driver
that RGA uses to compile Direct3D 11 shaders for AMD GPUs.

This file contains setup instructions and other details that are more
appropriate for development rather than consumption. If you want to use
`libamddxgsa` in your `build2`-based project, then instead see the accompanying
[`PACKAGE-README.md`](libamddxgsa/PACKAGE-README.md) file.

The development setup for `GPUOpen-radeon_gpu_analyzer` uses the standard `bdep`-based workflow.
For example:

```
git clone .../GPUOpen-radeon_gpu_analyzer.git
cd GPUOpen-radeon_gpu_analyzer

bdep init -C @gcc cc config.cxx=g++
bdep update
bdep test
```
