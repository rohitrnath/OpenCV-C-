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
#Create a variable called SRC
SET(SRC main.cpp
        utils.cpp
        colors.cpp
        )
#Create our executable
ADD_EXECUTABLE( ${PROJECT_NAME} ${SRC})
#Link our library
TARGET_LINK_LIBRARIES( ${PROJECT_NAME} ${OpenCV_LIBS})