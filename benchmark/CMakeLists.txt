CMAKE_MINIMUM_REQUIRED(VERSION 3.11.0 FATAL_ERROR)

project(Distruptor
  VERSION 0.0.5
  LANGUAGES CXX
)

if(NOT CMAKE_BUILD_TYPE AND NOT CMAKE_CONFIGURATION_TYPES)
  set(CMAKE_BUILD_TYPE "RelWithDebInfo")
endif()

set(EXAMPLES
  diamond.cpp
  multicast.cpp
  pipeline.cpp
  sequencer.cpp
  unicast.cpp
)

foreach (example ${EXAMPLES})
  get_filename_component(example_name ${example} NAME)
  string(REGEX REPLACE ".cpp" "" example_name ${example_name})
  add_executable(${example_name} ${example})
  target_compile_options(${example_name} PRIVATE -Wno-interference-size -Wall -pedantic -Wextra -O3)
  target_compile_features(${example_name} PRIVATE cxx_std_23)
  target_include_directories(${example_name} PRIVATE ../include)

endforeach()
