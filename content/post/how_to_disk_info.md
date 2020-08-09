---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How To: disk info"
subtitle: "How to get some information about your disk from linux command line."
summary: "How to get some information about your disk from linux command line."
authors: ["admin"]
tags: ["HowTo", "Linux", "df", "bash"]
categories: ["HowTo"]
date: 2020-08-09T14:30:16+02:00
lastmod: 2020-08-09T14:30:16+02:00
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

### list of all disks/mounts with total space, used, free space  

```bash
df -h
```

### total space of  

a folder:  

```bash
sudo du -hs /home
```

many folders (with script):  

```bash
#!/bin/bash  
for folder in $(ls -1 /home/)
do
    echo "/home/${folder}"
    if [[ "${folder}" != "dip-sys" && "${folder}" != "lost+found" ]]; then
        echo "sudo du -hs /home/${folder}"
        sudo du -hs /home/${folder}
    fi
done
```

or  

```bash
#!/bin/bash  
for folder in $(ls -1 /home/)
do
    if [[ "${folder}" != "dip-sys" && "${folder}" != "lost+found" ]]; then
      du -hs /home/${folder}
    fi
done
```

then run with `sudo ./script.sh`  
