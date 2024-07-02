---
title: WatchYourPorts
date: 2024-07-02 14:52:00 +/-0700
categories: [MyApps, WatchYourPorts]
tags: [golang, js, selfhosted]     # TAG names should always be lowercase
---

I'm using a lot of selfhosted apps, both at work and in my homelab. Of course, I can't remember all ports taken by those apps. So, the idea of ports inventory seems reasonable.

## Why

#### Why not just use Portainer or other Docker tool? 
- Not all apps are hosted in `Docker`. Some things must be run as `systemd` services.
- Port may be exposed in `Docker`, but blocked by firewall.
- There may be ports exposed to the world, you are not aware of. 

#### So, the purposes of WatchYourPorts are:
1. Inventory
2. Security 
3. Monitoring

Monitoring is the last one, because it's not the main purpose of this app. There are already tools for that. `WatchYourPorts` can do simple port scan on timer and export data to `InfluxDB2/Grafana`.

![Screenshot](https://raw.githubusercontent.com/aceberg/WatchYourPorts/main/assets/Screenshot1.png) 

## Details

- No DataBase, all config is stored in two `yaml` files.
- All configuration can be done through `ENV` variables, `yaml` or `GUI`.
- `Docker` images for `arm/v6`,`arm/v7`,`arm/arm64`.
- Binary [releases](https://github.com/aceberg/WatchYourPorts/releases) for many platforms.
- Export to `InfluxDB2`, which allows to build a `Grafana` dashboard.
- Simple [API](https://github.com/aceberg/watchyourports#api) to get data from `WatchYourPorts`.

## How
Full installation guide is available in the [README](https://github.com/aceberg/WatchYourPorts) file. The easiest way to try it:

```sh
docker run --name wyp \
-e "TZ=$YourTimeZone" \
-v ~/.dockerdata/WatchYourPorts:/data/WatchYourPorts \
-p 8853:8853 \
aceberg/watchyourports
```