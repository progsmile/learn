### List ssh keys
- `ssh-add -l`

### Keys permissions (owner, group, public)
- `~/.ssh`                700 (drwx------)
- `~/.ssh/config`         600 (-rw-------)
- public key (.pub file): 644 (-rw-r--r--)
- private key (id_rsa):   600 (-rw-------)

### Copy public key to host
- `ssh-copy-id -i ~/.ssh/rsa_id.pub user@example.com`

### Connect with alias
- Set alias in config
```
Host my_host
  User my_user
  HostName 111.222.111.222
```
- `ssh my_host`

