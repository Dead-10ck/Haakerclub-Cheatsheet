# Haakerclub-Cheatsheet

تو این ریپازیتوری ، ابزار ها و قطعه کد هایی که مینویسید قرار گرفته و به جای هر قسمتی که خودتون باید پر کنید ، اون قسمت داخل عبارت `<...>` قرار گرفته که راحت تشخیصش بدید.

ادامه چیت شیت فینگلیش نوشته شده

داخل کد های پایتون راهنمایی هایی داخل کامنت گذاشته شده.
---

# Abzar

---

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
