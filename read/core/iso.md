---
title: ISO
nav_order: 1000
has_children: true
---


# ISO




## 主題

| 主題 |
| --- |
| [Download ISO](https://samwhelp.github.io/note-about-voidlinux/read/core/iso/download-iso.html) |
| [Boot ISO](https://samwhelp.github.io/note-about-voidlinux/read/core/iso/boot-iso.html) |




## Live Account

> 使用「Debian Live ISO」開機後，自動登入的帳號。

| Live Account  | Value       |
| ------------- | ----------- |
| Username      | `anon`      |
| Password      | `voidlinux` |


| Root Account  | Value       |
| ------------- | ----------- |
| Username      | `root`      |
| Password      | `voidlinux` |


> 執行下面指令，更改目前登入帳號的密碼。

``` sh
sudo passwd $(whoami)
```


> 執行下面指令，移除目前登入帳號的密碼。

``` sh
sudo passwd -d $(whoami)
```
