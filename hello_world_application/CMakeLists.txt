cmake_minimum_required(VERSION 3.10)
project(hello_world)

# creating an executable from source
add_executable(hello_world ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp)

# building formatter_ex separately
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib ${CMAKE_CURRENT_BINARY_DIR}/formatter_ex_lib)

# let the compiler know where is the .h file
target_include_directories(hello_world PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)

# linking with formatter_ex
target_link_libraries(hello_world PRIVATE formatter_ex)
