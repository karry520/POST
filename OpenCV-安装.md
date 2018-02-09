---
title: OpenCV-Introduction
date: 2018-01-24 21:32:42
tags: OpenCV
---
- ### Required Packages 

---
~~~
[compiler] sudo apt-get install build-essential
[required] sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
[optional] sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev
~~~
- ### Getting OpenCV source Code 

---
[opencv/releases](https://opencv.org/releases.html)
- ### Building OpenCV 

---
- Create a temporary directory directory.
~~~
cd ~/opencv
mkdir build 
cd build
~~~
- Configuring.
~~~
cmake -D CMAKE_BUILD_TYPE=Release -D CMAKE_INSTALL_PREFIX=/usr/local ..
~~~
- Build.
~~~
make -j7 # runs 7 jobs in parallel
~~~
- Building documents
~~~
cd ~/opencv/build/doc/
make -j7 doxygen
~~~
- ### Install libraries 

---
~~~
sudo make install
~~~
- ### Configering environment

---
~~~
sudo vim /etc/ld.so.conf.d/opencv.conf
add
/usr/local/lib
sudo ldconfig
sudo vim /etc/bash.bashrc
add
PKG_CONFIG_PATH=$PKG_CONFIG_PATH:/usr/local/lib/pkgconfig 
export PKG_CONFIG_PATH
~~~
- ### Runing tests
 
---
~~~
#include <opencv2/opencv.hpp>
#include <iostream>
using namespace std;
using namespace cv;

int main()  
{  
    Mat img= imread("1.jpg",0);
    imshow("test",img);
    waitKey(0);
    return 0;
}
~~~
