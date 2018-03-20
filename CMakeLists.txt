project(jitify_reproducer)
cmake_minimum_required(VERSION 3.4)

set(JITIFY_REPRODUCER_ROOT_SOURCE_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})
set(JITIFY_REPRODUCER_ROOT_BINARY_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR})

include(blt/SetupBLT.cmake)
set(CMAKE_CXX_STANDARD 11)
set(BLT_CXX_STANDARD 11)
set(BLT_CUDA_FLAGS "${BLT_CUDA_FLAGS} -std=c++11")
include_directories(${CMAKE_CURRENT_SOURCE_DIR})
blt_add_executable(NAME oops.exe
  SOURCES jitify_example.cu
  DEPENDS_ON cuda)
