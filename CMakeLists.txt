cmake_minimum_required(VERSION 3.6)

project(OptPy CXX)

set(CLANG_PATH "/usr/local/bin")
set(CMAKE_C_COMPILE "${CLANG_PATH}/clang")
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_COMPILER "${CLANG_PATH}/clang++")
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_AR "${CLANG_PATH}/llvm-ar")
set(CMAKE_LINKER "${CLANG_PATH}/llvm-ld")

set(CMAKE_CXX_FLAGS_RELEASE "-O2 -Wall")
set(CMAKE_CXX_FLAGS_DEBUG "-O0 -g3 -Wall")
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS_DEBUG})

set(CMAKE_C_FLAGS_RELEASE "-O2 -Wall -stdlib=libc")
set(CMAKE_C_FLAGS_DEBUG "-O0 -g3 -Wall -stdlib=libc")
set(CMAKE_C_FLAGS ${CMAKE_C_FLAGS_DEBUG})

include_directories(${PROJECT_SOURCE_DIR}/include)
set(INSTALL_DIR ${PROJECT_SOURCE_DIR}/bin)

add_subdirectory(lib)
add_subdirectory(src)
add_subdirectory(test)
