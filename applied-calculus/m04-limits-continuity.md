---
title: '04: Limits and Continuity'
---

The secant line slope approaches the tangent line slope as the interval between the two points gets smaller.
The **limit** gives us a better language to describe this idea of “approaches.”

TODO: GRAPH

## Definition of a Limit

The limit of a function describes its behavior when the variable is near, **but does not equal**, a given number.
If the values of $$f(x)$$ get closer to some number $$L$$ as the values of $$x$$ get very close to (but not equal to) some number $$c$$.
No matter how close to $$L$$ we need, there is always a number close to $$c$$ that will get there.

In words we say "the limit of $$f(x)$$ as $$x$$ approaches $$c$$ is $$L$$."
In math notation, this is written as $$\displaystyle\lim_{x \to c}{f(x)} = L$$.

Contrast how this new limit idea describes sometime a little different than the function definition before:
- $$f(x)$$ describes the behavior of $$f(x)$$ **at** the point $$x=c$$.
- $$\displaystyle\lim_{x \to c}{f(x)}$$ describes the behavior of $$f(x)$$ **near, but not at**, the point $$x=c$$.

If we have a graph of the function near $$x=c$$, it is usually easy to determine $$\displaystyle\lim_{x \to c}{f(x)}$$.
Using function tables it is not technically possible to satisfy the defifinition of the limit, but with a few very light assumptions we can get a good idea of what the limit idea looks like.

TODO: Add table/formula disscussion?

