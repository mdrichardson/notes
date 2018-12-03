# Bit Manipulation

## Binary Numbers

### Positive

In base 10 583 is equal to `5*10^2 + 8*10^1 + 3*10^0`

In base 2 (binary) 101 is equal to `1*2^2 +  0*2^1 + 1*2^0`, which is 5 in base 10

### Addition

When you add, you do the same as you would in base 10.

```
  583
+ 637
------
 1220
```

You carry over the extra digits when you go over 10. Same for binary, but when it hits 2:

```
  101
+ 011
-------
 1000
```

### Negative

If we're using 8-bit integers and have 18, in base 10...

In base 2: `00010010`

The first 0 is the *sign bit*. The 0 means it's positive. A 1 would mean it's negative.

To convert from 18 to -18, you need to figure out what we add to the binary representation of 18 (00010010), to make it equal 2^8 (since we're working with 8 bit integers).

There's two steps to this process.

1. Invert all of the numbers. So...
    `00010010` becomes
    `11101101`
    If you add those two together, you end up with
    `01111111`

2. To make `01111111` become `10000000` (2^8 in binary), you need to add 1.

So, -18 in binary is `1101110`. Note that this is `11101101` plus 1--you add 1 to the 1 at the right, and that carries over and to the 2nd digit from the right. Again, the steps are:

1. Invert all of the 1s and 0s
2. Add one

### Shifting

To left shift, you move everything over by one, to the left. Anything that goes too far is basically just forgotten.

```
00010111 (23) becomes
00101110 (46)
```

Right shift works the same, but in reverse

```
00010111 (23) becomes
00001011 (11)
```

In a *Logical* left/right shift, you change the *sign bit* as necessary when the numbers shift over. This can be a little strange, math-wise as 

```
11101001 (-23) becomes
01110100 (116) with a right shift
```

With an *arithmetic* shift, everything shifts over like it would otherwise, but the *sign bit* stays the same, no matter what.

```
11101001 (-23) becomes
11110100 (-12)
```

```
>>> = Logical Right Shift
<< = Arithmetic Left Shift
>>=1 = Arithmetic Right Shift by 1
```

With an arithmetic shift, the result is equal to half of the original, rounded up. So:

```
10110101 (-75) >>> = 11011010 (-38)
```

### Masks

```
AND: Only get 1 if both bits are 1
0&0 => 0
0&1 => 0
1&1 => 1

OR: Get 1 if either are 1
0|0 => 0
0|1 => 1
1|1 => 1

XOR (Exclusive OR): Get 1 if exactly 1 bit is a 1
0^0 => 0
0^1 => 1
1^1 => 0

NOT: Inverts all
```

### Get Bit

Gets the value of num at i'th digit from right.

```javascript
getBit = (num, i) => {
  return (num & (1 << i)) != 0;
}
```

### Set Bit

Sets the value of num at i'th digit from right to 1.

```javascript
setBit = (num, i) => {
  return num | (1 << i);
}
```

### Clear Bit

Sets the value of num at i'th digit from right to 0.

```javascript
clearBit = (num, i) => {
  const mask = ~(1 << i);
  return num & mask;
}
```

### Update Bit

Sets the value of num at i'th digit from right to 0 or 1.

```javascript
updateBit = (num, i, bitValue) => {
  const mask = ~(1 << i);
  return num & mask | (bitValue << i);
}
```

## Why Use Bitwise Operators

1. Save space: instead of 8 true/false flags, you can just represent it as 00010101. Still easy to turn all on/off, etc using masks/operators