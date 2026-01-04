---
title: Download ISO
nav_order: 1000
has_children: false
parent: ISO
---


# Download ISO




## Void Linux

* Void Linux / [News](https://voidlinux.org/news/)




## 下載腳本

* [下載腳本](https://github.com/samwhelp/voidlinux-adjustment/tree/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-voidlinux-iso)




## 下載點

> 可以到「Void Linux / [Download](https://voidlinux.org/download/)」找到下載點。

* [https://repo-default.voidlinux.org/live/current/](https://repo-default.voidlinux.org/live/current/)




## 下載方式


### iso-download.txt

先產生一個檔案「`iso-download.txt`」，內容如下

```
https://repo-default.voidlinux.org/live/current/void-live-x86_64-20250202-xfce.iso
```


### iso-download.sh

接著執行下面的指令，就會下載剛剛「`iso-download.txt`」裡面所列的檔案

``` sh
wget -c -i iso-download.txt
```

> 關於「`-c`」指的是續傳

> 關於「`-i iso-download.txt`」，指的是下載「`iso-download.txt`」裡面所列的檔案




## Boot ISO

> 簡單「[驗證](#驗證)」過「下載完成的ISO檔案」，接下來可以選擇不同的「[Boot ISO](https://samwhelp.github.io/note-about-voidlinux/read/core/iso/boot-iso.html)」方式。





## 驗證


### sha256sum

* [man sha256sum](https://manpages.debian.org/bookworm/coreutils/sha256sum.1.en.html)

執行

``` sh
wget -c https://repo-default.voidlinux.org/live/current/sha256sum.txt

sha256sum -c sha256sum.txt
```

會看到類似如下的內容

```
void-live-x86_64-20250202-xfce.iso: OK
```
