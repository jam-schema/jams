Journal Article Metadata Schema
===============================

Standardized method to represent scholarly metadata in JSON or YAML.


Project Background
==================

We are using different tools to produce and use author lists, and it would be great if we could transform author list written for one tool, into the author list another tool is using.
To do this transformation, we want to follow the pandoc "sandglass" logic where a general representation is used as a flexible intermediate format to convert between different author metadata formats.
We want to develop an open standard for this general metadata representation.
For this purpose, we are trying to initiate a braod discussion and build a community of people interested in the creation and exchange of author lists.

As an example, consider the [`rticles`](https://github.com/rstudio/rticles) R-package or [Manubot](https://manubot.org/).
With both tools you can write a markdown-based manuscript, translate them to TeX, and render a PDF document.
The problem is that even within `rticles` it is not possible simply switch manuscript styles without adpating the YAML front matter, which contains the author metadata.
Consider the following simplified example taken from the PLOS template:

~~~yaml
author:
  - name: Alice Anonymous
    affiliation: Some Institute of Technology
  - name: Bob Security
    affiliation: 
      - Another University
      - Some Institute of Technology
      
address:
  - code: Some Institute of Technology
    address: Department 1, Street, City, State, Zip
  - code: Another University
    address: Department 2, Street, City, State, Zip
~~~

Now compare this to the YAML front matter of the JOSS template:

~~~yaml
authors:
  - name: Adrian M. Price-Whelan
    affiliation: "1, 2" # (Multiple affiliations must be quoted)
  - name: Author 2
    affiliation: 2

affiliations:
 - name: Lyman Spitzer, Jr. Fellow, Princeton University
   index: 1
 - name: Institution 2
   index: 2
~~~

More incompatibilities arise when we switch tools.
For example, Manubot uses yet another structure to represent this information,

~~~yaml
authors:
  - name: John Doe
    affiliations:
      - Department of Something, University of Whatever
  - name: Jane Roe
    affiliations:
      - Department of Something, University of Whatever
      - Department of Whatever, University of Something
~~~

while the format for the same information in [zenodo](https://zenodo.org/) looks largely different:

~~~json
{
  "creators": [
    {
      "affiliation": "Department of Something, University of Whatever",
      "name": "John Doe",
      "orcid": "0000-0001-7288-XXXX"
    }
~~~

Our goal is to develop a general representation of this information that allows us to convert from one format to another.
If we succeed, we will for example be able to make these different types of YAML front matter interoperable, via a `pandoc` extension that is responsible for the translation
(NB: other elements may not be compatible between `rticles` templates, but we hope you got the idea). 
While we hope to go beyond YAML front matter for manuscript creation, we are planning to start there.

Besides the basic information given in the examples above, the standard should of course include fields for things like, e-mail addresses, ORCiD, and contribution roles (CRediT, CRO, and/or datacite roles).

The Initiators
==============

We are people interested using markdown and `pandoc` to write manuscripts, and include contributor lists in research outputs (datasets, software, artilces).
We work on different projects like [GIN](gin.g-node.org), [`pandoc-scholar`](https://github.com/pandoc-scholar/pandoc-scholar), the [`tenzing`](https://github.com/marton-balazs-kovacs/tenzing) and [`papaja`](https://github.com/crsh/papaja).

