# My bias
I use C everyday for work. I'm somewhat familiar with Python and Groovy. I appreciate what higher level languages offer, but sometimes high level languages make it hard to do some things, such as get an array of bytes or control the memory layout of data.

## Tool selection principle (ideally)
Go with what works. If something works better, go with that instead.

# Development thoughts
These are taken from people on the internet and my personal experience. These are not in any order in particular.

1. Performance is mostly derived from using the CPU cache as efficiently and effectively as possible. Here are a couple ways you can do that:
    1. Keep your data set as small as possible
    2. Condense arrays of pointers to a single array (not good if you need quick item insertion though)
    3. Use arrays wherever possible (From one of Chandler Carruth's CppCon talks). 
    4. If you're using perf, and you see `mov` instructions taking morst of the time, then you have a memory bottleneck.
    5. If you're memory bottlenecked, this may help. If the platform you write code for does not have a cache, then these tips won't help.
        1. Let the CPU spend more time working on data that's in cache. For example, instead of using a linked list, use a list with data in 64 byte blocks.
        2. Cache lines are about 64 bytes long. That means you can work on about 8 64 bit, 16 32 bit, or 32 16 bit units of data before another memory fetch __might__ happen (some CPUs may fetch more memory if they can. I've heard Intel CPUs can fetch more than 1 cache line at a time.)
        3. Using smaller integers and smaller data helps keep data in cache. There are many cases where you can use a 32 bit integer instead of a 64 bit integer.
    6. Don't condense extra items into a for/while loop. Doing the following:
    ```
    sum = 0
    for(number in array)
      sum += number
    endfor
  
    othersum = 0
    for(number in otherarray)
      othersum += number
    endfor
    ```
    is faster than doing this:
    ```
    othersum = 0
    sum = 0
    for(item in array, otheritem in otherarray )
      othersum += otheritem
      sum += item
    endfor
    ```
    The latter is slower because the program now has to hold 2 arrays in cache. Since they are competing for cache and space, the processor may have to fetch data from memory more often. Fetching data from memory is an order of magnitude slower than getting data from cache.
  
2. Separate a behavior into a function whenever you are going to that behavior more than once. It will be more compact and reduce code size.

3. Easy development originates from using someone else's well documented library.

4. Examples are the best documentation.

5. If you want to learn about development, watch programming conference talks on Youtube. Those people are probably some of the best in their field, and can show you more useful information in an hour than most college classes will in a week. These are some good places to start:
    1. This [talk](https://www.youtube.com/watch?v=z43bmaMwagI) by Jules May. To summarize, if's with shared conditions are the cause of the vast majority of bugs.
    2. Any talk that Kevlin Henny does. He talks mostly about coding style and design simplicity.
    3. CppCon talks are really good, even if you don't use C++. C++ is popular, and is the backbone of a lot of modern technology, so a lot of very smart people talk at these CppCon. Start with the ones with Chandler Carruth in them. I have found those to be consistently good.
    4. James Mickens is very funny, and has good security insights. It's a pity there are not more videos of him on YouTube.
    5. Brian Cantrill (Worked on Solaris in the Sun days) is fun to listen to, and his enthusiasm is engaging. [This is probably one of his best talks](https://www.youtube.com/watch?v=9QMGAtxUlAc)
    
6. Web development is hard. You need to know 4 proramming languages (html, javascript, css, and a backend language of your choice) to be able to do anything really good. You can tell the existing tools suck because people keep making new ones (coffeescript, typescript, elm, etc.)

7. Know your data, your setup and their unique properties. There are often optimizations that only you can make in your unique situation. Inspired by this [talk](https://www.youtube.com/watch?v=zqs87a_7zxw&t=4404s) by M. Skarupke.

8. Read first, ask questions later: often a thorough reading of documentation, or a internet search will clear things up.

9. Test and check: If you are not sure of anything's behavior, test it.

10. Failure modes are often the weakest parts of a program.

11. When starting a development project, start with what you need to do, and write code quickly and as messily as you please until it works, then test it. Once your are done with that, you can start refactoring and cleaning things up. Making optimizations midway through development can work, but you want to get the whole picture so that you don't waste time reverting optimizations you made before you had the whole picture.

12. Sleep on it: You are in your most creative state when you are about to fall asleep and when you are just waking up. Use that to your advantage. Thomas Edison and Albert Einstein both would almost fall asleep in their chair, while holding an object, and then that object falling out of their hand would wake them up when they fell asleep. They then used those ideas they got when falling asleep in their work. [Source](https://www.youtube.com/watch?v=vd2dtkMINIw&t=1510s)

13. Change things up (taken from one of Kevlin Henny's talks): Change your routine. That may help you get a different perspective on a problem.

14. Be curious and never stop learning: I use [lobste.rs](https://lobste.rs/) and [Hacker News](https://news.ycombinator.com/) to learn new development-related things and I still get my mind blown once in a while.

15. Don't be afraid of breaking things (If you are using modern source control): Modern source control's ability to revert to a working state should be used to its full advantage. If you are still afraid, then I probably cannot help you.

16. Don't beat yourself up: Being hard on yourself associates negative emotion with a general activity and makes your failure more memorable. That means that you will be more reluctant to try that activity next time, or more reluctant to improve on the area where you struggled. However, you should not make excuses or refuse to take blame.

17. When naming variables and functions, try to be as accurate as possible (from Kevlin Henny). Make sure that the names you give those parts of your program reflect the purpose and intent of what you are doing with them. I've caught bugs by giving variables better names.

18. Whenever you name a process, make sure that it is named so that you can tell what you use it for. A bad example is low pass and high pass filters. You use low pass filters to reject high frequency signals and an you use high pass filters to reject low frequencies. That extra step you have to take to translate the term into what you use it for could be avoided if that term was better made. A better example are band pass and band reject filters, since you use a band pass filter to pass through a small band of frequencies, and you use a band reject filter to reject a small band of frequncies.

19. Don't do work you've already done, and don't do work you don't need to do.

20. The simpler way to do things is usually better.

21. A good engineer measures things. Good measurements let you know if you are hitting goals or not. A good engineer also know what to measure to get good measurements. 

22. Be specific about your goals. If you're more specific about what you want, it becomes much easier to tell what you don't want or need. What you don't can be almost as important as what you don't need when you're trying to maintain simplicity

23. Be willing to spend time to get the bottom of things. In bigger companies, people that are higher up don't necessarily have the time to verify everything. If you don't verify things, then you don't know what reality is. If you don't know what reality is, then reality may bite you in unexpected ways.

# Development Tools (what I use)

## Code editors
I mostly pick code editors based on how satisfied I am while using them. When making a config for your own code editor, build it around you. Pick what makes you a faster and better developer. Take inspiration from others, but don't copy their config completely unless its better for you than your own.

1. [Neovim](https://neovim.io/) and [Vim](https://github.com/vim/vim): I use these primarily, with many plugins.

2. [Visual Studio Code](https://code.visualstudio.com/): I occasionally try to use this for work, but it keeps updating itself, and that can break plugins that are necessary for my job.

3. [Emacs](https://www.gnu.org/software/emacs/): You _need_ to configure Emacs to make it work well. It is more configurable than the vims, but slower and less satisfying to use (IMO). It don't use it much anymore.

## Favorite Programming laguages (that I have used)
+ [Zig](https://ziglang.org/): Simple enough, and fulfills a low-level programming C replacement niche that few have tried to fill.

+ [Julia](https://julialang.org/): The syntax and ease of use of a scripting language, and speed that is close enough to a compiled language. It also has the features of a modern programming languages (tests, package manager, build system, etc.)

## Source Control
+ [Git](https://git-scm.com/)

## Misc. Unix style tools:
+ Grep replacements:
    + [silver searcher](https://github.com/ggreer/the_silver_searcher)
    + [ripgrep](https://github.com/BurntSushi/ripgrep))
+ [fzf](https://github.com/junegunn/fzf) (fuzzy file finder)

## Tools that I should make someday
+ A low level language (like C) that incorporates lisp's metaprogramming capabilities without sacrificing speed or ease of use.

+ A single web development language that can replace HTML, Javascript, CSS, and your favorite backend language.

+ A language construct that removes the possiblity for shared conditions in code.

## Misc.
+ [gdb-dashboard](https://github.com/cyrus-and/gdb-dashboard): This is a premade configuration for GDB that makes it a lot more usable.
+ [GUD](https://www.emacswiki.org/emacs/GrandUnifiedDebugger): The emacs debugger, This one is pretty good if you are using Emacs anyway, but it does not have a watch window _by default_, wich I miss from Visual Studio Code.
