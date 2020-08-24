# Personal fork of dwm (Dynamic window manager for X)
[dwm's official webpage](dwm.suckless.org) Original source code at: [git.suckless.org/dwm/](git.suckless.org/dwm/).

## Patches applied
If not declared otherwise, assume most recent version for all mentioned patches.
- [Fullgaps](https://dwm.suckless.org/patches/fullgaps/): This patch adds gaps between client windows. It is similar to gaps, but contains additional functionality.
- [Shiftview](https://lists.suckless.org/dev/att-7590/shiftview.c): A better implementation of the [nextprev](https://dwm.suckless.org/patches/nextprev/) patch. See [discussion](https://lists.suckless.org/dev/1104/7590.html).
- [Autostart](https://dwm.suckless.org/patches/autostart/): This patch will make dwm run "autostart_blocking.sh" and "autostart.sh &" before entering the handler loop. One or both of these files can be ommited.
This fork is built using the patch version which conforms to the [XDG Base Directory specification](https://specifications.freedesktop.org/basedir-spec/basedir-spec-latest.html) and requires it to be set up. If you don't have it set up, patch it with this [diff](https://dwm.suckless.org/patches/autostart/dwm-autostart-20161205-bb3bd6f.diff).
- [Xresources](https://dwm.suckless.org/patches/xresources/): This patch allows to handle settings from Xresources. It differs from xrdb patch in that it can handle any kind of setting as opposed to only color settings.
- [Swallow](https://dwm.suckless.org/patches/swallow/): This patch adds "window swallowing" to dwm as known from Plan 9's windowing system rio. Depends on libxcb, Xlib-libxcb and xcb-res.
- [Statuscmd](https://dwm.suckless.org/patches/statuscmd/): This patch adds the ability to execute shell commands based on the mouse button and position when clicking the status bar.
Required for integration with my personal [dwmblocks fork](https://github.com/brlipi/dwmblocks). The [statuscmd-signal](https://dwm.suckless.org/patches/statuscmd/dwm-statuscmd-signal-6.2.diff) diff was patched.

## Emoji support
This fork has two branches, on which `master` is supposed to be used by those with the [xft-bgra fix for libXft](https://gitlab.freedesktop.org/xorg/lib/libxft/-/merge_requests/1/diffs?commit_id=b77e5752cbd4acef90904e00c0f392984c321ca9). If you do not have it, then you will need to use th `no-emoji` branch. After cloning this repository, run: 
```bash
  git fetch origin
  git branch no-emoji no-emoji/origin
  git checkout no-emoji
  git pull
```
Make sure you're in the correct branch before proceeding with installation.

## Installation
After cloning this repository in the directory of your choice, then, if you wish to change its default namespace installation (/usr/local), edit the `config.mk` file. Afterwards run `sudo make clean install`.
