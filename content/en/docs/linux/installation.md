---
title: Installation
linkTitle: Installation
weight: 20
description: >-
  Install SPL Sense on the Raspberry Pi and set it up as a service that starts at boot.
---

SPL Sense is installed via the command line, either directly on the Raspberry Pi (program **Terminal**) or via SSH from
another computer. With SSH you can copy and paste the commands and avoid typing errors.

## Connecting via SSH

Your computer must be in the same network as the Raspberry Pi.

- **macOS and Linux:** in the terminal `ssh <user>@<ip-address>`, for example `ssh pi@192.168.10.144`
- **Windows:** in the terminal (PowerShell) also `ssh <user>@<ip-address>`, or with PuTTY: enter the IP address under
  **Host Name**, set **Connection type** to **SSH**, then **Open**

User and password are the ones you set in the Raspberry Pi Imager.

## General notes

- Linux is case-sensitive. Copy the commands exactly.
- A successful command usually shows no message. If an error message appears, read it and fix the error before you
  continue.
- At the first `sudo`, the Raspberry Pi asks for your user's password.

## 1. Create a user for SPL Sense

```bash
sudo useradd splsense -m -d /opt/splsense-data
```

SPL Sense runs under this dedicated user and stores its data in `/opt/splsense-data`.

## 2. Download and unpack SPL Sense

For a **32-bit** operating system:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

For a **64-bit** operating system:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm64 -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

## 3. Move the program to its place

```bash
sudo mv splsense /usr/local
sudo chown splsense /usr/local/splsense -R
sudo chgrp splsense /usr/local/splsense -R
```

## 4. Set up the service

So that SPL Sense starts automatically at boot, set it up as a system service. Open a new file in the `nano` editor:

```bash
sudo nano /etc/systemd/system/splsense.service
```

Copy this content into it:

```ini
[Unit]
Description=SPL Sense
After=network-online.target
User=splsense
Group=splsense

[Service]
Type=simple
ExecStart=/usr/local/splsense/SplSense.App.Browser
WorkingDirectory=/usr/local/splsense
Environment="ASPNETCORE_URLS=http://0.0.0.0:8080"
Environment="SPLSENSE_DATA=/opt/splsense-data"

[Install]
WantedBy=multi-user.target
```

Save and close: <kbd>Ctrl</kbd>+<kbd>X</kbd>, then confirm with <kbd>Y</kbd>.

The `ASPNETCORE_URLS` line defines the address and port at which SPL Sense can be reached: here `8080` on all network
interfaces. Enter a different port here if needed. Without this line, SPL Sense can only be reached on the Raspberry Pi
itself (`http://localhost:5000`).

## 5. Enable and start the service

```bash
sudo systemctl enable splsense
sudo service splsense start
```

## 6. Restart

```bash
sudo reboot
```

## Done

SPL Sense now starts automatically at every boot and runs in the background. In the browser of the Raspberry Pi or of
another device in the network, open the IP address with the port, for example `http://192.168.10.144:8080`.

From here it works as on any other platform, for example with the
[quick start]({{< relref "/docs/quick-start#2-connect-the-sensor" >}}). For operation as a permanent measuring station,
see [Operation]({{< relref "operation" >}}).
