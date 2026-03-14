# gRPC Demo Project

This project demonstrates a gRPC-based client-server application implemented in Go. It includes examples of unary, server streaming, client streaming, and bidirectional streaming RPCs.

## Features

- **Unary RPC**: A simple request-response interaction.
- **Server Streaming RPC**: The server sends a stream of responses for a single client request.
- **Client Streaming RPC**: The client sends a stream of requests, and the server responds once.
- **Bidirectional Streaming RPC**: Both the client and server send a stream of messages to each other.

## Prerequisites

- Go 1.19 or later
- Protocol Buffers Compiler (`protoc`) installed
- gRPC and Protocol Buffers Go plugins installed:
  ```sh
  go install google.golang.org/protobuf/cmd/protoc-gen-go@latest
  go install google.golang.org/grpc/cmd/protoc-gen-go-grpc@latest

  Setup
Clone the repository:

git clone https://github.com/akhil/grpc-demo-yt.git
cd grpc-demo-yt

Install dependencies:
go mod tidy

Generate gRPC code (if not already generated):
protoc --go_out=. --go-grpc_out=. proto/greet.proto

Running the Application
Start the Server
Navigate to the server directory:
cd server

Run the server as well as the file you want to test:
go run main.go [file]

Run the Client
Navigate to the client directory:
cd client

Open main.go and uncomment the desired RPC call:

callSayHello(client)
callSayHelloServerStream(client, names)
callSayHelloClientStreaming(client, names)
callSayHelloBidirectionalStream(client, names)
Run the client and the desired rpc call:
go run main.go [file]

Protocol Buffers
The proto/greet.proto file defines the gRPC service and message types. It includes the following RPC methods:

SayHello: Unary RPC
SayHelloServerStreaming: Server streaming RPC
SayHelloClientStreaming: Client streaming RPC
SayHelloBidirectionalStreaming: Bidirectional streaming RPC
Notes
The project uses insecure transport credentials for simplicity. For production, use secure credentials.
Modify the NamesList in the client to test with different inputs.
Dependencies
google.golang.org/grpc
google.golang.org/protobuf
License
