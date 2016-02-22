cmake_minimum_required(VERSION 3.3)
project(arrayfire1)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
include_directories("/usr/local/include/")

# find arrayfire library and add its include directory
FIND_PACKAGE(ArrayFire REQUIRED)
INCLUDE_DIRECTORIES(${ArrayFire_INCLUDE_DIRS})

set(SOURCE_FILES main.cpp)
add_executable(arrayfire1 ${SOURCE_FILES})

# link arrayfire lib to executable
TARGET_LINK_LIBRARIES(arrayfire1 ${ArrayFire_LIBRARIES} )
