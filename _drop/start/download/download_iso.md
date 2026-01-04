---
title: Download ISO
nav_order: 7010
has_children: false
parent: 下載
grand_parent: 入門
---



# Download ISO


## 下載腳本

* [下載腳本](https://github.com/samwhelp/note-about-grub/blob/gh-pages/_demo/prototype/boot_iso/demo_41_custom/VoidLinux/latest/iso/download.sh)


### iso-download.txt

```
https://alpha.de.repo.voidlinux.org/live/20210930/void-live-x86_64-20210930-xfce.iso
https://alpha.de.repo.voidlinux.org/live/20210930/void-live-x86_64-musl-20210930-xfce.iso
https://alpha.de.repo.voidlinux.org/live/20210930/void-live-x86_64-20210930.iso
https://alpha.de.repo.voidlinux.org/live/20210930/void-live-x86_64-musl-20210930.iso
https://alpha.de.repo.voidlinux.org/live/20210930/void-x86_64-ROOTFS-20210930.tar.xz
https://alpha.de.repo.voidlinux.org/live/20210930/void-x86_64-musl-ROOTFS-20210930.tar.xz
```


### iso-download.sh

``` sh
wget -c -i iso-download.txt
```
