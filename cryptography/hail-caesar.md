# Hail Caesar

**Event:** DEADFACE CTF 2026  
**Category:** Cryptography

## Challenge

The challenge asked me to recover a faculty member’s dog’s name from a password hint written on a sticky note beside their computer.

## Solution

I opened the provided image and found the encoded text:

```text
Zl qbt'f anzr vf Srgpu
```

The challenge title suggested a Caesar cipher, but I did not initially know the shift. I entered the text into a Caesar cipher decoder and tried different rotations.

Using ROT13, which shifts each letter by 13 positions, produced:

```text
My dog's name is Fetch
```

The decoded hint identified the dog’s name as Fetch, giving the flag:

```text
deadface{Fetch}
```

## Takeaway

Trying the possible shifts of a Caesar cipher quickly revealed the readable message and the password hint.

[Back to challenge index](../README.md)
