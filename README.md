OVERVIEW
==================

[mse2wp.py](https://github.com/davidlowryduda/mse2wp) is a script that converts
[Math.SE](http://math.stackexchange.com/) style markdown or certain .tex files 
into an html file that can be copypasted into the 
[Math.SE community blog](http://math.blogoverflow.com/).

GETTING STARTED
===============

Have mse2wp.py and your Math.SE-style markdown file (which you might bet by copying
an answer that renders on Math.SE into a file `myfile.md`, for example) in the
same directory. 

Then type

    :~$ python mse2wp.py myfile.md

mse2wp will output

    :The output is now in myfile.html.
    :There may have been errors. Please check the output.

And the file `myfile.html` is ready to be copy-pasted into the Math.SE Community
Blog. Not everything in markdown and latex is supported and automated, but the
fixes should be clear. 

*Note that it is necessary to hit* **preview** *on Wordpress to properly render
markdown*, and you can't simply rely on the `visual panel`. 
    
USAGE ON LATEX FILES
====================

Simply calling

    :~$ python mse2wp.py myfile.tex

will produce a file `myfile.html`, but this behaves poorly with custom macros. 
A more reliable way is to create your latex file from the `post-template.tex`,
or to make sure that your latex file compiles when put in the form of the template. 

It is possible to add in your own customized macros by editing `M` in `mse2wp.py`
and the macro definitions in `macrosblog.tex.`

See the file `example.tex` to see examples of a good looking tex file that
produces good looking blog posts. 

A TYPICAL ERROR
===============

The file `example.tex` yields `example.html` with mse2wp, and yields one type
of error that is caused by the interplay of html, tex, and markdown. There is
a line that should be

    \[ \E_{x \in X} f(x) := \sum_{x\in X} \P [x] \cdot f(x) \]

but because markdown interprets `_stuff_` as _stuff_ (italicized), this breaks
the MathJax. A fix would be to separate one of the underscores, like

    \[ \E_{x \in X} f(x) := \sum _{x\in X} \P [x] \cdot f(x) \]

and this is not done automatically. This sort of error will likely come up, and 
needs to be handled manually. (Nobody's perfect, I suppose)

THANKS
======

This was modified from [latex2wp](http://lucatrevisan.wordpress.com/latex-to-wordpress/),
which has saved me a lot of time over the years. 
