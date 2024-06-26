# ENS evmgateway

This repository implements ENS gateway contracts built on top of [evmgateway](https://github.com/ensdomains/evmgateway)

## Packages

This is a monorepo divided up into a few packages:

### [crosschain-resolver](/crosschain-resolver/)

A resolver contract that is built on top of [evm-verifier](https://github.com/ensdomains/evmgateway/tree/main/evm-verifier).

### [crosschain-reverse-resolver](/crosschain-reverse-resolver/)

A reverse resolver contract that is built on top of [evm-verifier](https://github.com/ensdomains/evmgateway/tree/main/evm-verifier).


## Demo app

https://github.com/makoto/my-l2-app-v2

## Dependencies

- [ens-contracts](https://github.com/ensdomains/ens-contracts/tree/feature/crosschain-resolver-with-reverse-registrar)
- [evmgateway](https://github.com/ensdomains/evmgateway/pull/39)
- [l2 subgraph](https://github.com/makoto/ens-l2-delegatable-resolver-subgraph)

## How to setup locally

```
gh repo clone ensdomains/ens-l2-contracts
bun install
bun run test
```


## Troubleshooting

### Error HH12: Trying to use a non-local installation of Hardhat, which is not supported.

`yarn test` spawns `hardhat test` in the forked process. When `hardhat` command is installed under the node_modules of under each workspace, it complains that it's using locally installed hardhat. Remove hardhat from local node_modules and make sure it's only installed under the root `node_modules`

```
rm -rf *-*/node_modules/hardhat
rm bun.lockb
bun install
```