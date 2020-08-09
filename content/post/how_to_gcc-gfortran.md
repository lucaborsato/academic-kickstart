---
# Documentation: https://sourcethemes.com/academic/docs/managing-content/

title: "How To: install gcc & gortran from source"
subtitle: "A simple guide on how to install from source gcc and gfortran"
summary: "A simple guide on how to install from source gcc and gfortran"
authors: []
tags: ["HowTo", "Linux", "gcc", "gfortran"]
categories: ["HowTo"]
date: 2020-08-09T14:39:37+02:00
lastmod: 2020-08-09T14:39:37+02:00
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

### download  

1. go to website: [https://gcc.gnu.org/mirrors.html](https://gcc.gnu.org/mirrors.html)  
2. select the mirror  
3. enter `releases/gcc-X.Y.Z/`  
4. download desired tar.gz or tar.bz2 file  
5. unpack into a folder, e.g., `/home/user/gcc/src/gcc-X.Y.Z/`  

### pre-compile  

1. create an empty folder where to build gcc, i.e., `/home/user/gcc/build/build_gcc-X.Y.Z/`
2. download prerequisites executing **from source folder** (`/home/user/gcc/src/gcc-X.Y.Z/`):  
  `./contrib/download_prerequisites`  
3. create executable folder, e.g., `/home/user/gcc/bin/gcc-X.Y.Z/`
4. **from build folder** run configure:  
  `/home/user/gcc/src/gcc-X.Y.Z/configure --prefix=/home/user/gcc/bin/gcc-X.Y.Z --program-suffix=-X.Y.Z --enable-languages=c,c++,fortran --enable-checking=release --disable-bootstrap`  

### compile and install  

**from build folder**:  

1. `make`
    * `make -jN` for multi-cpu compiling  
2. `make install`  

### linkin libraries and bin

1. Add `PATH` to the `.bashrc` file:  
  export bin path  
  `export PATH='/path/to/gcc/bin':$PATH`  
2. Add `LIBGCC` to the `.bashrc` file:  
  export lib path:  
  `export LIBGCC='/path/to/gcc/lib64':'/path/to/gcc/lib':$LIBGCC`  
  and add it to the `LD_LIBRARY_PATH`:   
  `export LD_LIBRARY_PATH=$LIBGCC:$LIBOMPI:$LD_LIBRARY_PATH`  

