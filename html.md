[Guidelines Introduction](README.md) | [Coding Standards & Guidelines](coding.md)

HTML5
=========
Markup should only define the structure, outline & content of the document and offer a structured content. Markup should not be mixed with Inline CSS or JavaScript to define the look and feel or behavior of the content on the page beyond rudimentary concepts such as headers, paragraphs, and lists. The presentation attributes of HTML have all been deprecated and style should be contained in separate stylesheets.

HTML5 is the version of HTML & XHTML needs to be followed for all our new developments. [HTML5 draft](http://www.w3.org/TR/html5/) defines a single language that can be written in HTML & XML. 

HTML5 DOCTYPE would be used and any cross-browser and gracefully degradable feature would be used where ever possible.

Markup would be validated as per the validation section for mostly well-formed code. 100% valid code is not required if valid code is not aligned with user experience we will prefer maintaining user experience over valid code. 

Page should be readable without CSS & content hierarchy should be maintained.

###Boilerplate
A toned down version of HTML5 Boilerplate is provided [here](#) which fits our requirements. The repository would be maintained and any issues or pull requests would be added if are genuine and add value to the project.

###Guidelines


- All markup should be delivered as `UTF-8` as it is most friendly for internationalization. 
`<META CHARSET=”UTF-8”>` charset attribute in `<META>` tags can be used.
- Markup should be semantically correct and well-formed. 
- All tags should be lowercase.
- Attributes values should be enclosed in double quotes. For example `src="img/bg/top.gif"`.
- All ID and CLASS names should be meaningful and in lower case. In case of a name longer that 1 word a hyphen(-) should be used to separate. For example, top navigation can be given an ID or CLASS as `class="top-nav"` or `id=top-nav`. This is recommended to follow for semantic consistency of naming the various attributed values. 
- [HTML entities](http://entitycode.com/) can be used when appropriate.

####HTML5 Sematic Tags
HTML5 semantic elements like `<nav>, <figure> & <figcaption>, <header>, <footer>, <section>, <aside>, <article>` should be used with a JavaScript polyfill for backward compatability with older browsers like IE8 and below browsers like [MODRENIZR](http://modernizr.com/).

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




