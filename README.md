# Basic-custom-CSS-grid-example

https://codepen.io/anon/pen/yvpLMO?editors=1100
A basic example of how I use custom grids as learned via the "Advanced CSS and Sass" course by Jonas Schmedtmann on Udemy. This is a great method to utilize over it's alternative, CSS grid due to it's low browser support. Feel free to take any of this code to use for yourself if you find it useful!

---[The HTML markup]---

-I first start out by creating a "div.grid-container". This can be anything you'd like (a section would be great too), just make sure the rows are grouped within one custom grid. This is important later on when we use the CSS selector "last-of-type" to remove vertical spacing on the bottom row of the grid system (Which is unecessary and makes for slightly sloppy work!).

-The rest is quite straightforward, have "div.row"s and "div.col"s inside them.

-As for naming the column classes, in this example I used "col-1-of-2" if I wanted the column to take up half the width of the row, "col-1-of-3" for a third the width, and so on. There are instances where you may want to have it take up 2/3rds instead, but I didn't show it here for simplicity's sake.

---[The CSS styling]---

-I included the clearfix mixin in the beginning so that the elements don't collapse as we're building up the grid.

-The 3 variables listed on lines 14-16 greatly affect the overall layout of your grid. I included comments on what each variable is for.

-Lines 26-31 are the boilerplate code for the grid rows. Keep in mind that flex isn't 100% supported yet. I just added that display property to keep all columns equal height with each other. 

-It gets slightly tricky when we begin calculating widths for columns starting at line 43. To simplify what's going on here, we first take the full width of the row (100%), and subtract one width of horizontal gutter. We subtract just one width of that because we expect there to be only 2 items in this row, so the only place where the gutter would go is in the middle. Then divide by 2 because we're expecting there to be 2 items. Same concept for the others.

-margin-right will always be declared as $gutter-horizontal. The last column will have a margin-right of 0 due to lines 38-39. This allows the columns to be spaced out properly.
