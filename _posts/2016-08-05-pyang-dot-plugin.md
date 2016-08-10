---
layout: post
title: Vacation hacks
---

Swedish vacations (known for being long) are excellent for some out-of-office hacking. Having just come back from mine, I've pushed a some things to github:

### Pyang DOT output plugin
Finding myself needing to visualize relationships (i.e. imports and includes) between large sets of YANG modules using some reasonable well supported graph format and associated visualizing tools. I ended up picking up the venerable (DOT)[https://en.wikipedia.org/wiki/DOT_(graph_description_language)] format as it seemed to be enough for my fairly simple feature needs (digraphs) and it certainly has wide and deep support in terms of output format and visualizing tools.

I wrote up a very simple pyang to produce DOT files from sets of YANG modules available (here)[https://github.com/cmoberg/pyang-module-catalog-plugin/].

### Pygments YANG lexer
I still haven't seen any of the well-known code highlight libraries gaining support for YANG. So I thought I'd use some vacation time for this as well. I started out with Pygments, a "generic syntax highlighter suitable for use in code hosting, forums, wikis" written in python.

I did a fairly complete YANG lexer for Pygments, available (here)[https://github.com/cmoberg/pygments-yang-lexer]