Using sphinx-quickstart
=======================

Once you’ve done your planning and have your directory structure figured out, the next step is to start creating your project. You’ll need to create your base directory, use the sphinx-quickstart script to set up your basic project structure and configuration, and then – if needed – add some extra structure.

Create your base directory
--------------------------

You’ll need a base directory. You can name this whatever you want – for example docs, manuals, written-content. Set up your local code repository in this base directory.

.. include:: run-sphinx-quickstart.rst

Multiple guides?
----------------
If you’ll be creating multiple guides from your source files, I recommend that you complete the following steps now:

* Create a _children subdirectory in the source directory. This is where you’ll save the vast majority of your documents.
* Create an _images or _media subdirectory in the source directory.
* Create a subdirectory in the source directory for each guide you’ll be producing.
* Copy index.rst and conf.py from the source directory to the guide subdirectories.
* Change the name of each index.rst file to reflect which guide it is used for.
* Modify each conf.py file’s master_doc entry to its corresponding new guide filename.