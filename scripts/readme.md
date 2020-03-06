# Scripts

## Validate template property binding

A python script `validate-templates.py` automatically validates the use of lanugage properties inside the velocity templates.

It expects two input parameters:

| Parameter | Description | Default |
|:---|:---|:---|
|`-l | --lang_props`|A language properties file.|`/opt/ldregistry/config/language/messages/en.properties`|
|`-t | --template_root`|A templates root directory.|`/opt/ldregistry/templates`|

The script reports:
- __Unused properties__ - properties that are defined in the language properties file but are not used in any of the templates.
- __Missused properties__ - properties that are defined in the language properties file but the incorrect number of parameters are passed to it.
- __Undefined properties__ - properties that are __*not*__ defined in the language properties file but their use is attempted by one or more templates.