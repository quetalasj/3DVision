cmake_minimum_required(VERSION 3.22)
project(3DVision)

set(CMAKE_CXX_STANDARD 17)

find_package(OpenCV REQUIRED)
find_package(Pangolin REQUIRED)
find_package(Sophus REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})
include_directories("/usr/include/eigen3")
include_directories(${Sophus_INCLUDE_DIRS})

add_executable(jointMap jointMap.cpp)

target_link_libraries(jointMap ${OpenCV_LIBS} ${Pangolin_LIBRARIES} Sophus::Sophus)
#
file(COPY color/ DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/color)
file(COPY depth/ DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/depth)
file(COPY poses.txt DESTINATION ${CMAKE_CURRENT_BINARY_DIR})