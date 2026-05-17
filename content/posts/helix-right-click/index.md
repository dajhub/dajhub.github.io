+++
title = "Helix Text Editor: Opening through Thunar file manager"
date = "2025-11-14"

[taxonomies]
tags = ["software"]
+++

While I am still using the Micro text editor, I have also been testing out the [Helix editor](https://helix-editor.com) as an easier introduction (for me) to vim and Neovim.
<br>  
  
> __<span style="color:red;">Note:</span>__
> 
> You can use any terminal with helix.  I'm using kitty so be aware that some of the guidance below relates to kitty. I am on Sway and Hyprland.

<br>
As with the Micro text editor a couple of problems I came across were:

1. Right-clicking in the file manager Thunar to open a file in the Helix editor, I would get an error message "Unable to find terminal required for application".
2. Copying text from Helix into another application.


### SOLUTION 1: Opening a file from Thunar into Helix


- Find where helix is installed with this command:

  ```bash
  sudo find /usr -type f -name hx 2>/dev/null
  ```

  For me the file location was at `/usr/lib/helix/hx`

- Edit the system-wide desktop entry using the text editor of your choice, e.g. nano

  ```bash
  sudo nano /usr/share/applications/helix.desktop
  ```

  Within the file find the line that starts `Exec=` and edit it so that it now contains the following:

  ```plain
  Exec=kitty -e /usr/lib/helix/hx %F
  ```
<br>

> __<span style="color:red;">Note:</span>__
> 
> You mat need to change `/usr/lib/helix/hx` depending on the file location of helix."

<br>

  When you have saved the file (ctrl+O and ctrl+x to exit) you can then update the desktop database:

  ```bash
  sudo update-desktop-database /usr/share/applications
  ```

  If you then reload thunar and then right-click a file → Open With → Helix, kitty should open correctly and run /usr/lib/helix/hx.


### SOLUTION 2: Copying a piece of text from Helix into another application

- As I am using Sway and Hyprland you need to ensure that wl-clipboard is installed:

  ```bash
  sudo pacman -S wl-clipboard`
  ```

The copy and paste function should now be working in Helix!
