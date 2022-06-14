# JSON schema notes

## Validation

Structural validation can be performed using any JSON schema validator. 
A convenient version is available online at [https://www.jsonschemavalidator.net/](https://www.jsonschemavalidator.net/).

## Approach

The approach taken in the schema files is to set up definitions of the various kinds of objects handled
and then to use wrapper objects to allow them to be substituted in the shorthand (normal) schema form
by either object definitions or (where applicable) simple strings that can be turned into objects.

## Status

Currently the content is limited: the many optional fields we would like to include for various objects are not listed.
Institutions, for example, don't have fields for street addresses 
(although the JSON validates allowing arbitrary values for undefined properties).
