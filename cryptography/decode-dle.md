# DECODE-DLE

**Event:** DEADFACE CTF 2026  
**Category:** Cryptography

## Challenge

The challenge presented a number puzzle with clues for determining a three-digit lock combination.

## Solution

I started with the second combination, which allowed me to eliminate 2, 5, and 0 from consideration.

Next, I compared the third and fifth clues. These suggested that 1 and 7 were part of the code. With 7 identified as a correct digit, I used the fourth clue to eliminate 3.

After working through the clues, I narrowed my candidates down to:

```text
716
718
```

I tested 716, and it was accepted, giving the flag:

```text
deadface{716}
```

## Takeaway

Comparing the clues helped eliminate digits and narrow the possible combinations. I then confirmed the solution by testing one of the remaining candidates.

[Back to challenge index](../README.md)
