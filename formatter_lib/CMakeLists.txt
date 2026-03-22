cmake_minimum_required(VERSION 3.10)
project(formatter)

# creaing a static library from source file
add_library(formatter STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter.cpp)

# let the compiler know where is the .h file
target_include_directories(formatter PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
