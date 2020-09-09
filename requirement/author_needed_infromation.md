This is for all contributors, this include people that would not be listed in the author list.

Main sourece of information: https://jats4r.org/authors-and-affiliations, https://github.com/ORCID/orcid-model/blob/master/src/main/resources/common_3.0/common-3.0.xsd

# ORCID information one can extract

- orcid ID (cannot be empty)
- first name (cannot be empty)
- family name
- publication name

- email

- affiliation (work):

    - organisation
    - address
    - PID


- funder information

# JTSxml

## name

There are different ways to deal with this, pandoc will only use the name string to create tex/pdf version (ALBERT?), while Jats can, but does not must, have given name and family name entry.
Because some people do not have a family name, there should be a way to get author name without having to enter some family name.

I would propose the format to have:
- string-name
- first name
- middle name
- family name

Exceptions: author can also be a group, not a person, then the collab term is used in jats, instead of string-name. Member of the group may be indicated with a specific contributor type

# PID (<contrib-id>.)

- type
- id

# Affiliation
