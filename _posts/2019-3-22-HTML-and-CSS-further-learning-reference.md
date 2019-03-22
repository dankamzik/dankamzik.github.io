
To start off with, lets look at the general type of boxes you will use in creating most HTML pages, including WordPress pages.
They are;
Block Boxes and Inline boxes.
Block Boxes: Are the main perimeter of a paragraph or content housing.
Inline Boxes: Are the innards of Block Boxes. They are the words, buttons, symbols, etc. that you place inside the block boxes.
In a wordpress stylesheet, you generally use css to manipulate Inline Boxes, because they contain your content.
So, for wordpress, there are different elements that you can call on to perform different tasks:
For example, in a wordpress stylesheet, you define the block boxes as <h1> and <p>, because they are the surrounding material around that section of content,
whereas the inline boxes would be defined as <em> and <strong> because these tags manipulate the content within the main Block Box.
Example:

```html

<!DOCTYPE html>
<html lang='en'>
  <head>
    <meta charset='UTF-8'/>
    <title>Boxes Are Easy!</title>
    <link rel='stylesheet' href='box-styles.css'/>
  </head>
  <body>
    <h1>Headings Are Block Elements</h1>

    <p>Paragraphs are blocks, too. <em>However</em>, &lt;em&gt; and &lt;strong&gt;
       elements are not. They are <strong>inline</strong> elements.</p>

    <p>Block elements define the flow of the HTML document, while inline elements
       do not.</p>
  </body>
</html>

```

So, from our html we would define the block box and inline box in the style sheet as such:
Example:

```css

h1, p {
  background-color: #DDE0E3;    /* Light gray */
}

em, strong {
  background-color: #B2D6FF;    /* Light blue */
}

```

To define the parameters for a block element, use the property "display"
Example:
```css

em, strong {
  background-color: #B2D6FF;
  display: block;
}

```
___________________________________________________________________________________________________________________________
CONTENT, BORDER, PADDING AND MARGIN
___________________________________________________________________________________________________________________________

The “CSS box model” is a set of rules that determine the dimensions of every element in a web page. It gives each box (both inline and block) four properties:

    Content – The text, image, or other media content in the element.
    Padding – The space between the box’s content and its border.
    Border – The line between the box’s padding and margin.
    Margin – The space between the box and surrounding boxes.

________
PADDING:
--------
Let’s start from the inside out.
You define padding as such:
Example:

h1 {
  padding: 50px;
}

This adds 50 pixels to each side of the <h1> heading. Notice how the background color expands to fill this space.
That’s always the case for padding because it’s inside the border, and everything inside the border gets a background.

You can use traditional css tags as well to get into more detail:
Example:

p {
  padding-top: 20px;
  padding-bottom: 20px;
  padding-left: 10px;
  padding-right: 10px;
}
________
BORDERS:
--------
Continuing our journey outward from the center of the CSS box model, we have the border:
a line drawn around the content and padding of an element. The border property requires a new syntax that we’ve never seen before.
First, we define the stroke width of the border, then its style, followed by its color.
Example:

h1 {
  padding: 50px;
  border: 1px solid #5D6063;
}

Like padding, there are -top, -bottom, -left, and -right variants for the border property
Borders are common design elements, but they’re also invaluable for debugging. When you’re not sure how a box is being rendered, add a border: 1px solid red; declaration to it.
This will clearly show the box’s padding, margin, and overall dimensions with just a single line of CSS.
After you figured out why your stuff is broken, simply delete the rule.

_______
MARGINS
-------
Margins define the space outside of an element’s border. Or, rather, the space between a box and its surrounding boxes.
Let’s add some space to the bottom of each <p> element:
Example:

p {
  padding: 20px 0 20px 10px;
  margin-bottom: 50px;          /* Add this */
}

Margins and padding can accomplish the same thing in a lot of situations, making it difficult to determine which one is the “right” choice. The most common reasons why you would pick one over the other are:

    The padding of a box has a background, while margins are always transparent.
    Padding is included in the click area of an element, while margins aren’t.
    Margins collapse vertically, while padding doesn’t (we’ll discuss this more in the next section).

VERTICAL MARGIN COLLAPSE:
Another quirk of the CSS box model is the “vertical margin collapse”.
When you have two boxes with vertical margins sitting right next to each other, they will collapse.
Instead of adding the margins together like you might expect, only the biggest one is displayed.
For example, let’s add a top margin of 25 pixels to our <p> element:
Example:

