cmake_minimum_required(VERSION 3.6)

project(cmake-template CXX)

IF(NOT MSVC)
set(CMAKE_C_COMPILE "clang")
set(CMAKE_CXX_COMPILER "clang++")
set(CMAKE_AR "llvm-ar")
set(CMAKE_LINKER "lld")
set(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS_DEBUG})
set(CMAKE_C_FLAGS_RELEASE "-O2 -Weverything -Werror -stdlib=libc")
set(CMAKE_C_FLAGS_DEBUG "-O0 -g3 -Weverything -Werror -stdlib=libc")
set(CMAKE_C_FLAGS ${CMAKE_C_FLAGS_DEBUG})
ENDIF()

IF(MSVC)
include_directories($ENV{CPLUS_INCLUDE_PATH})
include_directories($ENV{C_INCLUDE_PATH})
link_directories($ENV{LD_LIBRARY_PATH})
set(CMAKE_CXX_FLAGS "-W4 -WX -EHsc")
set(CMAKE_C_FLAGS "-W4 -WX")
ENDIF()

include_directories(${PROJECT_SOURCE_DIR}/include)
set(INSTALL_DIR ${PROJECT_SOURCE_DIR}/bin)

add_subdirectory(lib)
add_subdirectory(src)
add_subdirectory(test)
