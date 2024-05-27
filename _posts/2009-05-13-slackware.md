---
layout: post
title: "Slackware"
categories: slackware
tags: slackware nvidia kde vendor
---

<img src="https://github.com/sif/sif/raw/main/files/post_files/slackware.png" width=60px />

* TOC
{:toc}

## Installation

- Swapless setup is not a good idea, even if you have a 64 bit system. It is not needed but it is preferred since hard drives are so big and inexpensive these days.
- Use `smartctl -a /dev/sda` (or whatever your drive is) to see how it's doing. If it's failing, when_failed column would show something.
- You can find the kernel in `/usr/src/linux`.



### Bootup

/etc/rc.d/rc.local
\#\# You may add custom initialisation below this
ulogd -d
ipkungfu



## Hardening

- encrypt everything
- force everything to use encryption if possible, even if weakest is the only option you can use
- remember, your privacy is a different issue
- protect yourself from your isp / government / commercial and local / physical threats
- security is a process
- don’t use multiple sign-in unless needed like msn for x-box account
- Set passwords to change every so often.
- Disable unneeded services.



### Logs

Check:

  - /var/log/secure
  - /etc/passwd
  - /etc/shadow



## Packages

As a quick reference:

```
tar zxvf package.tar.gz
mv package-version.tar.gz package/
cd package
sudo ./package.SlackBuild
installpkg /tmp/package.SBo.tgz
```

After installing slackbuild packages, delete everything in /tmp/sb0 and anything with sb0 in /tmp. When slackpkg ask about what I should do with "excess" files, I prefer using "overwrite.”

- AIDE
- chkrootkit
- clamav
- cryptoki
- fail2ban
- keepassx
- rkhunter
- TrueCrypt
- wxGTK
- lynis
- tripwire
- tiger
- bastille
- snort
- samhain



## Services

To stop it from booting up:

```
chmod -x /etc/rc.d/rc.sshd
chmod -x /etc/rc.d/rc.inetd
```

Reboot the PC after doing so.

- ssh = 22
- X11 = 6000
- bootp = 68

I don't think I would worry about 68 or 6000.

"For example, to turn off nfs, enter: # /etc/init.d/nfs stop"



## NVIDIA

Stick with NVIDIA's package. Anything else and you risk errors. Use glxinfo if you run into any problems.

If you run into unfixable issues, reinstall:

```
chmod +x
./NV [tab]
```

Do what it says and install and reboot at the very last step.

If composite does not work, do: `nvidia-xconfig --composite`

If your flash videos turn blueish or something similar, right click on the video and turn off hardware acceleration.

My old video card issues..

