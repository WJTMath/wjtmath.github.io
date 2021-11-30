---
title: '02: Functions and Graphing'
---

# {{ page.title | split: ':' | last }}

The natural world is full of relationships between quantities that change. When we see these relationships, it is natural for us to ask “If I know one quantity, can I then determine the other?” This establishes the idea of an input quantity, or independent variable, and a corresponding output quantity, or dependent variable. From this we get the notion of a functional relationship in which the output can be determined from the input.

For some quantities, like height and age, there are certainly relationships between these quantities. Given a specific person and any age, it is easy enough to determine their height, but if we tried to reverse that relationship and determine height from a given age, that would be problematic, since most people maintain the same height for many years.

A **function** is a rule for a relationship between an input, or independent, quantity and an output, or dependent, quantity in which each input value uniquely determines one output value.
We say “the output is a function of the input.”
{: .code-example }

<panel title="Example 1">
In the height and age example above, is height a function of age? Is age a function of height?

<label type="success">Solution</label>

In the height and age example above, it would be correct to say that height is a function of age, since each age uniquely determines a height. For example, on my 18th birthday, I had exactly one height of 69 inches.

However, age is not a function of height, since one height input might correspond with more than one output age. For example, for an input height of 70 inches, there is more than one output of age since I was 70 inches at the age of 20 and 21.
</panel>

----

## Function Notation

To simplify writing out expressions and equations involving functions, a simplified notation is often used. We also use descriptive variables to help us remember the meaning of the quantities in the problem.

Rather than write “height is a function of age”, we could use the descriptive variable h to represent height and we could use the descriptive variable a to represent age.

“height is a function of age” if we name the function f we write “h is f of a” or more simply h = f(a) we could instead name the function h and write h(a) which is read “h of a”

Remember we can use any variable to name the function; the notation h(a) shows us that h depends on a. The value “a” must be put into the function “h” to get a result. Be careful - the parentheses indicate that age is input into the function (Note: do not confuse these parentheses with multiplication!).

<panel title="Function Notation" icon="fa fa-book">
The notation output = f(input) defines a function named f. This would be read “output is f of input”
</panel>

<panel title="Example 2">
A function N = f(y) gives the number of police officers, N, in a town in year y. What does f(2005) = 300 tell us?

<label type="success">Solution</label>

When we read f(2005) = 300, we see the input quantity is 2005, which is a value for the input quantity of the function, the year (y). The output value is 300, the number of police officers (N), a value for the output quantity. Remember N=f(y). So this tells us that in the year 2005 there were 300 police officers in the town.
</panel>

### Tables as Functions

Functions can be represented in many ways: Words (as we did in the last few examples), tables of values, graphs, or formulas. Represented as a table, we are presented with a list of input and output values.

This table represents the age of children in years and their corresponding heights. While some tables show all the information we know about a function, this particular table represents just some of the data available for height and ages of children.

(input) a, age in years 5 5 6 7 8 9 10 (output) h, height inches 40 42 44 47 50 52 54

<panel title="Example 3">
Which of these tables define a function (if any)?

<label type="success">Solution</label>

The first and second tables define functions. In both, each input corresponds to exactly one output. The third table does not define a function since the input value of 5 corresponds with two different output values.
</panel>

===== Solving and Evaluating Functions =====

When we work with functions, there are two typical things we do: evaluate and solve. Evaluating a function is what we do when we know an input, and use the function to determine the corresponding output. Evaluating will always produce one result, since each input of a function corresponds to exactly one output.

Solving equations involving a function is what we do when we know an output, and use the function to determine the inputs that would produce that output. Solving a function could produce more than one solution, since different inputs can produce the same output.

<panel title="Example 4">
Using the table shown, where Q=g(n)

a) Evaluate g(3)

Evaluating g(3) (read: “g of 3”) means that we need to determine the output value, Q, of the function g given the input value of n=3. Looking at the table, we see the output corresponding to n=3 is Q=7, allowing us to conclude g(3) = 7.

b) Solve g(n) = 6

<label type="success">Solution</label>

Solving g(n) = 6 means we need to determine what input values, n, produce an output value of 6. Looking at the table we see there are two solutions: n = 2 and n = 4.

When we input 2 into the function g, our output is Q = 6

When we input 4 into the function g, our output is also Q = 6
</panel>

