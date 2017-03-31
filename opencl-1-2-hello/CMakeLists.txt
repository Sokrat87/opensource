project(opencl-1-2-hello)
cmake_minimum_required(VERSION 3.1)

find_package(OpenCL REQUIRED)

include_directories(${OpenCL_INCLUDE_DIRS})

add_executable(${PROJECT_NAME} ${PROJECT_SOURCE_DIR}/src/hello.cpp )
target_link_libraries(${PROJECT_NAME} ${OpenCL_LIBRARIES})
  
configure_file(${PROJECT_SOURCE_DIR}/src/hello.cl ${CMAKE_CURRENT_BINARY_DIR}/hello.cl COPYONLY)
