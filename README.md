# Development tools and practice

## My bias
I am working toward being a computer engineer, and as a result do not use high level languages like Python or Javascript as much as C or C++. Because of my experience, I prefer to use faster programming languages, or ones that can be optimized to be fast (Cython for Python for example). I do not prefer languages like Java and C# because, IMO, They provide even more verbosity than C/C++ without the speed of C++/C. 

Granted, Java and C# have other benefits, but those benefits are basically all runtime-related, and are not attached to the language syntax.

## Tool selection principle (ideally)
Go with what works. If something works better, go with that instead.

# Development thoughts
Most of these are derived from the internet, and my personal experience.

1. Performance is mostly derived from using the CPU cache as efficiently and effectively as possible. Here are a couple ways you can do that:
  1. Keep your data set as small as possible
  2. Condense arrays of pointers to a single array (not good if you need quick item insertion though)
  3. Use arrays wherever possible (From one of Chandler Carruth's CppCon talks)
  4. Don't condense extra items into a for/while loop. Doing the following:
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
  The latter is slower because the cache has to hold 2 arrays now. Those 2 arrays are competeting for cache space.
  
2. When should you make something into a separate function? In my opinion, separate a behavior into a function whenever you are going to that behavior more than once. It will be more compact and reduce code size.

3. Well documented libraries that someone else made make development easy.

4. Examples are the best documentation.

5. If you want to learn about development, watch programming conference talks on Youtube. Those people are probably some of the best in their field, and can show you more useful information in an hour than most college classes will in a week. These are some good places to start:
  1. Any talk that Kevlin Henny does. He talks mostly about coding style and design simplicity.
  2. CppCon talks are really good, even if you don't use C++. C++ is popular, and is the backbone of a lot of modern technology, so a lot of very smart people talk at these CppCon. Start with the ones with Chandler Carruth in them. I have found those to be consistently good.
  3. James Mickens is very funny, and has good security insights. It's a pity there are not more videos of him on YouTube.
  4. Brian Cantrill (Worked on Solaris in the Sun days) is fun to listen to, and his enthusiasm is engaging. [This is probably one of his best talks](https://www.youtube.com/watch?v=9QMGAtxUlAc)


