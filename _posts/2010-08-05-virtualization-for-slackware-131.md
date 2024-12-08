---
layout: post
title: "Virtualization for Slackware 13.1"
categories: slackware
tags: slackware virtualization kernel qcow2 
---

## Intro

You need to make sure your setup allows for virtualization. Check your CPU manual.

- <a href="http://www.linux-kvm.com/content/kvm-73-kvmintel-wont-load-2626-64-bit-kernel" title="kvm-73 kvm_intel won't load in 2.6.26 64 bit kernel">kvm-73 kvm_intel won't load in 2.6.26 64 bit kernel</a> It was BIOS. I totally forgot that. Thanks trhodes!
- <a href="http://blog.incase.de/index.php/cpu-feature-flags-and-their-meanings/" title="CPU flags and their meaning">CPU flags and their meaning</a>

## Instruction

qcow2 is qemu copy on write second version. qcow2 is good, use it.

<a href="http://www.linux-kvm.org/page/HOWTO1" title="HOWTO1 - KVM">Virtualization simplified</a>:

1. Install <a href="http://slackbuilds.org/repository/13.1/system/qemu-kvm/" title="qemu-kvm">qemu-kvm</a> (<code>KVMGROUP=users sh qemu-kvm.SlackBuild</code>).
2. `modprobe kvm_intel`
3. Create an image (`qemu-img create -f qcow2 environment.img 50G`). I named mine "environment."
4. Install the desired os (`sudo qemu-system-x86_64 -hda environment.img -cdrom /home/sifer/slackware-13.1-install-dvd.iso \
-boot d -m 384`). I needed another one to mess with the kernel.
5. Run the newly installed os (`sudo qemu-system-x86_64 -hda environment.img -m 512 -soundhw all -smp 4 -cpu host -no-acpi -snapshot -localtime -boot c -usb -usbdevice tablet -net [your network options here]`).
