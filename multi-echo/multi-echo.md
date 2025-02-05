# Multi-Connection Echo Server

## Overview
Create a multi-connection echo server in C that listens on a single port. Whenever it receives data from any connected client, it echoes that data back to all connected clients.

## Behavior
- Listens on a port that is specified via command line argument.
- Accepts multiple connections.
- When data is received from *any* client, echo it back to *all* clients.
- Message processing happens in concurrent and/or parallel manner.
- Bonus: Each client's messages can be identified by other clients

## Required libraries

- liblogger:  Provides logging utilities, take inspiration from the python standard library logging module (but drastically cut down in scope, simplify when appropriate).  This library should be able to be configured to log to stderr, stdout, or a file, or multiple of those with a single function call.  There should be a function that can take the log level as one of its parameters, and functions that are explicitly one specific level (e.g. log_dbg("my debug message") and log(10, "my debug message").  Macros and #defines should be used as appropriate.
- libnetwork:  Provides well checked functions to handle the common network related tasks.  Again, take inspiration from the python standard library but *drastically* reduced scope. Some suggested abstractions
1. create_server
2. create_connection
3. send_all
4. recv_exactly
5. recv_until

Others can be added if you find them useful.

## Build

- The project should be well structured.  Use the https://github.com/vector-of-bool/pitchfork project as a guide, deviate as you see fit.

- Use Make.  The Makefile should support the following targets:
  - all
  - clean
  - test
  - debug

Other targets can be added at your discretion.

