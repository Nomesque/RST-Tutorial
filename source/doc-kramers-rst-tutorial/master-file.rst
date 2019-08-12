Master File
===========

A master file controls almost all of the content that will be included in your user manual. It contains a list of your base documents and specifies what your table of contents will look like.

.. include:: ../child-documents/example-master-file.rst

Inside your master file
-----------------------

Comment
.......

By default, this contains a statement about the sphinx-quickstart script creating the master file, and when. Not overly helpful. Replace with your own text, for example the author(s) and what the manual is for.

Keep the following points in mind:

* You need the initial .. and space.
* When starting a new line of the comment, indent it three spaces.

Title
.....

This is displayed before the table of contents, once built. In a PDF, it will be on the title page, and the table of contents on the next page. In HTML output, it will be used for the page title of index.html.

toctree directive
.................

This directive builds the table of contents and also designates the base documents that make up the skeleton of your manual.

It consists of:

* ``..`` indicates a directive – something that Sphinx needs to recognise as not just text.
* ``toctree`` tells Sphinx that it needs to create a table of contents.
* ``::`` is the standard RST connection between a command and the information Sphinx needs – in this case, some parameters and then file names.
* ``:max-depth:`` is a parameter for the directive. In the example above, it’s set to 2; the table of contents will include level 1 and 2 headings only. Increase or decrease this depending on the granularity you want in your TOC.
* ``:caption:`` is the heading on the table of contents. I’ve used Contents, but you might want Table of Contents or other text.
* The blank line after the caption tells Sphinx that you’ve finished setting parameters for the directive.
* The list of file names, one per line, give Sphinx the exact names of the base documents minus their file extension. Sphinx will extract headings from these documents – and any subdocuments they include – for inclusion in the table of contents.

Configuration
.............

Make sure the build script will be able to find your master file. Check that the corresponding conf.py file has the correct master_doc and source_suffix settings.

For example, if your master file is named index.rst, then master_doc must be set to 'index' and source_suffix to '.rst'.