p {
  padding: 20px 0 20px 10px;

  margin-top: 25px;
  margin-bottom: 50px;
}

Each paragraph should have 50 pixels on the bottom, and 25 pixels on the top. That’s 75 pixels between our <p> elements, right? Wrong!
There’s still only going to be 50px between them because the smaller top margin collapses into the bigger bottom one.

PREVENTING MARGIN COLLAPSE:
Sometimes you do want to prevent the margins from collapsing. All you need to do is put another invisible element in between them:
Example:

<p>Paragraphs are blocks, too. <em>However</em>, &lt;em&gt; and &lt;strong&gt;
elements are not. They are <strong>inline</strong> elements.</p>

<div style='padding-top: 1px'></div>  <!-- Add this -->

<p>Block elements define the flow of the HTML document, while inline elements
do not.</p>

The important part here is that only consecutive elements can collapse into each other.
Putting an element with non-zero height (hence the padding-top) between our paragraphs forces them to display both the 25px top margin and the 50px bottom margin.

______________
GENERIC BOXES:
--------------

there are many times when we need a generic box purely for the sake of styling a web page. This is what <div> and <span> are for.
For now, let’s create a simple button by adding the following to the bottom of our boxes.html file:
Example:

<div>Button</div>

And here are the associated styles that need to go into box-styles.css.
Example:

div {
  color: #FFF;
  background-color: #5995DA;
  font-weight: bold;
  padding: 20px;
  text-align: center;
  border: 2px solid #5D6063;
  border-radius: 5px;
}

This will give us a big blue button that spans the entire width of the browser.

____________________
EXPLICIT DIMENSIONS:
--------------------

So far, we’ve let our HTML elements define their dimensions automatically.
The paddings, borders, and margins we’ve been playing with all wrap around whatever content happens to be inside the element’s box.
But, sometimes our desired layout calls for an explicit dimension, like a sidebar that’s exactly 250 pixels wide.
For this, CSS provides the width and height properties. These take precedence over the default size of a box’s content.
Example:

div {
  /* [Existing Declarations] */
  width: 200px;
}

Instead of being as wide as the browser window, our button is now 200 pixels, and it hugs the left side of the page.
Also notice that if you make the button’s title longer, it will automatically wrap to the next line, and the element will expand vertically to accommodate the new content.
You can change this default behavior with the white-space and overflow properties.

_______________________________
CONTENT BOXES AND BORDER BOXES:
-------------------------------

The width and height properties only define the size of a box’s content. Its padding and border are both added on top of whatever explicit dimensions you set.
This explains why you’ll get an image that’s 244 pixels wide when you take a screenshot of our button, despite the fact that it has a width: 200px declaration attached to it.
Fortunately, CSS lets you change how the width of a box is calculated via the box-sizing property.
By default, it has a value of content-box, which leads to the behavior described above.
Let’s see what happens when we change it to border-box:
Example:

div {
  color: #FFF;
  background-color: #5995DA;
  font-weight: bold;
  padding: 20px;
  text-align: center;
  border: 2px solid #5D6063;
  border-radius: 5px;

  width: 200px;
  box-sizing: border-box;  /* Add this */
}

_______________
ALIGNING BOXES:
---------------

We already saw the text-align property, which aligns the content and inline boxes inside of a block-level element.
Aligning block boxes is another story.
Try adding the following rule to our stylesheet.
It will only align the content inside of our block boxes—not the blocks themselves.
Our <div> button is still left-aligned regardless of the <body>’s text alignment:
Example:
body {
  text-align: center;
}

There are three methods for horizontally aligning block-level elements:
“auto-margins” for center alignment,
“floats” for left/right alignment, and
“flexbox” for complete control over alignment.
we can center our button with the following:
Example:
div {
  color: #FFF;
  background-color: #4A90E2;
  font-weight: bold;
  padding: 20px;
  text-align: center;

  width: 200px;
  box-sizing: border-box;
  margin: 20px auto; /* Vertical  Horizontal */
}

_________________
RESETTING STYLES:
-----------------

Different browsers have different default styles for all of their HTML elements, making it difficult to create consistent stylesheets.
It’s usually a good idea to override default styles to a predictable value using the “universal” CSS selector (*).
Try adding this to the top of our box-styles.css file:
Example:
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

_______
FLOATS:
-------

