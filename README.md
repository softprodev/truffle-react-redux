# Truffle-Contracts-Web-DApp

The `truffle-contracts-web-dapp` provide the template for your next dapp. It separate the concern of `contracts` and `web` frontend by putting them in separate folder and include the glue scripts to handle the dependencies and bridge the both sides.

* `contracts/` This project was bootstrapped with `truffle init`
* `web/` This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app).
* glue scripts: help install dependency modules at once, help copy JSON abi from `contracts/` to `web/` project.

## Installation

1. Install Truffle and lerna globally.
    ```sh
    npm install -g truffle lerna
    ```

2. Download the box. This also takes care of installing the necessary dependencies.
    ```sh
    truffle unbox gasolin/truffle-contracts-web-dapp
    ```

3. Glue script allow you to install `contracts/` and `web/` project dependencies at once via [lerna bootstrap](https://github.com/lerna/lerna#bootstrap)

    ```sh
    npm run bootstrap

    # or you can install dependency modules via separate command
    $ cd contracts && npm install
    $ cd ../web && npm install
    ```


## Contracts development

Enter `contracts/` folder

1. Run the development console.
    ```sh
    truffle develop
    ```

2. Compile and migrate the smart contracts. Note inside the development console we don't preface commands with `truffle`. Smart contract changes must be manually recompiled and migrated.
    ```sh
    compile
    migrate

    # If outside the development console..
    npm run build
    ```

3. Glue scripts can copy compiled JSON files into `web/src/lib` to access contract.

```sh
npm run deploy
```

4. Truffle can run tests written in Solidity or JavaScript against your smart contracts. Note the command varies slightly if you're in or outside of the development console.
  ```sh
  # If inside the development console.
  test

  # If outside the development console..
  truffle test

  # glue script
  npm run test
  ```



## Web development

Enter `web/` folder

1. Run the front-end hot reloading in `web/` (outside the truffle development console).
    ```sh
    // Serves the front-end on http://localhost:8080
    npm run start
    ```

2. Build the web project for production.

```sh
npm run build
```

3. Create-react-app can run tests within src/ folder.

```
npm run test
```

## Dependencies

### whole project

* [lerna](https://github.com/lerna/lerna#bootstrap) Manage `contracts/` and `web/` project.

### contracts sub project

* [truffle](http://truffleframework.com/): Build, debug, deploy the smart contracts

### web sub project

* [Create React App](https://github.com/facebookincubator/create-react-app): Create React apps with no build configuration
* redux & react-redux: State management
