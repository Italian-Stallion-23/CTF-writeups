# BSides Rochester 2026 - MetaCTF Challenge: Which Witch

## Challenge Description
Help, I'm trying to figure out which witch wrote this hex, but the only thing I have to go off of is this weird text signing the end of the spell. Can you read what it says?

## Objective
The goal of this challenge was to decode a hex-encoded string to reveal the hidden message (flag).

## Tools Used
- CyberChef (From Hex operation)

## Steps

### 1. Identifying the Encoding
The provided string appeared to be hexadecimal based on its format (characters 0-9 and a-f).

### 2. Decoding the Message
I used CyberChef and applied the “From Hex” operation to decode the string.

Encoded string: 4d6574614354467b62337731746368316e675f336e633064316e67357d

### 3. Retrieving the Flag
The decoded output revealed the hidden flag.

## Flag
MetaCTF{b3w1tch1ng_3nc0d1ng5}

## Key Takeaways
- Recognized hexadecimal encoding based on character set
- Used CyberChef to decode hex into ASCII text
- Reinforced pattern recognition for encoded data in CTF challenges


<img width="1910" height="1027" alt="bsides2" src="https://github.com/user-attachments/assets/961218b6-ec76-4712-937b-8bf10f76179b" />

