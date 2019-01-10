---
layout: post
title:  "CSS Notes"
date:   2019-01-09 10:38:00 -0400
categories: Digital Life
---

Daniel Kamzik

1/9/2019

Hello All,
I'v been wanting to do this for a while. I have tons of notes on HTML, CSS, JS, C++ and more that I will eventually house on this website. My goal is twofold; 1) to create a decent resource for anyone interested to learn from, right off my own website and 2) to have a digital copy of my notes that I can access with or without my personal computer.
So, here goes - CSS!

As a side note to any who may be reading, the below is a free manual on Cascading Style Sheets. The notes begin with CSS basics and progressively become more in depth as the sections build upon one another. Enjoy!

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

--------------
CSS SHORTHAND:
--------------
CSS shorthand is written in a clockwise or cardinal direction type manner.
Meaning: top, right, bottom, left

Example:

margin: 0px 0px 0px 0px;

Example:

border: 3px solid #f2f2f2
*the above would be width/style/color*

--------------
Display types:
--------------
The Css display types are:
none, block, inline, inline-block

Block elements:
stretch the full width of the container
behave as though there is a line break before and after the element
The full box model can be manipulated

Inline elements:
Typically found inside a Block element.
They do not take up the entire width of the container.
They do not generate a line break before or after the content.

Inline-block elements:
Only stretch the width of the container they are in
Have the same flow as an inline element but behave as a block element

---------------------
Horizontal Centering:
---------------------
Centering a block level element horizontally:
DONT USE PADDING TO CENTER, NON-RESPONSIVE
Instead, define a width, and the elements width must be less than that of it's parent container.
Then, use:

margin: 0, auto;
text-align: center;

--------------------
Basic CSS Animation:
--------------------

You dont need javascript to perform basic animations on a web page!
You can handle basic animations with HTML and CSS alone!
Below is an example of setting a profile picture, and upon hover, it grows larger and rotates 5 degrees:
  Example:

header .profile-image{
    margin-top:50px;
    width: 150px;
    height: 150px;
    border-radius: 50%;
    border: 3px solid white;
    transition: all .5s;
    }
header .profile-image:hover{
transform: scale(1.2) rotate(5deg);
}

---------------------------------
Creating more visible white text:
---------------------------------

Use a css element called "text-shadow" to create a shadow around your text in order to make it pop more.
You can go online a google "text-shadow generator" to easily and quickly find the code.

-------------
css selectors
-------------

:nth-child(A NUMBER) {
ATTRIBUTES
}

The above selector allows for an element to be selected by specifying which number in the div class/list/section etc. by inputting a number after
":nth-child". So, to select the second element down in a list, you input the number 2. Easy.

_________
Flex Box:
---------
Flex box is a way to lay out columns and rows in an easier way than pure css can muster. It consists of two axies;
the main (horizontal) axis and the cross axis (vertical).


Ex:
  .container{
  display: flex; /*this designates the container as a flex box*/
  height: 300px; /*dictates the height of the flex box*/
  }

/*the above will create a flex box out of the container we specified, however the items within the box dont take up the entire box,
leaving some awkward space to the right of the items. To fix this, see below*/

Ex:
  .container{
  display: inline-flex; /*this designates the container as a flex box and now will make the container conform to the inline items*/
  height: 300px; /*dictates the height of the flex box*/
  }

Flex Direction Property:
  Elements within a flex box are automatically laid out horizontally from left to right along the main axis.
  We can easily change the direction our elements are facing by using the "flex direction" property.
  Ex:
       .container{
       display: flex; /*this designates the container as a flex box*/
       height: 300px; /*dictates the height of the flex box*/
       flex-direction: row-reverse; /*this reverses the main axis direction, meaning your elements begin from right to left*/
       }

  Ex:
    .container{
    display: flex; /*this designates the container as a flex box*/
    height: 300px; /*dictates the height of the flex box*/
    flex-direction: column; /*this changes your standard row into a column. You can also use the "column-reverse"
                              property to reverse the order and direction of the column*/
    }

Flex Box Responsivity:

  In order to make our flexbox responsive, use the flex-wrap property.
   Ex:
     .container{
     display: flex; /*this designates the container as a flex box*/
     height: 300px; /*dictates the height of the flex box*/
     flex-wrap: wrap; /*when there isnt enough room on a screen for the flexbox, then it will wrap the items within the box along the main axis*/
     }

In adition to this, you can use percentages in defining your margin and/or padding. Ex: .div {padding: 18% 24%}, this percentage will always stay the same , regardless of whether you shrink the web page or enlarge it.

