cmake_minimum_required(VERSION 3.10)
project(solver)

# creating an executable from source
add_executable(solver ${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp)

# building formatter_ex separately
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib ${CMAKE_CURRENT_BINARY_DIR}/formatter_ex_lib)

# building solver_lib separately
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib ${CMAKE_CURRENT_BINARY_DIR}/solver_lib)

# let the compiler know where are the .h files
target_include_directories(solver PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)
target_include_directories(solver PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib)

# linking with formatter_ex and solver_lib
target_link_libraries(solver PRIVATE formatter_ex PRIVATE solver_lib)
