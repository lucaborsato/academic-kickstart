---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How To: gpu info under linux"
subtitle: "Not-complete guide on how to get info about your gpu under Linux."
summary: "Not-complete guide on how to get info about your gpu under Linux."
authors: ["admin"]
tags: ["HowTo", "Linux", "gpu"]
categories: ["HowTo"]
date: 2020-08-09T15:10:21+02:00
lastmod: 2020-08-09T15:10:21+02:00
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

Check which gpu you have via VGA controller:  

```bash
lspci -v |grep VGA
```

Run a program on the discrete gpu (nvidia):  

```bash
DRI_PRIME = 1 COMMAND
```

Check if opengl working:  

```bash
glxinfo | grep -i opengl
DRI_PRIME=1 glxinfo | grep -i opengl
```

Use the `acpi_call` to check model:  

[web_page_acpi_call](http://hybrid-graphics-linux.tuxfamily.org/index.php?title=ACPI_calls)

Other info:  

[Use acpi_call](https://abz89.wordpress.com/2012/11/26/disabling-discrete-gpu-in-most-linux-system/)  

[Full info webpage graphics](https://www.cyberciti.biz/faq/linux-tell-which-graphics-vga-card-installed/)  

## In case of hybrid NVIDIA-INTEL linux pc

With nvidia driver:  

How to switch from one graphic card to the other.
Starting from nVidia 435 drivers, we can finally offload apps like on Windows without having to use very complicated setups with Bumblebee.
If during the script you chose to not enabling offloading, you can use the classic prime-select command:

Intel:

```bash
sudo prime-select intel
```

Nvidia:

```bash
sudo prime-select nvidia
```

Note: A full reboot or log out/in could be required when switching graphic cards.

When selected nvidia you can change settigs via:  

```bash
nvidia-settings
```

and other info, such fan, temperature, memory etc via:  

```bash
nvidia-smi
```
