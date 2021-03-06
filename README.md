# json-schema-to-avro

[![npm](https://img.shields.io/npm/v/json-schema-to-avro.svg)](https://www.npmjs.com/package/jsonschema-avro)
[![Build Status](https://travis-ci.org/katsanva/jsonschema-avro.svg?branch=master)](https://travis-ci.org/katsanva/jsonschema-avro)

Converts JSON Schema definitions into Avro Schema definitions.

## Install

    npm install json-schema-to-avro

## Consume

```js
    const jsonSchemaAvro = require('json-schema-to-avro')

    const inJson = {
      "$id": "http://your-domain.com/schemas/your-schema.json"
      "description": "Example description",
      "type": "object",
      "properties": {
        "first_name": { "type": "string" },
        "address": {
          "type": "object",
          "properties": {
            "street_address": { "type": "string" }
          }
        }
      }
  }

  const avro = jsonSchemaAvro.convert(inJson)
```

Please ensure that the input JSON schema is dereferenced so that all external references have been resolved. [json-schema-ref-parser](https://www.npmjs.com/package/json-schema-ref-parser) can do this, prior to using this module.

## Test

    npm test

## TODO

* Handle `anyOf` and `allOf`.
