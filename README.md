<p align="center">
  <a href="https://www.twitch.tv/charlyautomatiza"><img alt="Twitch" src="https://img.shields.io/badge/CharlyAutomatiza-Twitch-9146FF.svg" style="max-height: 300px;"></a>
  <a href="https://discord.gg/wwM9GwxmRZ"><img alt="Discord" src="https://img.shields.io/discord/944608800361570315" style="max-height: 300px;"></a>
  <a href="http://twitter.com/char_automatiza"><img src="https://img.shields.io/badge/@char__automatiza-Twitter-1DA1F2.svg?style=flat" style="max-height: 300px;"></a>
  <a href="https://www.youtube.com/channel/UCwEb6xrQtQCEuN_gNgi_Xfg?sub_confirmation=1"><img src="https://img.shields.io/badge/Charly%20Automatiza-Youtube-FF0000.svg" style="max-height: 300px;" style="max-height: 300px;"></a>
  <a href="https://www.linkedin.com/in/gautocarlos/"><img src="https://img.shields.io/badge/Carlos%20 Gauto-LinkedIn-0077B5.svg" style="max-height: 300px;" style="max-height: 300px;"></a>
</p>

<p align="center">
    <a href="https://karatelabs.github.io/karate/">
        <img alt="Karate DSL" src="https://raw.githubusercontent.com/karatelabs/karate/v0.9.6/karate-core/src/main/resources/res/karate-logo.svg" height="60" width="60" style="max-width: 100%;">
    </a>
</p>

# API Test Automation - Karate DSL For Restful and GraphQL APIs

## Starter project created live on [Twitch.tv/CharlyAutomatiza](https://www.twitch.tv/charlyautomatiza) based on [Karate DSL for NodeJS/NPM Projects](https://github.com/karatelabs/karate-npm)

### Overview

Esta documentación está dispobible también en [**Castellano**](LEEME.md).

### General requirements

- Install a git client such as [git bash](https://git-scm.com/downloads)

Download and install

- Latest version of [Node.js](https://nodejs.org/es/download/)

### Installation of the testing framework

#### **Clone the repository:**

```bash
git clone https://github.com/charlyautomatiza/starter-karate-dsl-npm.git
```

#### **Install dependencies.**

```bash
npm install
```

#### **To run the API Rest and GraphQL tests, go to the root of the project and run**

```bash
npm run test ./src/features
```

**WARNING:** If you have errors please check [Known Issues](#known-issues) section and then re-try.

To run a specific API Rest test, for example the feature [users.feature](src/features/users/users.feature) those cases with the **@create_user** tag.

```bash
npm run test -- ./src/features "--t @create_user"
```

To execute a specific test of the **GraphQL API**, for example in  feature [users-gql.feature](src/features/graphql/users-gql.feature) those cases with the tag **@graphql_examples**.

```bash
npm run test -- ./src/features "-t @graphql_examples"
```

Another option:

```bash
npm run test:gql
```

To run all the API **Rest** and **GraphQL** tests, it can be run with the **@run** tag.

```bash
npm run test -- ./src/features "-t @run"
```

Another option:

```bash
npm run test:run
```

Running with `N threads` in parallel the cases that have the `@run` tag can be done with the `-T N` parameter.
With the `-C` parameter the `target` folder is removed and created again with the new test results.

```bash
npm run test -- ./src/features "-t @run" "-T 5" "-C"
```

```bash
npm run test:parallel
```

### **The unified report of test results**

After each execution, the reports in html format are generated in the **target/karate-reports** folder.

For more details you can consult [the official documentation](https://karatelabs.github.io/karate/#test-reports)

### Github Actions to run API tests

New folder [**.github/workflows**](.github/workflows) with file [**karate-test-runner.yml**](.github/workflows/karate-test-runner.yml) to run our tests from a Github Actions pipeline.

JUnit Report retrieved from [GitHub Marketplace](https://github.com/marketplace/actions/junit-report-action)

The workflow is configured to run on the following event:

- **push**: when a repository is pushed.
- **Pull request**: when a pull request is created.

## Known Issues

Users on Windows have reported [issues](https://github.com/karatelabs/karate-npm/issues/2) such as the `npm install` failing to complete and without any errors shown.

As a workaround, please [install JBang manually](https://www.jbang.dev/documentation/guide/latest/installation.html) and re-try the `npm install` step.
