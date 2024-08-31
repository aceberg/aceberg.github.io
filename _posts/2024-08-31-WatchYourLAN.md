---
title: WatchYourLAN
date: 2024-08-31 14:52:00 +/-0700
categories: [MyApps, WatchYourLAN]
tags: [golang, js, selfhosted]     # TAG names should always be lowercase
---

After two years of development, here is `WatchYourLAN` `v2` release!

## What's new?
- Basic `API`
- Export to `InfluxDB2`
- Choise between `SQLite` and `PostgreSQL` database
- User can pass arguments directly to `arp-scan`. Hope it will help with `vlan` issue.
- Better `UI` with `JS`
- Human-friendly `History` display

![Screenshot_1](https://raw.githubusercontent.com/aceberg/WatchYourLAN/main/assets/Screenshot_1.png) 

## Quick start
Full installation guide is available in the [README](https://github.com/aceberg/WatchYourLAN) file. The easiest way to try it:

```sh
docker run --name wyl \
	-e "IFACES=$YOURIFACE" \
	-e "TZ=$YOURTIMEZONE" \
	--network="host" \
	-v $DOCKERDATAPATH/wyl:/data/WatchYourLAN \
    aceberg/watchyourlan:v2
```
Web GUI should be at http://localhost:8840