find_package(doctest CONFIG REQUIRED)

add_executable(antara-tests
        antara.tests.cpp
        config/antara.tests.config.version.cpp)

target_link_libraries(antara-tests
        PRIVATE
        doctest::doctest
        antara_std::default_settings)

target_include_directories(antara-tests
        PRIVATE
        ${CMAKE_SOURCE_DIR}/include)

set_target_properties(antara-tests
        PROPERTIES
        RUNTIME_OUTPUT_DIRECTORY
        ¬"${CMAKE_BINARY_DIR}/test"
        )