<i class="fas fa-coffee"></i> Try: [Example 1](#example-1), [Example 2](#example-2)
{:.success}

## One Sided Limits

Sometimes a function's behavior at a place depends on the *direction* used to approach that place.
For example, if you approach Niagara Falls from the upstream side, you will be 182 feet higher and have different worries than if you approach from the downstream side.
Similarly, the value of a function near a point may depend on the direction used to approach that point.

The **left limit** of $$f(x) $$ as $$x$$ approaches $$c$$ is equal to $$L$$ if the values of $$f(x)$$ can get as close to $$L$$ as desired when $$x$$ is very close to, **but to the left of**  $$c$$.
That is, $$x<c$$.
In math notation: $$\displaystyle\lim_{x \to c^{-}}{f(x)}=L$$.
The difference is small: $$c^{-}$$ vs $$c$$.

The **right limit** of $$f(x)$$ is the same definition as the left limit except that $$x$$ must be very close to, **but to the right of** $$c$$.
That is, $$x>c$$.
In math notation: $$\displaystyle\lim_{x \to c^{+}}{f(x)}=L$$.
The difference is small: $$c^{+}$$ vs $$c$$.

Contrast these one-sided definitions of the limit with the definition above.
By not requiring that both sides of the limit agree with one another, we can define a limit for "jumps" in the graph, like in the graph below.

<div class="grid">
  <div class="jsxgraph" id="jxg_t1" style="width:200px; height:200px;">
    <noscript>Graph requires JavaScript to display.</noscript>
  </div>
  <div class="cell cell--auto pl-3" markdown="1">
    - \$$\displaystyle\lim_{x \to 1^{-}}{f(x)}=2$$
    - \$$\displaystyle\lim_{x \to 1^{+}}{f(x)}=4$$
    - $$\displaystyle\lim_{x \to 1}{f(x)}$$ does not exist.
  </div>
</div>
<script>
{
  let boardOpts = {
    boundingbox: [-1,5,5,-1],
  };
  let b = JXG.JSXGraph.initBoard('jxg_t1',boardOpts);
  b.create('functiongraph',[(x)=>x**2+1,-5,1]);
  b.create('functiongraph',[(x)=>x+3,1,5]);
  b.create('circle',[[1,2],[1.1,2.1]],{fillColor:'blue'});
  b.create('circle',[[1,4],[1.1,4.1]],{fillColor:'white'});
}
</script>

<i class="fas fa-coffee"></i> Try: [Example 3](#example-3)
{:.success}

## Continuity

A function that is “well-behaved” and doesn’t have any breaks or jumps in it is called **continuous**.  More formally, its two-sided limit is equal to the function definition. 

A function f is **continuous at $$x=c$$**  when $$\displaystyle\lim_{x \to c}{f(x)} = f(c)$$.
{:.info}

This short definition has a lot of nuance within it.
Think of continuity as the combination of three conditions:

1. The function is defined: $$f(c)$$
2. The function's limit is defined: $$\displaystyle\lim_{x \to c}{f(x)}$$
3. The definition is equal to the limit: $$f(c)=\displaystyle\lim_{x \to c}{f(x)}$$

If any of the three conditions are not met, the function is **discontinuous at $$x=c$$**.

The graph below illustrates some of the different ways a function can behave at and near a point, and the table contains some numerical information about the function and its behavior.

<div class="jsxgraph mx-auto" id="jxg_t2" style="width:400px; height:200px;">
  <noscript>Graph requires JavaScript to display.</noscript>
</div>
<script>
{
  let b = JXG.JSXGraph.initBoard('jxg_t2',{boundingbox: [-1,5,11,-1]});
  b.create('functiongraph',[(x)=>Math.sin(Math.PI/2*x)+2,-10,6]);
  b.create('functiongraph',[(x)=>2*Math.pow((x-6)/2,2)+1,6,8]);
  b.create('functiongraph',[(x)=>2*Math.pow((x-10)/2,2)+1,8,10]);
  b.create('functiongraph',[(x)=>1,10,15]);
  
  [[1,3],[4,1],[6,2]].map(function(p) {
    b.create('point',p,JXG.WJT.point);
  });
  [[4,2],[6,1],[8,3]].map(function(p) {
    b.create('point',p,JXG.WJT.openPoint)
  })
}
</script>

| $$c$$ | $$f(c)$$  | $$\displaystyle\lim_{x \to c}{f(x)}$$   | continuous at $$c$$? |
|:-----:|:---------:|:---------------------------------------:|:--------------------:|
| 1     | 3         | 3                                       | yes                  |
| 4     | 1         | 2                                       | no                   |
| 6     | 2         | does not exist                          | no                   |
| 8     | undefined | 3                                       | no                   |
{:.mx-auto}

The table include information about the definition of the function $$f(x)$$ at each point as well as its limit $$\displaystyle\lim_{x \to c}{f(x)}$$ at several points.
If the two are equal, the function is continuous at that point.

The behavior at $$x=4$$ and $$x=8$$ show a **hole** in the graph.
If that single point's value could be redefined to make the function continious, like at $$x=4$$, this is called a **removable discontinuity**.
The behavior at $$x=6$$ is called a **jump discontinuity** because the graph jumps between two values.

Which functions are continuous?
Most functions you have likely studied before are continuous: polynomial, radical, rational, exponential, and logarithmic functions are all continuous where they are defined.
Moreover, any combination of continuous functions is also continuous.

This property is helpful because the definition of continuity says that $$\displaystyle\lim_{x \to a}{f(x)}=f(a)$$.
The limit can be found by direct substitution (evaluating the function) if the function is continuous at $$a$$.

<i class="fas fa-coffee"></i> Try: [Example 4](#example-4)
{:.success}

## Examples

Example 1 <a name="example-1"></a>
{:.example-label}

Use the graph of $$y=f(x)$$ below to determine the following limits:

<div class="grid">
  <div class="cell cell--3" markdown="1">
  - \$$\displaystyle\lim_{x \to 1}{f(x)}
  - \$$\displaystyle\lim_{x \to 2}{f(x)}
  - \$$\displaystyle\lim_{x \to 3}{f(x)}
  - \$$\displaystyle\lim_{x \to 4}{f(x)}
  </div>
  <div class="cell cell--auto">
    <div class="jsxgraph" id="jxg_x1" style="width:200px; height:200px;">
      <noscript>Graph requires JavaScript to display.</noscript>
    </div>
  </div>
</div>
<script>
  var boardOpts = {
    boundingbox: [-1,5,5,-1]
  };
  var x1 = JXG.JSXGraph.initBoard('jxg_x1',boardOpts);

  x1.create('spline',[[-1,0,1,2,3,4],[2,1,2,3,1,2]]);
  x1.create('spline',[[4,4.5,5],[3,2.5,1]]);
  x1.create('circle',[[1,2],[1.1,2.1]],{fillColor:'blue'});
  x1.create('circle',[[2,3],[2.1,3.1]],{fillColor:'white'});
  x1.create('circle',[[3,1],[3.1,1.1]],{fillColor:'white'});
  x1.create('circle',[[3,2],[3.1,2.1]],{fillColor:'blue'});
  x1.create('circle',[[4,1],[4.1,1.1]],{fillColor:'blue'});
  x1.create('circle',[[4,2],[4.1,2.1]],{fillColor:'white'});
  x1.create('circle',[[4,3],[4.1,3.1]],{fillColor:'white'});
</script>

Solution 1
{:.example-solution-label}

 (a)     f(x)  = 2 .  
When  x  is very close to  1,  the values of  f(x) are very close to  y = 2.  In this example, it happens that  f(1) = 2, but that is irrelevant for the limit.  The only thing that matters is what happens for  x  close to 1 but  x ≠ 1.

(b) f(2) is undefined, but we only care about the behavior of  f(x)  for  x  close to 2 and  not equal to 2.  When  x is close to 2, the values of  f(x)  are close to  3.  If we restrict  x  close enough to 2, the values of  y  will be as close to  3  as we want,  so     f(x) = 3.  

(c) When  x  is close to  3  (or as  x approaches the value  3), the values of  f(x) are close to  1 (or approach the value 1),  so    f(x) = 1.  For this limit it is completely irrelevant that  f(3) = 2,  We only care about what happens to  f(x)  for  x  close to and not equal to 3.

(d) This one is harder and we need to be careful.  When  x  is close to  4 and slightly less than  4  (x  is just to the left of  4 on the  x–axis), then the values of  f(x)  are close to  2.  But if x is close to  4  and slightly larger than  4  then the values of  f(x)  are close to 3.   If we only know that  x  is very close to  4, then we cannot say whether  y = f(x)  will be close to  2  or close to  3 –– it depends on whether  x  is on the right or the left side of  4.  In this situation,  the  f(x)  values are not close to a single number so we say    f(x)   does not exist.  It is irrelevant that  f(4) = 1.  The limit, as  x  approaches 4, would still be undefined if  f(4)  was 3  or  2 or  anything else.


Example 2 <a name="example-2"></a>
{:.example-label}

Find $$\displaystyle\lim_{x \to 1}{\frac{2x^2-x-1}{x-1}}$$.

Solution 2 (v1)
{:.example-solution-label}

You might try to evaluate \( f(x) = \frac{2x^2-x-1}{x-1} \) at x = 1, but f(x) is not defined at x = 1.  It is tempting, but wrong, to conclude that this function does not have a limit as x approaches 1.  

__Using Tables__:  Trying some "test" values for x  which get closer and closer to 1 from both the left and the right, we get

TODO: TABLE

The function f is not defined at x = 1, but when x is close to 1, the values of f(x) are getting very close to 3. We can get f(x) as close to 3 as we want by taking x very close to 1 so \( \lim_{x \to 1}{\frac{2x^2-x-1}{x-1}} = 3\).

Solution 2 (v2)
{:.example-solution-label}

__Using algebra__:  We could have found the same result by noting that \( \frac{2x^2-x-1}{x-1} = 2x+1 \) as long as x ≠ 1.  (If x≠1, then  x–1 ≠ 0 so it is valid to divide the numerator and denominator by the factor  x–1.)  The \(x \to 1 \)  part of the limit means that x  is close to 1 **but not equal to 1**, so our division step is valid and \( \lim_{x \to 1}{\frac{2x^2-x-1}{x-1}} = \lim_{x \to 1}{2x+1} = 3 \), the correct answer.

Solution 2 (v3)
{:.example-solution-label}

__Using a graph__:  We can graph \( y = \frac{2x^2-x-1}{x-1} \) for  x  close to  1, and notice that whenever x  is close to  1, the values of  y = f(x) are close to 3. f is not defined at x = 1, so the graph has a hole above x = 1, but we only care about what f(x) is doing for x close to **but not equal to** 1.


Example 3 <a name="example-3"></a>
{:.example-label}

Evaluate the one sided limits of the function f(x) graphed here at x = 0 and x = 1.
TODO: GRAPH

Solution 3
{:.example-solution-label}

As x approach 0 from the //left//, the value of the function is getting closer to 1, so \( \lim_{x \to 0^{-}}{f(x)}= 1 \).

As x approaches 0 from the right, the value of the function is getting closer to 2, so \( \lim_{x \to 0^{+}}{f(x)} = 2 \). 

Notice that since the limit from the left and limit from the right are different, the general limit, \( \lim_{x \to 0}{f(x)} \), does not exist.

At x approaches 1 from either direction, the value of the function is approaching 1, so \lim_{x \to 1^{-}}{f(x)} = \lim_{x \to 1^{+}}{f(x)} = \lim_{x \to 1}{f(x)} = 1 \).


Example 4 <a name="example-4"></a>
{:.example-label}

Is is possible to evaluate these limits using continuity?
If so, evaluate.
If not, explain why not.

- {:.py-1} \$$\displaystyle\lim_{x \to 2}{(x^3-4x)}$$
- {:.py-1} \$$\displaystyle\lim_{x \to 2}{\frac{x-4}{x+3}}$$
- {:.py-1} \$$\displaystyle\lim_{x \to 2}{\frac{x-4}{x-2}}$$

Solution 4
{:.example-solution-label}

a) The function is polynomial and defined for all values of $$x$$.
Find the limit by direct substitution:

$$\lim_{x \to 2}{(x^3-4x)} = (2)^3-4(2) = 0$$

b) The function is rational.
It is not defined at $$x=-3$$, but the limit is as $$x$$ approaches 2.
$$f(x)$$ is defined and continuous at $$x=2$$, so direct substitution is possible:

