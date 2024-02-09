cmake_minimum_required(VERSION 3.5)

set(CMAKE_C_COMPILER "D:/devel_space/physics_simulation/mingw32/bin/gcc.exe")
set(CMAKE_CXX_COMPILER "D:/devel_space/physics_simulation/mingw32/bin/g++.exe")

project(chipmunk_demo)

set(CHIPMUNK_DLL_DIR "D:/devel_space/physics_simulation/chipmunk/bin")
set(CHIPMUNK_LIB_DIR "D:/devel_space/physics_simulation/chipmunk/lib")

link_directories(${CHIPMUNK_LIB_DIR})

set(FRAMEWORK_LIBS chipmunk)

include_directories("D:/devel_space/physics_simulation/chipmunk/include")

add_executable(chipmunk_demo main.c)

target_link_libraries(chipmunk_demo ${FRAMEWORK_LIBS})