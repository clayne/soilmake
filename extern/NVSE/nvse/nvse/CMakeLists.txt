set(NVSE_HEADERS
        CommandTable.h
        containers.h
        GameAPI.h
        GameBSExtraData.h
        GameData.h
        GameEffects.h
        GameExtraData.h
        GameForms.h
        GameObjects.h
        GameOSDepend.h
        GameProcess.h
        GameRTTI.h
        GameScript.h
        GameSettings.h
        GameTasks.h
        GameTiles.h
        GameTypes.h
        GameUI.h
        PluginAPI.h
        SafeWrite.h
        Utilities.h
        utility.h
)

set(NVSE_SOURCES
        containers.cpp
        GameAPI.cpp
        GameBSExtraData.cpp
        GameData.cpp
        GameExtraData.cpp
        GameForms.cpp
        GameObjects.cpp
        GameOSDepend.cpp
        GameProcess.cpp
        GameRTTI.cpp
        GameScript.cpp
        GameSettings.cpp
        GameTasks.cpp
        GameTiles.cpp
        GameTypes.cpp
        NiTypes.cpp
        printf.cpp
        SafeWrite.cpp
        Utilities.cpp
        utility.cpp
)

add_library(nvse STATIC "${NVSE_HEADERS}" "${NVSE_SOURCES}")

target_include_directories(nvse PRIVATE "${PROJECT_SOURCE_DIR}/nvse")

if ("${BUILD_ALGOHOL}")
    message("-- Got BUILD_ALGOHOL, linking NVSE with Algohol")

    target_link_libraries(nvse PUBLIC Algohol)
endif ()

target_compile_options(nvse PRIVATE
        /FI "${PROJECT_SOURCE_DIR}/nvse/nvse/prefix.h"
)

target_compile_definitions(nvse PRIVATE WIN32 NDEBUG _WINDOWS _USRDLL NVSE_EXPORTS RUNTIME_VERSION=0x040020D0 RUNTIME)
