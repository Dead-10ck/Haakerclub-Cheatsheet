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

### extract LSB
```py
from PIL import Image
img = Image.open("<imagename>")
w,h = img.size
pixels = img.load()

bits = ""

for y in range(h):
  for x in range(w):
    r,g,b = pixels[x,y]

    bits += str(r & 1)
    # bits += str(g & 1)
    # bits += str(b & 1)

print(bits)
```
---

### extract MSB
```py
from PIL import Image
img = Image.open("<imagename>")
w,h = img.size
pixels = img.load()

bits = ""

for y in range(h):
  for x in range(w):
    r,g,b = pixels[x,y]

    bits += str((r >> 7) & 1)
    # bits += str((g >> 7) & 1)
    # bits += str((b >> 7) & 1)

print(bits)
```
---

### make a new image
```py
img = Image.new("RGB", (600, 400), "black")
```

example:
```py
from PIL import Image

img = Image.new("RGB", (600, 400), "black")
w, h = img.size
pixels = img.load()

for y in range(h):
    for x in range(w):
        pixels[x, y] = (255, 0, 0)

img.save("<output.png>")
```

---
### inspect image before starting
```py
from PIL import Image

img = Image.open("<imagename>")

print(img.format)  # image format
print(img.mode)    # image colors mode -> like rgb , rgba , grayscale
print(img.size)    # width and height
```

### convert modes
```py
img = Image.open("<imagename>")

img = img.convert("RGB")
# img = img.convert("RGBA")
# img = img.convert("L")
```

---

### reverse pixels scanning
```py
for y in range(h-1, -1, -1):
    for x in range(w-1, -1, -1):
        r, g, b = pixels[x, y]
```

---
### split channels joda joda
baraye barresie joda jodaye channel haye rangi
```py
from PIL import Image

img = Image.open("<imagename>").convert("RGB")

r, g, b = img.split()

r.save("red.png")
g.save("green.png")
b.save("blue.png")
```
