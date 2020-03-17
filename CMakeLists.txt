cmake_minimum_required(VERSION 3.0.0)

project(windman VERSION 0.1 LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)

find_package(Qt5Core)
find_package(X11 REQUIRED)

message(STATUS "X11_FOUND = ${X11_FOUND}")
message(STATUS "X11_INCLUDE_DIR = ${X11_INCLUDE_DIR}")
message(STATUS "X11_LIBRARIES = ${X11_LIBRARIES}")

include_directories(${X11_INCLUDE_DIR})

link_directories(${X11_LIBRARIES})

add_executable(${PROJECT_NAME} "main.cpp")

target_link_libraries(${PROJECT_NAME} Qt5::Core ${X11_LIBRARIES})
