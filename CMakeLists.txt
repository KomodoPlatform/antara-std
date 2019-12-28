## Prologue
cmake_minimum_required(VERSION 3.16)

file(STRINGS "VERSION.md" VERSION_NB)

project(antara-std
        VERSION ${VERSION_NB}
        HOMEPAGE_URL https://github.com/KomodoPlatform/antara-std
        DESCRIPTION "Antara C++ Utilities"
        LANGUAGES CXX)

message(STATUS "${PROJECT_NAME} current version: ${VERSION_NB}")

##! Configuration
set(CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/cmake)
include(antara)

##! Options
option(ANTARA_TESTS "Build tests." ${ANTARA_DEVELOP})
option(ANTARA_EXAMPLES "Build Examples." ${ANTARA_DEVELOP})
option(ANTARA_ASAN "Enable asan for targets" OFF)
option(ANTARA_UBSAN "Enable ubsan for targets" OFF)
option(ANTARA_TSAN "Enable tsan for targets" OFF)
option(ANTARA_COVERAGE "Enable coverage for targets" OFF)

##! Tests
if (ANTARA_TESTS)
    add_subdirectory(test)
endif ()

##! Examples
if (ANTARA_EXAMPLES)
    add_subdirectory(example)
endif ()
