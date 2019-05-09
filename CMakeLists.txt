cmake_minimum_required (VERSION 2.8.11)
project (transforms)

find_package(Eigen3 REQUIRED)

add_library(transforms INTERFACE)
target_include_directories(transforms INTERFACE include)
