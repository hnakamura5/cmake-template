cmake_minimum_required(VERSION 3.6)

project(template_project CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_COMPILER "/usr/local/bin/clang++")
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_CXX_FLAGS_RELEASE "-O2 -Wall")
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -g3 -Wall")
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS_DEBUG})

include_directories(${PROJECT_SOURCE_DIR}/include)
set(INSTALL_DIR ${PROJECT_SOURCE_DIR}/bin)

add_subdirectory(lib)
add_subdirectory(src)
add_subdirectory(test)
