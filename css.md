[Guidelines Introduction](README.md) | [Coding Standards & Guidelines](coding.md) | [CSS](css.md)

Scalable CSS Guidelines:
=========

##Best Practices
Below are some best practices bullets to follow for having a scalable architecture for front-end development especially when writing markup and presentation layers:

- Separate structure from skin
- Separate container from content
- Maximize reuse of CSS rules
- Create maintainable  and concise CSS
- Use grids to layout & to determine width
- Container should provide restrains to when and where content flows whereas content height should flow naturally
- Make use of box-sizing a helpful property to redefine the box model


##Build a site wide component library
Use content objects like heading, list, headers, footers, grids and buttons etc. for content library these will serve as site wide LEGOS. For example:

Considering the h1 tag, there will be various variations of h1 with respect to different modules do not impose 1:1 relationship but instead 1:n. As in the example below:

**HTML**

    <h1>Title of the page</h1>
	<div class="top-story">
		<h1 class="mod-title">Title of module</h1>
	</div>

**CSS**

    h1 {
		font-family:arial;
		font-size:32px;
	}
	.mod-title { font-size:24px; }


This will make sure that the variations of h1 would be available everywhere and anywhere without the restrains of container being imposed.


##Base Rules
Apply base rules to an element using an element selector, child selector, a descendant selector along with any pseudo-classes. These should not include any ID or CLASS selectors.

For example:

    html, body { 
		margin:0; 
		padding:0; 
	}
	a { color:#cccccc; }
	a:active { outline:none; }

If a reset CSS is being using like normalize.css. Make sure to go through the CSS and update any base rules there which are not as per the user interface scope.


##Layout Rules
Each page has 2 kinds of components:

1. The major components that create the layout of the page like header, footer etc. 
2. The minor components like article module, advertisement module etc.

However if a grid system like [960 Grid System](http://960.gs) is being used it would be better to follow the rules implied by the Grid System itself.  


For example:

    #header { 
		width:960px; 
		height:210px; 
	}
	#footer { width:100%; }  

From layout perspective the only thing needed to be cared of is how each item relates to each other. It would be better to use `display:inline-block;` where ever possible instead of `float:left;`.

##Module Rules
A module is a more discrete component of the page. It can be the navigation, carousels, dialogs or widgets. Modules can sit inside of a layout container and even
 inside other modules.

Each module should be designed to exist as a standalone component. Modules can easily be moved to different parts of the layout without breaking.

When defining the rule set for a module, avoid using IDs and element selectors, sticking only to class names. A module will likely to contain a number of elements and there is likely to be a desire to use descendent or child selectors to target those elements.

**HTML**

    <div class="folder">
		<span>Folder Name</span>
	</div>

**CSS**

	/* The folder module */
	.folder > span {
		padding-left:20px;
		background-color:url(folder.icon);
	}

The problem here is as the project grows in complexity it is more likely that component functionality is needed to be expanded.

For example:

**HTML**

    <div class="folder">
		<span>Folder Name</span>
		<span>(32 items)</span>
	</div>

**CSS**

	/* The folder module */
	.folder > span {
        padding-left:20px;
        background-color:url(folder.icon);
	}

We don't want the icon to be shown in both spans. Rule is only including selector that holds semantics and `<div>` and `<span>` does not hold any. So creating a more expandable version of above example would be:

**HTML**

    <div class="folder">
		<span class="folder-name">Folder Name</span>
		<span class="folder-items">(32 items)</span>
	</div>

**CSS**

	/* The folder module */
	.folder span {
        padding-left:20px;
	}
	.folder .folder-name {
        background-color:url(folder.icon);
	}

##Sub-classing

If we have same modules in different sections use sub-classing as much as possible.

For example:

**HTML**

    <div class="pod pod-pixel"></div>
	<div class=”pod pod-percent”></div>


**CSS**

    /* The pod module */
	.pod { height:50px; }
	.pod.pod-pixel { width:200px; }
	.pod.pod-percent { width:50%; }

##State Rules
A state is something that augments or overrides all other styles. For example an accordion element might be expanded or collapsed.

For example:

**HTML**

    <div class="accordion is-collapsed">
    	<a href=”#”>Latest News</a>
		<div class=”news”></div>
	</div>

**CSS**

    /* The accordion module */
	.accordion .news{
		height:80px;
		width:200px;
	}
	.accordion.is-collapsed .news {display:none;}

The state can be applied to any element however the state implies a JavaScript dependency.

##Theme Rules
Themes can affect any of the primary types. They can override base styles. While writing theme styles this should be kept in mind that the theme should only override the properties that are imminent for change rest all the other properties should be kept within the default theme.

For example:

**HTML**

    <div class=”mod”>Default Styles</div>
	<div class=”mod blue”>Theme Styles</div>


**CSS**

    .mod {
		font-family:arial;
		color:#666;
	}
	.mod {
		color:#0000ff;
	}

##Depth
While writing a selector it should always be a concern of the developer to minimize the depth of the selector as much as possible but also keeping in mind the scalability & future extension.

For example:

**HTML**

    <aside id="sidebar">
	    <div>
	        <h3>Title</h3>
	        <ul>
	             <li>First</li>
	             <li>Second</li>
	             <li>Third</li>
	        </ul>
	    </div>
	</aside>


**CSS**

    #sidebar div h3 {color:#000000;}
	#sidebar div ul {margin-top:10px;}
	#sidebar div ul li {list-style-type:disc;}


In above example there would be issues when some other module comes in the same `<aside></aside>` element and specificity & override would kick-in. However above example can be re-written to clear that fact.

**HTML**

	<aside id=”sidebar”>
	    <div class=”pod”>
	        <h3>Title</h3>
	        <ul class=”pod-list”>
	             <li>First</li>
	             <li>Second</li>
	             <li>Third</li>
	        </ul>
	    </div>
	</aside>

**CSS**

	.pod h3 {color:#000000;}
	//if more h3 are present can be 
	//.pod > h3 {color:#000000;}
	
	.pod-list {margin-top:10px;}
	.pod-list li {list-style-type:disc;}

In above method we have reduced the depth. Also pod does not depend on the #sidebar to be its container to show proper styles.

Validating the styles either using Grunt build or manually doing over [CSSLINT](http://csslint.net) is always a better idea to clear any unseen warning or errors.














