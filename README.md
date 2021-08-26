# Motospeed CK61 linux layouts

The Motospeed CK61 keyboard misses the grave/tilde key and requires toggling
a layer to access the secondary function of the keys. This makes the keyboard
cumbersome to code on and to use daily. This repo includes a keymap for the
linux console and a xkb layout for X11 amending those problems.


## Linux console Keymap

This is a very simple modification of the us-acentos.map keymap for the linux
console, adding shift+Esc as the dead_tilde key and shift+alt+Esc as the
dead_grave key, mapping it into the usual location for these keys.
Ideally I would like to make the Menu key a modifier key in the console and
make it toggle the layered keys, but I don't know how to do that. Help would
be appreciated.

### Installation instructions

The easiest way is to gzip and copy the layout to the keymaps folder:

```
# gzip us-ck61.map && cp -v us-ck61.map.gz /usr/share/kbd/keymaps/i386/qwerty/
```

And use your distro's documentation to set this as the default linux console
keymap.


## Xkb keymap

This xkb keymap maps shift+Esc to dead_tilde and Menu+Esc produces dead_grave.
I chose to use the Menu key and avoid shift+alt+Esc as that is hard to type.
This map also adds the Menu key as mod3 in X, essentially turning it into a
working Fn key, shifting the keyboard to the second function of the keys.
To keep things simple I decided to leave out the cursor keys on the right,
mapping only the wasd keys and the print screen and pause break keys are also
left out.

### Installation instructions

You can just copy this to your preferred location in your home directory and
load it in .xinitrc using xkbcomp:

```
$ xkbcomp <wherever>/us_intl_ck61.xkb $DISPLAY
```


### Disclaimer

I made this for my own use, tuning it to my own taste, I'm not trying to
follow any convention or standard.