===== Graphs as Functions =====

Oftentimes a graph of a relationship can be used to define a function. By convention, graphs are typically created with the input quantity along the horizontal axis and the output quantity along the vertical.

<panel title="Example 5">
Which of these graphs defines a function \( y=f(x) \)?

<div class="grid">
  <div id="jxg_x5a" class="cell cell--4 jsxgraph" style="height:200px; min-width: 200px;"></div>
  <div id="jxg_x5b" class="cell cell--4 jsxgraph" style="height:200px; min-width: 200px;"></div>
  <div id="jxg_x5c" class="cell cell--4 jsxgraph" style="height:200px; min-width: 200px;"></div>
</div>
<script type="text/javascript">
var boardOpts = {
  boundingbox: [-5,5,5,-5],
  keepAspectRatio: true,
  axis: true,
  showCopyright:false
};
var strokeOpts = {
  strokeWidth: 2
};
var x5a = JXG.JSXGraph.initBoard('jxg_x5a',boardOpts);
var x5b = JXG.JSXGraph.initBoard('jxg_x5b',boardOpts);
var x5c = JXG.JSXGraph.initBoard('jxg_x5c',boardOpts);

x5a.create('functiongraph',[function(x){return (x+2)*(x-1)*(x+1);}],strokeOpts);
x5b.create('line',[[0,0],[1,1]]);
x5c.create('circle',[[0,0],[3,0]]);
</script>
 
<label type="success">Solution</label>

The first two graphs define a function \( y=f(x) \). For each defined input value along the horizontal axis there is exactly one corresponding output value along the vertical axis. The third graph does not define a function \( y=f(x) \). Some input values, such as \( x=2 \), correspond with multiple output values.
</panel>

<panel title="Definition: Vertical Line Test" icon="fa fa-book">
The **vertical line test** is a handy way to think about whether a graph defines the vertical output as a function of the horizontal input. Imagine drawing vertical lines through the graph. If any vertical line would cross the graph more than once, then the graph does //not// represent a function, since there are multiple outputs values for that input value.
</panel>

Evaluating a function using a graph requires taking the given input and using the graph to look up the corresponding output. Solving a function equation using a graph requires taking the given output and looking on the graph to determine the corresponding input(s).

<panel title="Example 6">
Given the graph below, evaluate \( f(2) \) and solve \( f(x) = 4 \).

<label type="success">Solution</label>

To evaluate \( f(2) \), find the input \( x=2 \) on the horizontal axis. Follow from there up to the graph. This matches with one point: \( (2,1) \), which is an output of \( y=1 \).  This means tht \( f(2) = 1 \).

To solve \( f(x) = 4 \), find the ouput \( y=4 \) on the vertical axis. Follow from there across to tghe graph. This matches with two points: \( (-1,4) \) and \( (3,4) \). This means that there are two solutions to \( f(x) = 4 \): \( x = -1 \) or \( x = 3 \). At //both// of these input values, the output value is 4.
</panel>

Notice that while the graph in the previous example is a function, getting two input values for the output value of 4 shows us that this function is not one-to-one. **TODO: IS ONE-TO-ONE DEFINED ELSEWHERE?**

### Formulas as Functions

 When possible, it is very convenient to define relationships using formulas. If it is possible to express the output as a formula involving the input quantity, then we can define a function.

<panel title="Example 7">
Express the relationship 2n + 6p = 12 as a function p = f(n) if possible.

<label type="success">Solution</label>

To express the relationship in this form, we need to be able to write the relationship where p is a function of n, which means writing it as p = [something involving n].

2n + 6p = 12 subtract 2n from both sides 6p = 12 - 2n divide both sides by 6 and simplify

Having rewritten the formula as p=, we can now express p as a function:
</panel>

Not every relationship can be expressed as a function with a formula.

As with tables and graphs, it is common to evaluate and solve functions involving formulas. Evaluating will require replacing the input variable in the formula with the value provided and calculating. Solving will require replacing the output variable in the formula with the value provided, and solving for the input(s) that would produce that output.

<panel title="Example 8">
Given the function a) Evaluate k(2) b) Solve k(t) = 1

<label type="success">Solution</label>

a) To evaluate k(2), we plug in the input value 2 into the formula wherever we see the input variable t, then simplify

So k(2) = 10

