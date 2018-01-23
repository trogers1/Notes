# Reversing Mouse Scroll #

According to <a href="http://unixnme.blogspot.com/2016/10/how-to-reverse-mouse-scroll-direction.html" target="_blank">this site</a>, which got the idea from <a href="https://jamesmcdonald.com/2011/07/invert-mouse-scroll-wheel-in-debian/" target="_blank">this post</a>, the idea is to go into `/usr/share/X11/xorg.conf.d` and edit the __10-evdev.conf__ file. However, that file didn't exist for me.

I did, however, find that __40-libinput.conf__ had the "MatchIsPointer" notation. From that file, in that section with "MatchIsPointer", you can the following line:

'''
Section "InputClass"
        Identifier "evdev pointer catchall"
        MatchIsPointer "on"
        MatchDevicePath "/dev/input/event*"
        `Option "ButtonMapping" "1 2 3 5 4 6 7 8"`
        Driver "evdev"
EndSection
'''

That should do it.
