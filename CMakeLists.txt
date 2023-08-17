cmake_minimum_required(VERSION 3.10)

project(main)

set(SRC_DIR "${CMAKE_CURRENT_SOURCE_DIR}")

include_directories(${SRC_DIR}/physics)
include_directories(${SRC_DIR}/libgraphics)


get_property(dirs DIRECTORY ${CMAKE_SOURCE_DIR} PROPERTY INCLUDE_DIRECTORIES)
message(">>> include_dirs=${SRC_DIR};${dirs}")


file(GLOB SOURCES
    "${SRC_DIR}/*.h"
    "${SRC_DIR}/*.c"
    "${SRC_DIR}/physics/*.h"
    "${SRC_DIR}/physics/*.c"
    "${SRC_DIR}/libgraphics/*.h"
    "${SRC_DIR}/libgraphics/*.c"
)

add_executable(
    ${PROJECT_NAME}
    ${SOURCES}
)
