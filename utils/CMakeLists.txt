#Add new variable for src utils lib
SET(UTILS_LIB_SRC
    computerTime.cpp
    logger.cpp
    plotting.cpp
    )
#create our new utils lib
add_library( Utils ${UTILS_LIB_SRC})
#Link our library
TARGET_LINK_LIBRARIES( Utils PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})