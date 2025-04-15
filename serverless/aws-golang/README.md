
https://github.com/open-telemetry/opentelemetry-lambda/tree/main/go
https://pkg.go.dev/go.opentelemetry.io/contrib/instrumentation/github.com/aws/aws-lambda-go/otellambda#section-readme

### Invoke local

```
serverless invoke local --function HelloWorldFunction --debug
SLS_DEBUG=* serverless offline
DISABLE_TRACING=true STAGE=dev serverless offline start
```

route events from your live architecture to your local code, allowing you to make quick changes without deployment - https://www.serverless.com/framework/docs/providers/aws/cli-reference/dev
```
serverless dev
```

```
curl -XPOST "http://localhost:9000/2015-03-31/functions/function/invocations" -d '{}'
```

### MacOS local
Update your serverless.yml:
Make sure your architecture matches in serverless.yml:

```
provider:
  architecture: arm64  # Changed from x86_64 to arm64
```

- macOS
docker run --platform linux/arm64 --rm -v $(pwd)/bin:/var/task public.ecr.aws/lambda/go:1 main
GOOS=linux GOARCH=arm64 go build -o bin/main main.go

### Docs
https://www.serverless.com/blog/framework-example-golang-lambda-support/
https://github.com/aws/aws-lambda-go/tree/main/events