#Open Match APIs

This directory contains the API specification files for Open Match. 

* [Protobuf .proto files for all APIs](./protobuf-spec/)
* [API documentation](./docs/)

These proto files are copied to the container image during `docker build` for the Open Match core components.  The `Dockerfiles` handle the compilation for you transparently, and copy the resulting `SPEC.pb.go` files to the appropriate place in your final container image.

References:

* [gRPC](https://grpc.io/)
* [Language Guide (proto3)](https://developers.google.com/protocol-buffers/docs/proto3)

Manual gRPC compilation commmand, from the directory containing the proto:
```protoc -I . ./<filename>.proto --go_out=plugins=grpc:.```
