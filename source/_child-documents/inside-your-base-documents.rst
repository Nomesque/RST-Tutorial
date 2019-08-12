Inside your base documents
--------------------------

We'll go into formatting in depth later, but here are the basics that you’ll need.

Level 1 Heading
...............

RST uses lines of punctuation to mark a heading. For example, this is what I use for a level 1 heading:

.. code-block:: 
   Heading text
   =============

The first heading in a base document will be used:

* As a chapter heading in the table of contents.
* To designate that punctuation character as a ‘level one’ heading.

The character that you use for each heading level must be consistent. For example, once I use = for a level 1 heading, I must use = for all other level 1 headings. I must use a different character for level 2 headings.

Here are the key requirements for heading markers:

* Must use one of these characters: ! ” # $ % & ‘ ( ) * + , – . / : ; < = > ? @ [ \ ] ^ _ ` { | } ~
* Each line of punctuation must have as many or more characters than the heading text.
* Must include a line of punctuation under the heading text.
* A line of punctuation above the heading text **may** be included, but isn’t mandatory.

.. note:: Recommendation: Create a style guide as you go that specifies the punctuation used in each heading level. Otherwise, confusion is almost guaranteed.

`See the heading characters used in Python’s Style Guide <http://docutils.sourceforge.net/docs/ref/rst/restructuredtext.html#sections>`.

Links to child documents
........................

To maximise your single-sourcing, I recommend that you put as much of your text as possible into child documents. So your base documents will consist primarily of a level-one heading and links to child documents.

Link to a child document like this:

.. code-block:: 
   .. include:: ../children/welcome.rst

The key parts of the statement above are:

* ``..`` indicates a directive – something that Sphinx needs to recognise as not just text. Note the space after it.
* ``include`` tells Sphinx to use the contents of a different file.
* ``:: `` is the standard RST connection between a command and the information Sphinx needs – in this case, a file location and name. 