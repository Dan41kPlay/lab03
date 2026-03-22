cmake_minimum_required(VERSION 3.10)
project(hello_world)

# creating an executable from source
add_executable(hello_world ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp)

# linking with formatter_ex
target_link_libraries(hello_world PRIVATE formatter_ex)
