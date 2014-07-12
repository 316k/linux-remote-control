# Linux Remote Control
Turn any device into a complete remote control for your GNU/Linux.

## How to install lrc-client

### Firefox OS ![alt tag](http://linuxremotecontrol.com/img/firefox-icon.png)

1 - Visit the app page on Firefox Marketplace for your device.

[https://marketplace.firefox.com/app/linux-remote-control](https://marketplace.firefox.com/app/linux-remote-control "Linux Remote Control")

2 - Click on Install button.

3 - [Install lrc-server](#how-to-install-lrc-server)

### Android ![alt tag](http://linuxremotecontrol.com/img/android-icon.png)

1 - Install Firefox 29 or higher on your Android.

[https://play.google.com/store/apps/details?id=org.mozilla.firefox](https://play.google.com/store/apps/details?id=org.mozilla.firefox "Firefox to Android")

2 - Visit the app page on Firefox Marketplace for your Android with Firefox.

[https://marketplace.firefox.com/app/linux-remote-control](https://marketplace.firefox.com/app/linux-remote-control "Linux Remote Control")

3 - Click on Install button.

4 - [Install lrc-server](#how-to-install-lrc-server)

### Other systems

1 - Download this repository and unzip
```bash
unzip linux-remote-control-master.zip
```

2 - Make a .deb package of the project
```bash
dpkg-deb -b linux-remote-control-master/ lrc.deb
```

3 - Install .deb package
```bash
sudo dpkg -i lrc.deb
```

4 - Move /opt/lrc-client directory to your device or to directory of your choice (if you prefer you can leave here)
```bash
sudo mv /opt/lrc-client your-directory/lrc-client
```

5 - Start lrc-server
```bash
node /opt/lrc-server/lrc.js
```

6 - Open the index.html of your-directory/lrc-client in a browser, add your server and have fun

## How to install lrc-server

1 - Download the lrc.deb package onto you GNU/Linux system.
```bash
wget http://www.linuxremotecontrol.com/lrc-ffos.deb
```

2 - Install .deb package.
```bash
sudo dpkg -i lrc-ffos.deb
```

3 - Start lrc-server.
```bash
node /opt/lrc/lrc.js
```

If an error occurs during installation of the package, run the following command.
```bash
sudo apt-get install -f
```
Or open .deb package by graphic interface (double click on the lrc-ffos.deb file)

### Configuration

Linux-remote-control will work out-of-the-box in most cases. However, if you wish to change the default settings (for instance, if you wish to use another music player than Rhythmbox), just modify the configuration file in /opt/lrc-server/node_modules/configuration.js

### Start the server on computer boot

If you wish to have the Linux Remote Control server to be always available, just add a cron job on reboot :

```bash
$ crontab -e
# Add this cron job
@reboot node /opt/lrc-server/lrc.js
```

## Dependences

The Linux Remote Control depends on some softwares to work correctly. Bellow is a list of this softwares.

Installed with lrc.

- Node.js (Express) (to execute commands on GNU/Linux)
- Xdotool (to execute most commands, like play, pause, mute, etc.)
- Xbacklight (to control backlight)

Usually already installed on GNU/Linux.

- Totem Movie Player (to control the video)

One of the following music players.

- Rhythmbox
- moc

## Bugs
The project still has some bugs that you can fix.

- Click by tapping the touchpad;
- Organize and modularize my dirty Javascript =/;
- Start lrc-server (node /opt/lrc-server/lrc.js) with computer boot;

## License
GNU GENERAL PUBLIC LICENSE V2
