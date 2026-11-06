# Haakerclub-Cheatsheet

تو این ریپازیتوری ، ابزار ها و قطعه کد هایی که مینویسید قرار گرفته و به جای هر قسمتی که خودتون باید پر کنید ، اون قسمت داخل عبارت `<...>` قرار گرفته که راحت تشخیصش بدید.

ادامه چیت شیت فینگلیش نوشته شده

داخل کد های پایتون راهنمایی هایی داخل کامنت گذاشته شده.

- [Abzars](#Abzar)
- [Linux Commands](#Commands)
- [Magic Bytes](#Signatures)
- [Pillow](./pillow.md)
- [Scapy](./scapy.md)


---

# Abzar


## steghide
for extract steghided data signature
```zsh
steghide <image.jpg>              # for vJPEG | BMP | WAV | AU files only
steghide extract -sf <image.jpg>  # for extract -> if password protected -> miporse azatoon
```

## zsteg
bishtar for lsbs check
```zsh
zsteg <image.png>       # checks lsb
zsteg -a <image.png>    # checks tamame halat haye momken
```

## binwalk
for hiding files inside another file
```zsh
binwalk <file>          # check for hided files 
binwalk -E <file>       # extract shenasayied files
binwalk -Me <file>      # check and for files recursively (inside each other)
```

## dd
for slice files (boridane file ha ba tavajoh be ye addresse khas)
```zsh
dd if=<inputfile> of=<outputfile> bs=1 skip=100 seek=200
# skip -> byte hayi ke az aval rad mikone ta berese be masalan byte 100 om
# seek -> byte hayi ke az akhar rad mikone ta berese be akhare file
# masalan too in mesal az byte 100 ta 200 ro estekhraj mikone
```

--- 

# Commands
just for memorize

```zsh
strings <filename>                # shows the printable strings of the file
exiftool <filename>               # shows the metadata
file <filename>                   # checks the headers to approve file format
xxd <filename>                    # shows the bytes of the file
xxd <filename> | head             # shows the first bytes of the file
xxd <filename> | tail             # shows the last bytes of the file
```


more expert
```zsh
grep <phrase>      # filter the phrase contained text
grep -r <phrase>   # searching recursively
grep -v <phrase>   # reverse search
grep -i <PhrAsE>   # case insesitive search
strings <file or path> | grep -iE "flag|ctf"    # finds flag or ctf contained texts
```

---

#Signatures

# Magic Bytes (File Signatures)

| File Format | Extension | Hex Signature | ASCII |
|---|---|---|---|
| PNG | `.png` | `89 50 4E 47 0D 0A 1A 0A` | `.PNG....` |
| JPEG | `.jpg, .jpeg` | `FF D8 FF` | - |
| GIF87a | `.gif` | `47 49 46 38 37 61` | `GIF87a` |
| GIF89a | `.gif` | `47 49 46 38 39 61` | `GIF89a` |
| BMP | `.bmp` | `42 4D` | `BM` |
| TIFF (Little Endian) | `.tif, .tiff` | `49 49 2A 00` | `II*.` |
| TIFF (Big Endian) | `.tif, .tiff` | `4D 4D 00 2A` | `MM.*` |
| WebP | `.webp` | `52 49 46 46` | `RIFF` |
| PDF | `.pdf` | `25 50 44 46` | `%PDF` |
| ZIP | `.zip` | `50 4B 03 04` | `PK..` |
| RAR | `.rar` | `52 61 72 21 1A 07` | `Rar!...` |
| 7-Zip | `.7z` | `37 7A BC AF 27 1C` | `7z....` |
| GZIP | `.gz` | `1F 8B` | - |
| BZIP2 | `.bz2` | `42 5A 68` | `BZh` |
| XZ | `.xz` | `FD 37 7A 58 5A 00` | - |
| ELF | `.elf` | `7F 45 4C 46` | `.ELF` |
| Windows EXE | `.exe, .dll` | `4D 5A` | `MZ` |
| MP3 | `.mp3` | `49 44 33` | `ID3` |
| WAV | `.wav` | `52 49 46 46` | `RIFF` |
| FLAC | `.flac` | `66 4C 61 43` | `fLaC` |
| OGG | `.ogg` | `4F 67 67 53` | `OggS` |
| SQLite | `.db, .sqlite` | `53 51 4C 69 74 65 20 66` | `SQLite f` |
| RTF | `.rtf` | `7B 5C 72 74 66` | `{\rtf` |
| ISO 9660 | `.iso` | `43 44 30 30 31` | `CD001` |
| Java Class | `.class` | `CA FE BA BE` | - |
| PCAP | `.pcap` | `D4 C3 B2 A1` | - |
| PCAP (Big Endian) | `.pcap` | `A1 B2 C3 D4` | - |
| PCAPNG | `.pcapng` | `0A 0D 0D 0A` | - |
| XML | `.xml` | `3C 3F 78 6D 6C` | `<?xml` |
| HTML | `.html` | `3C 21 44 4F 43` | `<!DOC` |
