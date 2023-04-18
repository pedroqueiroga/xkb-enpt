Custom keyboard mapping for logitech k380. Creates emacs-like binding when holding caps lock.

Modifications:

```
AltGr + c -> ç
AltGr + ; -> ^ (dead)
AltGr + ´ -> '
Caps Lock + a -> Home
Caps Lock + e -> End
Caps Lock + , -> Prior
Caps Lock + . -> Next
Caps Lock + f -> Right
Caps Lock + p -> Up
Caps Lock + b -> Left
Caps Lock + n -> Down
```

Add `  *		usbr		=	+usbr` to `evdev`. It must be below `! model		layout[2]	=	symbols`. I believe this kind of makes our grouping work.

```
...
! model		layout[2]	=	symbols
  *		usbr		=	+usbr
...
```

Add `usbr` to xkb symbols directory
Add `usbr` entry to your `evdev.xml`. How the layout should be setup can be found in this project's `evdev.xml`

After these steps you should see in input sources list the new entries `English (BR)` and `Emacs`. It is not clear to me if there is another way, but for this to work nicely these two should be your first two layouts

![gnome layout chooser showing three entries. 1. English (BR), 2. Emacs, 3. Portuguese (Brazil, IBM/Lenovo ThinkPad)](https://github.com/pedroqueiroga/xkb-enpt/blob/main/gnome-layout-chooser.png?raw=true)


You should never use `Emacs` directly in the gnome chooser, because Caps Lock is used to switch between group 1 and group 2. Group 1 will be normal keyboard, Group 2 will be emacs navigation, and Group 3 is whatever else (in my case it is Portuguese). This part needs improving because I do not truly understand what I am doing.
