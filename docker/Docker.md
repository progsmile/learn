### Ports
- `HOST:CONTAINER`
- `22222:22` - map container ssh port
- `3306`

### Ports long syntax
```yml
ports:
  - target: 80
    published: 8080
    protocol: tcp
    mode: host
```

### Dockerfile: Entrypoint + CMD
Default command + args
```Dockerfile
ENTRYPOINT ["php"]
CMD ["-v"]
```

### Docker multistage build
- Use it for making images more lightweight
```Dockerfile
FROM golang:1.21 as build
WORKDIR /src
COPY . .
RUN go build -o /bin/hello ./main.go

FROM scratch
COPY --from=build /bin/hello /bin/hello
CMD ["/bin/hello"]
```
