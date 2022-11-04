cmake_minimum_required(VERSION 3.23)
project(yaCADPro)

include(cmake/FindOCC.cmake)

set(CMAKE_CXX_STANDARD 20)

include_directories(${OCC_INCLUDE_DIR})

add_executable(yaCADPro main.cpp)

target_link_libraries(yaCADPro ${OCC_LIBRARIES})