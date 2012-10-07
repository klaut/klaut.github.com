---
layout: post
title: string permutations (from java to AS2)
tags:
- Actionscript
status: publish
type: post
published: true
meta: {}
---
In order to learn AS2 i've started to study java more intensely and translate various code snippets to AS2 and to great suprise, some of them can be just copy/pasted (syntactically speaking).
Here's an example. I came across <a href="http://www.cs.virginia.edu/~cs101/code/">this link </a>with some usefull java code to learn from. If you take a look at this <a href="http://www.cs.virginia.edu/~cs101/code/ch11/PermuteString.java">PermuteString java</a> class and the AS2 version below, you can see that i merely copied the code meat into an AS2 class (yeah, shame on me!).

<code>
class StringPermutator
{
private var __word:String;
private var __index:Number;
private var __substring:StringPermutator;</code>

<code>function StringPermutator(s:String)
{
__word = s;
__index = 0;
if(s.length &gt; 1) __substring = new StringPermutator(s.substring(1));
}</code>

<code>public function hasMorePermutations():Boolean
{
return __index</code>

<a href="http://www.klaustrofobik.org/blog/stuff/actionscript/permute_test.html">and you can test it here.</a>
