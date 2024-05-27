###### need basic knowledge about Protocol Buffers

https://github.com/pdichone/grpc-node-course

https://github.com/pdichone/grpc-node-course-dynamic-codegen

gRPC uses HTTP2

### HTTP1.1

- opens a new TCP connection to a server for each request
- doesnt compress headers (plain text)
-

### HTTP2

- supports multiplexing
- header compressed
- HTTP2 is binary
- HTTP2 is secure (SSL by default)

gRPC 4 types

- Unary
- Server Streaming
- Client Streaming
- Bi Directional Streaming

### start

```javascript
npm i -g grpc-tools

```
