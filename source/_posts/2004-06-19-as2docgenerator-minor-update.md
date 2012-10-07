---
layout: post
title: AS2docGenerator minor update
tags:
- Actionscript
status: publish
type: post
published: true
meta: {}
---
Finally, i have some minor updates to the AS2docGenerator:
- added suport for the @interface tag,
- you can now add as a parameter a directory containing .as class files (or other directories with .as class files) and it will generate a _docs directory with all the html outputs

<b>example usage</b>:
1) single .as file:
C:\&gt; [path to]AS2docGenerator.exe [path to]AS2class.as
this generates a AS2class_doc.html file in the same directory AS2class.as is in.

2) a directory with .as files and/or other directories:
C:\&gt; [path to]AS2docGenerator.exe [path to]AS2classDirectory
this generates a _docs directory in the same directory where the AS2docGenerator.exe was called from. All the asClass_doc.html files are in the _docs directory.

<a href="http://www.klaustrofobik.org/snippets/AS2docGenerator/AS2docGenerator.zip">download it from here.</a>

The project is still in beta so bugs and other naughty insects are possible ;)
