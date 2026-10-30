# Dump It

**Event:** DEADFACE CTF 2026  
**Category:** Medical Device

## Challenge

The challenge hinted that the kiosk still accepted keyboard input and had a maintenance console accessible through a key combination. The console included a debug function capable of dumping data.

## Solution

During Live Boot, I had inspected config.yaml and found details about the debug console. It listed the function debug.dump and three available tables:

```text
patients
calibration
audit
```

I plugged in the Rubber Ducky USB-A tool and configured its payload to use debug.dump, with patients as the target table. I chose that table because the investigation had focused on patient information.

After running the payload, the output revealed the flag:

```text
deadface{un10ck3d_k10sk_qu4cks_b4ck}
```

## Takeaway

The kiosk’s touchscreen interface did not prevent keyboard-based access to maintenance functionality. Details exposed in the configuration file helped me use the debug console to dump patient data.

[Back to challenge index](../README.md)
