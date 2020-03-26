option(ENABLE_COVERAGE "Build tests with coverage support" OFF)

if (ENABLE_COVERAGE)
    message(STATUS "Coverage feature enabled")
    if (NOT "${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
        message(FATAL_ERROR "Coverage feature requires GCC")
    endif()

    set(CMAKE_CXX_FLAGS "-g -O0 --coverage")
    set(CMAKE_C_FLAGS "-g -O0 --coverage")
endif()

add_executable(fsm fsm.cpp)
add_test(NAME fsm COMMAND fsm)
