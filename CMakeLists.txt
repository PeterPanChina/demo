cmake_minimum_required(VERSION 3.15)
project(demo)

set(CMAKE_CXX_STANDARD 14)

project(demo)
set(googleTestDir ./googletest)

#Add the google test subdirectory
add_subdirectory(${googleTestDir})
#include googletest/include dir
include_directories(${googleTestDir}/googletest/include)
#include the googlemock/include dir
include_directories(${googleTestDir}/googlemock/include)

find_package(GTEST REQUIRED)

add_executable(${PROJECT_NAME} main.cpp)

target_link_libraries(${PROJECT_NAME} ${GTEST_LIBRARIES})
