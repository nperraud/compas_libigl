cmake_minimum_required(VERSION 3.12)
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)

#Eigen
find_package (Eigen3 3.3 REQUIRED NO_MODULE)

#Pybind11
set(PYBIND11_CPP_STANDARD -std=c++11)
set(PYBIND11_PYTHON_VERSION 3.6)
set(PYTHON_EXECUTABLE "$ENV{HOME}/anaconda3/bin/python3.6")
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/ext/pybind11)

#Libigl
option(LIBIGL_WITH_TRIANGLE  "Use Triangle" ON)
find_package(LIBIGL REQUIRED)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/src)