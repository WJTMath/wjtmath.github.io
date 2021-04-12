---
layout: home
# articles:
#   excerpt_type: html
---

This is a paragraph.

$$ a^2+b^2 = c^2 $$

$$ a_2 + b_2 = c_2 $$ is the inline.

$$ \frac{1}{\frac{1}{\frac{1}{x^2}}} $$

<div id="jxg_p8" class="center-block jsxgraph" style="height:200px; width: 200px;"></div>
<script>
var p8 = JXG.JSXGraph.initBoard('jxg_p8',{
  boundingbox: [-1,12,4,-2],
  keepAspectRatio: false,
  axis: true
});

p8.create('functiongraph',[x => 10-Math.pow(x,2),-4,4]);
p8.create('functiongraph',[x => -4*x+14,-4,4],{
  strokeColor: '#ff0000',
  dash: 2
});
</script>