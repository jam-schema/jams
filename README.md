Journal Article Metadata Schema
===============================

Standardized method to represent scholarly metadata in JSON or YAML.


Project Background
==================

We are using different tools to produce and use author lists, and it would be great if we could transform author list written for one tool, into the author list another tool is using. To do this transformation, we want to follow the pandoc "sandglass" logic and get an open standards where the lists can be transcribed from and to. Therefore, we are trying to create a community of people interested in the creation and exchange of author lists.

As an example, take the rticles package. You can write a manuscript in markdown and get a tex and pdf output, but if you are using the PLOS template, you can not simply change the output type to get another type of article with the same markdown: the yaml front matter needs to be slightly different. If we succeed, we will be able to make these different type of yaml frontmatter compatible, simply using a pandoc extension (NB: other elements may not be compatible between rticles templates on top of author list in rticles, but we hope you got the idea).


Some of us would also be able to indicate contribution roles (Credit, CRO, and/or datacite roles), orcid numbers and maybe other elements in these lists.

The Initiators
==============

We are people interested using markdown and pandoc to write manuscripts, and including contributor lists in research outputs (datasets, software, artilces).
We work on different projects like gin.g-node.org, pandoc-scholar, the tenzing app and papaya.

