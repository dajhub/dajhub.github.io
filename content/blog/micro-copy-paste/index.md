+++
title = "Micro Text Editor - Copy and Paste Functionality in Wayland"
date = "2025-05-27"
description = "How to enable the external copy and paste function within the **micro** text editor." 
[taxonomies]
tags = ["window manager", "software"]
+++

I am not a developer or system administrator and have never really come to terms with the editors **vim** or **neovim**.  They are undoubtably configurable and efficient, but I do not use them enough to get to that "efficient" level. I am sure they would be great if you were using frequently, day in day out.   I have also used **nano** which is fine, but I have struggled to remember the shortcuts which do not always seem logical for me, e.g. Ctrl+K to cut, Ctrl+U to paste.  I have moved towards using [micro](https://micro-editor.github.io/) as a text editor.  For me it has the right level of functionality and the shortcuts are more familiar to me, e.g. CTRL+s to save, CTRL+c to copy, CTRL+v to paste.  You can even easily choose different themes.

While I have enjoyed using and learning **micro**, the biggest surprise I have had with the editor is that I was unable to copy text from micro into another external application.  Apparently micro has its own internal clipboard for copying and pasting, which cannot be used outside the editor.  I am currently using the Hyprland and Sway, which are window managers that use Wayland as a compositor.  To get the copy & paste function to work, you will need to install an external clipboard manager, i.e. [wl-clipboard](https://github.com/bugaevc/wl-clipboard).  To do this on **Arch**:

```bash
sudo pacman -S wl-clipboard
```

With **wl-clipboard** installed some changes need to be made to the settings in **micro**.  Using a text editor such as micro (!!) you can open and then edit the settings file.  To open the file:

```bash
micro .config/micro/settings.json
```

Within the opened file, add between the **{ }** brackets the following:

```bash
{
    "clipboard": "external"
}
```

My full settings file looks as follows:

```bash
{
    "colorscheme": "catppuccin-latte",
    "clipboard": "external",
    "softwrap": true
}
```

The only difference from the previous is that there is a **comma** at the end of the line, since it is not the end of the settings.
