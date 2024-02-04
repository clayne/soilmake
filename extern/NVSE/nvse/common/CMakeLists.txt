set(COMMON_HEADERS
        IArchive.h
        IBufferStream.h
        IConsole.h
        ICriticalSection.h
        IDatabase.h
        IDataStream.h
        IDebugLog.h
        IDirectoryIterator.h
        IDynamicCreate.h
        IErrors.h
        IEvent.h
        IFIFO.h
        IFileStream.h
        IInterlockedLong.h
        ILinkedList.h
        IMemPool.h
        IMutex.h
        IObjectPool.h
        IPipeClient.h
        IPipeServer.h
        IPrefix.h
        IRangeMap.h
        IReadWriteLock.h
        ISegmentStream.h
        ISingleton.h
        ITextParser.h
        IThread.h
        ITimer.h
        ITypes.h
)

set(COMMON_SOURCES
        IArchive.cpp
        IBufferStream.cpp
        IConsole.cpp
        IDatabase.cpp
        IDataStream.cpp
        IDebugLog.cpp
        IDirectoryIterator.cpp
        IDynamicCreate.cpp
        IErrors.cpp
        IEvent.cpp
        IFIFO.cpp
        IFileStream.cpp
        IInterlockedLong.cpp
        IMemPool.cpp
        IMutex.cpp
        IObjectPool.cpp
        IPipeClient.cpp
        IPipeServer.cpp
        IPrefix.cpp
        IRangeMap.cpp
        IReadWriteLock.cpp
        ISegmentStream.cpp
        ISingleton.cpp
        ITextParser.cpp
        IThread.cpp
        ITimer.cpp
        ITypes.cpp
)

add_library(common STATIC "${COMMON_HEADERS}" "${COMMON_SOURCES}")

target_include_directories(common PRIVATE "${PROJECT_SOURCE_DIR}/nvse")

target_compile_options(common PRIVATE
        /FI "${PROJECT_SOURCE_DIR}/nvse/nvse/prefix.h"
)
