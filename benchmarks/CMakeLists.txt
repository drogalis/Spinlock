# ==============================================================
# Benchmarks
# ==============================================================

cmake_minimum_required(VERSION 3.20)
project(SpinlockBenchmark)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)
include(GNUInstallDirs)

include_directories(${CMAKE_CURRENT_SOURCE_DIR})

cmake_path(GET CMAKE_CURRENT_SOURCE_DIR PARENT_PATH PARENT_DIR)

# Add a testing executable
add_executable(${PROJECT_NAME} spinlock-benchmark.cpp)

target_include_directories(${PROJECT_NAME} PRIVATE ${PARENT_DIR}/include)

include(${PARENT_DIR}/cmake/CompilerWarnings.cmake)

myproject_set_project_warnings(${PROJECT_NAME} TRUE "X" "" "" "X")

add_compile_options(-pipe -fPIC)

