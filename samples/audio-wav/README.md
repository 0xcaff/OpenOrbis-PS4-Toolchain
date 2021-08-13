# Sample: audio-wav

[![Version](https://img.shields.io/badge/Version-1.00-brightgreen.svg)](https://github.com/Cryptogenic/OpenOrbis-PS4-Toolchain)

This project contains example code for decoding and playing a 16-bit signed PCM (stereo / dual-channel).

- **Title ID**: BREW00080
- **Content ID**: IV0000-BREW00080_00-AUDIOWAVEX000000



## Directory structure
```
samples/audio-wav
|-- assets
    |-- audio
        |-- lets_go_go_go_tigerblood_jewel.wav    // wav file to decode and display
|-- audio-wav
    |-- x64
        |-- Debug                                 // Object files / intermediate directory
    |-- audio-wav.vcxproj                         // Visual studio project files
    |-- audio-wav.vcxproj.filters
    |-- audio-wav.cvxproj.user
    |-- build.bat                                 // Batch file for building on Windows
    |-- main.cpp                                  // Main source file
    |-- wav.cpp                                   // Contains definition for wav data to play
|-- sce_module                                    // Dependency modules for the pkg
    |-- libSceFios2.prx
    |-- libc.prx
|-- sce_sys                                       // Package materials (metadata)
    |-- about
        |-- right.prx
    |-- icon0.png
    |-- param.sfo
|-- eboot.bin                                     // Final eboot (not present until built)
|-- audio-wav.sln                                 // Visual studio solution file
|-- Makefile                                      // Make rules for building on Linux
|-- pkg.gp4                                       // Package project file
```
The ELF, Orbis ELF (OELF), and object files will all be stored in the intermediate directory `x64/Debug`. The final eboot.bin file will be found in the root directory.



## Libraries used

- libc
- libkernel
- libSceAudioOut
- libSceUserService



## Building

A visual studio project has been included for building on Windows. On Linux, a makefile has been included.

To build this project, the developer will need clang, which is provided in the toolchain. The `OO_PS4_TOOLCHAIN` environment variable will also need to be set to the root directory of the SDK installation.

__Windows__
Open the Visual Studio project and build, or run the batch file from command prompt or powershell with the following command:
```
.\build.bat .\x64\Debug "hello_world" "%OO_PS4_TOOLCHAIN%\\samples\\hello_world"
```

__Linux__
Run the makefile.
```
make
```



## Author(s)

- znullptr
- Specter

## Additional credit

- David Reid for the [wav decoding header library](https://mackron.github.io/dr_wav)
