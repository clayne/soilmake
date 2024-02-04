cmake_minimum_required(VERSION 3.26.4)

project(
        NVSE
        LANGUAGES CXX
        VERSION 1
)

include(cmake/Prerequisites.cmake)

set(CMAKE_CXX_STANDARD 23)

if ("${BUILD_ALGOHOL}")
    add_subdirectory(nvse/Algohol)
endif ()

add_subdirectory(nvse/common)

add_subdirectory(nvse/nvse)
