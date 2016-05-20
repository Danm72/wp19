# Quick start

npm install -g gulp (You can skip this step if you already have gulp installed)

npm install

gulp wpinit (Builds an installation from scratch)

gulp cleanup (Remove scaffolding files)

gulp php

# wp19

Scaffold a Wordpress project with a minimal starter theme in Bootstrap using Gulp.

Make sure you're running the latest version of NodeJS: [https://nodejs.org/en/download/](https://nodejs.org/en/download/). You should also have gulp installed.s
	
	npm install -g gulp
	git clone https://github.com/lab19digital/wp19.git . && npm install

To build an installation from scratch

	gulp wpinit

After installation, you will need to cleanup the scaffolding files (and remove the old repos)

	gulp cleanup

To run the server after build or on an existing project

	gulp php

## Out the box

This generator includes:

* Latest wordpress
* Latest wp-cli
* Gulp for compiling JavaScript, Sass, or Less (or whatever else you need)
* Webpack for compiling JavaScript

After installation the server will run automatically. A theme called "default" is generated. To start the server in future, run <code>gulp php</code> from the root.

**Sass**
We're using Less until Bootstrap 4 comes out, at which time we'll be switching over to Sass, which is why it's also included but optional for use.

**Wordpress Plugins**
Automatically installs the following plugins:

* advanced-custom-fields
* wordpress-seo
* duplicate-post
* timber-library (Twig templating)

Also removes the hello plugin and standard themes

**JavaScript Plugins**
Comes with jQuery, several other plugins are available but may not be imported by default:
- mustache
- parsleyjs
- gsap
- scrollmagic
- slick-carousel

**A note about JavaScript implementation**

We use Babel/ES6/Webpack to transpile ES6 JavaScript. This means it's easy to import modules
into your code, but may have some issues with older libraries or libraries without commonJS
implementation. You will see inside webpack.config.js that several aliases have been setup
for GSAP for this purpose. You can uncomment these to get GSAP/Scrollmagic working correctly.

You may require a similar approach for other JavaScript libraries.

# A word about the built in PHP server for Mac users
Mac users have reported issues with the built in PHP server not connecting to the MySQL database correctly. 
This seems to happen for MAMP users. A php.ini file is not defined for MAMP users when using the built
in server. You should copy your MAMP php.ini file to /etc/

For example:

	/Applications/MAMP/bin/php/phpX.X.XX/conf

Should be copied to:

	/etc/

Once this is done, the socket file for MySQL socket connections will be founds. If this is not the case
you need to confirm your socket files exists and is configured correctly in the PHP.ini file being used.

	mysql.default_socket = /Applications/MAMP/tmp/mysql/mysql.sock
	pdo_mysql.default_socket = /Applications/MAMP/tmp/mysql/mysql.sock



Created by <a href="http://lab19digital.com">Lab19 Digital</a>.