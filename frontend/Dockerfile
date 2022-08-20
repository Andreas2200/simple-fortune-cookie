FROM alpine
RUN apk add libc6-compat
COPY . .
EXPOSE 8080
ENTRYPOINT ["./frontend"]
