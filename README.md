[![Actions Status](https://github.com/Codibre/nodejs-tree-key-cache-avro/workflows/build/badge.svg)](https://github.com/Codibre/nodejs-tree-key-cache-avro/actions)
[![Actions Status](https://github.com/Codibre/nodejs-tree-key-cache-avro/workflows/test/badge.svg)](https://github.com/Codibre/nodejs-tree-key-cache-avro/actions)
[![Actions Status](https://github.com/Codibre/nodejs-tree-key-cache-avro/workflows/lint/badge.svg)](https://github.com/Codibre/nodejs-tree-key-cache-avro/actions)
[![Test Coverage](https://api.codeclimate.com/v1/badges/06192fe9ef64950d4ab7/test_coverage)](https://codeclimate.com/github/Codibre/nodejs-tree-key-cache-avro/test_coverage)
[![Maintainability](https://api.codeclimate.com/v1/badges/06192fe9ef64950d4ab7/maintainability)](https://codeclimate.com/github/Codibre/nodejs-tree-key-cache-avro/maintainability)
[![Packages](https://david-dm.org/Codibre/nodejs-tree-key-cache-avro.svg)](https://david-dm.org/Codibre/nodejs-tree-key-cache-avro)
[![npm version](https://badge.fury.io/js/%40tree-key-cache%2Favro.svg)](https://badge.fury.io/js/%40tree-key-cache%2Favro)

avro tree serializer fot tree-key-cache

## How to Install

```
npm i @tree-key-cache/avro
```


## How to use it

Instantiate TreeKeyCache passing your schema to **getAvroSerializers** with the full lookup type path:

```ts
const schema: Schema = {
	name: 'Test',
	type: 'record',
	fields: [
		{
			name: 'value',
			type: 'int',
		},
	],
};

target = new TreeKeyCache<{ value: number }, string>(
			map,
			{
				keyLevelNodes: 4,
				...(await getAvroSerializers(schema, lookupType)),
			},
		);
```

And that's it! You now have a TreeKeyCache instance that serializes and deserializes using avro, which will save you a lot of space!

## License

Licensed under [MIT](https://en.wikipedia.org/wiki/MIT_License).