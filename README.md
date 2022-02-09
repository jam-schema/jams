JAMS= Journal Article Metadata Schema
===============================

Standardized method to represent scholarly metadata in JSON or YAML,
focusing on author/contributor information.

A [first yaml schema](Jamschema_v1.yml) is ready for community review, validation and tests.
It was based on https;//JATS4r.org recommendations, and what orcid can provide (see requirement folder)

Project Background
==================

Some of us got frustrated when needing to re-use an author list for different
research outputs,
other want a way to create JATSXML outputs from markdown-written documents,
using pandoc, in order to allow single source publishing.
This lead to this this project that wants to:

-[] create a standard way to represent academic authors in a JSON or YAML format
-[] create tool to validate metadata entries
-[] develop pandoc, so this information will find its way in jatsxml, pdf and html outputs
-[] develop tools to transform author lists from one format to another.
-[] develop/list tools to facilitate data entries by researchers



Community
==================

Please see https://github.com/jam-schema/jams/issues/7 to participate in our efforts.
We do have a code of conduct and a contibuting section in this repository,
but we are not using GitHub as our main communication channel.

We have met pretty irregularly so far, and will welcome any suggestion, feedback or help.


The Initiators
==============

We are people interested using markdown and `pandoc` to write manuscripts, and include contributor lists in research outputs (datasets, software, artilces).
We work on different projects like [GIN](https://gin.g-node.org), [`pandoc-scholar`](https://github.com/pandoc-scholar/pandoc-scholar), the [`tenzing`](https://github.com/marton-balazs-kovacs/tenzing) and [`papaja`](https://github.com/crsh/papaja).