Justify Content:

  In order to make sure our flexbox elements are laid out proportionally, we use the "justify-content" property.
  The default justify content value is called "flex-start." This portions out your elements within the flexbox
  from the begining left hand side of the box itself and moves out from there. If I wanted my elements to begin from the end
  of the flexbox, I could use the "flex-end" value. If i wanted to center my elements within the flexbox I would sue the value "center".
  If you want you'r elements to be spaced out evenly within the flexbox, use the "space-around" value. To make your elements have equal
  space between them but begin at the far left and right of your flexbox, use the "space-between" value.  With "Space-evenly"
  items are distributed so that the spacing between any two items (and the space to the edges) is equal.

   Ex:
       .container{
       display: flex; /*this designates the container as a flex box*/
       height: 300px; /*dictates the height of the flex box*/
       justify-content: flex-start/flex-end/center/space-around/space-between;
     }

  You can also change out the spacing between individual elements within your flexbox by creating another css rule,
  and targeting the element in question.
    Ex:
        .container{
        display: flex; /*this designates the container as a flex box*/
        height: 300px; /*dictates the height of the flex box*/
        justify-content: flex-start/flex-end/center/space-around/space-between;
       }
         .element-1(name changes according to id){
          margin-right: auto; /*This will make your selected element hug the left of the box, and push all other elements to the extreme
                                other side. You can apply this to as many elements as you want. Very hand for creating a nav bar distributed
                                over one single row, but spaced out uniquely.*/
         }
______
Order:
______
  You can use the "order" property to change the order elements within a flexbox are...well...ordered.
  All you have to do is create a css rule that targets the element in question, then use the "order" property, then set the order value
  to wherever you want the element to be.
   Ex:
     .element-6(6 is just a random number){
      order: -1; /*This will bring the element number 6 to the first starting position within the flexbox. Because -1 is lower than 1, and we just assigned the -1 value to elemnt-6, it will appear first in the row.*/
     }

     Likewise, if I wanted a 1-value element to show up further down in a row or column, then I can assign it any value greater than 1.
     Keep in mind that the "order" property places elements in order RELATIVE to their assigned order values. So, if I assign any random
     element a, order: 1; value, and another an order: 2; value, regardless of the elements, the order:2; valued element will appear
     last in the row or column.
__________
Flex-Grow:
__________
  The flex-grow property determines the size of a selected element within it's flex container.
   Ex:
     .someelement{
     flex-grow: 1; /*This will give each item in a flexbox an equal size increase until there is no room left in the flex container*/
     }

     Say I wanted to make one element larger than another. I would select the emelent in question and then create a css rule that dictates
     the element in question as flex-grow:3/4/5; etc.
___________
Flex-basis:
___________
    The flex-basis property determines the point in which the elements within a flexbox begin to increase in size due to the flex-grow property.
      Ex:
        .someelement{
        flex-grow: 1;
        flex-basis: 200px; /*This will mean that the elements within the flexbox will expand to a 1:1 ratio, as soon as they dip below 200px
                             this is used for responsivity.*/
      }
_____________________
Lets talk about Flex:
_____________________

  Its is highly recommended that you use the "flex" shorthand to incorporate all of the above flex abilities. the property "flex" represents
  flex-grow, flex-basis and flex-shrink. So, when we use "flex" in a css rule, it acts the same as margin or padding shorthand.
   Ex:
     .someelement{
     flex: 1 _ _ ; /*This layout is ordered as flex grow, flex basis and then flex shrink*/
   }

