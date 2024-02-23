cmake_minimum_required(VERSION 3.6.0)
project(test)

set(CMAKE_EXE_LINKER_FLAGS "-static-libgcc -static-libstdc++")
set(DCMAKE_BUILD_TYPE "Debug")
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -g")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -g")

add_executable(test main.cpp)