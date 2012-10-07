---
layout: post
title: Learning Haskell - First Date
tags:
- haskell
- learning
status: publish
type: post
published: true
meta:
  _edit_last: '1'
---
Monday is here and so I met for the first time with Haskell.

Installation went quickly and without any problems (installed the <a href="http://hackage.haskell.org/platform/">Haskell platform for macosx</a>). You get a compiler, a bunch of standard modules and an interactive interpreter. I like having the interpreter as a way to quickly try out stuff in Python, so the fact that Haskell has its own as well immediately gained points  with me :)

It is much more convenient while you learn to have an immediate feedback than having to type some code to a file and compiling.

First thing you try is the “command line calculator”. Haskell is behaving as you would expect it to behave:
<code>ghci&gt; 2 + 4
ghci&gt; 6</code>

All the usual suspects are here: addition, multiplication, subtraction ... nothing differs from Python.
But then quickly the similarities stop to be, well, similar.

Haskell is a functional language and as such it does not modify state. That, translated to something meaningful to me is: variables are just symbols that hold values. Once you assign a value to a variable you can’t change it. Variables in Python and variables in Haskell are not the same. At the moment it is still difficult for me to grasp what this mean and how it can be useful. But right now I am still looking and evaluating Haskell from the imperative languages point of view. Also the fact that Haskell is known to be *lazy* is somehow odd, but then it sounds like a cool feature - the fact that it won’t bother to compute things until it is really forced to do so.

This means that you can create lists with infinite number of elements and Haskell it is quite happy to create them for you. Fast. Well, unless you try to create them at the interactive interpreter. You will have to stop it from spitting all the numbers till the end:
<code>ghci&gt; [1..]</code>

<strong>Lists.</strong>

They can have unlimited amounts of elements. But the elements must be all of the same type. Strings as we know them are lists of chars so the following examples are all the same to Haskell:
<code>ghci&gt; “hello”
ghci&gt; [“h”,”e”,”l”,”l”,”o”</code>]

If you want quickly construct a list of ranges you can do: [1..100]. This will create a list of numbers from 1 to 100. You can specify a step to the range as well: [1,3..20]. This will create the following list: [1,3,5,7,9,11,13,15,17,19].

For concatenating strings or lists you would use: [1,2] ++ [3,4] or “hello” ++ “ “ ++ “world”. Basically the ++ function inserts the stuff on the right (which must be a list) at the end of the list on the left side. But what if i want to insert something at the beginning? I can do that:
<code>ghci&gt; a:[b,c,d]
ghci&gt; [a,b,c,d]</code>

The only difference: the thing you insert is a single element. Not a list.

If you want to get the second element from a list (the indices start at 0) you would use the !! (yes, that is double exclamation mark):
<code>ghci&gt; [1,2,3,4]!!1
ghci&gt; 2</code>

There is a whole bunch of functions to manipulate lists and they all sound quite exotic (although I did remembered my CS semester of Prolog while trying some of them out).
Let’s say you want the first element from the list:
<code>ghci&gt; head [1,2,3,4]
ghci&gt; 1</code>

What about the last?
<code>ghci&gt; last [1,2,3,4]
ghci&gt; 4</code>

To get everything but the first element you use tail:
<code>ghci&gt; tail [1,2,3,4]
ghci&gt; [2,3,4]</code>

And everything but the last element? init.
<code>ghci&gt; init [1,2,3,4]
ghci&gt; [1,2,3]</code>

There is a lot of very well written and comprehensible material online that i am using as a learning material. Some of the best resource that I found are:
<ul>
	<li><a href="http://learnyouahaskell.com/">Learn You A Haskell For Great Good</a></li>
	<li><a href="http://book.realworldhaskell.org/read/">Real World Haskell</a></li>
	<li><a href="http://en.wikibooks.org/wiki/Haskell">Haskell Wikibook</a></li>
</ul>
All in all, I enjoyed my Monday evening. Haskell does feel strange for now and I can’t possibly think of how i would go on about writing real life programs with it. But hey, it is only my first Monday :)
