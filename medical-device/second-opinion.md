# Second Opinion

**Event:** DEADFACE CTF 2026  
**Category:** Medical Device

## Challenge

The challenge described a touchscreen that displayed only the current patient’s initials and a masked record number. It asked whether sensitive patient information could be recovered without logging in, using the device’s exposed maintenance ports.

## Solution

During my earlier investigation of Bedside Manner, I had connected an HDMI cable from the toolkit to the device’s HDMI port. This revealed a diagnostic on-screen display with levels ranging from 0/3 to 3/3.

Raising the diagnostic level to 3/3 exposed the patient’s name and a diag-session string:

```text
deadface{hdm1_l34ks_th3_wh0l3_p4t13nt}
```

I reused this previously discovered flag and submitted it for Second Opinion.

## Takeaway

Although the touchscreen masked patient information, the exposed HDMI interface revealed sensitive details through its diagnostic display without requiring authentication.

[Back to challenge index](../README.md)
