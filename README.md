# Jediswap SDK

[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)
[![npm version](https://img.shields.io/npm/v/@jediswap/sdk/latest.svg)](https://www.npmjs.com/package/@jediswap/sdk/v/latest)
[![npm bundle size (scoped version)](https://img.shields.io/bundlephobia/minzip/@jediswap/sdk/latest.svg)](https://bundlephobia.com/result?p=@jediswap/sdk@latest)

## Running tests

To run the tests, follow these steps. You must have at least node v10 and [yarn](https://yarnpkg.com/) installed.

First clone the repository:

```sh
git clone https://github.com/jediswaplabs/jediswap-sdk.git
```

Move into the jediswap-sdk working directory

```sh
cd jediswap-sdk/
```

Install dependencies

```sh
yarn install
```

## Local testing

There are two possible ways of local testing: by using the [yarn link](https://classic.yarnpkg.com/en/docs/cli/link) command or by manual transferring of built files

### Testing by using the [yarn link](https://classic.yarnpkg.com/en/docs/cli/link) command
- run `yarn link` in the root directory of our module. You should see in the console command for using the linked module, e.g. `yarn link "@jediswap/sdk"`
- run `yarn start` in the root directory of our module, you should see the `dist` folder after that
- go to the project where we want to test our module, e.g. `jediswap-interface`
- run `yarn link "@jediswap/sdk"`, it will install our linked package
- if everything was done right, you would see a success message in the console, and a symlink to our local package will appear in `node_modules`
- after that we can start working with our local module, all changes should be updated automatically
- once we're done, we can run the `yarn unlink` command in our module and `yarn unlink "@jediswap/sdk" && yarn install --check-files` in the project where we tested our module

### Testing with manual transferring of built files
This method is less convenient and requires a lot of manual operations
- run `yarn start` in the root directory of our module
- copy the contents of the `dist` folder to `node_modules/@jediswap/sdk/dist` of the project in which we want to test our module
-  if you are using `vite` in a project, you should add the `--force` flag to the project launch command, for example, `vite --open --force`
- when you change your module, you should copy and past the contents of the `dist` folder again
