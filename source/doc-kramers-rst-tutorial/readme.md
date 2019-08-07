Project Directory
=================

This is a main project directory. You could have several of these, or only one. Generally speaking, you should have one per end document that you want to create.

For example, I want to produce a tutorial document called Doc Kramer's reStructuredText and Sphinx Tutorial. I'll be producing it in two different formats - PDF and HTML. I don't need two separate project directories, though, because both formats will contain exactly the same content, and I'll use the same index and base documents for each.

The sphinx-quickstart script adds the master file and configuration file to the base source/ directory. I've moved them to this source/doc-kramers-rst-tutorial/ directory because I'm not ruling out creating other end documents that need their own master file, configuration file, and base documents.