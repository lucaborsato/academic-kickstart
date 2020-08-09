---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How To: dd with iso"
subtitle: "A simple guide on how to use the dd command to burn iso files."
summary: "A simple guide on how to use the dd command to burn iso files."
authors: ["admin"]
tags: ["HowTo", "Linux", "dd"]
categories: ["HowTo"]
date: 2020-08-09T14:23:14+02:00
lastmod: 2020-08-09T14:23:14+02:00
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

## Use `dd` command  

- for FEDORA iso:  
  `sudo dd bs=8M status=progress oflag=direct if=/path/to/iso/file.iso of=/dev/sdX`  
  old release of `dd` could not support the flag `status=progress`, so remove it.  

- other LINUXOS, such as K/X/L/Ubuntu and Manjaro can be burned with:  
  `sudo dd bs=4M if=/path/to/iso/file.iso of=/dev/sdX`  

- from ANTERGOS webpage:  
  `sudo dd bs=4M if=/path/to/antergos-x86_64.iso of=/dev/sdX status=progress && sync`  

At the end of the `dd` command you can add:

- `conv = fdatasync`  
- or `&& sync` in order to syncronise the device.  

### ALTERNATIVE: use `ddrescue` command

- install gddrescue
- sudo ddrescue -D --force img_or_iso_file /dev/sdx

