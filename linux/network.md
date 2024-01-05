### PC connections
- `sudo nmcli device status`
- `sudo nmcli device wifi list`

- `sudo service networking status`

---
### Check wifi signal
- `wavemon`


---
### NetCat
`nc` creates a TCP connection to the destination host and port, and then attaches the connection to stdin and stdout

```bash
nc example.com 80 <request.txt

curl -vvv http://example.com/

openssl s_client -verify_quiet -quiet -connect example.com:443
```


