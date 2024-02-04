set(ALGOHOL_HEADERS
        algMath.cpp
        paramTypes.cpp
)

set(ALGOHOL_SOURCES
        algMath.h
        algTypes.h
        paramTypes.h
)

add_library(Algohol STATIC "${ALGOHOL_HEADERS}" "${ALGOHOL_SOURCES}")

target_include_directories(Algohol PRIVATE "${PROJECT_SOURCE_DIR}/nvse")

target_compile_options(Algohol PRIVATE
        /FI "${PROJECT_SOURCE_DIR}/nvse/nvse/prefix.h"
)
