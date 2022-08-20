FROM golang:1.18 as BUILDER
ADD . /src/
RUN cd /src/ && go build -o frontend

FROM scratch
WORKDIR /app
COPY --from=BUILDER /src/frontend .
COPY --from=BUILDER /src/static .
EXPOSE 8080
ENTRYPOINT ["/frontend"]