“Floats” let you put block-level elements side-by-side instead of on top of each other.
Instead of working with proper HTML content as we have been in previous chapters, we’ll be styling a bunch of empty <div> elements.
First, create a new folder called floats, then add a new web page called floats.html with the following markup:
*ALL MARKUP DISPLAYED ON "floats.html" PAGE*

This gives us the basic structure for most websites on the Internet. We have a place to put a navigation menu, a sidebar, the main content of the page, and a footer.
Think of all these as container divs that you can put your actual HTML content into.
You won’t see much when you open floats.html in a browser because empty elements have zero height. We’ll fix this in the next section.

Also be sure to create a styles.css stylesheet that resets default box behavior, as shown below:
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

_____________________________
DEFAULT HTML LAYOUT BEHAVIOR:
-----------------------------
Floats alter the default layout of a web page, so we should probably start by reviewing what exactly that “default” behavior is.
We introduced this in block elements versus inline elements, but it’s about to become much more important.
We can get a better look at our example page by adding some background colors and explicit heights to each of our <div> elements.
Add this to styles.css:
.menu {
  height: 100px;
  background-color: #B2D6FF;    /* Medium blue */
}

.sidebar {
  height: 300px;
  background-color: #F09A9D;    /* Red */
}

.content {
  height: 500px;
  background-color: #F5CF8E;    /* Yellow */
}

.footer {
  height: 200px;
  background-color: #D6E9FE;    /* Light blue */
}

It’s worth taking a look at what happens when we shrink an element’s width.
Update our .sidebar rule to match the following:

.sidebar {
  width: 200px;                 /* Add this */
  height: 300px;
  background-color: #F09A9D;
}

The sidebar element gets narrower, but the rest of the boxes stay in the exact same position.
All the blocks are still rendered vertically one after another.
This is the behavior we’ll be changing with floats.

____________________
FLOATING AN ELEMENT:
--------------------

The CSS float property gives us control over the horizontal position of an element.
By “floating” the sidebar to the left, we’re telling the browser to align it to the left side of the page.
Go ahead and float our sidebar with the following line:

.sidebar {
  float: left;                  /* Add this */
  width: 200px;
  height: 300px;
  background-color: #F09A9D;
}

However, this doesn’t just align the sidebar—it also tells surrounding elements that they can flow around the sidebar instead of beginning underneath it.
This gives us a magazine-style layout.
if you’re overriding a float declaration, you can cancel it with the none value. These are the most common values for the float property.

float: right;  /* Right-aligned */
float: none;   /* Revert to default flow */

We now have all the tools necessary to align block-level elements: floats for left/right alignment and auto-margins for center alignment.
Remember that this only applies to block boxes.
Inline boxes are aligned with the text-align property.

___________________________
FLOATING INSIDE OF PARENTS:
---------------------------
Floated boxes always align to the left or right of their parent element. In our example, the sidebar’s parent is <div class='page'>, which is as wide as the browser window.
This is why our sidebar floats to the far left of the page.
Let’s change this by giving our page a fixed-width layout. Once again, the auto-margin centering technique comes in handy. Add this to styles.css:

.page {
  width: 900px;
  margin: 0 auto;
}

Now, we can see that .sidebar floats to the left of the .page container, opposed to the edge of the browser window.
Here, we started with .page to center everything, then we left-aligned a sidebar inside that centered page.
Things can get way more complex, but our simple example demonstrates the universal truth of CSS layouts: everything is a box inside of a box inside of another box.

________________
MULTIPLE FLOATS:
----------------

Let’s examine our current magazine-style float a little bit more by adding an explicit width to our .content block:

.content {
  width: 650px;                 /* Add this */
  height: 500px;
  background-color: #F5CF8E;
}

This clearly demonstrates that our sidebar is in fact inside the .content block:
if you take a screenshot of them, you’ll have an image that’s 650 pixels wide opposed to 850 pixels (our sidebar is 200 pixels wide).

______________
AFTER A FLOAT:
--------------

You probably noticed that our footer shows up in the top right, directly below .menu. That’s because floated boxes are removed from the normal flow of the page.
The height of our floated elements don’t contribute to the vertical position of the footer, so it simply sticks itself below the last element that wasn’t floated.
We can see this more clearly by adding a red border around our .page element:

.page {
  width: 900px;
  margin: 0 auto;
  border: 1px solid red;  /* Add this */
}

Notice how the border is only around the .menu and .footer elements.
It’s as if the floated elements weren’t even there.
There are two ways to fix this: clearing a float and hiding overflow.

