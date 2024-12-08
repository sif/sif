---
layout: post
title: "Running Warhammer Online on Slackware"
categories: slackware
tags: slackware warhammer wine windows
---

## Intro

I grew up with the Warhammer universe. I wanted to play it on Linux so I did some research and decided to write up something. For the latest updates see: <a href="http://appdb.winehq.org/objectManager.php?sClass=version&iId=13139">WineHQ  - Warhammer Online Live</a>

## Instruction

1. First get wine. I used wine-1.1.17.tar.bz2 but the latest wine version should work better. I think you can get that exact version <a href="http://ibiblio.org/pub/linux/system/emulators/wine/">here</a>. Now extract it somewhere close to home like the desktop folder.
2. Download this <a href="https://github.com/cassandriel/Personal/raw/master/5.othersifer/sfru%20(Wine)/war.patch">war.patch</a>. "Save Link As..."
3. Copy war.patch to the wine directory.
4. Open a console and type:
```
cd ~/Desktop/wine-1.1.17
patch -p0 < war.patch
./configure
make depend && make
sudo make install
winecfg
```
5. Change the windows type to Windows XP.
6. Create a folder on the desktop, call it WAR or something. Copy everything in data1 and data2 from the game DVDs to the newly created directory. When finished, open a console and type:
`mv ~/Desktop/WAR/ ~/.wine/drive_c/WAR/`
<br />Personally, I created a mount point to /mnt/war/ and moved everything in `~/.wine/drive_c/WAR/` to `/mnt/war/`.
7. Download <a href="http://wiki.winehq.org/winetricks">winetricks</a> and put it on Desktop.
8. Set permissions to the file so you can run it. After that open a console and type:
```
cd ~/Desktop
./winetricks directx9
```
If after the installation the window doesn't close, go to the terminal and hit Ctrl+C.
9. Download this <a href="https://raw.githubusercontent.com/cassandriel/Personal/master/5.othersifer/sfru%20(Wine)/script">"script"</a> and edit it accordingly. "Save Link As..." Set the proper permission so you can execute the script.
10. Open a console and type:
```
cd ~/.wine/drive_c/WAR/
wine warpatch.exe
```
11. When you want to play, run "script." When you're in the game, set the graphics to "Fastest Settings."

**Now you should be playing Warhammer Online on Linux!**

## Troubleshooting

If you get this error: `Warning: could not find DOS drive for current working directory '~/Desktop'`

This is a Z:\ symlink issue. Open up a console and do this: `ln -s / ~/.wine/dosdevices/z:`

Regarding winhttp.dll issue, download it <a href="https://github.com/cassandriel/Personal/raw/master/5.othersifer/sfru%20(Wine)/winhttp.dll">here</a>. Then open up the console and do this:

```
mv winhttp.dll ~/.wine/drive_c/windows/system32/winhttp.dll
winecfg
```

Hit the Libraries tab, find winhttp.dll from the dropdown menu and add it to the list. Click on edit on the right and set it to native. Apply and exit.
