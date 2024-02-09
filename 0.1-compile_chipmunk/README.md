# Compile Chipmunk

##  Download

[Chipmunk2D Physics - Downloads](https://chipmunk-physics.net/downloads.php)

Download the source code and unzip the .tgz compressed file (assume unzipped it to`D:\prj`)

directory structure:

```
demo/
doc/
include/
msvc/
objectivec/
src/
xcode/
CMakeLists.txt
LICENSE.txt
README.textile
VERSION.txt
```

## Edit `CMakeLists.txt`

edit some options of `CMakeLists.txt`, which is set `OFF` for `BUILD_DEMOS` and `INSTALL_DEMOS`.

```cmake
if(ANDROID)
  option(BUILD_DEMOS "Build the demo applications" OFF)
  option(INSTALL_DEMOS "Install the demo applications" OFF)
  option(BUILD_SHARED "Build and install the shared library" ON)
  option(BUILD_STATIC "Build as static library" ON)
  option(INSTALL_STATIC "Install the static library" OFF)
else()
  option(BUILD_DEMOS "Build the demo applications" OFF)
  option(INSTALL_DEMOS "Install the demo applications" OFF)
  option(BUILD_SHARED "Build and install the shared library" ON)
  option(BUILD_STATIC "Build as static library" ON)
  option(INSTALL_STATIC "Install the static library" ON)
endif()
```

## Build It

Execute the command `cmake -B build -G "MinGW Makefiles".`

It's OK to add `-D CMAKE_BUILD_TYPE=Release`, but it can be specified in `CMakeLists.txt`.

Into the `build`folder，execute `mingw32-make`.

After compiling, the content of `src` as follow:

```
CMakeFiles/
cmake_install.cmake
libchipmunk.a
libchipmunk.dll
libchipmunk.dll.a
Makefile
```

Then it is enable to compile code in this command:

`gcc .\main.c -o main.exe -L. -Ichipmunk -llibchipmunk`
