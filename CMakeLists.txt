cmake_minimum_required(VERSION 3.22)
project(
    MyCppyyLib
    VERSION 0.0.1 
    LANGUAGES CXX
)
set(CMAKE_CXX_STANDARD_REQUIRED 17)

find_package(Python3 COMPONENTS Interpreter)
message("Found:" ${Python3_SITELIB})

add_library(mylib SHARED src/mylib.cpp src/mylib.hpp)