---
layout: post
title: "Computer Architecture"
categories: hardware
tags: hardware architect
---

* TOC
{:toc}

Mary Allen Wilkes
https://en.wikipedia.org/wiki/LINC-8

https://www.righto.com/2020/07/the-intel-8086-processors-registers.html

Flynn's taxonomy

speedup (latency, throughput)

cache coherence

Amdahl's law

Gustafson's law

clock

Superscalar processor



<img src="https://github.com/sif/sif/raw/main/files/post_files/hextimestable.png" />



## [Binary](https://www.afterlifesong.com/binary/2002/03/25/binary.html)

$$2^n$$

| 128     | 64      | 32      | 16      | 8       | 4       | 2       | 1       |
| $$2^7$$ | $$2^6$$ | $$2^5$$ | $$2^4$$ | $$2^3$$ | $$2^2$$ | $$2^1$$ | $$2^0$$ |

## Arithmetic

arithmetic logic unit (ALU)



IEEE 754 is the standard for floating-point numbers (32 bits, 64 bits)

- IEEE 754-1985
- IEEE 754-2008
- IEEE 754-2019

754 also defines special values for:

- infinity (positive or negative)
- NaN (not a number) which represents undefined or unrepresentable values
- zero (positive or negative)

754 also defines the rounding rules



## Scheme

von Neumann architecture

Harvard architecture



## CISC



## RISC



## 8-Bit Registers

al



## 16-Bit Registers

ax



## 32-Bit Registers

2<sup>32</sup> = 4,294,967,296 bytes

More accurately, 2<sup>32</sup> - 1 since counting starts from 0 

32-bit architectures include: MIPS, ARM, PowerPC (or PPC), SPARC

In C, you could write:
```
  return 10;
```

The same code in ASM:
```
  mov eax, 10
  ret
```



## 64-Bit Registers

2<sup>64</sup> = 18,446,744,073,709,551,616 bytes

In 32-bit, you write eax, in 64-bit, you write rax



## x86

Comes from Intel 8086

Intel 80386 is known as i386



## x64 or x86-64

x64 includes Intel 64 and AMD 64


