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

add_library(NIOPosix
  "BSDSocketAPICommon.swift"
  "BSDSocketAPIPosix.swift"
  "BSDSocketAPIWindows.swift"
  "BaseSocket.swift"
  "BaseSocketChannel+SocketOptionProvider.swift"
  "BaseSocketChannel.swift"
  "BaseStreamSocketChannel.swift"
  "Bootstrap.swift"
  "ControlMessage.swift"
  "DatagramVectorReadManager.swift"
  "Errors+Any.swift"
  "FileDescriptor.swift"
  "GetaddrinfoResolver.swift"
  "HappyEyeballs.swift"
  "IO.swift"
  "IntegerBitPacking.swift"
  "IntegerTypes.swift"
  "Linux.swift"
  "LinuxCPUSet.swift"
  "LinuxUring.swift"
  "MultiThreadedEventLoopGroup.swift"
  "NIOThreadPool.swift"
  "NonBlockingFileIO.swift"
  "PendingDatagramWritesManager.swift"
  "PendingWritesManager.swift"
  "PipeChannel.swift"
  "PipePair.swift"
  "Pool.swift"
  "PooledRecvBufferAllocator.swift"
  "PosixSingletons+ConcurrencyTakeOver.swift"
  "PosixSingletons.swift"
  "RawSocketBootstrap.swift"
  "Resolver.swift"
  "Selectable.swift"
  "SelectableChannel.swift"
  "SelectableEventLoop.swift"
  "SelectorEpoll.swift"
  "SelectorGeneric.swift"
  "SelectorKqueue.swift"
  "SelectorUring.swift"
  "ServerSocket.swift"
  "Socket.swift"
  "SocketChannel.swift"
  "SocketProtocols.swift"
  "System.swift"
  "Thread.swift"
  "ThreadPosix.swift"
  "ThreadWindows.swift"
  "UnsafeTransfer.swift"
  "Utilities.swift"
  "VsockAddress.swift"
  "VsockChannelEvents.swift"
)

target_link_libraries(NIOPosix PUBLIC
    CNIOLinux
    CNIODarwin
    CNIOWindows
    NIOConcurrencyHelpers
    NIOCore
    _NIODataStructures)
set_target_properties(NIOPosix PROPERTIES
  INTERFACE_INCLUDE_DIRECTORIES ${CMAKE_Swift_MODULE_DIRECTORY})

_install_target(NIOPosix)
set_property(GLOBAL APPEND PROPERTY SWIFT_NIO_EXPORTS NIOPosix)
