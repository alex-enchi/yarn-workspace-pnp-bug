# Setup

This is yarn workspaces project with 2 packages: dummy vue and react appliations that were created via `yarn create react-app` and `yarn create vue`

# How to reproduce issue

1. clone repository
2. remove `.yarnc.yml` (yarn can't read that file and make setup properly)
3. run `yarn set version stable`
4. run `yarn plugin import workspace-tools`
5. `yarn` to install dependencies
6. `yarn build` to try and build <- that step fails

## How to fix this
1. change or add in `.yarnc.yml` `nodeLinker: pnp` to `nodeLinker: node-modules`

## Expected behaviour
`yarn workspaces` should work with `pnp` and `pnpm` linkers

