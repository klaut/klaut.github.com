---
layout: post
title: CSS classes case sensitive?
tags:
- General
status: publish
type: post
published: true
meta: {}
---
I didn't know this before: It appears that css classes are case sensitive, but you must declare a proper doctype in your html document for this to work (html 4.01 and above).

For example, this stylesheet:
<pre>
// myStyle.css

.myclass{
	background-color: Aqua;
	width: 50px;
	height: 50px;
}

.MyClass{
	background-color: Fuchsia;
	width: 100px;
	height: 100px;
}
</pre>
whit this html document:
<pre>
//test.html





	<title>Test</title>
	




              <div>&nbsp;</div>
              <div>&nbsp;</div>



</pre>
will apply to each div the proper class.
If you test this in Mozilla Firefox or Netscape 7.1 it works stright away. If you take out the xml declaration it works even in IE6. But if you delete the doctype declaration, then both divs will take the style of the latter class (MyClass in this example).
I should probably note, that this has been only tested on my local PC, so i don't know if this is true for the Mac as well...
