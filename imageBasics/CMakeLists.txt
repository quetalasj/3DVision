cmake_minimum_required(VERSION 3.22)
project(3DVision)

set(CMAKE_CXX_STANDARD 17)

find_package(OpenCV REQUIRED)
include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(imageBasics imageBasics.cpp)
target_link_libraries(imageBasics ${OpenCV_LIBS})

add_executable(undistortedImage undistortedImage.cpp)
target_link_libraries(undistortedImage ${OpenCV_LIBS})

file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/distorted.png DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
