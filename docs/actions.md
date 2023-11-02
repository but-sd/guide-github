Les `Actions` github sont des scripts qui peuvent être déclenchés par des événements sur le dépôt. Ils sont stockés dans le dossier `.github/workflows` du dépôt. Les actions sont définies dans un fichier YAML. 

Les actions peuvent être déclenchées par différents événements, elles permettent d'automatiser des tâches.

Nous allons plus particulièrement nous intéresser aux actions qui se déclenchent sur des événements de `Push` et de `Pull Request`. En effet afin de sécuriser le dépôt, nous allons mettre en place des actions qui vont vérifier que le code qui est poussé sur le dépôt est conforme à certaines règles.

Il s'agit de la première étape de la mise en place d'un processus de `Continuous Integration` (CI). L'intégration continue est un processus qui permet de vérifier que le code qui est poussé sur le dépôt est conforme à certaines règles. on s'assure ainsi en continu que le code est fonctionnel et qu'il respecte les règles de codage que l'on a définies.

## 1. Création d'une action

### 1.1. Utilisation d'un workflow prédéfini

github propose un certain nombre de workflow prédéfinis en fonction du langage utilisé. Nous allons utiliser le workflow `Node.js` qui permet de lancer des actions sur un projet Node.js.

![Node.js workflow](./images/nodejs-workflow.png)

Fichier YAML généré par github :

```yaml
# This workflow will do a clean installation of node dependencies, cache/restore them, build the source code and run tests across different versions of node
# For more information see: https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-nodejs

name: Node.js CI

on:
  push:
    branches: [ "develop" ]
  pull_request:
    branches: [ "develop" ]

jobs:
  build:

    runs-on: ubuntu-latest

    strategy:
      matrix:
        node-version: [14.x, 16.x, 18.x]
        # See supported Node.js release schedule at https://nodejs.org/en/about/releases/

    steps:
    - uses: actions/checkout@v3
    - name: Use Node.js ${{ matrix.node-version }}
      uses: actions/setup-node@v3
      with:
        node-version: ${{ matrix.node-version }}
        cache: 'npm'
    - run: npm ci
    - run: npm run build --if-present
    - run: npm test
```

Cet exemple contient plusieurs parties :

- La première partie `name` permet de donner un nom au workflow.
- La deuxième partie `on` permet de définir les événements qui vont déclencher le workflow. Dans cet exemple, le workflow sera déclenché sur les événements `push` et `pull_request` sur la branche `develop`.
- La troisième partie `jobs` permet de définir les jobs qui vont être exécutés par le workflow. Dans cet exemple, il n'y a qu'un seul job qui s'appelle `build`.
- La quatrième partie `build` permet de définir les étapes qui vont être exécutées par le job. Dans cet exemple, il y a 5 étapes qui vont être exécutées :
  - `actions/checkout@v3` : permet de récupérer le code du dépôt
  - `actions/setup-node@v3` : permet de configurer l'environnement Node.js
  - `npm ci` : permet d'installer les dépendances du projet
  - `npm run build --if-present` : permet de construire le projet si un script `build` est défini dans le fichier `package.json`
  - `npm test` : permet de lancer les tests

La partie `strategy` permet de définir les différentes versions de Node.js sur lesquelles on souhaite lancer les tests. Dans cet exemple, on lance les tests sur les versions 14, 16 et 18 de Node.js.

La documentation de github permet de comprendre le fonctionnement de chaque partie du fichier YAML : [https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions](https://docs.github.com/en/actions/learn-github-actions/workflow-syntax-for-github-actions)
