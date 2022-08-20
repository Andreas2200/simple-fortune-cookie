FROM golang:1.18 as BUILDER
ADD . /src/
run cd /src/ && go mod download github.com/gomodule/redigo && go build -o backend

FROM alpine
WORKDIR /app
COPY --from=BUILDER /src/backend .
EXPOSE 9000
RUN apk add libc6-compat && ls
ENTRYPOINT ["./backend"]
