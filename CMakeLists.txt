
cmake_minimum_required(VERSION 3.10)
project(liquid_glass_demo)
set(CMAKE_CXX_STANDARD 17)

add_subdirectory(glad)
add_subdirectory(stb)

include_directories(glad/include)
include_directories(stb)
include_directories(${CMAKE_SOURCE_DIR})

find_package(PkgConfig REQUIRED)
pkg_search_module(GLFW REQUIRED glfw3)

add_executable(liquid_glass_demo main.cpp)
target_link_libraries(liquid_glass_demo glad stb ${GLFW_LIBRARIES} GL X11 pthread dl)
