
### 1) Get the interface name and the ip addresses from ifconfig output 

```
s = """eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.1.10  netmask 255.255.255.0  broadcast 192.168.1.255
        inet6 fe80::a00:27ff:fe94:63a4  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:94:63:a4  txqueuelen 1000  (Ethernet)
        RX packets 5678  bytes 4567890 (4.3 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4321  bytes 3456789 (3.2 MiB)
        TX errors 0  dropped 0  overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING,LOWER_UP>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 1234  bytes 123456 (120.5 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 1234  bytes 123456 (120.5 KiB)
        TX errors 0  dropped 0  overruns 0  carrier 0  collisions 0

wlan0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        inet 192.168.0.15  netmask 255.255.255.0  broadcast 192.168.0.255
        inet6 2001:db8:85a3:0:0:8a2e:370:7334  prefixlen 64  scopeid 0x0<global>
        ether 00:c0:ca:88:53:9b  txqueuelen 1000  (Ethernet)
        RX packets 8910  bytes 6789012 (6.4 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 6543  bytes 5678901 (5.4 MiB)
        TX errors 0  dropped 0  overruns 0  carrier 0  collisions 0

docker0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.17.0.1  netmask 255.255.0.0  broadcast 172.17.255.255
        inet6 fe80::be5e:6eff:fe2e:67a8  prefixlen 64  scopeid 0x20<link>
        ether be:5e:6e:2e:67:a8  txqueuelen 0  (Ethernet)
        RX packets 789  bytes 56789 (55.4 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 987  bytes 67890 (66.3 KiB)
        TX errors 0  dropped 0  overruns 0  carrier 0  collisions 0"""

lines = s.splitlines()
interfaces = {}

for line in lines:
    line = line.strip()
    words = line.split(" ")
    if ":" in line and words[0].endswith(":"):
        interface_name = line.split(":")[0]
        interfaces[interface_name] = {"ipv4": [], "ipv6": []}
        continue
    if interface_name:
        parts = line.split()
        for part in parts:
            if "." in part and len(part.split(".")) == 4:
                interfaces[interface_name]['ipv4'].append(part)
            if ":" in part and len(part.split(":")) > 3:
                interfaces[interface_name]['ipv6'].append(part)
        
print(interfaces)
```

### 2) Given a paragraph describing a fruit stand's inventory (e.g., "12 apples, 5 bananas..."), extract the fruit names and their counts, and store them in a dictionary (e.g., {"apples": 12, "bananas": 5}).  Write a function to do this.

```
s = "The fruit stand has 12 apples, 5 bananas, and 7 oranges. There are also 3 pineapples and 20 strawberries. In total, there are 47 fruits."

op = {}
words = s.split(" ")
for i, word in enumerate(words):
    if word.endswith(".") or  word.endswith(","):
        word = word.strip(".,")
    try:
        num = int(word)
        if i+1 < len(words):
            op[words[i+1].strip(".,")] = num
    except ValueError:
        pass

print(op)
```
