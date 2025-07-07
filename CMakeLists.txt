cmake_minimum_required(VERSION 3.10)

project(ModelViewer)

set(CMAKE_CXX_STANDARD 23)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(BUILD_SHARED_LIBS OFF)
set(THIRDPARTY ${CMAKE_SOURCE_DIR}/thirdparty)

file(GLOB_RECURSE SRC_FILES "src/*")

include_directories(${THIRDPARTY}/volk)
add_library(Volk ${THIRDPARTY}/volk/volk.c)

add_executable(ModelViewer ${SRC_FILES})

target_link_libraries(ModelViewer Volk)
