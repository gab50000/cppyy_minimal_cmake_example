# Minimum CMake project for Cppyy

This repository shows how to use CMake with Cppyy in order to build a Python extension which provides bindings for a C++ library.

## Preparations

Ensure that all necessary libraries are installed:

```
pip install -r requirements.txt
```

## Build the extension

First you need to compile your C++ library and create the C++-Wrapper package:

```
mkdir build && cd build
cmake ..
make mylibbindingsCppyy
```

Within the build directory you should find a folder mylibbindings and a setup.py file.

## Install the extension

```
pip install .
```

## Try out the extension

Start python and type:

```python
import mylibbindings

x = mylibbindings.SomeClass()
print(x.f(1, 2))
```