CLEARING FLOATS:
“Clearing” a float is when we tell a block to ignore any floats that appear before it.
Instead of flowing around the floated box, a cleared element always appears after any floats.
It’s like forcing a box back into the default vertical flow of the page.

We can use the clear property to make our .footer drop down to the bottom of the page:

.footer {
  clear: both;            /* Add this */
  height: 200px;
  background-color: #D6E9FE;
}

Usually, you want to clear both left and right floats as we did here, but you can choose to clear only one or the other with the left or right values.
Note that the red border now wraps all the way around the footer, indicating that the floated elements indeed count towards the height of the .page container.
we’re going to explore float behavior more by transforming our page into a full-bleed layout that has background colors filling the entire browser window.

Watch what happens when we take the menu and footer out of the .page element. Change the <body> element to match the following:

<body>
  <div class='menu'>Menu</div>

  <div class='page'>
    <div class='sidebar'>Sidebar</div>
    <div class='content'>Content</div>
  </div>

  <div class='footer'>Footer</div>
</body>

HIDING OVERFLOW:
Clearing floats only fixes the height issue when there’s an element inside the container element that we can add a clear property to.
Now that our footer is outside .page, we need a new way to make floated elements contribute to the height of their container.

By adding an overflow: hidden declaration to a container div, we’re telling it to recognize the height of any floated elements it contains.
This is how we can add a background color to our .page element and have it actually render:

.page {
  width: 900px;
  margin: 0 auto;
  overflow: hidden;             /* Add this */
  background-color: #EAEDF0;    /* Add this */
}

You should now be able to see a light gray background in .page instead of the default white.
The important part here is the behavior of overflow: hidden.
Without it, we wouldn’t be able to see the .page container’s background because it would have zero height.

SUMMARY OF CLEARING FLOATS AND HIDING OVERFLOW:

When you have an extra unfloated HTML element at the bottom of a container div, use the clear solution.
Otherwise, add an overflow: hidden declaration to the container element.
The underlying idea for both options is that you need a way to tell the browser to incorporate floats
into the height of their container element in order for their backgrounds to show up.

___________________
FULL BLEED LAYOUTS:
-------------------

Next, we want to make our .page background fill the entire browser window without changing the alignment of our sidebar or content blocks.
The problem is, our .page is busy centering everything—we can’t use it for a full-bleed background because centering requires an explicit width property.

It’s time for another container div. Putting a box around .page lets it continue centering stuff while giving us a place to define a background-color property.
Change our <body> element to match the following:

<body>
  <div class='menu'>Menu</div>

  <div class='container'>                 <!-- Add this -->
    <div class='page'>
      <div class='sidebar'>Sidebar</div>
      <div class='content'>Content</div>
    </div>
  </div>                                  <!-- Add this -->

  <div class='footer'>Footer</div>
</body>

Remember that the default block-rendering behavior is for elements to fill the width of their container. So, we should be able to move our background-color declaration to a .container rule to get a full-bleed background:

.page {
  width: 900px;
  margin: 0 auto;
}

.container {
  overflow: hidden;
  background-color: #EAEDF0;
}
This gives us three nested <div> elements just for laying out our page:
a .container wrapper for full-bleed background color,
a fixed-width .page for centering everything,
and finally left-aligned .sidebar and .content blocks.
This kind of nesting and aligning is pretty typical of most website layouts.

_______________________________
FLOATS FOR EQUAL WIDTH COLUMNS:
-------------------------------

Floats can also be used to create multi-column layouts. This works just like our .sidebar and .content floats—we just have more of them.

Next we’re going to add three equal-width columns to our footer. Update the <footer> element, like so:

<div class='footer'>
  <div class='column'></div>
  <div class='column'></div>
  <div class='column'></div>
</div>

We can style each of these columns just like we laid out the rest of our page. Add a new rule to styles.css:

.column {
  float: left;
  width: 31%;
  margin: 20px 1.15%;
  height: 160px;
  background-color: #B2D6FF;    /* Medium blue */
}

This is the first time we’ve used percentage values instead of explicit pixel values.
Percentages in CSS are relative to the width of the parent element.
The result is three columns that automatically resize to one-third of the browser window.
Resize the browser window, and you’ll see our columns grow and shrink accordingly.

_________________
FLOATS FOR GRIDS:
-----------------

