# cool-retro-term

|> Default Amber|C:\ IBM DOS|$ Default Green|
|---|---|---|
|![Default Amber Cool Retro Term](https://user-images.githubusercontent.com/121322/32070717-16708784-ba42-11e7-8572-a8fcc10d7f7d.gif)|![IBM DOS](https://user-images.githubusercontent.com/121322/32070716-16567e5c-ba42-11e7-9e64-ba96dfe9b64d.gif)|![Default Green Cool Retro Term](https://user-images.githubusercontent.com/121322/32070715-163a1c94-ba42-11e7-80bb-41fbf10fc634.gif)|

## Description
cool-retro-term is a terminal emulator which mimics the look and feel of the old cathode tube screens.
It has been designed to be eye-candy, customizable, and reasonably lightweight.

It uses the QML port of qtermwidget (Konsole): https://github.com/Swordfish90/qmltermwidget.

This terminal emulator works under Linux and macOS and requires Qt6.

Settings such as colors, fonts, and effects can be accessed via context menu.

## Screenshots
![Image](<https://i.imgur.com/TNumkDn.png>)
![Image](<https://i.imgur.com/hfjWOM4.png>)
![Image](<https://i.imgur.com/GYRDPzJ.jpg>)

## Install

If you want to get a hold of the latest version, just go to the Releases page and grab the latest AppImage (Linux) or dmg (macOS).

Alternatively, most distributions such as Ubuntu, Fedora or Arch already package cool-retro-term in their official repositories.

## Building

cool-retro-term requires Qt 6.4 or newer, including the Qt Shader Tools (`qsb`) and Qt 5 Compatibility modules.

### Ubuntu 24.04

Install the build and runtime dependencies:

```sh
sudo apt install build-essential qmake6 qt6-base-dev qt6-base-dev-tools \
  qt6-declarative-dev qt6-shadertools-dev qt6-5compat-dev libqt6sql6-sqlite \
  qml6-module-qtquick qml6-module-qtquick-controls qml6-module-qtquick-templates \
  qml6-module-qtquick-dialogs qml6-module-qtquick-layouts \
  qml6-module-qtquick-localstorage qml6-module-qtquick-window \
  qml6-module-qtqml-models qml6-module-qtqml-workerscript \
  qml6-module-qt5compat-graphicaleffects qml6-module-qtcore
```

Clone with submodules, then build and run:

```sh
git clone --recursive https://github.com/jdinalt/cool-retro-term.git
cd cool-retro-term
qmake6 && make -j$(nproc)
./cool-retro-term
```

Use `qmake6`, not `qmake`: on Ubuntu, `qmake` is Qt 5. If the tree was ever configured with Qt 5, delete the generated `Makefile`s (`git clean -fdX && git submodule foreach git clean -fdX`) before running `qmake6`, because the subdirectory Makefiles are not regenerated.

### macOS

See the [macOS build instructions](https://github.com/Swordfish90/cool-retro-term/wiki/Build-Instructions-(macOS)).
