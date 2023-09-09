<div>
<img align="left" style="margin: 0px 15px 0px 0px;" src="OneDriveGUI.64x64.png" alt="OneDriveGUI Icon" />

# OneDriveGUI on Flatpak
&nbsp;
</div>

This project contains files to build [OneDriveGUI](https://github.com/bpozdena/OneDriveGUI) as a Flatpak app.

## How to build the app

### 1 - Prepare the environment
Ensure you have the following commands installed on your system:
- `git`
- `flatpak`
- `flatpak-builder`

Ensure you have the `flathub` repo enabled:
```shell
$ flatpak remote-add --user --if-not-exists flathub https://flathub.org/repo/flathub.flatpakrepo
```

Clone this project on your computer:
```shell
$ git clone https://github.com/mbugni/OneDriveGUIFlatpak.git
```

### 2 - Build and install the app
From the project directory run the command:
```shell
$ flatpak-builder --user --verbose --install --install-deps-from=flathub --force-clean \
  build io.github.bpozdena.OneDriveGUI.yaml
```

See [flatpak documentation](https://docs.flatpak.org/) for more info.

The first build can take 5 minutes, it depends on your machine performances. It install the app, making it available for your user in the system.

*NOTE:* if you want to install the app system wide, remove the `--user` option and the use `sudo` command.

### 3 - Run the app
You can run the OneDriveGUI launching it from your favorite desktop, or manually by using the `flatpak` command:
```shell
$ flatpak run io.github.bpozdena.OneDriveGUI
```

## OneDriveGUI files
Data files are in folder `~/.var/app/io.github.bpozdena.OneDriveGUI/data`.
Config files are in folder `~/.var/app/io.github.bpozdena.OneDriveGUI/config`.
