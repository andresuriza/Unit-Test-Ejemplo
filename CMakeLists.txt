cmake_minimum_required(VERSION 3.23)
project(test_tuto)

set(CMAKE_CXX_FLAGS "-fprofile-arcs -ftest-coverage")

enable_testing()

add_subdirectory(test)
include_directories(${gtest_SOURCE_DIR}/include ${gtest_SOURCE_DIR})
include_directories(${gmock_SOURCE_DIR}/include ${gmock_SOURCE_DIR})

add_executable(test_tuto testing_main.cpp)

target_link_libraries(test_tuto
        gtest
        gtest_main
        gmock_main)
