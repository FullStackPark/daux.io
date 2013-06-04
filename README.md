**TM Docs** is a auto documentation generator that uses your folder structure and markdown files to create custom documentation on the fly. It helps create great looking documentation in a developer frendly way.

## Features

* Supports Github Flavored Markdown
* Auto Syntax Hightlighting
* Auto Generated Navigation
* 12 Built-in Bootstrap themes
* 35 Syntax hightlighting themes
* Shareable/Linkable SEO Friendly URLs
* Built on Bootstrap
* No build step
* Git/SVN Friendly

## Download

Download this repository as a zip, and unpack. Copy the files to a webserver that can run php. You can also run the documentation locally using Grunt.js which is covered at the end of this readme.

## Folders
The generator will look for folders in the `/docs` folder. Add your folders inside the `/docs` folder. This project contains some example folders and files to get you started. It also contains a `Markdown Tests` folder which contains the official suite of tests for checking the functionality of the Markdown parser.

You can nest the folders any number of levels to get the exact structure you want. The folder structure will be converted to the nested navigation.

## Files
The generator will look for Markdown files inside the `/docs` folder and any of your subfolders.

You must use the `.md` file extension for your files. Also you must use underscores instead of spaces. Here are some example file names and what they will be converted to:

**Good**
01_Getting_Started.md = Getting Started
API_Calls.md = API Calls
200_Something_Else-Cool.md = Something Else-Cool

**Bad**
File Name With Space.md = FAIL


## Sorting
To sort your files and folders in a specific way, you can prefix them with a number and underscore. Ex. `/docs/01_Hello_World.md` and `/docs/05_Features.md` this will list Hello World before Features, overriding the alpha-numeric sorting which is the default. The numbers will be striped out of the navigation.

## Configuration
To customize the look and feel of your documentation, you can create a `config.json` file in the of the `/docs` folder. The `config.json` file is a simple json object that you can use to change some of the basic settings of the documentation.

**Title**
Change the title bar in the docs

	{
		"title": "TM-Docs the Todaymade Documentation Generator"
	}

**Default Homepage**
Set the default page someone is redirected to if they visit `/`

	{
		"homepage": "/Getting_Started"
	}

**Bootstrap Theme**
We support the 12 bootstrap themes from Bootswatch. To use on of the themes, just set this option to the lowercase name of the theme.

View the <a href="http://bootswatch.com/" target="_blank">**Demos**</a>


	{
		"theme": "spacelab"
	}

**Syntax Hightlighting**
We support all of the availible themes for highlight.js. To use one of the themes, set this option to one of the availible style names.

View the <a href="http://softwaremaniacs.org/media/soft/highlight/test.html" target="_blank">**Demos**</a>
View the <a href="https://github.com/isagalaev/highlight.js/tree/master/src/styles" target="_blank">**Possible Option Values**</a>

	{
		"hightlight": "dark"
	}

**Github Repo**
Add a 'Fork me on Github' ribbon.

	{
		"repo": "justinwalsh/tm-docs"
	}

**Twitter**
Include twitter follow buttons in the sidebar.

	{
		"twitter": ["justin_walsh", "todaymade"]
	}

**Links**
Include custom links in the sidebar.

	{
		"links": {
			"Github Repo": "https://github.com/justinwalsh/tm-docs",
			"Help/Support/Bugs": "https://github.com/justinwalsh/tm-docs/issues",
			"Todaymade": "http://todaymade.com"
		}
	}

## Running Locally

You can run the docs locally using <a href="http://gruntjs.com/" target="_blank">Grunt.js</a>

**Requirements:**
* Node.js
* npm
* Grunt.js
* PHP 5.4 or greater

This project contains a package.json file, so once you have the requirements installed, you can simply run a `npm install` and then `grunt` in the projects folder, to start the local webserver. By default the server will run at: <a href="http://localhost:8085" target="_blank">http://localhost:8085</a>

### Support

If you need help using TM Docs, or have found a bug, please create an issue on the <a href="http://localhost:8085" target="_blank">Github repo</a>.