Want a grid in the footer instead of 3 columns? No problem!
When there isn’t enough room to stack a floated element horizontally, it pops down to the next line.
All we need to do is add some more .column elements:

<div class='footer'>
  <div class='column'></div>
  <div class='column'></div>
  <div class='column'></div>
  <div class='column'></div>
  <div class='column'></div>
  <div class='column'></div>
</div>

Let’s replace the footer’s explicit height with another overflow: hidden so it can accommodate any number of grid items:

.footer {
  overflow: hidden;
  background-color: #D6E9FE;
}
 ___________________
 FLOATS FOR CONTENT:
 -------------------

 Let’s add some dummy content to our .content element so we have something to play with:

<div class='container'>
  <div class='page'>
    <div class='sidebar'></div>
    <div class='content'>

      <img src='?' class='article-image'/>

      <p>Ad netus sagittis velit orci est non ut urna taciti metus donec magnis
      hendrerit adipiscing mauris sit a proin ultrices nibh.</p>

      <p>Enim suspendisse ac scelerisque nascetur vestibulum parturient sed mi a
      dolor eu non adipiscing non neque scelerisque netus ullamcorper sed
      parturient integer.Eros dui risus non sodales ullamcorper libero a dis
      cubilia a orci iaculis cursus.</p>

      <p>Egestas at aliquam a egestas accumsan cum elementum consectetur conubia
      tristique eu et vitae condimentum in ante consectetur suscipit a a duis
      vestibulum gravida morbi sagittis.Parturient scelerisque facilisis
      ullamcorper a a pretium a nisl parturient semper senectus accumsan ipsum
      mus scelerisque eget ridiculus.Accumsan dolor a.</p>

      <p>Ligula taciti vel primis sit a tincidunt habitant parturient parturient
      in parturient ante nulla consectetur sem.Facilisis parturient litora.</p>

    </div>
  </div>
</div>

We’ve got an image and several paragraphs that we can style just like our structural divs. For example, let’s create a magazine-style layout by floating the image and letting the text flow around it. Add a couple more rules to our stylesheet:

.content {
  padding: 20px;
}

.article-image {
  float: left;
  width: 300px;
  height: 200px;
  margin-right: 20px;
  margin-bottom: 20px;
}

p {
  margin-bottom: 20px;
}

Notice how we have a float inside of a float, and everything works just fine.
Laying out a website is a recursive process: you build a high-level structure to work in, then you fill it with your actual content.
More complex layouts may need another layer or two of nesting, but the idea is the same.

____________________________
HIDING OVERFLOW FOR CONTENT:
----------------------------

Lets consider a basic user-comment thread. You have an image that’s floated left (avatar, profile pic, etc.) with a heading and some text next to it.
Let’s try creating this in our footer. In your favorite .column element, add the following:

<div class='column'>
  <div class='avatar'></div>
  <h3 class='username'>Bob Smith</h3>
  <p class='comment'>Aptent vel egestas vestibulum aliquam ullamcorper volutpat
  ullamcorper pharetra hac posuere a rhoncus purus molestie torquent. Scelerisque
  purus cursus dictum ornare a phasellus. A augue venenatis adipiscing.</p>
</div>

Let’s try creating this in our footer. In your favorite .column element, add the following:

<div class='column'>
  <div class='avatar'></div>
  <h3 class='username'>Bob Smith</h3>
  <p class='comment'>Aptent vel egestas vestibulum aliquam ullamcorper volutpat
  ullamcorper pharetra hac posuere a rhoncus purus molestie torquent. Scelerisque
  purus cursus dictum ornare a phasellus. A augue venenatis adipiscing.</p>
</div>

And the corresponding CSS rules:

.avatar {
  float: left;
  width: 60px;
  height: 60px;
  margin: 25px;
  border-radius: 40px;
  background-color: #D6E9FE;
}

.username {
  margin-top: 30px;
}

.comment {
  margin: 10px;
  overflow: hidden;  /* This is important */
}

__________________
RESPONSIVE DESIGN:
------------------

“Responsive design” refers to the idea that your website should display equally well in everything from
widescreen monitors to mobile phones. It’s an approach to web design and development that eliminates the distinction
between the mobile-friendly version of your website and its desktop counterpart. With responsive design, they’re the same thing.

/* FOR MOBILE DESIGN LAYOUTS AND EXAMPLES, REFER TO THE EXERCISE "responsive design" SAVED WITHIN htdocs/responsive-design */

