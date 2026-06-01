cmake_minimum_required(VERSION 4.2)
project(minecraft_clone)
include(FetchContent)

FetchContent_Declare(
        glfw
        GIT_REPOSITORY https://github.com/glfw/glfw.git
        GIT_TAG 3.4
        GIT_SHALLOW true
)

set(GLFW_BUILD_DOCS OFF CACHE BOOL  "")
set(GLFW_INSTALL OFF CACHE BOOL  "")

FetchContent_MakeAvailable(glfw)

set(CMAKE_CXX_STANDARD 20)

add_executable(minecraft_clone main.cpp)
target_link_libraries(minecraft_clone glfw)