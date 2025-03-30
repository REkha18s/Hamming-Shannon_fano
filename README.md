# Huffman-Shannon_fano
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that draw the tree diagram, the average code word length, Entropy, Variance, Redundancy, Efficiency.
# Aim
To compute the Average Codeword Length, Entropy, Efficiency, Redundancy, and Variance for a discrete memoryless source using Huffman and Shannon-Fano coding based on the given probabilities and codeword lengths.

# Tools Required

Python: A versatile programming language used for scientific computing and signal processing. NumPy: A powerful numerical library in Python for performing array-based operations and mathematical computations. Matplotlib: A plotting library for generating high-quality graphs and visualizations of data, essentialfor demonstrating the sampling process.

# Program
```
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

for k in range (n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

for k in range (n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e
hs = round(hs,3)

eff = hs / L
eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0
for k in range(n):
    var1 = p[k] * (lk[k]-L)**2
    var = var + var1
var = round(var,3)
print()
print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff*100} %")
print(f"Redudancy is : {red}")
print(f"Variance is : {var}")
```
# Calculation
![WhatsApp Image 2025-03-30 at 22 16 58_bbf4c76f](https://github.com/user-attachments/assets/bfcd3485-b2df-4edb-a505-3bba61284501)
![WhatsApp Image 2025-03-30 at 22 16 58_a30adc74](https://github.com/user-attachments/assets/c476bc4c-6b0b-49bb-9cbd-e1232a8bc05f)
![WhatsApp Image 2025-03-30 at 22 16 58_bb6ce3e2](https://github.com/user-attachments/assets/57a68dc2-fd93-4949-b08a-7f76f8a05d01)

# Results.

For the given probabilities {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25}:

Average Codeword Length: 2.625

Entropy: 2.625

Efficiency: 100.0%

Redundancy: 0.0

Variance: 0.484

