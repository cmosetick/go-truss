all: truss

# Generate go files containing the all template files in []byte form
gobindata:
	go generate github.com/TuneLab/go-truss/...

# Install truss and all dependencies 
truss: gobindata
	go install github.com/TuneLab/go-truss/...

# Remove the truss binarys
clean:
	rm -f $(GOPATH)/bin/truss
	rm -f $(GOPATH)/bin/protoc-gen-truss-gokit
	rm -f $(GOPATH)/bin/protoc-gen-truss-doc
	rm -f $(GOPATH)/bin/truss-integration-runner

# Run truss on all proto files in all dirs in ./tests/
test:
	go test -tags=integration -v ./integration_tests

testclean:
	go test -tags=integration ./integration_tests -clean