b) To solve k(t) = 1, we set the formula for k(t) equal to 1, and solve for the input value that will produce that output k(t) = 1 substitute the original formula subtract 2 from each side take the cube root of each side

When solving an equation using formulas, you can check your answer by using your solution in the original equation to see if your calculated answer is correct.

We want to know if is true when .

=

=  1 which was the desired result.
</panel>

## Basic Toolkit Functions

There are some basic functions that it is helpful to know the name and shape of. We call these the basic "toolkit of functions." For these definitions we will use x as the input variable and f(x) as the output variable.

Toolkit Functions Linear Constant: , where c is a constant (number) Identity:

Absolute Value:

Power Quadratic: Cubic:

Reciprocal:

Reciprocal squared: Square root: Cube root:

===== Graphs of the Toolkit Functions =====

Constant Function: Identity: Absolute Value:

Quadratic: Cubic: Square root:

Cube root: Reciprocal: Reciprocal squared:

One of our main goals in mathematics is to model the real world with mathematical functions. In doing so, it is important to keep in mind the limitations of those models we create.

This table shows a relationship between circumference and height of a tree as it grows.

Circumference, c 1.7 2.5 5.5 8.2 13.7 Height, h 24.5 31 45.2 54.6 92.1

While there is a strong relationship between the two, it would certainly be ridiculous to talk about a tree with a circumference of -3 feet, or a height of 3000 feet. When we identify limitations on the inputs and outputs of a function, we are determining the domain and range of the function.

<panel title="Definition: Domain and Range" icon="fa fa-book">
Domain: The set of possible input values to a function \\
Range: The set of possible output values of a function
</panel>

<panel title="Example 9">
Using the tree table above, determine a reasonable domain and range.

<label type="success">Solution</label>

We could combine the data provided with our own experiences and reason to approximate the domain and range of the function h = f©. For the domain, possible values for the input circumference c, it doesn’t make sense to have negative values, so c > 0. We could make an educated guess at a maximum reasonable value, or look up that the maximum circumference measured is about 119 feet. With this information we would say a reasonable domain is feet.

Similarly for the range, it doesn’t make sense to have negative heights, and the maximum height of a tree could be looked up to be 379 feet, so a reasonable range is feet.
</panel>

A more compact alternative to inequality notation is interval notation, in which intervals of values are referred to by the starting and ending values. Curved parentheses are used for “strictly less than,” and square brackets are used for “less than or equal to.” Since infinity is not a number, we can’t include it in the interval, so we always use curved parentheses with ∞ and -∞. The table below will help you see how inequalities correspond to interval notation:

Inequality Interval notation

(5, 10]

[5, 10)

(5, 10)

all real numbers

<panel title="Example 10">
Describe the intervals of values shown on the line graph below using set builder and interval notations.

TODO nummber line graph

<label type="success">Solution</label>

To describe the values, x, that lie in the intervals shown above we would say, “x is a real number greater than or equal to 1 and less than or equal to 3, or a real number greater than 5.”

As an inequality it is: In interval notation:
</panel>

<panel title="Example 11">
Find the domain of each function: a) b)

<label type="success">Solution</label>

a) Since we cannot take the square root of a negative number, we need the inside of the square root to be non-negative.

when  .


The domain of f(x) is .

b) We cannot divide by zero, so we need the denominator to be non-zero.

when x = 2, so we must exclude 2 from the domain.


The domain of g(x) is .
</panel>

# 1.1: Exercises

<label type="info">1.</label>
The amount of garbage, \( G \), produced by a city with population \( p \) is given by \( G = f(p) \). \( G \) is measured in tons per week and \( p \) is measured in thousands of people.
  * The town of Tola has a population of 40,000 people and produces 13 tons of garbage each week. Express this information in terms of the function \( f \).
  * Explain the meaning of the statement \( f(5) = 2 \).

<label type="info">2.</label>
The number of cubic yards of dirt, \( D \), needed to cover a garden with area \( a \) square feet is given by \( D = g(a) \).
  * A garden with area 5,000 square feet requires 50 cubic yards of dirt. Express this information in terms of the function \( g \).
  * Explain the meaning of the statement \( g(100) = 1 \).

<label type="info">3.</label>
Select all of the following graphs which represent \( y \) as a functions of \( x \).


