# Blockchain ND Project 3 - RESTful API

## Introduction

This project provides a REST API interface for the simple [block chain project]() utilizing [Express.js framework](), through which existing block data can be retrieved from a third party as well as creating new blocks.

## Deployment

This program relies on `node` 9.6+ and `npm` package manager.

```shell
npm install
node app.js
```

## Endpoints

### Get block information
GET `/block/{Block_Height}`, where `{Block_Height}` is the block height in the block chain, starting from `0`.

Example with `curl`:
```shell
curl http://localhost:8000/block/0
```

Response:
```shell
{"hash":"4b2ddc6b2c436505555eb55b6a1c49bad6843b79adf4ee8f8beeae1d418b8cb2","height":0,"body":"First block in the chain - Genesis block","time":"1537009024","previousBlockHash":""}
```

### Create new block
POST `/block`, block data should be in a JSON object with block data stored in `body` attribute.


Example with `curl`:
```shell
curl -d '{"body": "new block"}' -H "Content-Type: application/json" -X POST http://localhost:8000/block
```

Response:
```shell
{"hash":"2caf5e8e6133c8b7227d303ff80bc05eca25839e8eaa3e1de55481b0df45d2b8","height":1,"body":"new block","time":"1537009034","previousBlockHash":"4b2ddc6b2c436505555eb55b6a1c49bad6843b79adf4ee8f8beeae1d418b8cb2"}
```