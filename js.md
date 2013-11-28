[Guidelines Introduction](README.md) | [Coding Standards & Guidelines](coding.md)


#JavaScript Guidelines
All JavaScript should be placed in its own layer. For most of our projects jQuery is the library of choice, which is already a part of the provided [boilerplate](https://github.com/createlogic/html-boilerplate).

As a part of boilerplate a [Single Object Namespace Template](https://github.com/createlogic/html-boilerplate/blob/master/js/main.js) is provided.


##Code Guidelines

- 99% of code should be housed in external JavaScript files being included at the end of JavaScript
- Don’t rely on user-agent string. Do proper feature detection using [MODERNIZR](http://modernizr.com/) also provided [here](https://github.com/createlogic/html-boilerplate/blob/master/js/vendor/modernizr-2.6.2.min.js) as a part of provided boilerplate but it is always better to take the latest version from the actual repository.
- Variables and functions should be named logically using camel casing like `var hCarousel;`, `var popUpWindow;`, `var handleTopNavigation;`.
- All Boolean variable should be prepended with is e.g. `var isValidObject;`
- Documentation should follow [NaturalDocs](http://www.naturaldocs.org/) structure
- Code should be organized in one global singleton object e.g. `Namespace = {} || Namespace;`
- All application functionality should be extended to the object e.g.

For example:

    Namespace = {
					init:function(){//all initialization code goes here},
					config:function(){//all configuration objects go here }
	};

- All associated elements should be passed as parameters to methods acting upon in the `init()` function.

For example: If we have a `carousel()` function to be implemented on a `<div id="hero">...</div>` we need to initialize it in the following way in the `init()` method

    Namespace = {
					init():function(){
							this.carousel("#hero"); //passing element as parameter	
					}
	};


- For objects initiating only once [module pattern](http://www.uipress.com/patterns-in-javascript-the-module-pattern/) can be used and for objects needed to be initialized more than once [jQuery Plugin Pattern](http://coding.smashingmagazine.com/2011/10/11/essential-jquery-plugin-patterns/) can be used
- All site specific code should be placed in `main.js`
- All plugins can be separate files for source folder however a grunt minify and concatenate process should be done to created production versions.
- For event delegations the new jQuery `on` method should be used
- »	Naming conventions: all variables camel case e.g. count, found also all functions camel case with a verb in front e.g. `getName`, setName, handleNavigation and all constructor functions as Pascal case e.g. Person, GroupAccount etc. Whereas constants written will all upper case with words separated by underscore(_) e.g. MAX_COUNT, PI, AVG etc. 
