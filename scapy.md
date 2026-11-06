# Scapy

### simple scapy scan and print
```py
from scapy.all import *
packets = rdpcap('<filename>') #the file we want to check
# packets[2] is third packet for example

for p in packets: # p will be a packet every time
  p.show()
```

---

### for reading packets and indexes
```py
from scapy.all import *
packets = rdpcap('<filename>')

for i,p in enumerate(packets): # p will be a packet every time and i will be 0,1,2,3,4,5
  print(f"\n\n\n --- {i} --->")
  p.show()
```

---

check if a packet has a layer or not
```py
if p.haslayer(TCP):
```

accessing layer attributes 
```py
p[IP].dst # IP layer -> dst attribute
```

---
## accessing and getting packet information (basic)
```py
print(p.time)       # Timestamp
print(p.summary())  # Short summary
print(p.len)        # Packet length
print(p.src)        # Source (if available)
print(p.dst)        # Destination (if available)
```
---

print a packet kholase
```py
print(p.summary())
```

so ... for filter packet by protocol -> you can
```py
# filters and shows a summary of TCP packet
from scapy.all import *

packets = rdpcap("<filename>")

for p in packets:
    if p.haslayer(TCP):
        print(p.summary())
```

---

### extract Raw payload - for application layer data (sooo bekar miad):
```py
from scapy.all import *

packets = rdpcap("<filename>")

for p in packets:
    if p.haslayer(Raw):
        print(p[Raw].load)
```

for example if you want extract TCP layer payload:
```py
for p in packets:
    if p.haslayer(TCP) and p.haslayer(Raw):
        print(p[Raw].load)
```


for example if you want extract load to a specific file:
```py
data = b""

for p in packets:
    if p.haslayer(Raw):
        data += p[Raw].load

with open("<output.bin>", "wb") as f:
    f.write(data)
```
