cmake_minimum_required(VERSION 3.25)

set(CMAKE_C_STANDARD 99)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_EXE_LINKER_FLAGS "-static")
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

# Set build type to DEBUG by default if not specified
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "DEBUG" CACHE STRING "Choose the type of build (DEBUG, RELEASE)" FORCE)
endif()


project(imgui_win32_d3d12 LANGUAGES C CXX)

add_subdirectory(vendor)
add_subdirectory(app)


if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    message("Debug Mode")
elseif(CMAKE_BUILD_TYPE STREQUAL "Release")
    message("Release Mode")
elseif(CMAKE_BUILD_TYPE STREQUAL "Dist")
    message("Dist Mode")

endif()
