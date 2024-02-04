cmake_minimum_required(VERSION 3.26.4)

set(BUILD_ALGOHOL ON CACHE INTERNAL "Should Algohol be built?" FORCE)

project(
        insanity
        LANGUAGES CXX
        VERSION 1
)

set(CMAKE_CXX_STANDARD 23)

add_subdirectory(extern/NVSE)

add_subdirectory(src)
