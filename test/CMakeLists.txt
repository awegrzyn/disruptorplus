add_executable(bench benchmark.cpp)
target_compile_options(bench PRIVATE -Wno-interference-size -Wall -pedantic -Wextra -O3)
target_compile_features(bench PRIVATE cxx_std_23)
target_include_directories(bench PRIVATE ../include)
