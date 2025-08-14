# How to create an executable

An executable is a file that can be run.

There are multiple options:

- `[1]` Create a Linux executable
- `[2]` Create a standalone Linux executable
- `[3]` Create a Linux executable using the SteamSDK
- `[4]` Create a Windows executable using AppVeyor
- `[5]` Create a Windows executable using a cross-compiler

<!-- markdownlint-disable MD013 --><!-- Tables cannot be split up over lines, hence will break 80 characters per line -->

Option                                  |Advantage                                          |Disadvantage
----------------------------------------|---------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------
`[1]` Linux executable                  |Easiest                                            |Users will need to install libraries themselves or (?) you need to supply the `.so` files. Users will need to set up the launch options of your game
`[2]` Standalone Linux executable       |Can be run on own computer                         |A static compilation takes more time, harder to setup. Users will need to set up the launch options of your game
`[3]` Linux executable, SteamSDK        |Can be run on own computer                         |One needs to learn the SteamSDK, harder to setup
`[4]` Windows executable, AppVeyor      |Most gamers use Windows, no installation needed    |AppVeyor script development involves a lot of waiting
`[5]` Windows executable, cross-compiler|Most gamers use Windows, can be run on own computer|A cross-compilation takes more time, harder to setup

<!-- markdownlint-enable MD013 -->

## `[1]` Linux executable

This is the easiest way, to just upload your Linux executable.

These are the problems:

- The user must have all needed libraries
  (i.e. the things you install with `sudo apt-get install my_library`):
  installed.
  If the user is missing libraries
  the game will crash at startup,
  without a proper error message
- The user must use the 'Legacy runtime 1.0' launcher,
  which can be set in the properties of the Steam page of your game.

One solution for this is to create a web page on how to do so:
you can find
[an example documentation page on how to launch a game on Steam](launch_on_steam/README.md)
using this method.

!!! warning "Untested solution: provide the shared object files?"

    A possible and untested solution is to provide the needed libraries
    alongside the game executable. Maybe it works to upload
    the executable with all shared objects (`.so`) needed.

    Also, the user will still need to use the 'Legacy runtime 1.0' launcher.

## `[2]` Standalone Linux executable

The idea is to compile the Linux executable in such a way that it is
a standalone file.

These are the problems:

- You must create that standalone file
- The user must use the 'Legacy runtime 1.0' launcher,
  which can be set in the properties of the Steam page of your game.

To create a standalone file may be hard.
In C++, this can be done by so-called **static** compilations.
It can be hard to set this up and compilation will take a long time.

To solve the problem for the user,
one solution is to create a web page on how to do so:
you can find
[an example documentation page on how to launch a game on Steam](launch_on_steam/README.md)
using this method.

!!! warning "Untested solution: create a Debian file?"

    Maybe creating a Debian (`.deb`) file is a good way to do so?

!!! warning "Untested solution: use Flatpak?"

    Maybe using Flatpak file is a good way to do so?

    Based on
    [the documentation of the basic concepts of Flatpak](https://docs.flatpak.org/en/latest/basic-concepts.html),
    this seems to result in a standalone executable.

## `[3]` Linux executable, SteamSDK

TODO

## `[4]` Windows executable, AppVeyor

Using a Continuous Integration (CI) service that runs on Windows,
such as [AppVeyor](https://www.appveyor.com/),
one can create a Windows executable on a remote computer
from a script. In the end, the script should allow you
to download the Windows executable.

Unsure how that needs to be launched by the user.

## `[5]` Windows executable, cross-compiler

Using a crosscompiler, such as [MXE](https://mxe.cc/) for C++,
allows one to create a (standalone) Windows executable.

Unsure how that needs to be launched by the user.

