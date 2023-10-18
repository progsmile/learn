### [URI syntax](https://github.com/lettuce-io/lettuce-core/wiki/Redis-URI-and-connection-details#uri-syntax)

**Redis Standalone**
```
redis :// [[username :] password@] host [:port][/database]
[?[timeout=timeout[d|h|m|s|ms|us|ns]] [&clientName=clientName]
[&libraryName=libraryName] [&libraryVersion=libraryVersion] ]
```

**Redis Standalone (SSL)**

```
rediss :// [[username :] password@] host [: port][/database][?[timeout=timeout[d|h|m|s|ms|us|ns]] [&clientName=clientName]
[&libraryName=libraryName] [&libraryVersion=libraryVersion] ]
```

**Redis Standalone (Unix Domain Sockets)**

```
redis-socket :// [[username :] password@]path[?[timeout=timeout[d|h|m|s|ms|us|ns]] [&database=database]
[&clientName=clientName] [&libraryName=libraryName][&libraryVersion=libraryVersion] ]
```
