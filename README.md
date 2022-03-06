# Configurando o Typescript
Projeto para guardar todos os meus estudos de Typescript
Segue abaixo tudo que foi aprendido com esse projeto;

# Instalar Typescript
npm i typescript -D //instalar como devDependencies

# Instalar um interpretador/compilador typescript
npm i ts-node -D //instalar como devDependencies

# Para utilizar o code runner fazer a seguinte configuração
criar pasta com nome .vscode, criar arquivo settings.json, adicionar a seguinte regra to arquivo:
{
    "code-runner.executor":{
        "typescript": "npx ts-node --files"
    }
}

# Instalando o esLint
npm i eslint -D //instalar como devDependencies
Baixar tambem a extensao ESLint, que é quem faz a integração do vscode com eslint
utilizar o comando abaixo para integracao ao typescript
npm i @typescript-eslint/eslint-plugin @typescript-eslint/parser -D
Após isso, criar o arquivo ".eslintrc.js" na pasta raiz e adicionar a seguinte configuração:

module.exports = {
    env: {
        browser: true,
        es6: true,
        node: true,
    },
    extends: [
        'eslint:recommended',
        'plugin:@typescript-eslint/eslint-recommended',
        'plugin:@typescript-eslint/recommended',
    ],
    globals: {
        Atomics: 'readonly',
        SharedArrayBuffer: 'readonly',
    },
    parser: '@typescript-eslint/parser',
    parserOptions: {
        ecmaVersion: 11,
        sourceType: 'module',
    },
    plugins: ['@typescript-eslint'],
    rules: {},
};

# instalar o prettier para formatar e deixar o codigo mais bonito
npm i prettier eslint-config-prettier eslint-plugin-prettier -D
Após instalar, adicionar ao arquivo .eslintrc.js na seguinte parte:
extends: [
        'eslint:recommended',
        'plugin:@typescript-eslint/eslint-recommended',
        'plugin:@typescript-eslint/recommended',
        'plugin:prettier/recommended', //[adicionar_esta_linha]
    ]
Crie um arquivo .prettierrc.js e adicione a seguinte configuração:
module.exports = {
    semi: true,
    trailingComma: 'all',
    singleQuote: true,
    printWidth: 80,
    tabWidth: 2,
    endOfLine: 'auto',
    useTabs: true
}
Para ter o auto ';' assim que salvar o arquivo, adicione no seu settings.json de user do vscode, nao no que criamos na pasta .vscode:
"editor.codeActionsOnSave": {
        "source.fixAll.eslint": true,
        "source.fixAll": true
    }
Para ja criar e configurar os arquivos automaticamente com um script já criado execute o comando na pasta do projeto:
npx https://github.com/luizomf/eslint-prettier (sacanagem neh? fui ver isso depois tambem. kkk)

# Para configurar o Typescript
npx tsc --init
configuração utilizada em meu tsconfig.json:
{
  "compilerOptions": {
    "target": "es2016",
    "lib": [
      "DOM",
      "ESNext"
    ],
    "module": "commonjs",
    "outDir": "./dist",
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true,
    "strict": true,
    "skipLibCheck": true
  },
  "include": [
    "./src"
  ]
}

Para Acessar a documentação do compilerOptions acesse o link :
https://typescriptlang.org/docs/handbook/compiler-options.html

# configurar o config.json para o time
instalar a extension editorConfig for vsCode
Clicar com o botao direito na pasta raiz do projeto e "Generate .editorconfig"

Fim das configurações para o Typescript;

