# Set minimum CMake version
cmake_minimum_required(VERSION 3.12)

# Set CMake project name
project("vtk-playground")

# Load VTK package
find_package(VTK REQUIRED)
include(${VTK_USE_FILE})

# Include sub-projects.
add_subdirectory("CyclinderExample")