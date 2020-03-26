cmake_minimum_required (VERSION 3.5.1)
project(pfs-fsm VERSION 1.0 LANGUAGES CXX)

option(pfs_fsm_BUILD_TESTS "Build tests" ON)

if (pfs_fsm_BUILD_TESTS)
    enable_testing()
    include_directories(${CMAKE_CURRENT_LIST_DIR}/include)
    add_subdirectory(tests)
endif()
