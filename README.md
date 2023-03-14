# JSON Stringify

|           |                                                                                     |
| --------- | ----------------------------------------------------------------------------------- |
| name      | JSON Stringify                                                                      |
| version   | v1.0.1                                                                              |
| DockerHub | [weevenetwork/json-stringify](https://hub.docker.com/r/weevenetwork/json-stringify) |
| authors   | Paul Gaiduk                                                                         |

***
## Table of Content

- [JSON Stringify](#json-stringify)
  - [Table of Content](#table-of-content)
  - [Description](#description)
  - [Environment Variables](#environment-variables)
    - [Module Specific](#module-specific)
    - [Set by the weeve Agent on the edge-node](#set-by-the-weeve-agent-on-the-edge-node)
  - [Dependencies](#dependencies)
  - [Input](#input)
  - [Output](#output)
***

## Description

Accepts an arbitrary JSON object, and returns the stringified version.

## Environment Variables

| Environment Variables | type   | Description                               |
| --------------------- | ------ | ----------------------------------------- |
| OUTPUT_LABEL          | string | The output label of the resulting string. |

### Module Specific

### Set by the weeve Agent on the edge-node

| Environment Variables | type   | Description                                    |
| --------------------- | ------ | ---------------------------------------------- |
| MODULE_NAME           | string | Name of the module                             |
| MODULE_TYPE           | string | Type of the module (Input, Processing, Output) |
| INGRESS_HOST          | string | Host where app is running                      |
| INGRESS_PORT          | string | Port where app is running                      |
| EGRESS_URLS           | string | HTTP ReST endpoint for the next module         |

## Dependencies

The following are module dependencies:

* bottle
* requests

The following are developer dependencies:

* pytest
* flake8
* black

## Input

Input to this module can be any JSON

```json
[
    {
        "frequency": 270,
        "magnitude": 2
    },
    {
        "frequency": 6.135,
        "magnitude": 25.1
    }
]
```


## Output
Output of this module is that JSON converted to a string, with the OUTPUT_LABEL:

```json
{
    "OUTPUT_LABEL": "[{\"frequency\": 270, \"magnitude\": 2}, {\"frequency\": 6.135, \"magnitude\": 25.1}]"
}
```