Media queries always begin with the @media “at-rule” followed by some kind of conditional statement, and then some curly braces.
Inside the curly braces, you put a bunch of ordinary CSS rules. The browser only pays attention to those rules if the condition is met.

the exact pixel values for the min-width and max-width parameters in a media query (collectively known as the “breakpoints”
for a responsive website) don’t actually matter. Our website doesn’t care about the specific device the user is on.
All it needs to know is that it should display a layout that looks pretty at 400 pixels wide (or whatever).

MOBILE FIRST DEVELOPMENT:

It’s always a good idea to start with the mobile layout and work your way up to the desktop version.
Desktop layouts are typically more complex than their mobile counterparts, and this “mobile-first”
approach maximizes the amount of CSS that you can reuse across your layouts.
Make sure to add your CSS rules above the @media rules we created earlier and below
the universal selector rule that resets our margins and padding!

TABLET LAYOUT:

The only difference between the mobile and tablet mockups is that the Sign Up and Feature sections form a 2×2 grid instead of a single column.

Flexbox makes this real easy. Simply adjust the widths of the flex items to be half the screen and flex-wrap will take care of the rest.
Of course, we only want this behavior to apply to tablet-sized screens, so it needs to go into an @media rule.
Again, it doesn’t matter what the exact width of the screen is;
this layout will fluidly respond to any width in the media query’s range.

DESKTOP LAYOUT:

We don’t want our web page to expand endlessly, so we’re going to give it a fixed width and center it with auto-margins.
As with tablet styles, this needs to go into a media query.

DISABLING VIEWPORT ZOOMING:

We’ve got one final task for making a responsive web page. Before responsive design was a thing,
mobile devices only had a desktop layout to work with. To cope with this, they zoomed out
to fit the entire desktop layout into the width of the screen, letting the user interact with it by zooming in when necessary.
This default behavior will prevent mobile devices from using our mobile layout, which is obviously very terrible.
To disable it, add the following element to the <head> of our document.
Just like <meta charset='UTF-8'/>
this is a CRITICAL ELEMENT that should be on EVERY SINGLE web page you create:

<meta name='viewport'
      content='width=device-width, initial-scale=1.0, maximum-scale=1.0' />

______________
CSS SELECTORS:
--------------

#header .callout { }

The above selectors look nearly identical, but have pretty different uses.
the top one has no space between "#header" and ".callout" while the bottom one does.
This small difference makes a huge difference in what it does.

Here is the "plain English" of "#header .callout":

    Select all elements with the class name callout that are decendents of the element with an ID of header.

Here is the "plain English" of "#header.callout":

        Select the element which has an ID of header and also a class name of callout.

The big point here is that you can target elements that have combinations of
classes and IDs by stringing those selectors together without spaces.

----------------------
ID and Class Selector:
----------------------
As we covered above, you can target elements by a combination of ID and class.

HTML: <h1 id="one" class="two">This Should Be Red</h1>

CSS:  #one.two { color: red; }

----------------------
Double Class Selector:
----------------------
Target an element that has all of multiple classes. Shown below with two classes, but not limited to two.

HTML: <h1 class="three four">Double Class</h1>

CSS: .three.four { color: red; }

----------
Multiples:
----------
We aren't limited to only two here, we can combine as many classes and IDs into a single selector as we want.

CSS: .snippet#header.code.red { color: red; }


----------------
The ID selector:
----------------
Ex:
  HTML: <div id="happy-cake"></div>

  CSS:  #happy-cake { }

ID selectors are the most powerful type of selector in terms of CSS specificity.
Meaning that they beat out other types of selectors and the styles defined within win.
That sounds good, but that's typically considered bad because
it's nice to have lower-specificity selectors that are easier to override when needed.

---------------
Class Selector:
---------------

Ex:
  HTML: <div class="module"></div>

  CSS:  .module { }

  Class selectors are your friend. They are probably the most useful and versatile selectors out there.
  In part because they are well supported in all browsers. In part because you can add multiple
  classes (just separated by a space) on HTML elements.
  In part because there are JavaScript things you can do specifically for manipulating classes.

-------------
Tag Selector:
-------------
Ex:
  HTML: <h2>Hi Dan</h2>

  CSS:  h2 { }

#header.callout {  }

Tag selectors are at their most useful when changing properties that are unique to that HTML element.
Like setting the list-style on a <ul> or tab-size on a <pre>. Also in reset stylesheets where you are
specifically trying to unset styles that browsers apply to certain elements.
Don't rely on them too much though. It's typically more useful to have a class
define styling that you can use on any HTML element.

