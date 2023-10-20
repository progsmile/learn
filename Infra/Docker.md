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

- Copy ready binary instead of manual installation
```dockerfile
COPY --from=mlocati/php-extension-installer /usr/bin/install-php-extensions /usr/local/bin/

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer
```

### Multi-line condition
```Dockerfile
ARG arg
RUN if [ -z "$arg" ] ; then \
    echo Argument not provided; \
  else \
    echo Argument is $arg; \
  fi
```

### Copy with ownership and perms

```dockerfile
COPY --chmod=755 --chown=www-data:www-data ./ /var/www
```

