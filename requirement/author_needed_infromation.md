This is for all contributors, this include people that would not be listed in the author list.

Main sourece of information: https://jats4r.org/authors-and-affiliations, https://github.com/ORCID/orcid-model/blob/master/src/main/resources/common_3.0/common-3.0.xsd

# ORCID information one can extract

- orcid ID (cannot be empty)
- first name (cannot be empty)
- family name
- publication name

- email

- affiliation (work):
    
    - department (free text entry)
    - organisation name (automatic)
    - organisation address(automatic): city, region, country code
    - PID number (automatic)
    - PID source (automatic) (RINGOLD)


- funder information (could be used in the aknowledgement section):

  - title
  - organisation name + address
  - PID number (automatic)
  - PID source (automatic) (FUNDREF)
  - grant_number
  - grant url
  
- keywords (could be used as default keywords for the paper)

# JATSxml

Example 1 had many features explained.

```{xml}
<contrib-group>
  <contrib-group>
  <contrib contrib-type=”author” corresp="yes">
    <string-name> julien colomb</string-name>
    <contrib-id authenticated="true" contrib-id-type="orcid">https://orcid.org/0000-0002-9615-3022</contrib-id>
    <email>ahonigm@gwdg.de</email>
    <aff id=”aff1”>the world</aff>
    <xref ref-type="corresp" rid="cor1">
  </contrib>        
    <contrib contrib-type=”author”>
     <collab>The authors and affiliations working group 
       <contrib-group>
         <contrib><string-name>Prince Charles </string-name>
         <aff id=”aff1”>Buckingham Palace, England</aff></contrib><contrib>
         <string-name><surname>Cooke</surname><given-names>James L.</given-names></string-name>
         <aff id=”aff2”>Royal Navy, London, UK</aff></contrib>
        </contrib-group>
     </collab>
   <aff id=”aff3”>
    <institution-wrap>
      <institution-id institution-id-type=”ringgold”>2188</institution-id>
      <institution>Harvard Law School</institution>
    </institution-wrap>
    <city>Cambridge</city>, <state>MA</state> <postal-code>02138</postal-code>, <country @country=”us”>United States of America</country>
   </aff>
</contrib>
<author-notes><corresp id="cor1"><label>*</label>For correspondence: <email>ahonigm@gwdg.de</email> (AH);</corresp>

</contrib-group>
```

## groups

A group of people can be an author, in this case the collab tag is used.

the title of the group is given by collab
under the collab group, there may be the people tags, in this case a new <contrib-group> tag is used.

NB groups can have an affiliation.



## people

### contribution type

This allows to have contributors who are not authors. It can also be used for authors present in a group by seeting type = "non-byline author".
In practice, it would meant that people of type author are listed in the author list, while others would be indicated in the aknowledgement section.

For version 1, I think we can take for granted there is only the author type ?

### corresp + email

This option is set for the corresponding author, then the email should be indicated too, in the author-note section or directly (?).


### name

people are named using:

string-name

or

surname + given-names

NB: middle names are included in given-names with the initials


## PID (<contrib-id>)

- type
- id

# Affiliation

- name
- id type
- id number
- address
- country

<label> will be created automatically by pandoc
<institution> name of the institution
<institution-id>: type and id
<institution-id institution-id-type=”ringgold”>1812</institution-id>

# Summary info (jats term - orcid term)

# authors

## name:

string-name = publication name

given-names = first name
surname = family name

* either string-name or both given-names and surname should be indicated

## author other attributes (maybe included via xref)

PID
affiliation
author-notes:email or email = email
role (credit)

## contributor attributes:
type (author, non-byline author, editor ,??)
corresponding author (yes, no)

# affiliation

- name
- PID type
- PID number
- city
- region
- country
- postal code