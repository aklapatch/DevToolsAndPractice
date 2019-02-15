# Style and methodology preferences

## Development process
1. Start programming without an full idea of the entire system
2. Realize that I need to plan
3. Plan a little
4. Push forward
5. Realize I need to plan again
6. Repeat from 3
7. Find a way to improve my Development process

## Source control
Use git and github.

## Documentation
Use a Doxygen and Sphinx and Breathe together with the sphinx_rtd_theme.

## Coding standards
I will use the [LLVM coding standard](http://llvm.org/docs/CodingStandards.html) for C/C++, and will to refer to other languages preferences when using those languages.

# Tools

## Standalone gdb frontends (list [here](https://sourceware.org/gdb/wiki/GDB%20Front%20Ends))
+ [gdbgui](https://github.com/cs01/gdbgui/): browser based frontend for C++, rust and other languages.
  Works well, but it is in a browser. It can be installed with pip.
  
+ [Nemiver](http://home.gna.org/nemiver): GNOME based frontend (tried it and it may be buggy)

## Build tools
+ Cmake
+ Meson (I should probably use this. It seems easier and faster than cmake)
+ ninja (not as versatile as make, but fast)
+ make

## Best Linux Distros (for me)
+ Arch
+ Manjaro
+ Debian testing

## Other Cross Platform tools
+ cppcheck (static analysis)
+ sphinx (documentation)
+ doxygen (documentation)
+ git (source control)

## Windows Tools
+ MSYS2 (basically a must have for me)
+ Notepad++ (best out of the box autocomplete)
+ W10 Privacy (disables services and unecessary tasks for Windows)
+ ConEmu (If only Window's terminals natively supported tabbing)

## Linux Tools
+ i3 window manager

## IDE's
+ [Eclipse](https://www.eclipse.org/downloads/): Cross Platform, and feature rich, but heavy (Jave-based). It's plugin model allows us to adapt to most programming languages

+ [Visual Studio](https://visualstudio.microsoft.com/): If I have to. Best debugging I have seen so far, but too complicated for my liking

## Code editors
+ [vim](https://www.vim.org/download.php/): It's everywhere, and for good reason.

+ [Neovim](https://neovim.io/): Modernized vim. I try to use it instead of vim, but that tends to be difficult.

+ [Oni2](https://github.com/onivim/oni2): currently alpha, nvim IDE based on [revery](https://github.com/revery-ui/revery).

+ [Visual Studio Code](https://code.visualstudio.com/): The flexibility of a code editor with the power of an IDE. If only it was not made in Electron.

+ [Oni](https://github.com/onivim/oni): Nvim based nodal editor. A bit heavy, but I like it.

+ [Geany](https://www.geany.org/): Light, fast, and good autocompletion, but is not heavily developed and has no syntax checking
