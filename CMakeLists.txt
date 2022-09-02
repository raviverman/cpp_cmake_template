cmake_minimum_required(VERSION 3.10)
# specify the C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# project name
project(project-name VERSION 0.0.1)

# set directory for binaries
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bld)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)

# create shared libraries
add_library(helper SHARED src/helper.cpp)

# add the executable
add_executable(main src/main.cpp)
target_link_libraries(main PUBLIC helper)