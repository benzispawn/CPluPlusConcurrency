cmake_minimum_required(VERSION 3.11.3)

# set(CMAKE_CXX_STANDARD 17)
project(traffic_simulation)
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++17 -pthread")
#set(OpenCV_DIR /Users/rbenzi/Documents/opencv/build_opencv)
#set(OpenCV_DIR "/usr/local/include/opencv4")
#set(OpenCV_DIR /opt/homebrew/Cellar/opencv/4.5.3_2)

find_package(OpenCV 4.1 REQUIRED PATHS "/usr/local/include/opencv4")

include_directories(${OpenCV_INCLUDE_DIRS})
#include_directories("/Users/rbenzi/opencv")
link_directories(${OpenCV_LIBRARY_DIRS})
add_definitions(${OpenCV_DEFINITIONS})

# Find all executables
file(GLOB project_SRCS src/*.cpp) #src/*.h

# Add project executable
add_executable(traffic_simulation ${project_SRCS})
target_link_libraries(traffic_simulation ${OpenCV_LIBRARIES})
