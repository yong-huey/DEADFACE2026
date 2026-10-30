# Live Boot

**Event:** DEADFACE CTF 2026  
**Category:** Medical Device

## Challenge

The challenge asked me to access the device’s underlying filesystem and locate hardcoded keys that were not documented in the Field Manual.

## Solution

I plugged in the Linux USB-A tool to access a shell, then explored the available commands and files:

```bash
help
ls
```

The directory contained a README.txt file. Its instructions provided a command to mount the device’s disk partition:

```bash
sudo mount /dev/sda2 /mnt
```

The instructions also pointed me toward /mnt/opt/scanworks. I navigated to that directory and listed its contents:

```bash
cd /mnt/opt/scanworks
ls
```

Among the files was config.yaml. I inspected it using:

```bash
cat config.yaml
```

The configuration file contained the flag:

```text
deadface{h4rdc0d3d_k3ys_1n_th3_c0nf1g}
```

## Takeaway

Accessing the filesystem through the Linux USB environment allowed me to inspect the application’s configuration and discover hardcoded secrets.

[Back to challenge index](../README.md)