$$\lim_{x \to 2}{\frac{x-4}{x+3}} = \frac{(2)-4}{(2)+3} = -\frac{2}{5}$$ 

c) The function is rational.
It is not defined or continuous at $$x=2$$.
Direct substitution cannot be used to find this limit.


## Exercises

Exercise 1
{:.exercise-label}

Use the graph to evaluate the following limits.

<div class="grid">
  <div class="cell">
    <div class="jsxgraph" id="jxg_p1" style="width:200px; height:200px;">
      <noscript>Graph requires JavaScript to display.</noscript>
    </div>
  </div>
  <div class="cell cell--auto pl-3" markdown="1">
  - \$$\displaystyle\lim_{x \to 1}{f(x)}$$
  - \$$\displaystyle\lim_{x \to 2}{f(x)}$$
  - \$$\displaystyle\lim_{x \to 3}{f(x)}$$
  - \$$\displaystyle\lim_{x \to 4}{f(x)}$$
  </div>
</div>
<script>
{
  let boardOpts = {
    boundingbox: [-1,3,5,-3]
  };
  let b = JXG.JSXGraph.initBoard('jxg_p1',boardOpts);
  b.create('spline',[[-1,0,1,2,2.4,3],[1,1.5,2,1,0,-1]]);
  b.create('functiongraph', [(x)=>-Math.sqrt(x-3)+2,3,5]);

  let op = [[2,1],[3,2],[3,-1],[4,1]];
  op.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.1,p[1]+0.1]],{fillColor:'white'});
  });

  let cp = [[1,2],[2,2],[3,1]];
  cp.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.1,p[1]+0.1]],{fillColor:'blue'});
  });
}
</script>


