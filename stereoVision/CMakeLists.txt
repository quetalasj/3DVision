cmake_minimum_required(VERSION 3.22)
project(3DVision)

set(CMAKE_CXX_STANDARD 17)

find_package(OpenCV REQUIRED)
find_package(Pangolin REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})
include_directories("/usr/include/eigen3")
add_executable(stereoVision stereoVision.cpp)
target_link_libraries(stereoVision ${OpenCV_LIBS} ${Pangolin_LIBRARIES})
#
file(COPY left.png right.png DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
