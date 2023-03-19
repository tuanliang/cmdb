

make gen
```shell
protoc -I=. -I=common/pb --go_out=. --go_opt=module="github.com/tuanliang/cmdb" --go-grpc_out=. --go-grpc_opt=module="github.com/tuanliang/cmdb" apps/*/pb/*.proto
go fmt ./...
protoc-go-inject-tag -input=apps/*/*.pb.go
mcube generate enum -p -m apps/*/*.pb.go
```