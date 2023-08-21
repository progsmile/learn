
Expose address
```
ip address add interface=ether2 address=192.168.56.11/24
```

Remove address
```
ip address remove 0
```

Print IP address
```
ip address print
ip ad pr
```

Print interfaces
```
interface print
in pr
```

Check and install updates switching channels
```
system package update set channel=stable
system package update check-for-updates
system package update install

system package update set channel=upgrade
system package update check-for-updates
system package update install
```

Get serial number
```
system routerboard get serial-number
```

Reboot
```
system reboot
```


### Docker image
- `evilfreelancer/docker-routeros`
