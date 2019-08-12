Run sphinx-quickstart
---------------------

Sphinx has a neat little bit of functionality that does all the initial setup work for you.

1. Open a command prompt. 
   In Windows, press the Windows key and R (Windows icon-R), enter ``cmd`` and press Enter to open a command prompt window.
2. Navigate to the base directory that you created.
3. Enter ``sphinx-quickstart``.

Basic configuration
...................

The ``sphinx-quickstart`` script will start asking you questions about your project. I’ve listed the questions, with recommended answers (where appropriate):

**Separate source and build directories (y/n) [n]:** ``y``

I recommend separating the source and build directories because generally these will each belong to different phases of a project’s life cycle.

**Name prefix for templates and static dir [_]:** ``(press Enter)``

Unless you have a pressing reason to avoid using an underscore to denote standard subdirectories, just use the default. This will give you _templates and _static directories. 

.. note:: If you're using GitHub as your code repository, you'll need a .nojekyll file in your base directory. This tells GitHub to just treat directories starting with an underscore as standard project directories.

**Project name:** ``<Your product's name>``

The script adds this value to conf.py in the source directory. If you’ll only be creating a single user guide/knowledge base, you can enter the name that you want for your end document, for example ``MySoftware Knowledge Base``. If you’re going to be producing multiple documents, then what you enter here doesn’t really matter; you’ll be manually changing conf.py for each document anyway.

**Author name(s):** ``<Your name>``

The script adds this value to conf.py in the source directory. What you enter here depends on your company documentation policy. Options might be the name of your company, your name, or the name of your team.

**Project release []:** ``<documentation release number>``

The script adds this value to conf.py in the source directory. Generally you’ll be changing this every time you release documentation to your users. Often ``0.0.1`` is a good start.

**Project language [en]:** ``(press Enter)``

If you’ll be writing documentation in English, then all you need to do is press Enter. Otherwise, check this `list of language codes <http://www.sphinx-doc.org/en/master/usage/configuration.html#confval-language>`_ and enter the two-letter code that matches the language you’ll be using.

**Source file suffix [.rst]:** ``(press Enter)``

The script adds this value to conf.py in the source directory. This is the file extension that Sphinx will use to identify RST documents. In theory, you can use any file extension that you want when creating your documents. In practice, unless you have pressing need to do otherwise, I recommend sticking with the default.

**Name of your master document (without suffix) [index]:** ``(press Enter)``

The script adds this value to conf.py in the source directory. It’s the name of the file (without file extension – that comes from your answer to the previous question) that Sphinx will use as the backbone of your document. You could use the name of your user guide, especially if you’ll have multiple guides, but be aware that you’ll typically need a separate directory and conf.py file for each. I haven't tried using spaces in the master file name, but I wouldn't expect it to be a good idea.

**Do you want to use the epub builder (y/n) [n]:** ``(press Enter)``

If you want to build EPUB files – primarily used on ebook devices like Kobo’s Forma – then enter ``y``. 

.. note:: Kindle e-ink devices generally won’t display EPUBs; you’ll need MOBI files instead.

If you enter y, EPUB build options will be added to the conf.py file in the base directory.

Sphinx extensions
.................

The sphinx-quickstart script will go through a list of standard extensions that you might want to enable. Many of these are the legacy of Sphinx’s origin as a Python code documentation tool; I’ve added an asterisk next to extensions that you’ll want to enable if you want to automatically include docstrings in your documentation. This could be useful for developer-level documentation and API docs.

The sphinx-quickstart script will add options you enter here to the conf.py file in the base directory.

**\*autodoc: automatically insert docstrings from modules (y/n) [n]:** ``(press Enter)``

Autodoc takes docstrings from Python code. If you’re not creating documentation from code comments, you won’t need this extension enabled. If you are, though, there’s a good walkthrough here: `Getting Started with Sphinx / Autodoc <https://medium.com/@eikonomega/getting-started-with-sphinx-autodoc-part-1-2cebbbca5365>`_.

**\*doctest: automatically test code snippets in doctest blocks (y/n) [n]:** ``(press Enter)``

The doctest extension checks the code snippets included in your docstrings. Again, if you’re not creating documentation from code comments, you won’t need this. If you are, check out this article: `How to include test in your Python docstrings using doctest <https://thomas-cokelaer.info/tutorials/sphinx/doctest.html>`_.

**\*intersphinx: link between Sphinx documentation of different projects (y/n) [n]:** ``(press Enter)``

You’ll only need the intersphinx extension if you’re creating documentation from code comments AND want to easily link to existing code documentation. See: `Link to other projects’ documentation <https://www.sphinx-doc.org/en/master/usage/extensions/intersphinx.html#module-sphinx.ext.intersphinx>`_.

**todo: write “todo” entries that can be shown or hidden on build (y/n) [n]:** ``y``

The todo extension lets you add behind-the-scenes notes on documentation; if you use this and don’t want your users seeing it, ensure that you include ``todo_include_todos = False`` in your conf.py file.

**\*coverage: checks for documentation coverage (y/n) [n]:** ``(press Enter)``

Use the coverage extension if you want to check that your Python code is fully documented. If you’re not creating documentation from code comments, you don’t need this extension.

**imgmath: include math, rendered as PNG or SVG images (y/n) [n]:** ``(press Enter)``

If you’re including complex mathematical equations in your documentation AND want Sphinx to render it into images automatically, enable this extension (``y``).

**mathjax: include math, rendered in the browser by MathJax (y/n) [n]:** ``(press Enter)``

If you’re including complex mathematical equations in your documentation AND want Sphinx to include it in HTML pages in MathJax format, enable this extension (``y``).

**\*ifconfig: conditional inclusion of content based on config values (y/n) [n]:** ``(press Enter)``

I’m not a fan of this extension; I prefer to include or exclude documents and text using only statements and build parameters. It could be useful for some situations, though – see `ifconfig documentation <https://kite.com/python/docs/sphinx.ext.ifconfig>`_.

**\*viewcode: include links to the source code of documented Python objects (y/n) [n]:** ``(press Enter)``

Sphinx will automatically link back to the code that it has retrieved docstrings from. If you’re not creating documentation from code comments, you won’t need this extension.

**\*githubpages: create .nojekyll file to publish the document on GitHub pages (y/n) [n]:** ``(press Enter)``
By default, GitHub treata directories with names beginning with an underscore as not needing to be included in general project files. Sphinx uses directories like _templates by default. You’ll generally want these directories included in your GitHub commits. 

If you’re using GitHub, enter ``y`` so that Sphinx includes a .nojekyll file in the project.

Makefile
........

The sphinx-quickstart script will ask if you want to include some easy-build options. These are handy in the early stages of a project, and if you have a very simple project that won’t need parameters specified in the build command.

**Create Makefile? (y/n) [y]:** ``(press Enter)``

**Create Windows command file? (y/n) [y]:** ``(press Enter)``

Project initialised!
The sphinx-quickstart script should have created the following directories and files for you, if you hadn't already created them:

* source directory
* build directory
* source/index.rst (assuming you chose the default master document and file suffix options)
* source/conf.py