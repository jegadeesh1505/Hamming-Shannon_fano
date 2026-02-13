# Huffman-Shannon_fano

# Aim:
Consider a discrete memoryless source with symbols and statistics {0.4,0.2,0.2,0.1,0.1} for its output. 
Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.

# Tools Required:
Python IDE with Numpy and Scipy.

# Theory
Huffman coding is an optimal lossless compression algorithm that constructs codes based on symbol probabilities using a binary tree. It is widely used in digital communication systems for efficient data transmission.Shannon–Fano coding is a lossless data compression technique used in digital communication to reduce the number of bits required to represent data. It assigns shorter codes to symbols with higher probability and longer codes to symbols with lower probability.

# Program:
```python

0#Huffman and Shannon-Fano coding
import numpy as np
import math
L  = 0
hs = 0
p = []
lk = []
n = int(input("Enter the number of Samples : "))
for i in range (n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)
for j in range (n):
    l = float(input(f"Enter the length of the sample values {j + 1}: "))
    lk.append(l)
# Avg length of the code word
for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1
# Entropy
for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)
# Efficiency
eff =  hs / L
eff = round(eff,3)
# Redundancy
red =  round(1 - eff,3)
# Variance
var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")

```

# Calculations
![WhatsApp Image 2026-02-13 at 12 50 01 PM](https://github.com/user-attachments/assets/90d39da3-6a1f-4326-8ef8-6030a2b14a82)
![WhatsApp Image 2026-02-13 at 12 50 17 PM](https://github.com/user-attachments/assets/1e763f24-3125-4545-ac61-3332de743f35)


# Output
<img width="489" height="344" alt="image" src="https://github.com/user-attachments/assets/eb2ec44d-7595-4f3c-b1eb-e0798ee877ba" />

# Result
The Huffman and Shannon-Fano of the given statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} using python are verified.
