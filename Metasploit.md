# Metasploit

## Search
search does string searches

```bash
search ms08
```

returns searches for all modules with `ms08` in the name

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

# Meterpreter

```bash
ls
```

```bash
cat file.ext
```

```bash
download file.ext
```