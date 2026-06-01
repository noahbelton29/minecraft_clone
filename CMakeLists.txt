cmake_minimum_required(VERSION 4.2)
project(minecraft_clone)
include(FetchContent)

set(CMAKE_CXX_STANDARD 20)
set(GLFW_BUILD_DOCS OFF CACHE BOOL "")
set(GLFW_INSTALL OFF CACHE BOOL "")
FetchContent_Declare(
        glfw
        GIT_REPOSITORY https://github.com/glfw/glfw.git
        GIT_TAG 3.4
        GIT_SHALLOW true
)

FetchContent_MakeAvailable(glfw)

add_executable(minecraft_clone main.cpp external/glad/src/glad.c)
include_directories( SYSTEM "external/glad/include" )
target_link_libraries(minecraft_clone glfw)