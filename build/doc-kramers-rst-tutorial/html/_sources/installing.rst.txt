Installing Software
====================

This is the first post in a series that will explore using RST and Sphinx to create technical documentation. And the first question to answer is: what are these tools?

reStructuredText
----------------

reStructured Text is a markup language also known as ReST and RST. It uses symbols and tags to specify basic formatting options, which can be built upon later. Because it can be used to create docs like code, it’s often popular in software development environments. RST has a lot of similarities to Markdown, but it’s designed more with technical documentation in mind. 

Sphinx
------

Sphinx is the renderer/builder portion of the duo. It takes reStructuredText documents, and turns them into HTML, PDF, LaTeX, or ePub format – with pretty headers and headings, too, if that’s your thing. Sphinx runs on Python, since it was originally designed to create documentation for Python projects.

One thing you need to know up-front: Sphinx requires a fair bit of command-line use. 

-----

Step 1: Install Python
----------------------

.. include:: ../_child-documents/install-python.rst

Step 2: Install Sphinx
----------------------

.. include:: ../_child-documents/install-sphinx.rst

Step 3: Set up a code repository
--------------------------------

This is an optional but highly-recommended part of the process. Using a code repository – preferably not on your usual work machine – for your documentation project has several advantages:

* Backup
* Easy sharing of source documents
* Branching (this might not seem necessary, but so many software projects end up with multiple versions available to the public – and the documentation really should be available for each supported version)

Popular repository solutions are Git and CVS, but there are a stack more available too. Of them all, GitHub is arguably the simplest to set up and get running. And having a free (but public) option certainly helps.

While you will almost certainly need to install other utilities as you get further into creating your user manual, you now have everything that you need to start an RST/Sphinx project.