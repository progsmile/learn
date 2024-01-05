### Ports
- `HOST:CONTAINER`
- `22222:22` - map container ssh port
- `3306`

### Ports long syntax
```yml
ports:docker-php-entrypoint
  - target: 80
    published: 8080
    protocol: tcp
    mode: host
```

### Expose few ports
```Dockerfile
EXPOSE 1025 8025
```

### Entrypoint + CMD
Default command + args
```Dockerfile
ENTRYPOINT ["php"]
CMD ["-v"]
```

### Multistage build
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

- Copy ready binary instead of manual installation
```dockerfile
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
```

### Multi-line condition
```Dockerfile
ARG arg
RUN if [ -z "$arg" ] ; then \
    echo Argument not provided && \
    echo Argument not provided2 && \
    echo Argument not provided3; \
  else \
    echo Argument is ... && \
    echo Argument is $arg; \
  fi
```

### Copy with ownership and perms

```dockerfile
COPY --chmod=755 --chown=www-data:www-data ./ /var/www
```

---

### Debug container
- `docker build -t debug --progress plain --no-cache -f ./path/to/Dockerfile .`

### Debug compose service
- `entrypoint: ["sh", "-c", "sleep infinity"]`

### Run and remove container
- `docker run -it --rm node bash`

### Inspect service
- `docker inspect $(docker compose ps -q some-service)`

### Check merged config
- `docker compose -f ./docker-compose.yml -f ./docker-compose.test.yml config`

