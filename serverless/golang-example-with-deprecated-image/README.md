## AWS Lambda functions with Go1.x runtime
https://aws.amazon.com/blogs/compute/migrating-aws-lambda-functions-from-the-go1-x-runtime-to-the-custom-runtime-on-amazon-linux-2/

## Start
```
sls offline --config serverless.yml
serverless invoke local --function Ping --debug

```

## Install plugins

```
serverless plugin install -n serverless-go-plugin

```