cmake_minimum_required(VERSION 3.16...4.1.1 FATAL_ERROR)

#--------------------------------------------------------------------
# Project and version.
#--------------------------------------------------------------------

project(glad)

if (CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
  set(GLAD_IS_TOP_LEVEL ON)
else()
  set(GLAD_IS_TOP_LEVEL OFF)
endif()

#--------------------------------------------------------------------
# Configure variables for the library   
#--------------------------------------------------------------------

set(GLAD_LIB_NAME "glad")

set(GLAD_TARGET_NAME  ${GLAD_LIB_NAME})
set(GLAD_SOURCE_FILE "src/glad.c")
set(GLAD_INCLUDE_FILE "include/glad.h")

#--------------------------------------------------------------------
# Build library
#--------------------------------------------------------------------

add_library(${GLAD_LIB_NAME})
target_sources(${GLAD_LIB_NAME} PRIVATE ${GLAD_SOURCE_FILE})
target_include_directories(${GLAD_TARGET_NAME} PUBLIC
 $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>)