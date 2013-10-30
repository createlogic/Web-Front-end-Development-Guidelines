[Guidelines Introduction](README.md)


##Directory Structure & Boilerplate
This directory structure is a port from HTML5Boilerplate. There will be 3 folders at the root of each project:

    ├── source
    ├── documentation
    └── build
    
###source
This directory will contain the actual source with all the actual files without any compression or concatenation.


**Directory Structure** General overview of the directory structure for `source` directory is as follows:
    
    ├── css
    |	├── reset.css
    |	├── base.css
    |	├── main.css
    |	└── media.css
	├── font
    ├── img
	|   ├── bg
	|	├── content
	|	├── generic
	|	├── icon
	|	└── sprite
    ├── js
	|   ├── main.js
	|   ├── plugins.js
	|	└── vendor
	|   	├── jquery-1.10.2.min.js
	|   	└── modernizr-2.6.2.min.js
    ├── apple-touch-icon-precomposed.png
    ├── index.html
	└── favicon.ico


###css
This directory should consist of all the project's CSS files. [The CSS](css.md) section provides more in depth knowledge on the files & their contents provided in the `css` directory. 

###font
This directory will consist of various aliases of custom fonts being used. A font would consist of below aliases for better rendering on different browsers:

- .ttf
- .svg
- .woff
- .eot
       
The browser compatibility matrix for various font aliases could be found [here](http://webfonts.info/node/379).

###img
This directory would consist of all images for the templates. Further sub folder like `bg`, `content`, `generic`, `icon`, `sprite` help to semantically organize the images for easier search.

###js
This directory would consist of a basic structure for JavaScript. 

`main.js` should consist of all the custom JavaScript for the project in a single namespace pattern. 

`plugins.js` should consist of all external plugins other than major vendor libraries, concatenated and minified, with an index at start for identifying the libraries and their use.

`vendor` directory would consist of all the vendor libraries like jQuery and Modernizr.

[The JavaScript](js.md) section would provide more in depth knowledge on required coding practices to follow and other rules for validation.  

###documentation
This directory would contain necessary documentation to support templates structure, code style & various other aspects.

###build
This directory would contain the production version of the source using a build process using Grunt. All the plugins contributing to the build would also be provided with the package for an easy source update and build process. 




    