-------------------
Attribute Selector:
-------------------
Ex:
  HTML: <div data-modal="open"></div>

  CSS:  [data-modal="open"] { }

  You might argue that attribute selectors are even more useful than classes because they have the same specificity value,
  but can be any attribute not just class, plus they can have a value you can select by.

---------------------
Positional Selectors:
---------------------
Ex:
  HTML: <ul>
        <li>nope</li>
        <li>yep, I'm #2</li>
        <li>nope</li>
        </ul>

  CSS: :nth-child(2) { }

There are several different positional selectors beyond :nth-child.
Using simple expressions (like 3n = "every third") you can select elements based on their position in the HTML.
You can play with that idea here or check out some useful recipes.

-----------------------
Other Pseudo Selectors:
-----------------------
Ex:
  HTML:   <div></div>

  CSS:    :empty { }

  :empty is one of many pseudo selectors, which you can recognize by the colon (:) in them.
  They typically represent something that you couldn't know by just the element and attributes alone.
  Note that these are slightly different than pseudo elements, which you can recognize by the double colon (::).
  They are responsible for adding things to the page by the things they select.


____________________
Combining Selectors:
--------------------

------------
The Cascade:
------------
Within CSS, all styles cascade from the top of a style sheet to the bottom, allowing different styles to be added or overwritten as the style sheet progresses.

For example, say we select all paragraph elements at the top of our style sheet and
set their background color to orange and their font size to 24 pixels. Then towards the bottom of our style sheet,
we select all paragraph elements again and set their background color to green, as seen here.

Ex:
  p {
  background: orange;
  font-size: 24px;
  }
  p {
  background: green;
  }

Because the paragraph selector that sets the background color to green comes after the paragraph selector
that sets the background color to orange, it will take precedence in the cascade.
All of the paragraphs will appear with a green background.
The font size will remain 24 pixels because the second paragraph selector didn’t identify a new font size.

________________________
Calculating Specificity:
------------------------
Every selector in CSS has a specificity weight.
A selector’s specificity weight, along with its placement in the cascade, identifies how its styles will be rendered.
The type selector has the lowest specificity weight and holds a point value of 0-0-1.
The class selector has a medium specificity weight and holds a point value of 0-1-0.
Lastly, the ID selector has a high specificity weight and holds a point value of 1-0-0.
As we can see, specificity points are calculated using three columns.
The first column counts ID selectors, the second column counts class selectors, and the third column counts type selectors.

What’s important to note here is that the ID selector has a higher
specificity weight than the class selector, and the class selector has a higher specificity weight than the type selector.

Ex:
  HTML: <p id="food">...</p>

  CSS:  #food {
         background: green;}
        p {
         background: orange;}

Here we have a paragraph element with an id attribute value of food.
Within our CSS, that paragraph is being selected by two different kinds of selectors: one type selector and one ID selector.
Although the type selector comes after the ID selector in the cascade,
the ID selector takes precedence over the type selector because it has a higher specificity weight;
consequently the paragraph will appear with a green background.

_______________
File Structure:
---------------

I know it seems pretty basic, but without proper file structure it is impossible to link out to pages from your website,
as well as link to different pages within your site.

The structure "../" tells the computer to go up a directory level when navigating to a folder.
This is especially useful when linking to different pages within your website.

_________________
Horizontal Rules:
-----------------

Horizontal rules, displayed as <hr> in tag form, are useful bits of code that allow for more concise structuring of a page.
By placing a <hr> tag after an end of a section on a page, a horizontal line will be featured on your page, separating one section
from the next.

______________________________
Linking to places within page:
------------------------------

In order to link to a particular place on a webpage,  you need to assign the section yuo want to link to a unique id
using the <id="UNIQUE NAME"> tag.
Ex:
    <a href="#portfolio">Portfolio</a>

You can also link back to your home page (index.html) by placing a single forward slash (/) as the href value.
Ex:
    <a href="/">home</a>

______________
Email Linking:
--------------

You can create an email address that simply pops up in your form by using a basic tag.
Ex:
<section id="contact">
      <h2>Contact</h2>
      <p><strong>Email:</strong> <a href="mailto:coolvrexperience@gmail.com">coolvrexperience@gmail.com</a></p>

