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
