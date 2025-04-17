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

add_library(CNIOAtomics STATIC
  "src/c-atomics.c"
  "src/c-nioatomics.c"
)
target_include_directories(CNIOAtomics PUBLIC
  include)

set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS CNIOAtomics)