You can also add a phrase within the subject line in the email form by adding a bit more code:
Ex:
<section id="contact">
      <h2>Contact</h2>
      <p><strong>Email:</strong> <a href="mailto:coolvrexperience@gmail.com?subject:Hi There!">coolvrexperience@gmail.com</a></p>

______________
HTML Entities:
--------------

There are snippets of code that allow you to input symbols into your website. HTML supports a good range of symbols,
but they must be entered in  in the proper way.

Below I am going to put in a greater than and less than symbol in my heading.
Ex:
    <header>
      <h1>&lt;Experience&gt;</h1>
    </header>

Entities are especially useful for displaying snippets of code on a web page.
Ex:
    <pre>
      &lt;div&gt;
        This is a div...
        &lt;p&gt; This paragraph is nested &lt;/p&gt;
    &lt;/div&gt;
    </pre>
  The above will display the code in HTML format on a web page. Make note that the entire code snippet in housed within a <pre> tag.

  _______________________
  Commenting Within Code:
  -----------------------
   To comment: <!-- comments -->
   Anything inside those gt lt symbols is ignored by the browser.
   This is useful because we can comments out pieces of code in testing, rather than delete them altogether.

   SHORTCUT: Ctrl/

   ______________
   CSS:
   ______________

   The Universal Selector is a selector that applies a set of properties to the entire web page.
   It is expressed as * .
   Ex:
        *{
        margin: 0;
        padding: 0;
        color: red;
        }

  ____________________________
  Styling with Pseudo Classes:
  ----------------------------

  A pseudo class is designed to target a specific feature within a pre existing class.
  For example, you would use a pseudo class to chnage the color of a link on your site, before it has ever been clicked.
  You can then use another pseudo class to change the color once again after the button has been clicked.
  Ex:
      a:link{
        color: orange;
      }
      The above will change the color of an unclicked link on your website.

  Ex:
      a:visited{
        color: blue;
      }
      The above will change the color of your link on your site to blue, after it has been clicked.

  Ex:
      a:hover{
        color: green;
      }

    ________________
    Comments in CSS:
    ----------------

    Comments in CSS are styled as follows:

    /*COMMENT*/

    You can also comment out CSS rules in a stylesheet

    ==========================================================
    To target Specific Pages using CSS:
    ==========================================================
Sometimes when you make a change to something in a site, it will reflect that change universally through out all of the sites pages.
In order to target a specific page, you must find that page's specific id number called page-id. It can be found within the body tag
when using inspector mode.
The page id should be added to the beginning of your CSS.

Ex:

.page-id-829 div.page_title_wrapper{
padding-bottom: 30px;
}

====================================================================
Creating a 1/3 to 2/3 page layout in wordpress with Grandconf theme:
====================================================================

1.Nav to Edit Page section
2.Create a new content section, by sleecting the "+" sign at the top of the page
3.Select "Text Contained Content" section
4.Google WP shortcodes for 1/3 to 2/3 section layout. I already did, they are;  [one_third]other[/one_third]
										[two_third_last]test[/two_third_last]
5. Once you properly fill out one section of content and it is displaying exactly how you want it to, you can then use the code as a template and fill in
   the code with different content.

   Ex:

[one_third]<img src="/wp-content/uploads/crashcode.png"/>[/one_third]


[two_third_last]
<h2 class="ppb_title">Crashcode</h2>

<strong>We teach the skills you need to jumpstart your journey as a developer.</strong>

Our “Micro-Degree” is structured as 8-week courses plus an additional 2-weeks per course that you will dedicate to your final project with the help of your instructor, mentors, and classmates before presenting it to the Crashcode community. Our courses are offered at Beginner, Intermediate and Advanced levels and focus on the fundamentals of programming for the web, up to launching rich web applications. At Crashcode, you'll learn to solve problems with code, while applying industry best practices in a supportive, collaborative environment.

<a href="https://crashcode.com/">www.crashcode.com</a>

[/two_third_last]

====================================================================
Ordering Items on a page in WP:
====================================================================

Navigate to "toolset" within WP, then nav to "post type". Here you can select the post that you want to manipulate.
Then you can scroll down to "Sections to display when editing team members". Check off "Page Attributes".
Say, for instance, that you have a bunch of bios that need to go in a particular order on a "Team Member" page.
In WordPress, you can navigate to the page you want to manipulate, and on the right hand side will be an option for "Post Attributes".
In this box you can put a numerical value, which will be assigned to that particular post. The posts will then be ordered by
ascending or descending order, depending on which you select.
