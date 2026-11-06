# Haakerclub-Cheatsheet

تو این ریپازیتوری ، ابزار ها و قطعه کد هایی که مینویسید قرار گرفته و به جای هر قسمتی که خودتون باید پر کنید ، اون قسمت داخل عبارت `<...>` قرار گرفته که راحت تشخیصش بدید.

ادامه چیت شیت فینگلیش نوشته شده

داخل کد های پایتون راهنمایی هایی داخل کامنت گذاشته شده.

- [Abzars](#Abzar)
- [Linux Commands](#Commands)
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
