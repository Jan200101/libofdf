cmake_minimum_required(VERSION 3.12)

if(CMAKE_POLICY_DEFAULT_CMP0017 OR CMAKE_POLICY_DEFAULT_CMP0020)
    # touch these to remove warnings
endif()

if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING
        "Choose the type of build, options are: None Debug Release RelWithDebInfo MinSizeRel." FORCE)
endif()

project(OFDF LANGUAGES C)

option(ENABLE_TESTS "Enable tests of the various components" OFF)
if (ENABLE_TESTS)
    enable_testing()
endif()

add_subdirectory(vdf)