Exercise 2
{:.exercise-label}

Use the graph to evaluate the following limits.

<div class="grid">
  <div class="cell">
    <div class="jsxgraph" id="jxg_p2" style="width:200px; height:200px;">
      <noscript>Graph requires JavaScript to display.</noscript>
    </div>
  </div>
  <div class="cell cell--auto pl-3" markdown="1">
  - \$$\displaystyle\lim_{x \to 1}{f(x)}$$
  - \$$\displaystyle\lim_{x \to 2}{f(x)}$$
  - \$$\displaystyle\lim_{x \to 3}{f(x)}$$
  - \$$\displaystyle\lim_{x \to 4}{f(x)}$$
  </div>
</div>
<script>
{
  let boardOpts = {
    boundingbox: [-1,3,5,-3]
  };
  let b = JXG.JSXGraph.initBoard('jxg_p2',boardOpts);
  b.create('spline',[[-1,0,0.5,1,1.5,2],[0.5,1,1.3,1,0.7,1]]);
  b.create('functiongraph', [(x)=>2,2,3]);
  b.create('functiongraph', [(x)=>2*Math.abs(x-4),3,5]);

  let op = [[1,1],[2,1],[3,2]];
  op.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.1,p[1]+0.1]],{fillColor:'white'});
  });

  let cp = [[2,2],[3,1],[4,0]];
  cp.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.1,p[1]+0.1]],{fillColor:'blue'});
  });
}
</script>


