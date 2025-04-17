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

add_library(NIOConcurrencyHelpers
  "NIOAtomic.swift"
  "NIOLock.swift"
  "NIOLockedValueBox.swift"
  "atomics.swift"
  "lock.swift"
)

target_link_libraries(NIOConcurrencyHelpers PUBLIC
  CNIOAtomics)
set_target_properties(NIOConcurrencyHelpers PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_Swift_MODULE_DIRECTORY})

_install_target(NIOConcurrencyHelpers)
set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS NIOConcurrencyHelpers)