- [Driver dilemma in KDE workspaces 4.5](http://blog.martin-graesslin.com/blog/2010/09/driver-dilemma-in-kde-workspaces-4-5/)
- [Performance issues, one script, and call for testers](http://hugo-kde.blogspot.com/2010/09/performance-issues-one-script-and-call.html)

## KDE

If you have a screen-configurations.xml in ~, you can safely delete it.

If you run into a problem with Pidgin, do this:

```
removepkg pidgin
./configure --disable-gtkspell --disable-gstreamer --disable-meanwhile --disable-avahi --disable-nm
```

If this error is seen:

`pidgin: error while loading shared libraries: libpurple.so.0: cannot open shared object file: No such file or directory`

Do this: `sudo ldconfig`

There is a bug mainly in KDE 4.4. When I set my desktop to consider each page a different activity, it allows me to move my desktop. However I don't like that, so if you're experiencing something similar and need to set KDE straight:

1. Right click -> "Desktop Activity Settings"
2. Go to activity then set it to "Folder View."
3. Then back to "Desktop."
4. Exit X/KDE.
5. Voila, no more moving the desktop.

Repeat if you have to with however many desktop you have.

## Compiz Fusion

I think future Slackware / KDE will have a lot of the Compiz stuff built in. But in the event that you are building Compiz Fusion from grounds up, you need to install the following in this order:

1. compiz-bcop
2. libcompizconfig
3. compizconfig-backend-kconfig
4. compizconfig-python
5. ccsm
5. simple-ccsm
6. compiz-fusion-plugins-main
7. compiz-fusion-plugins-extra
8. compiz-fusion-plugins-unsupported
9. emerald
10. emerald-themes
11. fusion-icon
12. kicker-compiz
13. taskbar-compiz

The reason for 13 and 14 is because neither KDE taskbar or pager support viewports. Add `ShowAllWindows = false` to `[General]` in `/home/sif/.kde/share/config/ktaskbarrc` after installing.

If you run into problems, try this first: `compiz --replace --sm-disable --ignore-desktop-hints ccp &`

Make sure desktop icons are enabled.

When KDE+Compiz-Fusion just doesn't want to work..

Alt+F2 then paste in `kwin`.

## Enabling Cube

- Open CCSM
- General Options -> Desktop Size tab
- Horizontal virtual size = 4, the other two settings = 1
- Hit "Back" -> Go "Desktop" category
- Make sure Desktop Cube, Rotate Cube, Show Desktop, Viewport Switcher, and Widget Layer are all enabled
- Hit "Rotate Cube" and push up "Zoom" slider to about 1.000
- Go "Effects" category -> Enable animations add-on if there is
- Enable Cube Reflection and Deformation, Fading Windows, Windows Decoration, and Wobbly Windows
- Go "Utility" category -> Enable Crash Handler, Dbus, Resize Info, Regex Matching, Video Playback, and Workarounds
- Go "Window Management" category -> Enable Applications Switcher, Move Window, Place Windows, Put, Resize Window, and Scale
- Hit CTRL+ALT+hold down a left mouse button and drag
- Go to "Rotate Cube" to adjust zoom slider
- Will need the Wallpaper plugin in order to use different backgrounds for different virtuals and get KWin to stop writing the desktop

## Wine

If you ever download any DLL, this is where you should place your DLLs. I've only ever needed DLLs in this location:

/home/sif/.wine/drive_c/windows/system32

Uninstalling winetricks - So.. you delete the ~/.wine directory to uninstall everything you got winetricks to install for you. Just a tip since I have not seen any instruction anywhere on how to uninstall what winetricks installed.

## Firefox & Thunderbird

To access the profile manager with Firefox or Thunderbird, type this:

```
firefox -profilemanager
thunderbird -profilemanager
```

The profiles are stored in: ~/.mozilla/

## VLC

I don't know if this "trick" still works but..

1. Open VLC.
2. Ctrl + N.
3. Type in `screen://`.
4. Hit play.

Enjoy.

Preferences -> Show All -> Video -> Disable "Show media title on video"

## CLI

If you want something relatively random.. a quick generator for your password or something, here it is: `dd if=/dev/random bs=1 count=16 | xxd -ps`

If you want to mount asap: `mount -o loop image your_folder`

Remember, it's `cfdisk /dev/sda`, not `cfdisk /dev/sda1`.

To archive: `tar cfv "file.tar" file`

To compress: `tar cjpv "file.tar.bz2" file`

Speaking of tarball, in order to preserve symlink, use --preserve.

`updatedb` was useful for slocate, not sure if still is.

To clear bash: `history -c && history -w`

One way to see the checksum: `md5sum <file>`

To add a user to the sudo file: `visudo`

```
last
lsof
lsof | egrep 'ESTAB|LIST'
w
who
fuser
netstat -pant | grep LISTEN
netstat -tap > listening.services | less listening.services
sudo
freshclam
clamscan --exclude-dir=^/mnt --exclude-dir=^/sys --exclude-dir=^/dev --exclude-dir=^/proc --detect-pua=yes --log=/home/sif/.Desktop/clamlog.log -ri /
```



## Version History

- 9
- 10.2
- 11
- 12.1
- 13
- 13.1
- 13.37
