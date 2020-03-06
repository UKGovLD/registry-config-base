# Scripts

## Validate template property binding

A python script `validate-templates.py` automatically validates the use of lanugage properties inside the velocity templates.

It expects two input parameters:

| Parameter | Short Name | Description | Default |
|:---|:---|:---|:---|
| `--lang_props` | `-l` | A language properties file.|`/opt/ldregistry/config/language/messages/en.properties`|
| `--template_root` | `-t` |A templates root directory.|`/opt/ldregistry/templates`|

To run the script with default parameters, use the command:

```
python3 validate-templates.py
```

from the `scripts` directory of `registry-config-base`.
You can also supply the `-h` parameter to show help documentation. 

The script reports:
- __Unused properties__ - properties that are defined in the language properties file but are not used in any of the templates.
- __Missused properties__ - properties that are defined in the language properties file but the incorrect number of parameters are passed to it.
- __Undefined properties__ - properties that are __*not*__ defined in the language properties file but their use is attempted by one or more templates.