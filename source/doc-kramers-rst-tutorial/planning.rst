Planning
========

I hate doing extensive, unnecessarily repetitive document maintenance every couple of months – especially when the need for it could have been avoided with better documentation design in the first place. And this is a big strength of Sphinx and RST – together, we can use them to minimise ongoing maintenance time and costs.

Here are a few of the things to think about before putting your project together:

Shared functionality
--------------------

Look at the product(s) that you’ll be documenting. Are there areas in which repetition might occur in documenting functionality? Some examples of this might be:

* Multiple products sharing a code base
* API calls with the same attributes
* Tasks with the same or very similar workflows.

.. pullquote:: Map these areas of overlap before planning the documentation to give you a leg up in creating a single-source solution.

Changeable names
----------------

I worked with a company that produced a large, sprawling enterprise software solution and an equally large and sprawling documentation suite. They changed the name of their main product.

“Is this likely to ever happen again?” I asked, eyeing the dozens of documents now requiring careful find-and-replace missions.

“Never! This is the first time in twenty years!” I was cheerfully informed.

So, the doc team spent days combing through documentation on a number of platforms to update the product name. And you guessed it – a few months later, the product name changed again. Cue several more days of an entire team’s work spent changing a product name.

Why is this applicable? Because if we’d assigned a product name to a variable in that documentation, it would have required maybe a day of one person’s time to change the variable value and re-build the doc suite, then check in the new documents, each time the product name changed.

.. pullquote:: List any names that might change as the market does – company names, product names, department names, etc. These should be assigned variables in the documentation if at all possible.

File system structure
---------------------

By default, Sphinx gathers up all RST documents in the base directory for inclusion in an HTML build, even if those documents aren’t referenced in the index or other child documents. This can be a right royal pain in the behind, especially when mixing source documents for multiple products. My favoured solution is to create a child-documents directory for the majority of documents and a base-documents directory for each product, which contains the index and main chapter files, then configure Sphinx to ignore the child-documents directory unless a document is specifically referenced.

Why am I talking about this in the planning stage? Because using single-sourcing, you’ll create a lot of absolute or relative links between documents, and it can be annoying and time-consuming (speaking from experience) to go back through 100 documents to change each link.

.. pullquote:: Figure out in advance, if at all possible, the directory structure that you’ll use for your source material. I recommend using a single directory for the vast majority of documents, another specifically for images, and one base directory for each product.

Code repository
---------------

If you haven’t already set up a code repository for the project, now is a really good time to do it. This doesn’t just provide a non-local backup option if something goes wrong – it also allows for branching and for retrieval of previous revisions if someone accidentally saves over a file or two. Setting up a GitHub repository is probably the easiest and fastest option.

.. pullquote:: Set up your code repository before beginning the documentation.