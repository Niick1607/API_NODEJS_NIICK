# 1º Passo: Criar pasta e organizar estrutura do projeto


```
mkdir projetoBackend
```

```
touch readme.md
```

#### Iniciar o gerenciador de pacotes Node
```
npm init -y
```

#### Instalar os pacotes
```
npm i express nodemon dotenv
```
* express: framework web para construção da infraestrutura da API;
* nodemon: monitora as mudanças nos arquivos do projeto e reinicia automaticamente o servidor Node;
* dotenv: gerencia as variáveis de ambiente dentro do projeto;
* A confirmação da instalação dos pacotes pode ser vista na chave 'dependencies' no arquivo package.json, conforme imagem abaixo

```
nano .gitignore
```

#### Adicionar no arquivo .gitignore
```
node_modules
```

#### Criar estrutura de arquivos e pastas
```
mkdir src
```

#### Criar arquivos na pasta src
```
touch src/app.js
```
* Arquivo responsável de criar a configuração da API
```
touch src/server.js
```
* Arquivo responsável em receber as configurações da aplicação e rodar a API

#### Criar pastas dentro da pasta src
```
mkdir src/config
```
* Pasta para gerenciar a conexão com o banco de dados
```
mkdir src/controllers
```
* Pasta para gerenciar as requisições das rotas e conexão com banco de dados
```
mkdir src/routes
```
* Pasta para gerenciar as rotas da API


#### Criar arquivo .env na raiz

```
nano .env
```

#### Digitar no arquivo .env
```
PORT = 1607
```

#### Adicionar arquivo .env no .gitignore
```
nano .gitignore
```
```
.env
```

#### Criar arquivo de exemplo para para as variáveis necessárias da aplicação
```
nano .env.example
```

#### Adicionar no arquivo .env.example
```
PORT = 
```

#### Abrir o arquivo app.js e colocar
```
const express = require('express');
```

```
const dotenv = require('dotenv').config();
```

```
const app = express();
```

```
app.set('port', process.env.PORT || 3333);
```

```
module.exports = app;
```

#### Abrir o arquivo server.js e colocar
```
const app = require('./app');
```

```
const port = app.get('port');
```

```
app.listen(port, () => {
    console.log(`Running on port ${ port }!`);
});
```

#### Abrir o arquivo package.json e alterar 'scripts'
* Substituir 'test' por 'start' na linha 7
```
"start":"nodemon src/server.js"
```

#### Rodar
```
npm run start
```

