A small library designed to work with d3-sankey-circular to append arrows to sankey links, like in this [example](https://bl.ocks.org/tomshanley/6eb025290888935f10b142e4bc576d8d).

The function creates a path for each link in the data, and uses **dash-array** to create individual arrows.  I use **dash-array** works well where there are curves in a path

## Usage

Call the function **appendArrows** on selection that has link data from the d3-sankey-circular function.

```js
var arrowsG = linkG.data(sankeyLinks)
      .enter()
      .append("g")
      .attr("class", "g-arrow")
      .call(appendArrows, 20, 300, 4)
```
The function accepts three parameters:

* **arrowLength**: length of the arrow, in pixels

* **gapLength**: the gap between each arrow, in pixels

* **arrowHeadSize**: the width of the arrow head
