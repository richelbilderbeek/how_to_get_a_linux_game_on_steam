# How to create an executable

An executable is a file that can be run.

There are multiple options:

- `[1]` Create a Linux executable
- `[2]` Create a standalone Linux executable
- `[3]` Create a Windows executable using AppVeyor
- `[4]` Create a Windows executable using a cross-compiler

<!-- markdownlint-disable MD013 --><!-- Tables cannot be split up over lines, hence will break 80 characters per line -->

Option                                  |Advantage                                          |Disadvantage
----------------------------------------|---------------------------------------------------|------------------------------------------------------------------------------------------
`[1]` Linux executable                  |Easiest                                            |Users will need to install libraries themselves or (?) you need to supply the `.so` files
`[2]` Standalone Linux executable       |Can be run on own computer                         |A static compilation takes more time, harder to setup
`[3]` Windows executable, AppVeyor      |Most gamers use Windows, no installation needed    |AppVeyor script development involves a lot of waiting
`[4]` Windows executable, cross-compiler|Most gamers use Windows, can be run on own computer|A cross-compilation takes more time, harder to setup

<!-- markdownlint-enable MD013 -->
