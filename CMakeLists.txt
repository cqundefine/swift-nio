##===----------------------------------------------------------------------===##
##
## This source file is part of the SwiftNIO open source project
##
## Copyright (c) 2025 Apple Inc. and the SwiftNIO project authors
## Licensed under Apache License v2.0
##
## See LICENSE.txt for license information
## See CONTRIBUTORS.txt for the list of SwiftNIO project authors
##
## SPDX-License-Identifier: Apache-2.0
##
##===----------------------------------------------------------------------===##

cmake_minimum_required(VERSION 3.19)

project(SwiftNIO
  LANGUAGES C Swift)

list(APPEND CMAKE_MODULE_PATH ${CMAKE_CURRENT_SOURCE_DIR}/cmake/modules)

include(SwiftSupport)

option(BUILD_SHARED_LIBS "Build shared libraries by default" YES)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)

set(CMAKE_Swift_MODULE_DIRECTORY ${CMAKE_BINARY_DIR}/swift)

set(CMAKE_POSITION_INDEPENDENT_CODE ${BUILD_SHARED_LIBS})

# find_package(dispatch CONFIG)
# find_package(Foundation CONFIG)

include(FetchContent)

find_package(SwiftSystem CONFIG)
if(NOT SwiftSystem_FOUND)
  message("-- Vending swift-system")
  FetchContent_Declare(System
    GIT_REPOSITORY https://github.com/apple/swift-system
    GIT_TAG 1.4.0)
  FetchContent_MakeAvailable(System)
endif()

find_package(SwiftCollections CONFIG)
if(NOT SwiftCollections_FOUND)
  message("-- Vending swift-collections")
  FetchContent_Declare(Collections
    GIT_REPOSITORY https://github.com/apple/swift-collections
    GIT_TAG 1.1.4)
  FetchContent_MakeAvailable(Collections)
endif()

find_package(SwiftAtomics CONFIG)
if(NOT SwiftAtomics_FOUND)
  message("-- Vending swift-atomics")
  FetchContent_Declare(Atomics
    GIT_REPOSITORY https://github.com/apple/swift-atomics
    GIT_TAG 1.1.0)
  FetchContent_MakeAvailable(Atomics)
endif()

add_subdirectory(Sources)
add_subdirectory(cmake/modules)
