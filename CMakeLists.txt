cmake_minimum_required(VERSION 2.8)
list(APPEND CMAKE_MODULE_PATH ${GOPRO_TOOLS_DIR}/cmake)
include("${GOPRO_TOOLS_DIR}/cmake/gopro.cmake")

gopro_init(CocoaLumberjack)
gopro_begin_lib(CocoaLumberjack GROUP 3rdparty PLATFORMS ios)
gopro_public_include_dirs(
    Classes
    Classes/CLI
    Classes/Extensions
)
gopro_files(DIR Classes GROUP src
    CocoaLumberjack.swift
    DDASLLogCapture.m
    DDASLLogger.m
    DDAbstractDatabaseLogger.m
    DDFileLogger.m
    DDLog.m
    DDTTYLogger.m
)
gopro_public_files(DIR Classes INSTALL_DIR public_include
    CocoaLumberjack.h
    DDASLLogCapture.h
    DDASLLogger.h
    DDAbstractDatabaseLogger.h
    DDAssertMacros.h
    DDFileLogger.h
    DDLegacyMacros.h
    DDLog+LOGV.h
    DDLog.h
    DDLogMacros.h
    DDTTYLogger.h
)
gopro_files(DIR Classes/CLI GROUP src/cli
    CLIColor.m
)
gopro_public_files(DIR Classes/CLI GROUP public_include/cli INSTALL_DIR public_include/cli
    CLIColor.h
)
gopro_files(DIR Classes/Extensions GROUP src/extensions
    DDContextFilterLogFormatter.m
    DDDispatchQueueLogFormatter.m
    DDMultiFormatter.m
)
gopro_public_files(DIR Classes/Extensions GROUP public_include/extensions INSTALL_DIR public_include/extensions
    DDContextFilterLogFormatter.h
    DDDispatchQueueLogFormatter.h
    DDMultiFormatter.h
)
gopro_end_lib()

