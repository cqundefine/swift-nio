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

add_library(CNIOSHA1 STATIC
  "c_nio_sha1.c"
)
target_include_directories(CNIOSHA1 PUBLIC
  include)

set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS CNIOSHA1)
