cmake_minimum_required (VERSION 2.6)
cmake_policy(SET CMP0012 NEW)
Project(Chapter2)
#Require OpenCV
FIND_PACKAGE( OpenCV 3.0.0 REQUIRED)
#FIND_PACKAGE( OpenCV 3.0.0 REQUIRED core) #To include only core functinalities, otherwise include all submodules
#Show a message with the opencv version detected
MESSAGE("OpenCV version : ${OpenCV_VERSION}")
include_directories(${OpenCV_INCLUDE_DIRS})
link_directories(${OpenCV_LIB_DIR})

add_subdirectory(utils)

#Add optional log with a precompiler definition
option(WITH_LOG "Build with output logs and images in tmp" OFF)
if(WITH_LOG)
    add_definitions(-DLOG)
endif(WITH_LOG)
#generate our new executable
ADD_EXECUTABLE( ${PROJECT_NAME} main.cpp)
#Link our library
TARGET_LINK_LIBRARIES( ${PROJECT_NAME} ${OpenCV_LIBS} Utils)