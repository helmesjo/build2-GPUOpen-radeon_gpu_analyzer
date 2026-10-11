# libamddxgsa - AMD Direct3D 11 GSA shader compile extension C++ headers

This is a `build2` package for the
[`radeon_gpu_analyzer`](https://github.com/GPUOpen-Tools/radeon_gpu_analyzer)
C++ library. It provides the headers of the GSA shader compile extension of
the AMD Direct3D 11 driver, which the Radeon GPU Analyzer (RGA) uses to
compile Direct3D shader bytecode (DXBC) or AMD IL text for a target AMD GPU
without that GPU being installed. The compiled shader is returned as an ELF
object with the AMD IL and GPU ISA binaries, their disassembly, and the
shader's register and memory usage statistics.


## Usage

To start using `libamddxgsa` in your project, add the following `depends`
value to your `manifest`, adjusting the version constraint as appropriate:

```
depends: libamddxgsa ^2.15.0
```

Then import the library in your `buildfile`:

```
import libs = libamddxgsa%lib{amddxgsa}
```


## Importable targets

This package provides the following importable targets:

```
lib{amddxgsa}
```

The shader compile extension header and the AMD GPU chip identifiers, both
included with their upstream subdirectory prefix
(`#include <GSA/AmdDxGsaCompile.h>` and `#include <AsicReg/devices.h>`).

This package is headers only. The `AmdDxGsaCompileShader()` and
`AmdDxGsaFreeCompiledShader()` functions declared in `AmdDxGsaCompile.h` are
exported by the AMD Direct3D 11 driver DLL (`atidxx64.dll` or
`atidxx32.dll`), which is not included, so they cannot be linked against.
Instead, load the driver DLL at runtime with `LoadLibrary()` and resolve the
functions with `GetProcAddress()` using the `PfnAmdDxGsaCompileShader` and
`PfnAmdDxGsaFreeCompiledShader` function pointer types declared in the header.

As in upstream, `AmdDxGsaCompile.h` includes `<windows.h>` and so is only
usable on Windows. `devices.h` defines the chip family (`FAMILY_*`) and
revision values for the `chipFamily` and `chipRevision` members of
`AmdDxGsaCompileShaderInput` and is usable on all platforms. It can only be
included once per translation unit since not all of its declarations are
covered by include guards.


## Configuration variables

This package provides no configuration variables.
