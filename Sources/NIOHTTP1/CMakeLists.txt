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

add_library(NIOHTTP1
  "ByteCollectionUtils.swift"
  "HTTPDecoder.swift"
  "HTTPEncoder.swift"
  "HTTPHeaderValidator.swift"
  "HTTPHeaders+Validation.swift"
  "HTTPPipelineSetup.swift"
  "HTTPServerPipelineHandler.swift"
  "HTTPServerProtocolErrorHandler.swift"
  "HTTPServerUpgradeHandler.swift"
  "HTTPTypedPipelineSetup.swift"
  "HTTPTypes.swift"
  "NIOHTTPClientUpgradeHandler.swift"
  "NIOHTTPObjectAggregator.swift"
  "NIOTypedHTTPClientUpgradeHandler.swift"
  "NIOTypedHTTPClientUpgraderStateMachine.swift"
  "NIOTypedHTTPServerUpgradeHandler.swift"
  "NIOTypedHTTPServerUpgraderStateMachine.swift"
)

target_link_libraries(NIOHTTP1 PUBLIC
    NIOCore
    NIOConcurrencyHelpers
    CNIOLLHTTP)
set_target_properties(NIOHTTP1 PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_Swift_MODULE_DIRECTORY})

_install_target(NIOHTTP1)
set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS NIOHTTP1)
