## This is disk forensics cheatsheet
use it and take halesho

for unziping:0
```zsh
unzip -d filename.zip
gunzip filename.gz
unzip -d -FF filename #for fix corrupted file
7z x filename.7z
```

---

`autopsy` is somth for manage disk files and stuff!
so yad it!

---

## FLS
is somth for charkhing in `.img` disk files to find somth

```zsh
fls -r disk.img # garding recursive
fls -d disk.img  # garding for the deleted files
fls -rd disk.img # recursive gashting for deleted files too
icat -f dist.img [id] > asdf.wav # like extracting somth in disk
```

##MMLS
```zsh
mmls -f filename
```
---

## Mounting
```zsh
mount -o loop disk.img /mnt/asdf
umount /mnt/asdf
```

---

## Volatility 2,3 | 2 is better
volatility is for storing RAM memory

```zsh
volatility -f file.vmem imageinfo # momkene ke aslan .vmem nabashe vali filesh data hast ba hajme bala . havaset jam bashe
volatility -f file.vmem --profile=Win7SP1x64
volatility -f file.vmem --profile=Win7SP1x64 netscan
volatility -f file.vmem --profile=Win7SP1x64 pslist
volatility -f file.vmem --profile=Win7SP1x64 psscan
volatility -f file.vmem --profile=Win7SP1x64 pstree
volatility -f file.vmem --profile=Win7SP1x64 dlllist -p [pid | ppid]
volatility -f file.vmem --profile=Win7SP1x64 procdump -D dump/ -p [pid]
volatility -f file.vmem --profile=Win7SP1x64 memdump -D dump/ -p [pid] # gives the memory not the executable file

volatility -f file.vmem --profile=Win7SP1x64 dumpfiles -Q [addr] -D dump/
volatility -f file.vmem --profile=Win7SP1x64 filescan | grep filan
```


## Volatility 3
```zsh
vol -f mem.vmem windows.info.Info
vol -f mem.vmem windows.pslist.PsList
vol -f mem.vmem banners.Banners
vol -f mem.vmem windows.psscan.PsScan
vol -f mem.vmem windows.pstree.PsTree
vol -f mem.vmem windows.netscan.NetScan
vol -f mem.vmem windows.dlllist.DllList --pid PID
vol -f mem.vmem windows.cmdscan.CmdScan
vol -f mem.vmem windows.consoles.Consoles
vol -f mem.vmem windows.filescan.FileScan
vol -f mem.vmem windows.filescan.FileScan | grep somth #like this
vol -f mem.vmem -o dump/ windows.dumpfiles.DumpFiles --virtaddr ADDR
vol -f mem.vmem -o dump/ windows.dumpfiles.DumpFiles --physaddr ADDR
vol -f mem.vmem windows.malfind.Malfind
vol -f mem.vmem windows.handles.Handles
vol -f dumpedfile windows.memmap --pid <pid> --dump
```
[regexr.com](https://regexr.com) for create regx

dll : is a file that a program needs it to execute

---

## Dump file Visualize
open dumped file and change it to .dat file
open in gimp and var with offset, width and height to visualize it


Websites to check for volatility:
- [CyberDefenders](https://cyberdefenders.org)
- [Memory Forensic](https://memoryforensic.com)
- [FLAGYARD](https://flagyard.com)
- [CyberEDU](https://cyber-edu.co)

---
### Dudes that you could learn from them for overtraining
`live Overflow` , `Gynvael` , `John Hammond` <br>
and `Ippsec` (taha said : not recommended)
---

to yad:
- `fls`
- `icat`
- `mmls`
- `fsstat`
- `tsk_recover`
