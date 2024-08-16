cmake_minimum_required(VERSION 3.10)

# Set the project name and version
project(GlistShaderToHeader VERSION 1.0)

# Specify the C++ standard
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# Add the source directory
add_executable(GlistShaderToHeader src/ShaderToHeader.cpp)

if(CMAKE_SYSTEM_NAME STREQUAL "Linux")
    message(STATUS "Configuring for Linux x86_64")
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -m64")
elseif(CMAKE_SYSTEM_NAME STREQUAL "Darwin")
    message(STATUS "Configuring for macOS")
    # Set architecture to both x86_64 and arm64 if you want a universal binary
    set(CMAKE_OSX_ARCHITECTURES "x86_64;arm64")
elseif(CMAKE_SYSTEM_NAME STREQUAL "Windows")
    message(STATUS "Configuring for Windows x86_64")
    set(CMAKE_GENERATOR_PLATFORM x64)
endif()