<label type="info">4.</label>
Select all of the following graphs which represent \( y \) as a functions of \( x \).

<label type="info">5.</label>
Select all of the following tables which represent \( y \) as a functions of \( x \).

<label type="info">6.</label>
Select all of the following tables which represent \( y \) as a functions of \( x \).

<label type="info">7.</label>
Given the function graphed below:
  * Evaluate \( g(2) \).
  * Solve \( g(x) = 2 \).

GRAPH:e^.5x+2

<label type="info">8.</label>
Given the function graphed below:
  * Evaluate \( f(4) \).
  * Solve \( f(x) = 4 \).

GRAPH: h. reflect

<label type="info">9.</label>
Based on the table below:
  * Evaluate \( f(3) \).
  * Solve \( f(x) = 1 \).

TABLE

<label type="info">10.</label>
Based on the table below:
  * Evaluate \( f(8) \).
  * Solve \( f(x) = 7 \).

TABLE

<well>
For exercises 11--18, evalute \( f(-2) \), \( f(-1) \), \( f(0) \), \( f(1) \), and \( f(2) \).
</well>

<label type="info">11.</label>
\( f(x) = 4-2x \)

<label type="info">12.</label>
\( f(x) = 8-3x \)

<label type="info">13.</label>
\( f(x) = 8x^2-7x+3 \)

<label type="info">14.</label>
\( f(x) = 6x^2-7x+4 \)

<label type="info">15.</label>
\( f(x) = 3+\sqrt{x+3} \)

<label type="info">16.</label>
\( f(x) = 4-\sqrt[3]{x-2} \)

<label type="info">17.</label>
\( \displaystyle f(x) = \frac{x-3}{x+1} \)

<label type="info">18.</label>
\( \displaystyle f(x) = \frac{x-2}{x+2} \)

<label type="info">19.</label>


<label type="info">20.</label>


<label type="info">21.</label>


<label type="info">22.</label>


<label type="info">23.</label>
Write the domain and range of the relation's graph below in interval notation.

<label type="info">24.</label>
Write the domain and range of the relation's graph below in interval notation.

<well size="sm">
For exercises 25--30, write the domain of each function in interval notation.
</well>

<label type="info">25.</label>
\( f(x) = 3\sqrt{x-2} \)

<label type="info">26.</label>
\( f(x) = 5\sqrt{x+3} \)

<label type="info">27.</label>
\( \displaystyle f(x) = \frac{9}{x-6} \)

<label type="info">28.</label>
\( \displaystyle f(x) = \frac{6}{x-8} \)

<label type="info">29.</label>
\( \displaystyle f(x) = \frac{3x+1}{4x+2} \)

<label type="info">30.</label>
\( \displaystyle f(x) = \frac{5x+3}{4x+1} \)









5. Select all of the following tables which represent y as a function of x. a. x 5 10 15 y 3 8 14

b.    x    5    10    15


y 3 8 8

c.    x    5    10    10


y 3 8 14

6. Select all of the following tables which represent y as a function of x. a. x 2 6 13 y 3 10 10

b.    x    2    6    6


y 3 10 14

c.    x    2    6    13


y 3 10 14

7. Given the function graphed here, a. Evaluate b. Solve 8. Given the function graphed here. a. Evaluate b. Solve

9. Based on the table below, a. Evaluate b. Solve x 0 1 2 3 4 5 6 7 8 9

74 28 1 53 56 3 36 45 14 47

10. Based on the table below, a. Evaluate b. Solve x 0 1 2 3 4 5 6 7 8 9

62 8 7 38 86 73 70 39 75 34

For each of the following functions, evaluate: , , , , and 11. 12. 13. 14. 15. 16. 17. 18.

19. Let a. Evaluate b. Solve

20. Let a. Evaluate b. Solve

21. Using the graph shown, a. Evaluate b. Solve c. What are the coordinates of points L and K?

22. Match each graph with its equation. a. b. c. d. e. f. g. h.

Write the domain and range of each graph as an inequality. 23. 24. Find the domain of each function

25. 26.

27. 28.

29. 30.

# 1.1: Solutions


<accordion>
<panel title="Licenses and Attributions">
Based on //[[http://www.opentextbookstore.com/details.php?id=14|Applied Calculus]]//, Chapter 1.1, by Calaway, Hoffman, and Lippman. \\
</panel>
</accordion>