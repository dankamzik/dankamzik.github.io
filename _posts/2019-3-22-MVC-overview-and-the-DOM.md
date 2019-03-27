//MVC Notes

What are MVC's?

MVC is an acronym that stands for Model View Controller.
Lets break that down for clarification:

Model: Structures your data in a reliable form and prepares it based on controller’s instructions
View: Displays data to user in easy-to-understand format, based on the user’s actions
Controller: Takes in user commands, sends commands to the model for data updates, sends instructions to view to update interface.

What do they do?

MVC's are frameworks for manipulating the DOM in a cleaner way. We manipulate the DOM by making a request to the computer. The controller takes that request, processes it using the model it has, and the view is the visible change you see on screen.

How do they work?

Lets make an analogy.
You walk into a bar and order a fuzzy naval.
You are acting as the user inputting a request from the bartender, who is acting as the computer.
The bartender's brain acts as the controller.
It breaks down the drink order into a series of steps:
1. Grab a glass
2. Add a ratio of vodka
3. Add a ratio of orange juice
4. Add ice
5. Receive payment

The bartender knows what to do so long as you ordered a drink in a language that they can understand. Supposing that you did and the bartender's brain was able to successfully process the order, the bartender now has to take inventory of the tools at their disposal to make your drink. Some tools the bartender has are:
1. His hands
2. Glasses
3. Liquors
4. Ice
5. Stirrers

Outside of these tools, the bartender has nothing to work with.
In this case the bartender (computer) has the necessary tools (model) and brain (controller) to make your drink (view). When you finally receive your completed drink you have reached the end of the cycle and have a complete view.
The view is built out of limited options from the model and arranged and transmitted by the controller.    

Some things to consider about the Model View Controller:

Once the drink is gone, you cannot ask the empty glass (view) for another. You have to go to the bartender (computer) and their brain (controller).  

The time spent between the bartender hearing the request and starting to create the drink should be absolutely minimal. This is sometimes known as a “skinny controller”- in other words, the controller should contain a minimal amount of logic, and delegate as much as possible to the model. A great bartender will not only have recipes memorized, but will also prepare the ingredients and tools in a reliable manner every night so that a minimal amount of searching and arranging is needed once the customers start ordering.

You want to keep as much of your logic within the model as possible as opposed to within the view. In other words, making the drink behind the bar is preferable to mixing it within the customer’s mouth.

Why use the MVC?

There are multiple ways we can go about manipulating a DOM. We could choose to rely on a Document Object Model Manipulation Library such as jQuery, but it is easy to get lost in code that consists of mostly queries. You will end up with a ton of nested query callbacks and DOM elements without any true structure in place. This will make debugging and adding onto your DOM increasingly difficult.
Using an MVC structure is a way around this issue.

We will return to the MVC in just a moment. First I want to make a quick digression into what a Document Object Model is:

A DOM connects web pages to scripts or other programming languages. That usually means JavaScript.
The DOM represents a document with a logical tree. Each branch of the tree ends in a node and each node contains objects.
DOM methods allow programmatic access to the tree. With these methods you can change the documents structure, style or content. Nodes can also have event handlers attached to them. Once an event is triggered, the event handlers execute.
The Document Object Model (DOM) is a programming interface (API) for HTML and XML documents. It represents the page so that programs can change the document structure, style, and content. The DOM represents the document as nodes and objects. That way, programming languages can connect to the page.
A Web page is a document. This document can be either displayed in the browser window or as the HTML source. But it is the same document in both cases. The Document Object Model (DOM) represents that same document so it can be manipulated. The DOM is an object-oriented representation of the web page, which can be modified with a scripting language such as JavaScript.

How Do I Access the DOM?
Section

You don't have to do anything special to begin using the DOM. Different browsers have different implementations of the DOM, and these implementations exhibit varying degrees of conformance to the actual DOM standard, but every web browser uses some document object model to make web pages accessible via JavaScript.

When you create a script–whether it's inline in a <script> element or included in the web page by means of a script loading instruction–you can immediately begin using the API for the document or window elements to manipulate the document itself or to get at the children of that document, which are the various elements in the web page. Your DOM programming may be something as simple as the following, which displays an alert message by using the alert() function from the window object, or it may use more sophisticated DOM methods to actually create new content, as in the longer example below.

This following JavaScript will display an alert when the document is loaded (and when the whole DOM is available for use):
```html
<body onload="window.alert('Welcome to my home page!');">
```
Another example. This function creates a new H1 element, adds text to that element, and then adds the H1 to the tree for this document:
```html
<html>
  <head>
    <script>
       // run this function when the document is loaded
       window.onload = function() {

         // create a couple of elements in an otherwise empty HTML page
         var heading = document.createElement("h1");
         var heading_text = document.createTextNode("Big Head!");
         heading.appendChild(heading_text);
         document.body.appendChild(heading);
      }
    </script>
  </head>
  <body>
  </body>
</html>
```

Hopefully that clarifies what a DOM is.

Okay, back to the MVC.

Not all MVC frameworks follow the formula described using the bartender analogy.
Some MVC frameworks include something other than a controller, for specific tasks. There also exist variations of MVC known as MVP (Model-View-Presenter) and MVVM (Model-View ViewModel). These different frameworks are called Design Patterns. These are words you will hear a lot when learning and using JavaScript.
Because there are so many different design patterns, MVC frameworks are commonly referred to as MV*. The * which usually is the controller can be replaced with something else.

This was an introductory guide about DOM's and MVC/MV*'s. We are just scratching the surface here.
