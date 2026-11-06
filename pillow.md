# Pillow

### simple image scan
```py
from PIL import Image
img = Image.open("<imagename>")
w,h = img.size
pixels = img.load()

for y in range(h):
  for x in range(w):
    r,g,b = pixels[x,y]
    # r,g,b,a = pixels[x,y]
```

---

### print unrepeated pixels
```py
from PIL import Image
img = Image.open("<imagename>")
w,h = img.size
pixels = img.load()

pix = set()

for y in range(h):
  for x in range(w):
    pix.add(pixels[x,y])

print(pix)
```
---

### change pixels
```py
from PIL import Image
img = Image.open("<imagename>")
w,h = img.size
pixels = img.load()

for y in range(h):
  for x in range(w):
    r,g,b = pixels[x,y]
    if <condition>:
        pixels[x,y] = (<r,g,b>)

img.save(<out.png>)
```
---
