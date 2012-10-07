---
layout: post
title: Extending AS2 Array
tags:
- Actionscript
status: publish
type: post
published: true
meta: {}
---
According to <a href="http://www.gskinner.com/blog/archives/000021.html">gSkinner's post</a>, when you extend an array you must call the superClass constructor in a particular way so that the indefinite amount of arguments get passed along correctly to the parent class:
<code>
class ArrayExtended extends Array
{
	function ArrayExtended(){
		super.constructor.apply(this, arguments);
	}
	public function someFunc(){
          return length;
    }

}
</code>
Well, that never worked for me... actually that's very strange because it appears as if it works for some but not for others..

today i came across a post a <a href="http://www.tweenpix.net/cgi-bin/mt-comments.cgi?entry_id=36">Tween Pix</a> and the solution that i saw there is working:
<code>
class ArrayExtended extends Array
{
	function ArrayExtended(){
		splice.apply(this, [0, 0].concat(arguments));
	}
	public function someFunc(){
          return length;
    }

}
</code>

but im still wondering WHY the gskinner's variant doesn't work for me??!

<b>UPDATE:</b>
The solution above (the one that works for me) was actually first posted at <a href="http://chattyfig.figleaf.com/ezmlm/ezmlm-cgi?1:mss:90588">flashcoders mailing list</a>
