cmake_minimum_required(VERSION 3.14 FATAL_ERROR)

# create project
project(NM4P)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# add dependencies
include(cmake/CPM.cmake)
CPMAddPackage("gh:ziotom78/gplotpp#master")
CPMAddPackage("gh:p-ranav/argparse#master")

foreach(loop_var IN ITEMS balle)
  add_executable(${loop_var} ${loop_var}.cpp)

  if (gplotpp_ADDED)
    set(GPLOTPP_INCLUDE_DIR "${gplotpp_SOURCE_DIR}")
    target_include_directories(${loop_var} PUBLIC ${GPLOTPP_INCLUDE_DIR})
  endif()


  if (argparse_ADDED)
    set(ARGPARSE_INCLUDE_DIR "${argparse_SOURCE_DIR}/include")
    target_include_directories(${loop_var} PUBLIC ${ARGPARSE_INCLUDE_DIR})
  endif()

  # link dependencies
  target_link_libraries(${loop_var})
endforeach()
