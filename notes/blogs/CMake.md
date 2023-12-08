# CMAKE 
notes from this blog: https://viblo.asia/p/dao-dau-voi-cmake-thong-qua-vi-du-07LKXNbelV4

make 
Makefiles 
    provide a BUILD SYSTEM 
    but COMPLEX for:
        + nesting projects 
        + multi-platform build

-> CMake born to SOLVE the COMPLEX part 
    -> it GENERATE MAKEFILE for different platform :v

CMakeLists.txt FILE STRUCTURE: 

    CMake lowest version 
        vd: cmake_minimum_required(VERSION 2.8.9)
    Project name 
        vd: project(hello)
    Add header folder to the project 
        vd: include_directories(include)
    Add source files to the project 
        vd: file(GLOB SOURCES "src/*.cpp")
            GLOB SOURCES: store all the file names with the given expression 
                          to the variable "SOURCES"
    Create executable:
        vd: add_executable(hello ${SOURCES})
        ->params: 
            + executable name  
            + source file 
    or 
    Create Library: 
        shared: 
            vd: add_library(test SHARED ${SOURCES})
        static: 

    Install the library: 
        install(...) - check for parameters in the cmake doc 

Build project using CMake:  
    1. Generate make files 
        -> cmake .
    2. Run the make files 
        -> make 
