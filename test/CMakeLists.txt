find_package(doctest CONFIG REQUIRED)

add_executable(antara-tests antara.tests.cpp)
target_link_libraries(antara-tests PRIVATE doctest::doctest)