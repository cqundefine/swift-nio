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

add_library(NIOTestUtils
  "ByteToMessageDecoderVerifier.swift"
  "EventCounterHandler.swift"
  "NIOHTTP1TestServer.swift"
)

target_link_libraries(NIOTestUtils PUBLIC
    NIOCore
    NIOPosix
    NIOEmbedded
    NIOHTTP1)
set_target_properties(NIOTestUtils PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_Swift_MODULE_DIRECTORY})

_install_target(NIOTestUtils)
set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS NIOTestUtils)
