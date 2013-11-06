[Guidelines Introduction](README.md)

Coding Standards & Guidelines
=========
The section would drill deep into best practices & standards on `HTML`, `CSS` & `JavaScript` separately. It would also cover code linting and validating HTML, CSS & JavaScript using [Grunt Task Runner](http://gruntjs.com/). There is an easy to follow [guide](http://gruntjs.com/getting-started) to install Grunt & associated contributed modules using [NodeJS](http://nodejs.org/) package manager. 


##Separation of Concerns 

SoC(Separation of Concerns) is a software design principle for separating different concerns of the program into different layers in a loosely coupled manner so that changes made to one layer do not directly inflict other layers.

In front-end the classic concerns are Content(HTML), Presentation(CSS) & Behavior(JavaScript) which should be divided into three top level layers where each layer addressing single concern and there should not be any overlapping between them.

###Guidelines

- There should not be any CSS inlined into the element or document.
- Fixed layout changes should be addressed by using different classes. For example there should be a class `.show` to show an element and `.hide` to hide an element, where as JavaScript should only be used to toggle between the classes.
- HTML should not be mixed in the JavaScript layer or vice versa.
- **templating engine** if there is a requirement of mixing JavaScript with Content(Markup). It is highly advisable and recommended to using semantic templating using [Handlebars](http://handlebarsjs.com/) or [Mustache](http://mustache.github.io/).

This section is divided into the following sections:

1. [HTML5](html.md)



