---
layout: post
title: "Giving i3wm a try"
date: "2015-10-27 16:57"
published: false
---
While i really like to handle my tools via keyboard shortcuts, i tend to handle my windows with the mouse or trackpad.

Don't ask me why, but on my Macbook this feels totally natural and does not impact my flow, but on the linux box i use at work it's kinda awkward.
Maybe it's the absence of the trackpad and gesture control and [Moom][0], i can't tell...

As the number of tools i use on the aforementioned box is quite overseeable, i thought that i could give the [i3wm][1] a try.

For my taste, i3 needs a little love in the beginning, so here is what i did.
You can find a list of sources i used as links in the corresponding section.


Locking & shutdown (-r|-h)
--------------------------

Coming from Gnome, i am used to hit _the windows key + L_ to lock my system, when i leave my desk. In i3 you'd have to use dmenu and issue ``i3lock`` to achive this. The same goes for rebooting, hibernating or shutting down your box.

I currently use Ubuntu 15.04 on my box and it's default Power Management puts the notebook into hibernation mode when i close the lid, so there is no need to handle this in particular.

Thanks to [this gist][2] i found this solution to define a mode where the other systemctl operations are handled:

    # Create Log out, Reboot, Poweroff bindings
    mode "(L)ogout, (R)eboot, (P)oweroff" {
          # exit i3 (logs you out of your X session)
          bindsym $mod+l exec "i3-nagbar -t warning -m 'Exit i3?' -b 'Yay' 'i3-msg exit'"
          bindsym $mod+r exec "i3-nagbar -t warning -m 'Reboot machine?.' -b 'Yay' 'systemctl reboot'"
          bindsym $mod+p exec "i3-nagbar -t warning -m 'Shutdown machine?.' -b 'Yay' 'systemctl poweroff'"

          # back to normal: Enter or Escape
          bindsym Return mode "default"
          bindsym Escape mode "default"
    }

    bindsym $mod+Shift+u mode "(L)ogout, (R)eboot, (P)oweroff"

Locking the system is done with the default keybinding:

    # Lock i3
    bindsym $mod+Escape exec "i3lock;"


Managing Workspaces
-------------------

Actually i am used to vim keybindings for many things. One of the first things that grinded my teeth was that i constantly pressed the wrong key to change focus or move containers around, because i3 defaults to ``j, k, l, ;`` as movement keys, vim to ``h, j, k, l``, so i decided to go with the arrow keys for movements.


### Moving workspaces around

A nice thing is, that i3 has a good understanding for dual screen setups out of the box - it is possible to refer to an output as left or right.

When there is the need to move an entire workspace to another output, i have a mode called _reorder_, where i focus a workspace and then move it somewhere with the arrow keys.

    mode "reorder" {
        bindsym Left move workspace to output left
        bindsym Right move workspace to output right
        bindsym Up move workspace to output up
        bindsym Down move workspace to output down

        # back to normal: Enter or Escape
        bindsym Return mode "default"
        bindsym Escape mode "default"
    }

    bindsym $mod+p mode "reorder"

This mode is inspired by [https://github.com/Feh/configs/blob/master/.i3/config](https://github.com/Feh/configs/blob/master/.i3/config#L51).

Another set of configuration examples (mostly workspaces)
https://github.com/aswen/dotfiles/blob/master/i3wm-config


### Getting Nautilus back to work

Issue the following command in the terminal to have Nautilus working like you're (probably) used to:

  gsettings set org.gnome.desktop.background show-desktop-icons false

[0]: https://manytricks.com/moom/
[1]: http://i3wm.org/
[2]: https://gist.github.com/athmane/6200074
