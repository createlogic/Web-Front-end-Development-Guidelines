[Guidelines Introduction](README.md)

Coding Standards & Guidelines
=========
The section would drill deep into best practices on `HTML`, `CSS` & `JavaScript` separately. It would also cover code linting and validating HTML, CSS & JavaScript using [Grunt Task Runner](http://gruntjs.com/). There is an easy to follow [guide](http://gruntjs.com/getting-started) to install Grunt & associated contributed modules using Node.js package manager. 


#Separation of Concerns 
Separation of Content (Markup), Presentation (CSS) & Behavior (JavaScript) should be imposed there should not be any overlapping of any of the three technologies at any point of time into each other’s layer.

So no CSS code should be mixed in HTML neither any JavaScript code should be written inside HTML layer. Each should sit in its own layer with loosely coupled selector based linking.

**Using templating engine**
If there is a requirement of mixing JavaScript with Content(Markup). It is highly advisable and recommended to using semantic templating using [Handlebars](http://handlebarsjs.com/) or 
[Mustache](http://mustache.github.io/).

This section is divided into the following sections:

1. [HTML5](html.md)



