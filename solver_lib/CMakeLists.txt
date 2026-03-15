cmake_minimum_required(VERSION 3.10)
project(solver_lib)

# creaing a static library from source file
add_library(solver_lib STATIC ${CMAKE_CURRENT_SOURCE_DIR}/solver.cpp)

# let the compiler know where is the .h file
target_include_directories(solver_lib PRIVATE ${CMAKE_CURRENT_SOURCE_DIR})
