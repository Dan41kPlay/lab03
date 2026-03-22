cmake_minimum_required(VERSION 3.10)
project(formatter_ex)

# creating a static library from source file
add_library(formatter_ex STATIC ${CMAKE_CURRENT_SOURCE_DIR}/formatter_ex.cpp)

# let the compiler know where is the .h file
target_include_directories(formatter_ex PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})

# linking with formatter
target_link_libraries(formatter_ex PUBLIC formatter)
