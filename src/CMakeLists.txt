cmake_minimum_required(VERSION 2.8.2)

project(ArmVm_Exe)

# Get the source files (could use GLOB_RECURSE)
file(GLOB ArmVm_SOURCES "*.cpp")

# Add includes
include_directories("../inc/")

# Compiler flags
if( CMAKE_CXX_COMPILER_ID MATCHES "Clang" )
    set( CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -g -std=c++14 -stdlib=libc++" )
else()
    set( CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -g -std=c++14" )
endif()

add_executable(armvm ${ArmVm_SOURCES})
