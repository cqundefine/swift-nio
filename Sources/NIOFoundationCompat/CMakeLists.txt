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

add_library(NIOFoundationCompat
  "ByteBuffer-foundation.swift"
  "Codable+ByteBuffer.swift"
  "JSONSerialization+ByteBuffer.swift"
  "WaitSpinningRunLoop.swift"
)

target_link_libraries(NIOFoundationCompat PUBLIC
    NIOCore)
set_target_properties(NIOFoundationCompat PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_Swift_MODULE_DIRECTORY})

_install_target(NIOFoundationCompat)
set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS NIOFoundationCompat)
