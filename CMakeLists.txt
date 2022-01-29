cmake_minimum_required(VERSION 3.22)
project(
    MyCppyyLib
    VERSION 0.0.1 
    LANGUAGES CXX
)
set(CMAKE_CXX_STANDARD_REQUIRED 17)

find_package(Python3 COMPONENTS Interpreter)
set(CPPYY_MODULE_PATH "${Python3_SITELIB}/cppyy_backend/cmake")
list(APPEND CMAKE_MODULE_PATH "${CPPYY_MODULE_PATH}")
message("modules path:" ${CMAKE_MODULE_PATH})
find_package(Cppyy)

add_library(mylib SHARED src/mylib.cpp src/mylib.hpp)

cppyy_add_bindings(
    mylibbindings
    "0.0.1"
    "Gabriel Kabbe"
    "gabriel.kabbe@mail.de"
    LINK_LIBRARIES mylib
    H_FILES src/mylib.hpp
)