________________________
Align-Items, Align-Self:
________________________

  The align-items property works only within a flex container (you'r flexbox). This will make the elements in the box stretch from the start of the
  cross axis to the end of the cross axis (vertical).
   Ex:
     .flexboxcontainer{
    display: flex:
    flex-wrap: wrap;
    height: 450px;
    align-items: stretch; /*makes elements stretch from the start of the cross axis to the end of the cross (vertical) axis*/
     }
if i want to align all elements to the start of the cross axis...
   Ex:
     .flexboxcontainer{
    display: flex:
    flex-wrap: wrap;
    height: 450px;
    align-items: flex-start; /*Makes the elements adhere to the top of the flex container*/

if i want to align all elements to the bottom of the cross axis...
   Ex:
          .flexboxcontainer{
         display: flex:
         flex-wrap: wrap;
         height: 450px;
         align-items: flex-end; /*Makes the elements adhere to the bottom of the flex container*/

if i wanted to center my elements along the cross axis...

    Ex:
      .flexboxcontainer{
     display: flex:
     flex-wrap: wrap;
     height: 450px;
     align-items: center; /*This centers all the elements along the cross axis*/

if i wanted to PERFECTLY CENTER an element within my flexbox so that it sits directly in the center of the entire box...
    Ex:
      .flexboxcontainer{
      display: flex;
      min-height: 50vh;
      justify-content: center;
      align-items: center;
      }
      .someelement{
      align-self: center;
      }

_______________________________
Building a Layout with Flexbox:
_______________________________

 1. define the flexbox container (css->display{flex;})
 2. it is often advantageous to beign designing around a mobile platfrom first, and then move to full scale
 3. add in your content and elements
 4. scale

_______________________________
Box Sizing with CSS:
_______________________________
 under your layout conventions, you can create a class called box-sizing and give it the property border-box.
 Ex:
   .primary-content{
      box-sizing: border-box;
   }

 This is pretty necessary to define when using pixels as measurement, so the computer doesnt think that the total width/height of your box includes the padding as well. Using border-box separates the padding from the content in terms of measurement.

_______________________________
The universal selector:
_______________________________

In CSS, there is a universal selector that when called applies a property to the entire page.
The universal selector is defined as *.
Ex:
  *{
  box-sizing: border-box;
  }

The universal selector is only good practice to be used on things that you definately want to apply to all elements in your page. The box-sizing property is a good example to use universally because you are more than likely to have the same sizing convention throughout a page.

_______________________________
The max-width property:
_______________________________

This property limits the larges size of a div or content housed insode a div, such as an image. This is helpful for larger screen sizes or when you are coding on a smaller screen.

_______________________________
Setting a background Image:
_______________________________

Ex:
  .main-header{
    background-image: url("../mountains.jpg")
    background-size: cover;
    background-repeat: no-repeat;
    background-position: center bottom;
  }

   There are ways to set an image behind your text, as the background for that content within a box, without using paralax.
   Use the background-image property. The above code will allow you to place an image behind whatever text content you have on your page.
   Sometimes the image you use for this can be too large or small. You can try to adjust the image size by using the background-size rule.
   Oftentimes an image will repeat if it's not big enough to take up the full space of the div's background. Use the background-repeat property to set the rule to no-repeat. Alternatively, if you want the image to take up the full width of the container, use the rule "cover".
   In order to position the image, use the background-position property. The first rule in the property sets the positioning on the x-axis, the second sets it for the y-axis. If you only have one rule for background-position, then it will follow that rule for the entire container. "Center" in this case would center the image directly in the middle of you r container. You can also use percentages in both x and y values to adjust marginally.

   _______________________________
   List style types:
   _______________________________

   You can change an ordered or unordered list's bullet function to lots of different styles by naming the list-style-type property.
   Ex:
     ul{
        list-style-type: square;
        border: 1px solid #000;
     }
The above code will display square bullets. You can change them to lower-roman or lower-greek types, decimal-leading-value or none, which does not disply the bullets at all. You can also create a table by placing a border within the ul class.

_______________________________
Font and Text Shadow:
_______________________________

You can drop in a shadow behind words using css.
  Ex:
      h1{
      text-shadow: -5px -8px #222;
      }

The first value is the vertical offset and the second is the horizontal offset; positve values move the shadow up while negative values move it down. You can add in a thrid pixel value, which creates a blur effect. The final value specifies shadow color. The color can be set to rgba (0, 0 , 0, .8), for more control over opacity. the keyword "inset" can also be used in the beginning of your box-shadow rules list to create a shadow inside the container, rather than around the outside.
You can even create 3D text by using text-shadow alone!

  Ex:
      h1 {
  text-shadow: 0 1px 0 #ccc,
               0 2px 0 #c9c9c9,
               0 3px 0 #bbb,
               0 4px 0 #b9b9b9,
               0 5px 0 #aaa,
               0 6px 1px rgba(0,0,0,.1),
               0 0 5px rgba(0,0,0,.1),
               0 1px 3px rgba(0,0,0,.3),
               0 3px 5px rgba(0,0,0,.2),
               0 5px 10px rgba(0,0,0,.25),
               0 10px 10px rgba(0,0,0,.2),
               0 20px 20px rgba(0,0,0,.15);
               }

Ex:
    h1 {
box-shadow: inset 0 1px 0 rgba (0, 0 , 0, .8);
}

_______________________________
Border Radius:
_______________________________
 Border-radius can be used to round off corners of a container. The shorthand version begins from the top left corner and continues clockwise.
  Ex:
      .image-card{
        border-radius: 50px 10px 50px 10px;

      }

  Any unit of measurement can also be used here, namely percentages are useful in dictation radus.

_______________________________
Gradients:
_______________________________

Gradients are aesthetic tools used to add a sweeping effect from one color to another. You set the rules of a color gradient as follows.
  Ex:
      .main-header{
        background-image: linear-gradient(#ffa949, firebrick );

      }

You can also change the order of the gradident by reversing the value placement or adding in the keywords "to top" "to left" or "to right". We can also use the "deg" keyword to set the graident as a degree value. A "0deg" would be te standard top to bottom gradient, 90deg would be left to right, etc.
    Ex:
      .main-header{
        background-image: linear-gradient( 45deg, #ffa949, firebrick );

      }

There are also radial gradients, which have a sort of sunburst effect. This gradient blooms outward from an ellipse.
  Ex:
      .main-header{
        background-image: radial-gradient(#ffa949, firebrick );

      }

Radial gradients too have keywords we can use to alter what we see. The keyword "circle" is used to create a more evenly spread gradient blooming out from a more perfect circle. You can still use the "at top" "at bottom" "at left" and "at right" keywords to reposition the pinnacle of the gradient.
  Ex:
      .main-header{
        background-image: radial-gradient( circle at top, #ffa949, firebrick);

      }

Gradients dont have to be limited to only two colors. Not only this, but you can specify using percentages how dominant each color is.
  Ex:
      .main-header{
        background-image: radial-gradient(#ffa949 60%, firebrick 40% );

      }

Images in CSS can mercifully be layered on top of one another as well. The image at the top of the rule list is going to be the top most layer, with any following images being layered underneith. We can layer a gradient on top of a background image like so.
    Ex:
      .main-header{
        background-image: linear-gradient(#ffa949, transparent 90% ),
                          #ffa949 url("../img/mountains.jpg") no-repeat center;

      }

_______________________________
Importing Web Fonts:
_______________________________
In any project, you should have a "font" folder. Place any fonts you plan on using into this folder, then use the @font-face query to import any fonts you want to bring into the project. This should be done at the top of the html page.
Ex:
  @font-face{
      font-fmaily: "abolition regular";

  }

There will also be a few lines of CSS code that contain different styles of "abolition regular" fonts. All you have to do is copy and paste this code right after the semi-colon.

In order to change the font of a particulare pert of the web page, you have to call the font-family rule.
Ex:
  h1,
  h2{
    font-family:"abolition regular", Helvetica, Arial, sans-serif;
  }

_______________________________
Responsiveness: Media Queries:
_______________________________
Media queries should go in their own section in the html code sheet, at the bottom. The first thing you need to do is set the rule using @media(). Remeber to not use a semi-colon after the first rule.
Ex:
    @media(max-width: 960px){
        body{
            backgorund: royalblue;
            }
}

@media(max-width: 480px){
    body{
    background: darkred;
    }
}

@media(min-width: 481px) and (max-width: 700px){
    body{
    background: seagreen;
    }
}

The above code will change background colors and font colors, depending on the viewport height.
To make a webpage responsive, see below.
Ex:
  @media(max-width: 1024px){
      .priamary-Content,
      .secondary-content{
          width: 90%;
      }
  }

    @media(max-width: 768px){
          .priamary-Content,
          .secondary-content{
              width: 100%;
              padding: 20px;
              border: none;
          }
          .main-header{
          max-height: 380px;
          padding: 50px 25px 0px;
          }
          .title{
          font-size: 1.3rem;
          border: none;
          }
          h1{
          font-size: 1rem;
          line-height: 1.1;
          }
          .arrow{
          display: none;
          }
          .intro{
          font-size: 1rem;
          }
      }

The above CSS code is imperitive to have because it defines your layout and when to intitiate the changes. However, we need to specify this to the computer. We do this by going to the top of our HTML page and creating a meta tag that looks liek this.
<meta name="viewport" content="width=max-width">

_______________________________
CSS Debugging Tips:
_______________________________

If you notice that there is a grey background in inspector mode, within the styles section, that means that the rule was generated by the UAS or User Agent Stylesheet. The uas is kind of like a preset for layout and stylistic choice.

The .cls function in inspector mode is useful for writing in new classes or pulling up all of the rules for a particular class. It acts as an enhanced search button.

The Sources tab in inspector mode is useful for copying chnaged code you made in inspector mode and putting it pack into your source file without having to make the changes twice.

XXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXXX

There you have it! The above is enough for anyone to become dangerous with CSS. I will be updating these notes with other tips, tricks and tutorials so keep an eye out.  
