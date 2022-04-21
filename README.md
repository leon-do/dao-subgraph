# DAO Subgraph

## Start Subgraph

`git clone https://github.com/graphprotocol/graph-node/
cd graph-node/docker
vi docker-compose.yml`

`cd graph-node/docker`

`vi docker-compose.yml`

`edit ethereum: 'mainnet:YOUR_RPC'`

`./setup.sh`

`docker-compose up -d`

## Index Subgraph

`npm install`

`vi configs/sample.json`

```bash
npx graph-compiler --config configs/config.json --include node_modules/@openzeppelin/subgraphs/src/datasources --export-schema --export-subgraph
```

```bash
graph create generated/sample --node http://localhost:8020
```

```bash
graph deploy --ipfs http://localhost:5001 --node http://localhost:8020 generated/sample ./generated/sample.subgraph.yaml
```
