---
title: Boot ISO By USB
nav_order: 7020
has_children: false
parent: 下載
grand_parent: 入門
---


# Boot ISO By USB

## 操作步驟

先在「Void Linux / [Download](https://voidlinux.org/download/)」，

找到「最新的ISO檔案下載網址」，

假設下載「[void-live-x86_64-20210930-xfce.iso](https://alpha.de.repo.voidlinux.org/live/current/void-live-x86_64-20210930-xfce.iso)」

先執行下面指令，找到「USB隨身碟」的「Device代號」

``` sh
lsblk
```

假設是「/dev/sdb」

接著執行下面指令，就會寫入「USB隨身碟」。

``` sh
sudo dd if=./void-live-x86_64-20210930-xfce.iso of=/dev/sdb bs=4M status=progress && sync
```

接著重新開機，在「BIOS」選擇使用「該USB隨身碟」開機。


## 範例腳本

* [iso-to-usb.sh](https://github.com/samwhelp/note-about-grub/blob/gh-pages/_demo/prototype/boot_iso/demo_41_custom/VoidLinux/latest/iso/iso-to-usb.sh)
