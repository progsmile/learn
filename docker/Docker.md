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
Default command + args:
```Dockerfile
ENTRYPOINT ["php"]
CMD ["-v"]
```
