cmake_minimum_required(VERSION 2.8)
#project name
set(PROJECT_NAME_STR LowPassFilter)
project(${PROJECT_NAME_STR} C CXX)

SET(CMAKE_CXX_FLAGS "-g -Wall -std=c++11")

## Debug definition: ##
if(CMAKE_BUILD_TYPE STREQUAL "Debug")
  add_definitions("-DDEBUG")
endif()

##############################################################################

# sources
file(GLOB_RECURSE HPP_SOURCES RELATIVE ${PROJECT_SOURCE_DIR} FOLLOW_SYMLINKS include/*.hpp config/*.hpp)
file(GLOB_RECURSE CPP_SOURCES RELATIVE ${PROJECT_SOURCE_DIR} FOLLOW_SYMLINKS src/*.cpp)


# add the library
add_library(low_pass_filter STATIC ${HPP_SOURCES} ${CPP_SOURCES})

