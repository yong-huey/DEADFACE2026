# Factory Reset

**Event:** DEADFACE CTF 2026  
**Category:** Medical Device

## Challenge

The challenge asked me to find valid technician credentials for the ScanWorks login, hinting that the vendor’s default credentials had not been changed.

## Solution

During my investigation of Bedside Manner, I had found an asset label underneath the medical device. Clicking it opened a PDF containing the device documentation, including a default technician account.

I reused those credentials to log into ScanWorks successfully. After logging in, the following flag appeared at the top of the page:

```text
deadface{d3fault_cr3ds_n3v3r_ch4ng3d}
```

Although this flag had been rejected for Bedside Manner, it was the correct flag for Factory Reset.

## Takeaway

The vendor’s documented default credentials were still active, allowing access to the device’s technician account.

[Back to challenge index](../README.md)
