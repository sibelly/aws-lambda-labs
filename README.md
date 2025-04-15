### Study project to execute local aws lambda

```
npm install serverless-offline --save-dev
sls offline --help
SLS_DEBUG=* serverless offline

serverless invoke local --function HelloWorldFunction --debug
GOARCH=amd64 GOOS=linux go build -o bootstrap main.go
GOOS=linux GOARCH=amd64 go build -o bin/main aws-golang/main.go
```

### Some of the study source
https://www.youtube.com/watch?v=y6uYE62cp9g
https://blog.matthiasbruns.com/running-multiple-golang-aws-lambda-functions-on-arm64-with-serverlesscom
https://medium.com/@myownmusing/deploying-go-on-aws-lambda-overcoming-the-bootstrap-hurdles-40fb37bd7c91
https://github.com/matthiasbruns/golang-sls-provided.al2-arm64/blob/main/serverless.yml
https://github.com/serverless/examples/blob/v4/aws-golang-simple-http-endpoint/serverless.yml

https://github.com/open-telemetry/opentelemetry-go-contrib/blob/main/instrumentation/github.com/aws/aws-lambda-go/otellambda/example/main.go