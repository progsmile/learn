Clone another repo or submodule with $CI_JOB_TOKEN (previously must add repo that refers)
```bash
git clone https://gitlab-ci-token:${CI_JOB_TOKEN}@gitlab.com/myuser/mydependentrepo
```


### Runners

Docker runner config
```toml
[[runners]]
....
[runners.docker]
    tls_verify = false
    image = "docker:24.0-dind"
    privileged = true
    disable_entrypoint_overwrite = false
    oom_kill_disable = false
    disable_cache = false
    volumes = ["/var/run/docker.sock:/var/run/docker.sock", "/cache"]
    shm_size = 0
    network_mtu = 0
```
