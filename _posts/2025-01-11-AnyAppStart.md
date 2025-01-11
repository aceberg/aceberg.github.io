---
title: AnyAppStart
date: 2025-01-11 16:52:00 +/-0700
categories: [MyApps, AnyAppStart]
tags: [golang, react, selfhosted]     # TAG names should always be lowercase
---
I created [AnyAppStart](https://github.com/aceberg/AnyAppStart) - control panel to `Start`/`Stop`/`Restart`/`View Logs` for Docker, Systemd, VMs or anything else (with user scripts). Written in `Go` and `React`. Features:

- User can add any types (like LXC or WakeOnLAN)
- Control remote machines via SSH
- Config in `yaml` files, no DB
- Simple API

![Screenshot](https://raw.githubusercontent.com/aceberg/AnyAppStart/refs/heads/main/assets/Screenshot_05.png)

## Reasons for creating AnyAppStart
My use cases:
- Resource heavy but rarely used apps. Start them only when necessary
- Environments for development, learning and experimenting. I do not need them all running at the same time
- Being able to control local and remote apps from one place, no matter what type (Docker, Systemd, VM, bash script)

## Installation
There is Docker image [available](https://github.com/aceberg/AnyAppStart?tab=readme-ov-file#installation), but inside the container only Docker Type will work, which kinda defeats the purpose of this app. So installing binary is recommended. 

All binary packages can be found in the [latest](https://github.com/aceberg/AnyAppStart/releases/latest) release. There are `.deb`, `.rpm`, `.apk` (Alpine Linux) and `.tar.gz` files.   

Supported architectures: `amd64`, `i386`, `arm_v5`, `arm_v6`, `arm_v7`, `arm64`.   

For `amd64` there is a `deb` repo [available](https://github.com/aceberg/ppa)