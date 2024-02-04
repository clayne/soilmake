set(PLUGIN_HEADERS
        ./fn_intro_to_script_functions.h
        ./fn_typed_functions.h
)

set(PLUGIN_SOURCES
        ./main.cpp
)

add_library("${PROJECT_NAME}" SHARED "${PLUGIN_HEADERS}" "${PLUGIN_SOURCES}")

target_include_directories("${PROJECT_NAME}" PRIVATE "${PROJECT_SOURCE_DIR}/extern/NVSE/nvse")

target_link_libraries("${PROJECT_NAME}" PRIVATE common)

target_link_libraries("${PROJECT_NAME}" PRIVATE nvse)

target_compile_options("${PROJECT_NAME}" PRIVATE
        /FI "nvse/prefix.h"
)
