# Injection-BOF

Beacon Object Files for injects desired shellcode into target process

![](_img/01.png)


## inject-cfg

A beacon object file implementation of the process injection proof-of-concept from my blog post [Control Flow Hijacking via Data Pointers](https://www.legacyy.xyz/defenseevasion/windows/2025/04/16/control-flow-hijacking-via-data-pointers.html). Hijacks control flow via overwriting `combase.dll`'s Control Flow Guard function pointers called by COM proxying functions.
- From my testing, `explorer.exe` is the current best candidate in terms of an easy triggering mechanism due to its heavy reliance on COM proxying. Would recommend experimenting.
- **Make sure** shellcode is 64-bit as this BOF only supports 64-bit beacons & target processes.
- This has only been tested on windows versions `Win10 21H2 (19044.5737)` & `Win11 24H2 (26100.3775)`.

```
inject-cfg <pid> <shellcode file>
```



## inject-sec

Injects desired shellcode into target process using section mapping
```
inject-sec <pid> <shellcode file>
```

## inject-pp

Injects shellcode into target process using Pool Party injection techniques

General usage:
```
inject-sec <variant> <pid> <shellcode file>
```

To specify which Pool Party technique you want to use, select from v4-v8

### Variant 4
This variant utilizes the TP_IO work item to inject into the target's thread pool.

Usage:
```
inject-sec v4 <pid> <shellcode file>
```

### Variant 5
This variant utilizes the TP_ALPC work item to inject into the target's thread pool.

Usage:
```
inject-sec v5 <pid> <shellcode file>
```

### Variant 6
This variant utilizes the TP_JOB work item to inject into the target's thread pool.

Usage:
```
inject-sec v6 <pid> <shellcode file>
```

### Variant 7
This variant utilizes the TP_DIRECT work item to inject into the target's thread pool.

Usage:
```
inject-sec v7 <pid> <shellcode file>
```

### Variant 8
This variant utilizes the TP_TIMER work item to inject into the target's thread pool.

Usage:
```
inject-sec v8 <pid> <shellcode file>
```

## Credits
* secinject - https://github.com/apokryptein/secinject
* DataInject-BOF - https://github.com/iilegacyyii/DataInject-BOF
* PoolPartyBof - https://github.com/0xEr3bus/PoolPartyBof