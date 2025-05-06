cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

# create project
project(NM4P)

# add executable
add_executable(main balle.cpp)

# add dependencies
include(cmake/CPM.cmake)

CPMAddPackage("gh:ziotom78/gplotpp#master")
if (gplotpp_ADDED)
    set(GPLOTPP_INCLUDE_DIR "${gplotpp_SOURCE_DIR}")
    target_include_directories(main PUBLIC ${GPLOTPP_INCLUDE_DIR})
endif()

CPMAddPackage("gh:p-ranav/argparse#master")
if (argparse_ADDED)
    set(ARGPARSE_INCLUDE_DIR "${argparse_SOURCE_DIR}/include")
    target_include_directories(main PUBLIC ${ARGPARSE_INCLUDE_DIR})
endif()

# link dependencies
target_link_libraries(main)
