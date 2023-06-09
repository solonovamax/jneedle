# jneedle
Yet another jar malware detection tool

---
## How to find the needle in a haystack? - Use a strong enough magnet

The detection tool is parsing jar `.class` files looking for signature instruction sequences.
It is actually similar to string search:

Is the following sequence: `"jump into the well"`
in the program:
```text
exit house and lock door,
get the bus and to the shop to buy milk
jump into the well then get the bus
come home
```

