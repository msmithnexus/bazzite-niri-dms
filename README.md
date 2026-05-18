# Interlace

This custom Bazzite image is based on `bazzite-gnome`. It includes Dank Material
Shell and niri along with all of the recommended extras for Dank Linux.

My goal with this image is to offer a vanilla DMS/niri experience with gaming
capabilities (via Bazzite). I have added ghostty as the default termianl along
with tools to allow developers to create their own DMS plugins.

Feel free to suggest additional software - or just fork this repo and do
whatever you like.

To switch, run the following from a terminal in any Universal Blue or Fedora
Atomic based install:

```
sudo bootc switch ghcr.io/irunatbullets/interlace
sudo bootc switch ghcr.io/irunatbullets/interlace-nvidia
sudo bootc switch ghcr.io/irunatbullets/interlace-dx
sudo bootc switch ghcr.io/irunatbullets/interlace-dx-nvidia
```

**Important Note:** After switching to this image the login will backup any
existing niri configutation and replace it with standard dms niri configs.
Updates will not retrigger this event.

**Also:** To enable background image syncing with the dms greeter, run the
following from your terminal and follow the steps:

```
dms greeter sync
```
I would like to automate this in future but I'm simply not smart or patient
enough to do it at the moment.

## For flatpak theme support

```
sudo flatpak override --filesystem=xdg-config/gtk-3.0:rw --filesystem=xdg-config/gtkrc-2.0:rw --filesystem=xdg-config/gtk-4.0:rw --filesystem=xdg-config/gtkrc:rw
```

## Confessions

I borrowed this line from bazzirco, which is an image that blends Zirconium and
Bazzite.

```
# REQUIRED for dms-greeter to work
tee /usr/lib/sysusers.d/greeter.conf <<'EOF'
g greeter 767
u greeter 767 "Greetd greeter"
EOF
```

