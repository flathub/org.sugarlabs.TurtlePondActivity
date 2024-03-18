# Turtle Pond Flatpak

Turtle in a Pond is a strategy game. The goal is to surround the turtle before it runs off the screen.

To know more refer https://github.com/sugarlabs/turtlepond

## How To Build

```
git clone https://github.com/flathub/org.sugarlabs.TurtlePondActivity.git
cd org.sugarlabs.TurtlePondActivity
flatpak --user remote-add --if-not-exists flathub-beta https://flathub.org/beta-repo/flathub-beta.flatpakrepo
flatpak -y --user install flathub-beta org.gnome.{Platform,Sdk}//46beta
flatpak -y --user install org.sugarlabs.BaseApp//24.04
flatpak-builder --user --force-clean --install build org.sugarlabs.TurtlePondActivity.json
```

## Check For Updates

Install the flatpak external data checker
```
flatpak --user install org.flathub.flatpak-external-data-checker
```

Now to update every single module to the latest stable version use
```
cd org.sugarlabs.TurtlePondActivity
flatpak run --filesystem=$PWD org.flathub.flatpak-external-data-checker org.sugarlabs.TurtlePondActivity.json
```