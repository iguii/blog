+++
title = 'gRPC with Java and Spring Boot - Udemy'
date = 2024-09-17T16:55:07-04:00
draft = true
type = 'page'
showTableOfContents = true
tags = ['Software Development', 'gRPC', 'Java', 'Spring Boot']
+++

# What is gRPC?

It is a modern lightweight RPC (Remote Procedure Call) framework from Google made for service-to-service communication.

It is used by Google, Netflix, Square, and many other companies.

While traditional communication works with request and response, gRPC uses four communications patterns:

- Unary (Same as traditional REST Request and Response)
- Server-streaming
- Client-streaming
- Bidirectional-streaming

## gRPC vs. REST comparison

| gRPC                | REST                                     |
| ------------------- | ---------------------------------------- |
| Architectural style | A RPC framework                          |
| Resource oriented   | More Flexible and action oriented        |
| ~JSON + HTTP        | Specific to inter-services communication |

## Protocol Buffers

In non gRPC communication, we use JSON to serialize and deserialize data. In gRPC, we use Protocol Buffers.

Protocol Buffers are a language-neutral, platform-neutral, extensible mechanism for serializing structured data. It is
a binary format that is smaller, faster and simpler than JSON.

this is an example of a Protocol Buffer definition:

```proto
syntax = "proto3"; // This is the syntax version

package sec01; // this specifies the package name for the generated java classes

option java_multiple_files = true; // this specifies that each message will be in its own file

option java_package = "com.example.proto.sec01"; // this specifies the package name for the generated java classes

/*
  This is a multi-line comment
*/

message Person {
  string name = 1;
  int32 age = 2;
}
```

we define the message in a .proto file.

This file can be universal for all languages.

### Protocol Buffers - Data Types - Scalar Types

| Java    | Protocol Buffers |
| ------- | ---------------- |
| int     | int32/sint32     |
| long    | int64/sint64     |
| float   | float            |
| double  | double           |
| boolean | bool             |
| String  | string           |
| byte[]  | bytes            |

> Protocol Buffers don't have a char type. Instead, we use a string.
