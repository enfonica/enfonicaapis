# Enfonica APIs

This repository contains the original interface definitions of public
Enfonica APIs that support both REST and gRPC protocols (with the exception
of streaming APIs which support gRPC only). Reading the original interface
definitions can provide a better understanding of Enfonica APIs and help you
to utilize them more efficiently. You can also use these definitions with
open source tools to generate client libraries, documentation, and other
artifacts.

## Overview

Enfonica APIs are typically deployed as API services that are hosted
under different DNS names. One API service may implement multiple APIs
and multiple versions of the same API.

Enfonica APIs use [Protocol Buffers](https://github.com/google/protobuf)
version 3 (proto3) as their Interface Definition Language (IDL) to
define the API interface and the structure of the payload messages. The
same interface definition is used for both REST and RPC versions of the
API, which can be accessed over different wire protocols.

There are several ways of accessing Enfonica APIs:

1. [Enfonica Client Libraries](https://enfonica.com/docs):
You can use these libraries to access Enfonica APIs. They are based
on gRPC for better performance and provide idiomatic client surfaces for
a better developer experience.

2. JSON over HTTP: You can access all Enfonica APIs (excluding streaming
APIs) directly using JSON over HTTP.

3. Protocol Buffers over gRPC: You can access Enfonica APIs published
in this repository through [gRPC](https://github.com/grpc), which is
a high-performance binary RPC protocol over HTTP/2. It offers many
useful features, including request/response multiplex and full-duplex
streaming.

## Repository Structure

This repository uses a directory hierarchy that reflects the Enfonica
API product structure. In general, every API has its own root
directory, and each major version of the API has its own subdirectory.
The proto package names exactly match the directory: this makes it
easy to locate the proto definitions and ensures that the generated
client libraries have idiomatic namespaces in most programming
languages.
