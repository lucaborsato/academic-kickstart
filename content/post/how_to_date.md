---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How To: date"
subtitle: "A collection of commands to use to set/get date and time under Linux."
summary: "A collection of commands to use to set/get date and time under Linux."
authors: ["admin"]
tags: ["HowTo", "Linux", "date"]
categories: ["HowTo"]
date: 2020-08-09T14:46:54+02:00
lastmod: 2020-08-09T14:46:54+02:00
featured: false
draft: false

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
# Focal points: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight.
image:
  caption: ""
  focal_point: ""
  preview_only: false

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects: []
---

## Linux Set Date Command Example

Use the following syntax to set new data and time:

```bash
date --set="STRING"
```

For example, set new data to 2 Oct 2006 18:00:00, type the following command as root user:

```bash
date -s "2 OCT 2006 18:00:00"
```

or  

```bash
date --set="2 OCT 2006 18:00:00"
```

You can also simplify format using following syntax:  

```bash
date +%Y%m%d -s "20081128"
```

## Linux Set Time Examples  

To set time use the following syntax:  

```bash
date +%T -s "10:13:14"
```

Where,  
10: Hour (hh)  
13: Minute (mm)  
14: Second (ss)  

Use %p locale's equivalent of either AM or PM, enter:  

```bash
date +%T%p -s "6:10:30AM"
date +%T%p -s "12:10:30PM"
```

How do I set the Hardware Clock to the current System Time?  

Use the following syntax:  

```bash
hwclock --systohc
```

or  

```bash
hwclock -w
```

## SYNCHRONIZE TIME WITH POOLSERVER

install ntp and to file `/etc/ntp.conf`:

```bash
server 0.europe.pool.ntp.org
server 1.europe.pool.ntp.org
server 2.europe.pool.ntp.org
server 3.europe.pool.ntp.org
```

then run  

```bash
sudo service ntp stop
# >> * Stopping NTP server ntpd
sudo ntpdate europe.pool.ntp.org
# >> 18 Jul 00:59:15 ntpdate[25758]: adjust time server 129.70.132.37 offset 0.015345 sec
sudo service ntp start
# >> * Starting NTP server ntpd
sudo ntpq -p
# wait...and done :-)
```

or use this:  

```bash
sudo ntpdate -d ntp.ubuntu.com
```

update time:  

```bash
sudo ntpdate -uv it.pool.ntp.org
```

or  

```bash
sudo ntpdate -uv europe.pool.ntp.org
sudo ntpdate -uv ntp.ubuntu.com
```
