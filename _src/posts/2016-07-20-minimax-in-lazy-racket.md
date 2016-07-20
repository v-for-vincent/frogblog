    Title: Minimax in lazy Racket
    Date: 2016-07-20T12:34:50
    Tags: Racket, A.I., game playing, hash langs

Recently, I implemented a generic [minimax](https://en.wikipedia.org/wiki/Minimax) algorithm in Racket.
The code is on [Github](https://github.com/v-for-vincent/racket-minimax).
I'm pretty happy with the code itself, which also includes pruning and loop checking against ancestor nodes (not other nodes, as that might not be worth the performance hit).

What's important about this bit of code, to me, is that it made Racket "click".
See, I needed lazy evaluation to solve this without compromising on elegance.
And I knew there was a lazy variant of Racket which I could activate by switching the `#lang` at the top of my file from `racket` to `lazy`.
But the implications of doing that became clear when I first tested my code in a separate `#lang racket` file with a specific evaluation function, game over check and ''rules'' (the states were nonsensical so I use the term lightly).

*I was calling code written in one language in a different language.*

With Racket, you get fantastic language interop.
You use different languages, all implemented in Racket, for different tasks and you can combine them.
And you don't need some gruesome foreign function interface.
You get the exact syntax you want, but in the end it's all Racket.

I'm still new to the language, but really realizing this has made it my favourite language.
I'm going to be writing a lot more of it in the future.
And now I really, *really* wish [Whalesong](http://www.hashcollision.org/whalesong/) was a 100% complete Racket implementation.
