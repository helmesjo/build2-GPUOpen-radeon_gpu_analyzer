# GPUOpen-radeon_gpu_analyzer - <SUMMARY>

This is a `build2` package repository for [`GPUOpen-radeon_gpu_analyzer`](https://<UPSTREAM-URL>),
a <SUMMARY-OF-FUNCTIONALITY>.

This file contains setup instructions and other details that are more
appropriate for development rather than consumption. If you want to use
`GPUOpen-radeon_gpu_analyzer` in your `build2`-based project, then instead see the accompanying
[`PACKAGE-README.md`](<PACKAGE>/PACKAGE-README.md) file.

The development setup for `GPUOpen-radeon_gpu_analyzer` uses the standard `bdep`-based workflow.
For example:

```
git clone .../GPUOpen-radeon_gpu_analyzer.git
cd GPUOpen-radeon_gpu_analyzer

bdep init -C @gcc cc config.cxx=g++
bdep update
bdep test
```
