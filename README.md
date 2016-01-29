Papyros
=======

[![Join the chat at https://gitter.im/papyros/papyros](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/papyros/papyros?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)

[![GitHub issues](https://img.shields.io/github/issues/papyros/papyros.svg)](https://github.com/papyros/papyros/issues)
[![Bountysource](https://img.shields.io/bountysource/team/papyros/activity.svg)](https://www.bountysource.com/teams/papyros)

General issue tracking and wikis for Papyros, along with a CMake superbuild
for easy building of all the papyros projects.

### Superbuild dependencies

 * Qt 5.5, including the following modules:
   * QtQuick.Controls
   * QtGraphicalEffects
   * QtWayland
 * Wayland
 * CMake
 * [Extra CMake Modules](http://api.kde.org/ecm/manual/ecm.7.html)
 * [QT5XDG](https://github.com/lxde/libqtxdg)
 * KDE Frameworks
   * [KConfig](http://api.kde.org/frameworks-api/frameworks5-apidocs/kconfig/html/)
   * [KWallet](http://api.kde.org/frameworks-api/frameworks5-apidocs/kwallet/html/)
   * [KDeclarative](http://api.kde.org/frameworks-api/frameworks5-apidocs/kdeclarative/html/)
   * [Solid](http://api.kde.org/frameworks-api/frameworks5-apidocs/solid/html/)
   * [NetworkManagerQt](http://api.kde.org/frameworks-api/frameworks5-apidocs/networkmanager-qt/html/)
   * [ModemManagerQt](http://api.kde.org/frameworks-api/frameworks5-apidocs/modemmanager-qt/html/) (optional)
 * ALSA or PulseAudio
 * [xdg-app](https://github.com/alexlarsson/xdg-app/) compiled with `--enable-libxdgapp`

### Building the superbuild

The `CMakeLists.txt` provides a superbuild which checks out and builds the following projects:

 * qml-material
 * libpapyros
 * greenisland
 * papyros-shell
 * terminal-app
 * settings-app
 * software-app

To build the superbuild, run the following commands:

    mkdir build; cd build
    cmake .. -DCMAKE_INSTALL_PREFIX=/usr # or ~/.local for local builds
    make

That's it! CMake will automatically download, build, and install the included projects!

To run the desktop shell, simply run:

    papyros-session
