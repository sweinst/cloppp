cmake_minimum_required(VERSION 3.21)
set(CMAKE_CXX_STANDARD 20)

project(clop__)

option(BUILD_TESTS "Do not build tests by default" OFF)
option(BUILD_EXAMPLES "Do not build examples by default" OFF)

if(BUILD_TESTING)
    add_subdirectory(tests)
endif()
if(BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()

add_executable(clop__ main.cpp include/clop++/clop++.h)
