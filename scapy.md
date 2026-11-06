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
