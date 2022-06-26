# Identity Suite

## Identity Suite – Digital Identity for All

Identity Suite is a collection of applications and developer tools that provide an accessible entry into digital identity for everyone, everywhere. Built on-top of the IOTA Identity Protocols using a familiar JavaScript front end, Certify & Vira can enable any developer an easy entry into the Digital Identity space and will provide a platform for the easy creation of proof of concept and future solutions for any developer, business, organisation, or SME, with basic js knowledge.

## Project Information

Digital Identity for Everyone, Everywhere.
The Identity Suite project has been created to hopefully help enable ease of access into the digital identity space for organisations, institutions, businesses, and individuals. The IOTA Identity Protocols are some of the most powerful in the IOTA eco-system and we are aiming to demonstrate this through the project.
With the IOTA eco-system especially suited the IoT side of things, we are seeing some amazing initiatives, partnerships, research, and developments using IOTA Identity, that solve a huge number of current edge challenges.
Where we focus is on the human aspect of digital identity.
The use of Digital Identity for organisations and individuals offers countless solutions across a range of industries and institutional sectors. From government to education, healthcare to finance, retail through to real estate. And within these sectors, it covers a range of versatile use cases such as personal identity, licensing, registration, certification, insurance, medical documentation, passports, and so much more.
With such scope for social development in this space, we have channelled our focus towards creating the Identity Suite, that can introduce these solutions and make IOTA Identity easily accessible for organisations and businesses around the world.

## Installation

Identity Suite Consists of 3 important components that need to be setup in order to run a basic instance of Identity Suite.

```
Identity Suite
    |-> identity-api
    |-> certify-client
    |-> vira-wallet
```

---

### 1. Identity API

Identity API is the core of identity suite and certify and this is where most of the action happens.

**NOTE** : All commands here are assumed are being run in the `identity-api` directory

- In `identity-api/src/` you will find `SAMPLE.env` update rename that file to `.env` and update the values to be what you want to set them to

- We use yarn to manage our dependencies so it is essential that you also have yarn installed to make sure the lock file is being used.
  to install Yarn run

On UNIX systems (MacOS/Linux)

```
sudo npm i -g yarn
```

On windows run a command prompt as admin and

```
npm i -g yarn
```

- now run `yarn` in the root directory of identity-api

- you can now either run `src/server.ts` using `ts-node` or you can transpile it using `tsc` and run the outputted `server.js` in `./dist/`
- If all goes right you will have two logs on the console.
  - MongoDB connection status
  - Server PORT

### 2. Certify Client

Certify Client is the frontend of certify, it's written in React. Credits to [Danish](https://github.com/DSS3113) for his amazing work with the frontend :)

**NOTE** : All commands are assumed to be running in `certify-client` folder

- To start you will need to edit the `package.json` and update the proxy to point to the port that Identity API is running on. For example if your identity API is running on port 4000. edit the `proxy` property to be `"proxy": "http://127.0.0.1:4000"`
- now run `yarn` in the root dir of `certify-client`, to see how to install yarn see the documentation provided in the `identity-api` section
- to run the dev server run `yarn start` and certify would be open :)

### 3. Vira Wallet

Vira is the self sovereign identiy wallet that is where you store all of your DID, PII and VCs.
Vira is built on React and leverages Capacitor to expose the Native APIs.
Again, credits to [Danish](https://github.com/DSS3113) for helping out with the frontend.

**NOTE** : All commands are assumed to be running in the `vira-wallet` directory

- In `src` you will find a `config.ts` file, it contains two build variables that you can edit according to your setup. the first is `share_service` this is the where your websocket service that helps in sharing is being hosted, in your case that would be the same as where your `identiy-api` is running. The second is `isInternalOnly` set this to true if you are running on localhost, set to false if running on a web server.

- Run `yarn` to install all the dependencies. See `identity-api` section to see how to install `yarn`

- Now we need to build the frontend, run `yarn build`

- Now connect your phone or Simulator and run `npx cap run android` for android and `npx cap run ios` for ios.

in case you face any trouble, feel free to ask away in the `#identity-suite` channel on the [Tangle Labs Discord](https://discord.gg/rmQQnwddmK)
