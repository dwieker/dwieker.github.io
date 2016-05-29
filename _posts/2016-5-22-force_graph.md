---
layout: post
title: Embedding d3 in github.io posts
---

<iframe src="http://embed.vida.io/documents/d82uSDX89uRFet64D" width="800" height="600" seamless frameBorder="0" scrolling="no"></iframe>

<iframe src="http://bl.ocks.org/dwieker/81f56a30d1f9d3ebece4246e840ac39f" width="800" height="600" seamless frameBorder="0" scrolling="no"></iframe>


You can embed d3 into [jekyll github blogs!](https://jekyllrb.com/) Try dragging around nodes. I'm using [vida.io](https://vida.io/) to host the visualization and the "iframe" html5 tag to render it here. Check the page source! 

For those unfamiliar with "d3": It's essentially a java script library that allows you to easily create "data driven (web) documents" (3 d's... GET IT?). From d3's website itself: "You can use D3 to generate an HTML table from an array of numbers. Or, use the same data to create an interactive SVG bar chart with smooth transitions and interaction." 

In the visualization above, each node is binded to a point in a javascript array. You can transform these points and use d3 to easily render the newly shifted nodes and lines in an html document. Without d3, you would have to arduously modify html attributes yourself.

[Here's a cool collection of d3 visualizations.](https://bl.ocks.org/mbostock)



