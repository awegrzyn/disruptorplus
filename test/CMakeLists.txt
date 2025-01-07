CMAKE_MINIMUM_REQUIRED(VERSION 3.11.0 FATAL_ERROR)

project(Distruptor
  VERSION 0.0.5
  LANGUAGES CXX
)

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  set(CMAKE_BUILD_TYPE "RelWithDebInfo")
endif()


add_executable(bench benchmark.cpp)
target_compile_options(bench PRIVATE -Wno-interference-size -Wall -pedantic -Wextra -O3)
target_compile_features(bench PRIVATE cxx_std_23)
target_include_directories(bench PRIVATE ../include)
