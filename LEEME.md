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

## Starter project creado en vivo en stream de [Twitch.tv/CharlyAutomatiza](https://www.twitch.tv/charlyautomatiza) basado en [Karate DSL for NodeJS/NPM Projects](https://github.com/karatelabs/karate-npm)

### Overview

This documentation is also available in [**English**](README.md).

### Requerimientos generales

- Instalar algún cliente git como por ejemplo [git bash](https://git-scm.com/downloads)

Descargar e instalar

- Instalar última versión de [Node.js](https://nodejs.org/es/download/)

### Instalación del framework de pruebas

#### **Clonar el repositorio:**

```bash
git clone https://github.com/charlyautomatiza/starter-karate-dsl-npm.git
```

#### **Instalar las dependencias.**

```bash
npm install
```

#### **Para la ejecución de los test de API Rest y GraphQL situarse en la raíz del proyecto y ejecutar**

```bash
npm run test ./src/features
```

If you have errors please check [Known Issues](#known-issues) section and then re-try.

Para ejecutar un test específico de API Rest, por ejemplo del feature [users.feature](src/features/users/users.feature) aquellos casos con el tag **@create_user**.

```bash
npm run test -- ./src/features "--t @create_user"
```

Para ejecutar un test específico de API GraphQL, por ejemplo del feature [users-gql.feature](src/features/graphql/users-gql.feature) aquellos casos con el tag **@graphql_examples**.

```bash
npm run test -- ./src/features "-t @graphql_examples"
```

Otra opción:

```bash
npm run test:gql
```

Para ejecutar todos los tests tanto de API Rest como de GraphQL se puede ejecutar con el tag **@run**.

```bash
npm run test -- ./src/features "-t @run"
```

Otra opción:

```bash
npm run test:run
```

Ejecutar con `N hilos` en paralelo los casos que tengan la tag `@run` se puede con el parámetro `-T N`.
Con el parámetro `-C` se elimina la carpeta `target` y se crea nuevamente con los nuevos resultados de las pruebas.

```bash
npm run test -- ./src/features "-t @run" "-T 5" "-C"
```

```bash
npm run test:parallel
```

### **El reporte unificado de los resultados de los test**

Luego de cada ejecución se genera dentro de la carpeta **target/karate-reports** los reportes en formato html.

Para más detalle se puede consultar [la documetación oficial](https://karatelabs.github.io/karate/#test-reports)

### Github Actions para ejecutar los test de APIs

Nueva carpeta [**.github/workflows**](.github/workflows) con el archivo [**karate-test-runner.yml**](.github/workflows/karate-test-runner.yml) para ejecutar nuestros tests desde un pipeline de Github Actions.

JUnit Report obtenido desde [Marketplace de GitHub](https://github.com/marketplace/actions/junit-report-action)

El workflow está configurado para que se ejecute ante el siguiente evento:

- **push**: cuando se hace un push a un repositorio
- **Pull request**: cuando se crea un pull request

## Known Issues

Users on Windows have reported [issues](https://github.com/karatelabs/karate-npm/issues/2) such as the `npm install` failing to complete and without any errors shown.

As a workaround, please [install JBang manually](https://www.jbang.dev/documentation/guide/latest/installation.html) and re-try the `npm install` step.
