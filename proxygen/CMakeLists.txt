cmake_minimum_required(VERSION 3.0)
project(proxygen)

set(CMAKE_CXX_COMPILER clang++)
set(CMAKE_C_COMPILER clang)

set(CMAKE_CXX_FLAGS "-std=c++14 -fcolor-diagnostics")

include_directories(${proxygen_SOURCE_DIR}/..)

add_subdirectory(lib)
