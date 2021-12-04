cmake_minimum_required(VERSION 3.0)

SET(CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../../../CMake/Toolchain/)
include(common)

## start setting
SET (this_target NanoLog)
PROJECT(${this_target})


add_definitions(-DUNICODE -D_UNICODE)


## section: include directory
INCLUDE_DIRECTORIES( ${INCLUDE_BASE}
    )

## section: source files
# Add your source files here (one file per line), please SORT in alphabetical order for future maintenance
SET (${this_target}_SOURCE_FILES
    NanoLog.cpp
    )

## section: header files
# Add your header files here(one file per line), please SORT in alphabetical order for future maintenance!
SET(${this_target}_HEADER_FILES
    NanoLog.hpp
    )


SET_SOURCE_FILES_PROPERTIES(${this_target}_HEADER_FILES
                            PROPERTIES HEADER_FILE_ONLY TRUE)
LIST(APPEND ${this_target}_SOURCE_FILES ${${this_target}_HEADER_FILES})


## section: add target

ADD_LIBRARY(${this_target} STATIC ${${this_target}_SOURCE_FILES} )

set_target_properties(${this_target} PROPERTIES FOLDER Libraries)
