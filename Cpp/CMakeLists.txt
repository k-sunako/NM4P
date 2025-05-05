cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

# create project
project(NM4P)

# add executable
add_executable(main test-plot.cpp)

# add dependencies
include(cmake/CPM.cmake)

CPMAddPackage("gh:ziotom78/gplotpp#master")
if (gplotpp_ADDED)
    set(GPLOTPP_INCLUDE_DIR "${gplotpp_SOURCE_DIR}")
    target_include_directories(main PUBLIC ${GPLOTPP_INCLUDE_DIR})
endif()

# link dependencies
target_link_libraries(main)
