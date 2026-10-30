# Bedside Manner

**Event:** DEADFACE CTF 2026  
**Category:** Medical Device

## Challenge

The challenge described a suspected compromise of an internal medical device at St Dymphna’s Medical Center. Two individuals had allegedly impersonated IT staff to gain physical access. Our first task was to identify strings left behind by developers in the device’s kiosk web browser.

## Solution

I initially explored the device’s physical interfaces. Connecting an HDMI cable to its HDMI port revealed a diagnostic on-screen display with levels ranging from 0/3 to 3/3. Raising the diagnostic level to 3/3 exposed a diag-session string:

```text
deadface{hdm1_l34ks_th3_wh0l3_p4t13nt}
```

I submitted it, but it was not accepted for this challenge.

Next, I found an asset label underneath the device. Clicking it opened a PDF containing device documentation, including default technician credentials. I used those credentials to log in successfully.

After logging in, another flag-like string appeared at the top of the page:

```text
deadface{d3fault_cr3ds_n3v3r_ch4ng3d}
```

This was also rejected for the challenge.

The diagnostic display had exposed a patient’s name, so I investigated that patient’s record while logged in as the technician. Their scan instructed me to refer it for radiologist review, but this did not resolve the task.

I reread the challenge and refocused on its specific wording: developer strings in the kiosk web browser. I inspected the JavaScript files and searched for /api/ to identify endpoints used by the application.

One endpoint I investigated was:

```text
/api/kiosk/login
```

I attempted to log in there using the technician credentials from the PDF, but I was not redirected elsewhere. I then opened View Page Source for the page. The flag was present in the source.

## Takeaway

The device exposed several interesting findings, but the challenge required a specific browser-related discovery. Returning to the prompt and inspecting the page source led me to the requested developer string.

[Back to challenge index](../README.md)
