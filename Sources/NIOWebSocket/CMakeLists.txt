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

add_library(NIOWebSocket
  "NIOWebSocketClientUpgrader.swift"
  "NIOWebSocketFrameAggregator.swift"
  "NIOWebSocketServerUpgrader.swift"
  "SHA1.swift"
  "WebSocketErrorCodes.swift"
  "WebSocketFrame.swift"
  "WebSocketFrameDecoder.swift"
  "WebSocketFrameEncoder.swift"
  "WebSocketOpcode.swift"
  "WebSocketProtocolErrorHandler.swift"
)

target_link_libraries(NIOWebSocket PUBLIC
    NIOCore
    NIOHTTP1
    CNIOSHA1
    _NIOBase64)
set_target_properties(NIOWebSocket PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_Swift_MODULE_DIRECTORY})

_install_target(NIOWebSocket)
set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS NIOWebSocket)
