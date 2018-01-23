# Reversing Mouse Scroll #

According to <a href="http://unixnme.blogspot.com/2016/10/how-to-reverse-mouse-scroll-direction.html" target="_blank">this site</a>, which got the idea from <a href="https://jamesmcdonald.com/2011/07/invert-mouse-scroll-wheel-in-debian/" target="_blank">this post</a>, the idea is to go into `/usr/share/X11/xorg.conf.d` and edit the _10-evdev.conf_ file. However, that file didn't exist for me.

I did, however, find that _40-libinput.conf_ had the "MatchIsPointer" notation. From that file, in that section with "MatchIsPointer", you can the following line:

<pre>
Section "InputClass"
        Identifier "libinput pointer catchall"
        MatchIsPointer "on"
        MatchDevicePath "/dev/input/event*"
        <b>Option "ButtonMapping" "1 2 3 5 4 6 7 8"</b>
        Driver "libinput"
EndSection
</pre>

That should do it. The idea being that you switched the `4 5` to `5 4`. If you want to switch horizontal scroll, I belive you flip `6 7`, but not sure.

Then restart X or restart the OS.
