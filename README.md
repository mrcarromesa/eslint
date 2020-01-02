<h1>Utilizar ESLint VSCode</h1>
<h3>Referências</h3>

* [VSCode - ESLint, Prettier & Airbnb Setup](https://gist.github.com/bradtraversy/aab26d1e8983d9f8d79be1a9ca894ab4)
* [Airbnb JavaScript Style Guide()](https://github.com/airbnb/javascript)
* [Melhorando a qualidade do seu código com Airbnb Style Guide (+ESLint)](https://medium.com/jaguaribetech/melhorando-a-qualidade-do-seu-código-com-airbnb-style-guide-eslint-ba2979cabcaa)
* [JSX not allowed in files with extension ' .js' with eslint-config-airbnb](https://stackoverflow.com/questions/43031126/jsx-not-allowed-in-files-with-extension-js-with-eslint-config-airbnb)

* [VSCode extension to integrate eslint into VSCode](https://github.com/microsoft/vscode-eslint)

* [Configuring ESLint](https://eslint.org/docs/user-guide/configuring#specifying-globals)

* [Configuration File Prettier](https://prettier.io/docs/en/configuration.html)

* [How to set up ESLint with Airbnb JavaScript Style Guide in WebStorm](https://www.themarketingtechnologist.co/eslint-with-airbnb-javascript-style-guide-in-webstorm/)

<hr />

<strong>Instalar Plugins no VSCode</strong>
* [ESLint - Code Style Guide](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
* [EditorConfig for VS Code - Manter padrão para outras ides](https://marketplace.visualstudio.com/items?itemName=EditorConfig.EditorConfig)

<strong>Nas configurações do VSCode:</strong>

* No mac OS Pressionar ```command + shift + P```
* No input que aparece digitar ``` JSON ```
* Selecionar ``` Preferences: Open Settings (JSON)  ```
* Adicionar o seguinte:
```js
"eslint.validate": ["javascript", "javascriptreact"],

// Corrigir automáticamente quando salva
"editor.codeActionsOnSave": {
    "source.fixAll": true,
    "source.fixAll.eslint": true
},
```


<strong>O que instalar em modo dev</strong>

```bash
yarn add eslint prettier eslint-plugin-prettier eslint-config-prettier eslint-plugin-node eslint-config-node eslint-plugin-jsx-a11y eslint-plugin-react eslint-plugin-import babel-eslint -D
```

<strong>O que instalar em modo normal</strong>

```bash
yarn add eslint-config-airbnb
```

<strong>Criar arquivos na raiz do projeto</strong>

* Criar arquivo ```.eslintrc.json``` adicionar o seguinte:

```js
    {
        "env": {
            "browser": true,
            "es6": true,
            "node": true
        },
        "extends": ["airbnb", "prettier", "eslint:recommended", "plugin:node/recommended"],
        "plugins": ["prettier"],
        "globals": {
            "Atomics": "readonly",
            "SharedArrayBuffer": "readonly"
        },
        "parserOptions": {
            "ecmaVersion": 2018,
            "sourceType": "module",
            "ecmaFeatures": {
                "jsx": true
            }
        },
        "overrides": [
            {
                "files": ["*.js"],
                "rules": {
                    "strict": 2
                }
            }
        ],
        "rules": {
            "prettier/prettier": "error",
            "no-unused-vars": "warn",
            "no-var": "error",
            // "no-console": "off",
            "func-names": "off",
            "no-process-exit": "off",
            "object-shorthand": "off",
            "class-methods-use-this": "off",
            "semi": 2,
            "react/jsx-filename-extension": [1, { "extensions": [".js", ".jsx"] }]
        }
    }
```

* Criar arquivo ```.prettierrc``` adicionar o seguinte:

```js
{
  "trailingComma": "es5",
  "tabWidth": 4,
  "semi": true,
  "singleQuote": true
}
```
* Gerar arquivo ```.editorconfig``` com o seguinte conteúdo:

```js
root = true

[*]
indent_style = space
indent_size = 4
charset = utf-8
trim_trailing_whitespace = true
insert_final_newline = true
```
