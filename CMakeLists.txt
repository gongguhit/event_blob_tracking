
project(blob_tracking)
cmake_minimum_required(VERSION 3.0)

set(CMAKE_CXX_STANDARD 11)
# using thread in Linux

SET(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -pthread")
find_package(OpenCV REQUIRED)


SET (PROJECT_ROOT "${PROJECT_SOURCE_DIR}")
SET (PROJECT_INCLUDE_DIR "${PROJECT_SOURCE_DIR}/src/include")

include_directories(
    ${PROJECT_INCLUDE_DIR}
    "/usr/local/include"
)

add_executable(${PROJECT_NAME}
    src/main.cpp
    src/blob.cpp
)

target_link_libraries(
    ${PROJECT_NAME} 
    gflags
    ${OpenCV_LIBS}
)

