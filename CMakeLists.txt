cmake_minimum_required(VERSION 3.20.0)
project(gl_project VERSION 0.1.0)

set(CMAKE_CXX_EXTENSIONS off)
set(CMAKE_C_EXTENSIONS off)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_C_STANDARD 17)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/exe)

find_package(glfw3 REQUIRED)

file(GLOB_RECURSE SRC src/*.cpp src/*.c main.cpp)
add_executable(gl_project ${SRC})

target_include_directories(gl_project PUBLIC src)

target_link_libraries(gl_project opengl32)
target_link_libraries(gl_project glfw)