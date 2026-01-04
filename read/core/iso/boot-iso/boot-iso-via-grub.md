---
title: Boot ISO Via GRUB
nav_order: 1040
has_children: false
parent: Boot ISO
grand_parent: ISO
---


# Boot ISO Via GRUB




## 範例專案

* boot-iso-via-grub / [demo-boot-voidlinux-iso](https://github.com/samwhelp/voidlinux-adjustment/tree/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-voidlinux-iso)




## 下載 ISO

先參考「[Download ISO](https://samwhelp.github.io/note-about-voidlinux/read/core/iso/download-iso.html)」這篇提到的下載方式，下載「Void Linux 官方提供最新的ISO檔案」。

將「ISO檔案」放到「`/opt/iso/voidlinux/latest/void-live-x86_64-20250202-xfce.iso`」這個路徑。

舉例執行下面指令

``` sh
sudo curl -fLo /opt/iso/voidlinux/latest/void-live-x86_64-20250202-xfce.iso --create-dirs \
	https://repo-default.voidlinux.org/live/current/void-live-x86_64-20250202-xfce.iso
```




## 設定範例

> 接著採用下面其中一種方式來設定。

| GRUB Boot ISO 範例 | 設定檔路徑 | 是否需要執行 update-grub |
| ----------------- | --------- | ---------------------- |
| demo_40_custom | [/etc/grub.d/40_custom](https://github.com/samwhelp/voidlinux-adjustment/blob/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-voidlinux-iso/asset/overlay/etc/grub.d/40_custom) | 修改後，需要執行 `sudo update-grub` |
| demo_41_custom | [/boot/grub/custom.cfg](https://github.com/samwhelp/voidlinux-adjustment/blob/main/core/iso/boot-iso/boot-iso-via-grub/demo-boot-voidlinux-iso/asset/overlay/boot/grub/custom.cfg) | 修改後，**不需要**執行 `sudo update-grub` |

> 關於「`sudo update-grub`」指的是「`sudo grub-mkconfig -o /boot/grub/grub.cfg`」




## GRUB Menu Entry / Boot ISO 樣板 / Debian

``` sh

menuentry "Void Linux ISO" --class voidlinux {
	set iso_file="/opt/iso/voidlinux/latest/void-live-x86_64-20250202-xfce.iso"
	search --set=iso_partition --no-floppy --file $iso_file
	probe --set=iso_partition_uuid --fs-uuid $iso_partition
	set img_dev="/dev/disk/by-uuid/$iso_partition_uuid"
	loopback loop ($iso_partition)$iso_file
	set boot_option=""
	#set boot_option="rd.luks=0 rd.md=0 rd.dm=0 loglevel=4 gpt add_efi_memmap vconsole.unicode=1 vconsole.keymap=us locale.LANG=en_US.UTF-8 rd.live.overlay.overlayfs=1 rd.live.ram"
	linux (loop)/boot/vmlinuz iso-scan/filename=$iso_file root=live:CDLABEL=VOID_LIVE ro init=/sbin/init $boot_option
	initrd (loop)/boot/initrd
}

```




## See Also

* Grub 探索筆記 / [GRUB Boot ISO 範例](https://samwhelp.github.io/note-about-grub/read/howto/boot_iso.html)
