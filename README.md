A small library designed to work with [d3-sankey-circular](https://github.com/tomshanley/d3-sankey-circular) to append arrows to sankey links, like in this [example](https://bl.ocks.org/tomshanley/6f3fcf68c0dbc401548733dd0c64e3c3).

The function creates a path for each link in the data, and uses **dash-array** to create individual arrows.  I use **dash-array** works well where there are curves in a path.

This library can be used with other chart types, as long as the path function can be specified to the pathArrows instance.

## Install

If you use NPM, `npm install d3-path-arrows`, else you can use the vanilla js file in the [compiled](https://github.com/tomshanley/d3-path-arrows/tree/master/compiled) folder.

## Usage

Create an instance of pathArrows, with function that will draw the path. Then call the instance of pathArrows on a selection that has the path data appended to it, for example:

```js
let arrows = pathArrows()
    	.arrowLength(10)
  	.gapLength(150)
    	.arrowHeadSize(4)
    	.path(function(link){ return link.path })

svg.append("g").data(sankeyLinks)
      .enter()
      .append("g")
      .attr("class", "g-arrow")
      .call(arrows)
```
The function accepts four parameters:

* **arrowLength**: length of the arrow, in pixels.

* **gapLength**: the gap between each arrow, in pixels.

* **arrowHeadSize**: the width of the arrow head.

* **path**: the function that will draw the path. If you are using this with d3-sankey-circular, use `function(link){ return link.path }` to access the path string.
