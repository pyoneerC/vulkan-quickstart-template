cmake_minimum_required(VERSION 3.29)
project(vulkan)

include(FetchContent)

FetchContent_Declare(
        glfw
        GIT_REPOSITORY https://github.com/glfw/glfw.git
        GIT_TAG        3.3.8
)
FetchContent_MakeAvailable(glfw)

find_package(Vulkan REQUIRED)

set(CMAKE_CXX_STANDARD 20)


add_executable(vulkan main.cpp)

target_include_directories(vulkan PRIVATE ${Vulkan_INCLUDE_DIRS})
target_link_libraries(vulkan PRIVATE glfw ${Vulkan_LIBRARIES})
