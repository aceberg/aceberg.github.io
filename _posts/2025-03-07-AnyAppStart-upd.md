---
title: AnyAppStart Update
date: 2025-03-06 16:52:00 +/-0700
categories: [MyApps, AnyAppStart]
tags: [golang, react, selfhosted]     # TAG names should always be lowercase
---
## AnyAppStart-0.1.3: now works fully from Docker!

[AnyAppStart](https://github.com/aceberg/AnyAppStart) is a control panel to `Start`/`Stop`/`Restart`/`View Logs, CPU, Memory` for Docker, Systemd, VMs or anything else (with user scripts).

### What's new
- Easyly **SSH** into other machines from Docker container 
- **CPU** and **Memory** consumption data
- Better performance

![Screenshot](https://raw.githubusercontent.com/aceberg/AnyAppStart/refs/heads/main/assets/Screenshot_06.png)

### Quick start (Docker)

```sh
docker run --name AnyAppStart \
  -e "TZ=$YOURTIMEZONE" \
  -v ~/.dockerdata/AnyAppStart:/data/AnyAppStart \ # yaml files here
  -v /var/run/docker.sock:/var/run/docker.sock \   # mount docker
  -p 8855:8855 \
aceberg/anyappstart # or ghcr.io/aceberg/anyappstart
```
Or use [docker-compose.yaml](https://github.com/aceberg/AnyAppStart/blob/main/docker-compose.yml)

Binary packages are still [available](https://github.com/aceberg/AnyAppStart/releases).