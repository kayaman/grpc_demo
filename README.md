# gRPC demo

"gRPC is roughly 7 times faster than REST when receiving data & roughly 10 times faster than REST when sending data"

## Development

## Get production ready

```shell
docker build . -f recommendations/Dockerfile -t recommendations

docker run -p 127.0.0.1:50051:50051/tcp recommendations
```

```shell
docker build . -f marketplace/Dockerfile -t marketplace

docker run -p 127.0.0.1:5000:5000/tcp marketplace
```

```shell
docker network create microservices

docker run -p 127.0.0.1:50051:50051/tcp --network microservices \
             --name recommendations recommendations
```

## References

- https://medium.com/@EmperorRXF/evaluating-performance-of-rest-vs-grpc-1b8bdf0b22da