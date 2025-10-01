cmake_minimum_required(VERSION 4.0)
project(vulkan_triangle)

include(FetchContent)
FETCHCONTENT_DECLARE(GLFW GIT_REPOSITORY https://github.com/glfw/glfw.git)
FETCHCONTENT_MAKEAVAILABLE(GLFW)

find_package(Vulkan REQUIRED)
if(Vulkan_FOUND)
    include_directories(${Vulkan_INCLUDE_DIRS})
    link_directories(${Vulkan_LIBRARY_DIRS})
endif()


set(CMAKE_CXX_STANDARD 20)

add_executable(vulkan_triangle main.cpp)

target_link_libraries(vulkan_triangle glfw ${Vulkan_LIBRARIES})