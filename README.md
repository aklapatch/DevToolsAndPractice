# Preferences for development

## My bias
I am working toward being a computer engineer, and as a result do not use high level languages like Python or Javascript as much as C or C++. Because of my experience, I prefer to use faster programming languages, or ones that can be optimized to be fast (Cython for Python for example). I do not prefer languages like Java and C# because the applications that use those languages a lot (Visual Studio and Eclipse) are slow. I will still use C# and Java if I need to, but from what I can see, there is almost always a better solution that C# or Java.

Go with what works. If something works better, go with that instead.

## Development process
1. Start programming without an full idea of the entire system
2. Realize that I need to plan
3. Plan a little
4. Code more
5. Repeat from 2
6. Find a way to improve my Development process

## Source control
Use [Git](https://git-scm.com/) and [Github](https://github.com/).

## Documentation
Use [Doxygen](http://doxygen.nl/) or find something better. [Natural Docs](https://www.naturaldocs.org/) and Doxygen + [Sphinx](http://www.sphinx-doc.org/en/master/) + [Breathe](https://breathe.readthedocs.io/en/latest/) (using the [sphinx_rtd_theme](https://github.com/rtfd/sphinx_rtd_theme)) both look promising.

## Coding standards
I will use the [LLVM coding standard](http://llvm.org/docs/CodingStandards.html) for C/C++, and will try to use other languages preferences when using those languages.

## Programming Languages 
This sections is for languages that I should learn because they are modern or offer lots of libraries or features.

+ [Rust](https://www.rust-lang.org/): I should learn this at some point. Memory safety and more than enough speed. 

+ [Julia](https://julialang.org/): Fast enough, and with more features than you can shake a stick at, this language is my go to scripting langauage. Unforutnately, it has fewer libraries than Rust, but is compatible with C libraries.

+ [C](https://en.wikipedia.org/wiki/C_%28programming_language%29): There is a C library to do almost anything. If you want to make a libary that you can use across programming languages, program it in C. Enough languages have C intefaces where that is a reasonable suggestion.

+ [C++](https://en.wikipedia.org/wiki/C%2B%2B): Please don't learn this language if you can avoid it. Its overly complex and (IMHO) survived because it was compatible with C and was better than anything else at the time. Use C++11 on if possible.

+ [Python](https://www.python.org/): Has a library for everything, and is easy to program in. If I did not use Julia, I would use Python.

+ [Lisp](https://en.wikipedia.org/wiki/Lisp_(programming_language): Utterly unique and remains so. Learn it, and it will give you a better perspective into programming in general (or so I have heard).

+ [PHP](https://secure.php.net/): Practical and useful web development language. Good for hooking up databases to websites too.

+ [Javascript](https://www.javascript.com/): The most prolific programming language as of writing this. I don't like it or use it. It seems to be associated with lots of slow and bloated things (probably no fault of its own).

# Tools

## Standalone gdb frontends (list [here](https://sourceware.org/gdb/wiki/GDB%20Front%20Ends))
+ [gdbgui](https://github.com/cs01/gdbgui/): browser based frontend for C++, rust and other languages.
  Works well, but it is in a browser. It can be installed with pip.
  
+ [Nemiver](http://home.gna.org/nemiver): GNOME based frontend (tried it and it may be buggy)

## Build tools
+ [Cmake](https://cmake.org/)
+ [Meson](https://mesonbuild.com/) (I should probably use this. It seems easier and faster than cmake)
+ [Ninja](https://ninja-build.org/) (not as versatile as make, but fast)
+ [Make](https://en.wikipedia.org/wiki/Make_(software))

## Database clients
+ [DBeaver](https://dbeaver.io/): A bit slow since it is java based, but is cross platform.
+ [HiediSQL](https://www.heidisql.com/): Has the best UI Layout (IMO) for a DBMS and works under WINE for Linux.

## Best Linux Distros (for me)
+ [Arch](https://www.archlinux.org/)
+ [Manjaro](https://manjaro.org/)
+ [DebianTesting](https://wiki.debian.org/DebianTesting): You can get it by using [SparkyLinux](https://sparkylinux.org/download/rolling/)

## UI Library
+ [WxPython](https://wxpython.org/): The best combination of an easy programming language, and a native/cross platform GUI that I could find.

## Graphics API
+ [Vulkan](https://www.khronos.org/vulkan/): Verbose, efficient API (Use the [LunarG SDK](https://www.lunarg.com/vulkan-sdk/))
+ [GLFW](https://www.glfw.org/): Cross-platform window creation

## Other Cross Platform tools
+ [Cppcheck](http://cppcheck.sourceforge.net/): Static analysis
+ [Ccache](https://ccache.samba.org/): Speeds up rebuilds of software
+ [Graphviz](https://graphviz.org/): Makes callgraphs in Doxygen

## Windows Tools
+ [MSYS2](https://www.msys2.org/) (basically a must have for me)
+ [Notepad++](https://notepad-plus-plus.org/) (best out of the box autocomplete)
+ [W10 Privacy](https://www.winprivacy.de/english-home/) (disables services and unecessary tasks for Windows)
+ [ConEmu](https://conemu.github.io/) (If only Window's terminals natively supported tabbing)

## Linux Tools
+ [i3 Window Manager](https://i3wm.org/)

## IDE's
+ [Eclipse](https://www.eclipse.org/downloads/): Cross Platform, and feature rich, but heavy (Java-based). It's plugin model allows us to adapt to most programming languages

+ [Visual Studio](https://visualstudio.microsoft.com/): If I have to. Best debugging I have seen so far, but too complicated for my liking

## Code editors
+ [Vim](https://www.vim.org/download.php/): It's everywhere, and for good reason.

+ [Neovim](https://neovim.io/): Modernized vim. I try to use it instead of vim, but that tends to be difficult.

+ [Oni2](https://github.com/onivim/oni2): currently alpha, nvim IDE based on [revery](https://github.com/revery-ui/revery).

+ [Visual Studio Code](https://code.visualstudio.com/): The flexibility of a code editor with the power of an IDE. If only it was not made in Electron.

+ [VSCodium](https://github.com/VSCodium/vscodium): VSCode without telemetry. Also what I currently use. I used the Shades of Purple theme and usually reduce the font size.

+ [Oni](https://github.com/onivim/oni): Nvim based nodal editor. A bit heavy, but I like it.

+ [Geany](https://www.geany.org/): Light, fast, and good autocompletion, but is not heavily developed and has no syntax checking

## Misc
