---
layout: post
title: Embedding d3 in github.io posts
---
<iframe src="https://vida.io/gists/4xhNr9bKjfue2F2Dg/index.html" seamless frameborder="0" width="968" height="508"></iframe>

You can embed d3 into [jekyll github blogs!](https://jekyllrb.com/) I'm using [vida.io](https://vida.io/) to host the visualization and the "iframe" html5 tag to render it here. Check the page source! This visualization was taken from Mike Bostock's [cool collection](https://bl.ocks.org/mbostock)


For those unfamiliar with "d3": It's essentially a java script library that allows you to easily create "data driven (web) documents" (3 d's... GET IT?). From d3's website itself: "For example, You can use D3 to generate an HTML table from an array of numbers. Or, use the same data to create an interactive SVG bar chart with smooth transitions and interaction." 

In the visualization above, each node is binded to a point in a javascript array. You can transform these points and use d3 to easily render the newly shifted nodes and lines in an html document. Without d3, you would have to arduously modify html attributes yourself.


Here's an interactive one. Try dragging around nodes.

<iframe src="http://embed.vida.io/documents/d82uSDX89uRFet64D" width="600" height="625" seamless frameBorder="0" scrolling="no"></iframe>



