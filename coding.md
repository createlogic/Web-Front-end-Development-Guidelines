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

1. [HTML5](#HTML5)
2. [CSS](#CCS)
3. [JavaScript](#JavaScript)
4. [Validation](#Validation)


##HTML5
Markup should only define the structure, outline & content of the document and offer a structured content. Markup should not be mixed with Inline CSS or JavaScript to define the look and feel or behavior of the content on the page beyond rudimentary concepts such as headers, paragraphs, and lists. The presentation attributes of HTML have all been deprecated and style should be contained in separate stylesheets.

HTML5 is the version of HTML & XHTML we tend to follow for all our new developments. [HTML5 draft](http://www.w3.org/TR/html5/) defines a single language that can be written in HTML & XML. 

HTML5 DOCTYPE would be used and any cross-browser and gracefully degradable feature would be used where ever possible.

Markup would be validated as per the validation section for mostly well-formed code. 100% valid code is not required if valid code is not aligned with user experience we will prefer maintaining user experience over valid code. 

Page should be readable without CSS & content hierarchy should be maintained.

###Boilerplate
A toned down version of HTML5 Boilerplate is provided [here](#) which fits our requirements. The repository would be maintained and any issues or pull requests would be added if are genuine and add value to the project.

###Guidelines
All markup should be delivered as `UTF-8` as it is most friendly for internationalization. 
`<META CHARSET=”UTF-8”>` charset attribute in `<META>` tags can be used.

Markup should be semantically correct and well-formed. All ID and CLASS names should be meaningful and in lower case. In case of a name longer that 1 word a hyphen(-) should be used to separate. For example, top navigation can be given an ID or CLASS as `class="top-nav"` or `id=top-nav`. This is recommended to follow for semantic consistency of naming the various attributed values. 

####HTML5 Sematic Tags
HTML5 semantic elements like `<nav>, <figure> & <figcaption>, <header>, <footer>, <section>, <aside>, <article>` should be used with a fallback JavaScript library for enabling these elements for IE8 and below browsers like [MODRENIZR](http://modernizr.com/).

####Headings
- All pages must use heading elements to define structure of document
- Heading elements should be ordered hierarchically i.e. if `<h2></h2>` tag is defined somewhere in document it should have a preceding `<h1></h1>` tag 
- Headings should be followed by further content `<h3>Title</h3><p>Content Text</p>`
- Headings should not have a consecutive series of same level in hierarchy `<h3>Title</h3><h3>Sub Title</h3>` 
- All headings and title should be title cased in the markup. If required can be transformed using CSS text-transform property

####Lists
- `<ul></ul>` should only be used when order of the list is not editorially significant
- `<ol></ol>` should be used when order of the list is editorially significant
- `<ul></ul>`, `<ul></ul>` must have at least 1 `<li></<li>`

####Tags must not be used
`<i>, <big>, <blink>, <marquee>, <s>, <small>, <strike>, <tt>, <u>, <center>, <nobr>, <font>`

####Tags must be used when content match their description
`<blockquote>, <q>, <cite>, <abbr>, <dfn>, <code>, <samp>, <kbd>, <var>, <ins>, <del>, <address>, <pre>, <br>, <sup>, <sub>`

####Schema
Use [schema.org](http://schema.org) to add rich snippets to the markup which are recognized by major search providers. These schemas add meaningful description to the associated elements.

####Comments
- All containers providing document structure must have an open and close comment indicated where a container has started and where it is ending
- All modules should be placed inside opening and closing comments indicating
- Descriptor comments should be used describing the use of a specific Markup element


##Validation
This section will cover methods used to validate / lint code. We will provide a list of grunt modules that can be used to validate / lint code for quality. 

[Grunt HTML Validation](https://npmjs.org/package/grunt-html-validation) can be used to validate HTML. All files markup should validate against a valid type and DTD either any of XHTML Strict or Transitional 1.0, HTML5 or any custom based on the requirements. The markup should also comply with Accessibility standards under WCAG 1.0 guidelines with a minimum Priority 2(AA) checklist.

[Grunt CSS Lint](https://npmjs.org/package/grunt-contrib-csslint) can be used to linting CSS. for code quality and defined patterns for performance and anti-patterns that needed to be removed or replaced with a better code that preserve for better performance. 

[Grunt JS Hint](https://npmjs.org/package/grunt-contrib-jshint) can be used for code quality and defined patterns for performance and anti-patterns that needed to be removed or replaced with a better code that preserve for better performance. 