Exercise 3
{:.exercise-label}

For the function $$f(x)=\dfrac{x^2+3x+3}{x-2}$$, evaluate the following limits.

- \$$\displaystyle\lim_{x \to 1}{f(x)}$$
- \$$\displaystyle\lim_{x \to 2}{f(x)}$$


Exercise 4
{:.exercise-label}

For the function $$f(x)=\dfrac{x+7}{x^2+9x+14}$$, evaluate the following limits.

- \$$\displaystyle\lim_{x \to 0}{f(x)}$$
- \$$\displaystyle\lim_{x \to 3}{f(x)}$$
- \$$\displaystyle\lim_{x \to 4}{f(x)}$$
- \$$\displaystyle\lim_{x \to 7}{f(x)}$$


Exercise 5
{:.exercise-label}

At which points is the following function discontinuous?

<div class="jsxgraph mx-auto" id="jxg_p5" style="width:400px; height:200px;">
  <noscript>Graph requires JavaScript to display.</noscript>
</div>
<script>
{
  let boardOpts = {
    boundingbox: [-2,4,8,-1]
  };
  let b = JXG.JSXGraph.initBoard('jxg_p5',boardOpts);
  b.create('spline',[[-2,-1,-0.5,0],[0,2,1.5,3]]);
  b.create('spline',[[0,0.5,1,2,2.5,2.8],[3,2,2.5,1.5,1,5]]);
  b.create('functiongraph', [(x)=>-Math.pow(x-4,2)+2,3,5]);
  b.create('functiongraph', [(x)=>-Math.pow(1.6,x-5)+3,5,9]);

  let op = [[1,2.5],[5,2]];
  op.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.07,p[1]+0.07]],{fillColor:'white'});
  });

  let cp = [[-1,2],[0,3],[2,1.5],[3,1],[5,1]];
  cp.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.07,p[1]+0.07]],{fillColor:'blue'});
  });
}
</script>


Exercise 6
{:.exercise-label}

At which points is the following function discontinuous?

<div class="jsxgraph mx-auto" id="jxg_p6" style="width:300px; height:200px;">
  <noscript>Graph requires JavaScript to display.</noscript>
</div>
<script>
{
  let b = JXG.JSXGraph.initBoard('jxg_p6',{boundingbox: [-2,4,4,-1]});
  b.create('functiongraph', [(x)=>-Math.cbrt(x+1)+2,-2,2]);
  b.create('functiongraph', [(x)=>-Math.pow(x-2,2)+3,2,3]);
  b.create('functiongraph', [(x)=>-Math.pow(x-4,2)+3,3,4]);
  b.create('functiongraph', [(x)=>-x+7,4,6]);


  let op = [[0,1],[2,-Math.cbrt(3)+2],[2,3]];
  op.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.07,p[1]+0.07]],{fillColor:'white'});
  });

  let cp = [[-1,2],[2,2],[4,3]]
  cp.forEach(function(p) {
  	b.create('circle',[[p[0],p[1]],[p[0]+0.07,p[1]+0.07]],{fillColor:'blue'});
  });
}
</script>


Exercise 7
{:.exercise-label}

For each function, find at least one point where the function is discontinuous.
Identify which of the three conditions of continuity is/are violated at that point.

- {:.py-1} \$$f(x)=\dfrac{x+5}{x-3}$$
- {:.py-1} \$$f(x)=\dfrac{x^2+x-6}{x-2}$$
- {:.py-1} \$$f(x)=\dfrac{x}{x}$$
- {:.py-1} \$$f(x)=\dfrac{\pi}{x^2-6x+9}$$
- {:.py-1} \$$f(x)=\ln(x^2)$$

<div class="end-matter" markdown="1">
Based on *[Applied Calculus](http://www.opentextbookstore.com/details.php?id=14)*, Chapter 2.1, by Calaway, Hoffman, and Lippman.<br>
[![license image](https://licensebuttons.net/l/by/4.0/80x15.png)][CC-BY-4.0] Licensed under [Creative Commons CC-BY-4.0][CC-BY-4.0].
</div>
[CC-BY-4.0]: https://creativecommons.org/licenses/by/4.0/