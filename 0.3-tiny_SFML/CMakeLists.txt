cmake_minimum_required(VERSION 3.5)

set(CMAKE_C_COMPILER "D:/devel_space/physics_simulation/mingw32/bin/gcc.exe")
set(CMAKE_CXX_COMPILER "D:/devel_space/physics_simulation/mingw32/bin/g++.exe")

project(tiny_SFML)

# set(CMAKE_CXX_FLAGS "-mwindows")
# option(BUILD_SHARED_LIBS "Build shared libraries" OFF)

set(SFML_DIR "../SFML-2.6.1/lib/cmake/SFML")

# set(SFML_STATIC_LIBRARIES TRUE)

find_package(SFML 2.6.1 COMPONENTS graphics window system REQUIRED)

link_libraries(sfml-graphics sfml-window sfml-system)

include_directories("../SFML-2.6.1/include")

add_executable(tiny_SFML main.cpp)

target_link_libraries(tiny_SFML sfml-graphics sfml-window sfml-system)

# install(TARGETS tiny_SFML)