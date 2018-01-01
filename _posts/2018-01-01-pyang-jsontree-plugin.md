---
layout: post
title: A JSON Tree Plugin
---

Another couple of days of free(ish) time over a holiday helped me finish a first version of a [JSON tree plugin](https://github.com/cmoberg/pyang-jsontree-plugin) for the vernable [pyang](https://github.com/mbj4668/pyang) tool. This (just like manu other things in life) was the ouctome of some serious [yak shaving](http://projects.csail.mit.edu/gsb/old-archive/gsb-archive/gsb2000-02-11.html) action over the last couple of weeks as I wanted to look for new and interesting ways of visualizing YANG.

When reading up on modern visualization libraries like [D3](https://d3js.org/), [vis.js](http://visjs.org/), [Treant.js](http://fperucic.github.io/treant-js/) and others I found that they all load JSON data for the tree content. Usually very simplistic, "schema-free" if you like, structures with a few required keywords to denote node names and lists of children. Since pyang builds and gives us access to a tree of YANG [statements](https://github.com/mbj4668/pyang/blob/e07beb02dbd0c4b3e7e9fe7c148ff4016f9ec2f7/pyang/statements.py#L2771) the plugin simply dumps the content of the `Statement` objects with the exception of the meta-statements (e.g. descriptions, references) that we keep in the nodes.

Small number of lines, but allowed me start in on what I hope will become an improved version of the `jstree` plugin.