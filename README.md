JAMS = Journal Article Metadata Schema
===============================

Standardized method to represent scholarly metadata in JSON or YAML,
focusing on authors/contributors information.

A [first yaml schema](/Jamschema_v1.yml) is ready for documentation, community review, validation and tests.
It was based on [JATS4R recommendations](https://jats4r.org/recommendations/)
and what orcid can provide (see requirement folder).

Objectives
==================

Some of us got frustrated when needing to re-use an author list for different
research outputs (grants, papers, datasets, software,...),
other want a way to create JATSXML outputs from markdown-written documents
(using pandoc), in order to allow single source publishing.
This lead to this this project that wants to:

- [X] create a standard way to represent academic authors in a JSON or YAML format
- [ ] create tool to validate metadata entries
- [ ] develop pandoc, so this information will find its way in jatsxml, pdf and html outputs
- [ ] develop tools to transform author lists from one format to another.
- [ ] develop/list tools to facilitate data entries by researchers



Community
==================

We have been working openly and collaboratively using Github and virtual meetings.
We have met pretty irregularly so far, and will welcome any suggestion, feedback or help.

We do have a code of conduct and a contibuting section in this repository,
but we are not using GitHub as our main communication channel.
Please see https://github.com/jam-schema/jams/issues/7 to participate in our efforts.



The Initiators
==============

We are people interested using markdown and `pandoc` to write manuscripts, and include contributor lists in research outputs (datasets, software, artilces).
We work on different projects like [GIN](https://gin.g-node.org), [`pandoc-scholar`](https://github.com/pandoc-scholar/pandoc-scholar), the [`tenzing`](https://github.com/marton-balazs-kovacs/tenzing), [`sciflow`](https://www.sciflow.net) and [`papaja`](https://github.com/crsh/papaja).

A list of contributor (maybe in the jams format) will be created relatively soon.


The Schema
==============

The schema has two forms: a **flat** form and a normal form.
The normal form can be turned into the **flat** form in a one-way operation; 
there are numerous ways in which a **flat** form can be rendered in normal form.
All JSON files that validate against the **flat** form of the schema will validate against the normal form.
This is not true in reverse.

The difference between these forms is that in the **flat** form, 
all objects are defined in full in a single place, 
and references are established between objects using their identifiers.
Whereas in normal form you can establish e.g. Roles and Authors by specifying names or objects:

```json
{
  "Credits": [
    {
      "Role": "Lead author",
      "Authors": [
        "Alexandra Smith",
        {
          "Author_id": 0,
          "Name": "Tiny Tim"
        }
      ]
    }
  ]
}
```

in **flat** mode you would have to define each object separately and reference by id:

```json
{
  "Roles": [
    { "Role_id":  0, "Name": "Lead author" }
  ],
  "Authors": [
    { "Author_id": 0, "Name": "Tiny Tim" },
    { "Author_id": 1, "Name": "Alexandra Smith" }
  ],
  "Credits": [
    { 
      "Role": 0, 
      "Authors": [0, 1]
    }
  ]
}
```

The **flat** mode is designed for machine-readbility while the normal mode is designed for human convenience.
A parser should be able to validate the JSON's data while expanding it from normal mode to **flat** mode. 

Basic validation of whether a file is structurally correct can be obtained by copying the relevant schema
(`schema_relaxed.json` for normal mode and `schema_flat.json` for **flat** mode) into the online
[JSON schema validator](https://www.jsonschemavalidator.net/) and entering the JSON you wish to validate
in the right-hand box.
