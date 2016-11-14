cmake_minimum_required(VERSION 3.0)
project(gtest_tp2)


set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O3")
include_directories(build/gtest/src/libgtest/googletest/include)
include_directories(build/gtest/src/libgtest/googlemock/include)

##ckick plugins section##
#ckick plugin: ClangComplete

#ckick plugin: GTest
include(build-gtest.cmake)
##end plugin section##

add_subdirectory(src)
add_subdirectory(test)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(SOURCE_FILES main.cpp)
add_executable(gtest_tp2 ${SOURCE_FILES})