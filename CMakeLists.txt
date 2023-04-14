cmake_minimum_required(VERSION 3.10)

set(this_target NanoLog)
project(${this_target})

set(HEADER_FILES
	NanoLog.hpp
)

set(SOURCE_FILES
	NanoLog.cpp
)

set_source_files_properties(HEADER_FILES PROPERTIES HEADER_FILE_ONLY TRUE)

list(APPEND BUILD_FILES ${HEADER_FILES} ${SOURCE_FILES})

add_library(${this_target} STATIC ${BUILD_FILES})

set_target_properties(${this_target} PROPERTIES FOLDER Libraries)

