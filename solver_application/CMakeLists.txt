cmake_minimum_required(VERSION 3.10)
project(solver)

# creating an executable from source
add_executable(solver ${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp)

# linking with formatter_ex and solver_lib
target_link_libraries(solver PRIVATE formatter_ex solver_lib)
