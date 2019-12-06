cmake_minimum_required (VERSION 3.5)

project(hello VERSION 1.0.0 LANGUAGES CXX)

add_library(${PROJECT_NAME} 
		hello.h 
		hello.cpp
	)

set_target_properties(${PROJECT_NAME} PROPERTIES CXX_STANDARD 14)

target_include_directories (${PROJECT_NAME}
	PUBLIC
	     $<INSTALL_INTERFACE:/${PROJECT_NAME}>
	     $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/>
	PRIVATE
	      # add extra include path which are specific to this project here,
	      # for example, if we have include files in src, put them here by:
	      # ${CMAKE_CURRENT_SOURCE_DIR}/src
	)
