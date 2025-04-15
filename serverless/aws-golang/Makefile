build:
	GOOS=darwin GOARCH=arm64 go build -o bin/bootstrap ping/main.go
	GOOS=darwin GOARCH=arm64 go build -o build/lambda/hello/bootstrap cmd/lambda/hello/main.go

zip:
    zip -j bin/ping.zip bin/bootstrap

.PHONY: clean
clean:
	rm -rf ./bin ./vendor Gopkg.lock

.PHONY: deploy
deploy: clean build
	sls deploy --verbose

start: build
	sls offline start  --host 0.0.0.0