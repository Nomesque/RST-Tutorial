Assign a directory to each manual
---------------------------------

Sphinx makes some weird assumptions that can trip up anyone trying to create a more complicated setup for the first time:

* The configuration file is named conf.py.
* conf.py is in the same directory as the master file.

The problem: if you’re writing multiple manuals, you’ll need to:

* Have multiple master files.
* (potentially) Set different configuration values for each.

My recommendation: assign a directory for each manual. In this directory, create:

* A configuration file (conf.py).
* A master file.
* Base documents.