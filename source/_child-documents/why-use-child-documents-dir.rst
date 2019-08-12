Why use a child-documents directory?
------------------------------------

When I started my first Sphinx/RST project, I didn’t use a child-documents directory. I found that builds took a long time, and incorporated every single document in the base documents directory into HTML output. It didn’t matter whether I’d linked them into a particular document or not. That was a pain. When users searched the HTML knowledge base, the results could include pages that weren’t supposed to be there.

Then I needed to amend the documentation to allow for two different versions of the same product (free and premium). I ran into even more problems trying to ensure that the right files made it into the right builds. Moral of the story: unless you’re absolutely sure that every file you create will be needed in the final build, and you’ll never have to worry about creating multiple versions of a manual or multiple manuals for a product… use a child-documents directory.

Your initial instinct will probably be to create a child-documents directory for every manual or product. Unless these will have absolutely zero content in common, though, I recommend that you use a top-level child-documents directory instead. You’ll find it easier to locate and link between child documents.

.. pull-quote:: When you use a child-documents directory, you can save build time, improve build sanitation, and optimise your re-use of source material.