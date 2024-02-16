- fixes CAps LOck DElay
- gives shift behavior to caps lock

> from arch wiki: https://wiki.archlinux.org/title/Xorg/Keyboard_configuration#Switching_state_immediately_when_Caps_Lock_is_pressed

note that the included xkbmap might not work for your layout, if so simply [export](https://wiki.archlinux.org/title/Xorg/Keyboard_configuration#Workaround) your own keyboard config and replace the relevant section by the following:
```
    key <CAPS> {      
        repeat=no,
        type[group1]="ALPHABETIC",
        symbols[group1]=[ Shift_Lock, Shift_Lock],
        actions[group1]=[ LockMods(modifiers=Shift), Private(type=3,data[0]=1,data[1]=3,data[2]=3)]
    };
```