---
title: Update
linkTitle: Update
weight: 30
description: >-
  Update SPL Sense on Linux: automatically or manually.
---

## Automatically

On Linux, SPL Sense updates itself like on the other platforms: when a new version is available, **Update available**
appears on the overview. Stop the measurement and click **Update** and **Update and restart**. See
[Installation and updates]({{< relref "/docs/spl-sense/installation-and-updates#updates" >}}).

This works if SPL Sense is set up as described in the [installation]({{< relref "installation" >}}).

## Manually

If the automatic update fails, update via the command line. Connect to the Raspberry Pi as in the
[installation]({{< relref "installation#connecting-via-ssh" >}}). The
[general notes]({{< relref "installation#general-notes" >}}) apply here too.

### 1. Stop SPL Sense

```bash
sudo service splsense stop
```

### 2. Download and unpack the new version

32 bit:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

64 bit:

```bash
wget https://r.spl.swiss/dl/splsense/linux-arm64 -O splsense-latest.tar.gz
tar xfvz splsense-latest.tar.gz
rm splsense-latest.tar.gz
```

### 3. Replace the old version

```bash
sudo rm -rf /usr/local/splsense
sudo mv splsense /usr/local
sudo chown splsense /usr/local/splsense -R
sudo chgrp splsense /usr/local/splsense -R
```

The measurement data is in `/opt/splsense-data` and is kept.

### 4. Start and restart

```bash
sudo service splsense start
sudo reboot
```
