CMAKE_MINIMUM_REQUIRED(VERSION 3.11.0 FATAL_ERROR)

project(Distruptor
  VERSION 0.0.1
  LANGUAGES CXX
)

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  set(CMAKE_BUILD_TYPE "RelWithDebInfo")
endif()


add_subdirectory(test)
add_subdirectory(benchmark)
