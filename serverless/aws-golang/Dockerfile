FROM golang:1.23.7 AS build

WORKDIR /aws-golang
# Copy dependencies list
COPY go.mod go.sum ./
# Build with optional lambda.norpc tag
COPY ping/main.go .
RUN go build -tags lambda.norpc -o main main.go
# Copy artifacts to a clean image
FROM public.ecr.aws/lambda/provided:al2023
COPY --from=build /ping/main ./main
ENTRYPOINT [ "./ping/main" ]