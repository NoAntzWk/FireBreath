
# Written to work with cmake 2.6
cmake_minimum_required (VERSION 2.6)
set (CMAKE_BACKWARDS_COMPATIBILITY 2.6)

include(${CMAKE_DIR}/paths.cmake)

Project (NPAPIHost)
message ("Generating project ${PROJECT_NAME}")

include_directories(
	${CMAKE_CURRENT_SOURCE_DIR}
    ${FIREBREATH_CONFIG_DIR}
    ${BOOST_SOURCE_DIR}
    ${SCRIPTINGCORE_SOURCE_DIR}
    ${NPAPIPLUGIN_SOURCE_DIR}
    ${GECKOSDK_SOURCE_DIR}
    )

file (GLOB GENERAL RELATIVE ${CMAKE_CURRENT_SOURCE_DIR}
    *.cpp
    *.h
    )

set (SOURCES
    ${GENERAL}
    )

add_library(NPAPIHost STATIC ${SOURCES})