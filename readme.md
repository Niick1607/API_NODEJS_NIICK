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
<hr>

## Insomnia

Criando sua API, é preciso testar as rotas que vão ser criadas no projeto, da pra usar o próprio navegador, mas só pode enviar requisições do tipo 'get', e os dados que voltam não são já formatados. Pra usar as outras requisições como post, put e delete, precisa usar softwares de terceiros, como o insomnia. Ele open source desenvolvido em javascript. Ele é um testador de rotas pra APIs, como os outros (postman e etc...), só colocar a url da API e o caminho da rota

#### Agora abra o insomnia no seu computador
* Criar um novo projeto clicando no ícone de setinha
* Dar um nome para esse projeto
* Depois, criar uma coleção de requisições para esse projeto
* Cliqua em 'New Collection'
* Vamos criar a primeira requisição para a API clicando no botão 'New HTTP Request', indicado na tela a seguir
* Da pra add outras requisições clicando no ícone
* Por padrão a requisição é criada no método GET
* Da pra alterar o método da requisição clicando no íconde de seta para baixo
* Agora só precisa colocar a url da nossa API com a porta que definimos (http://localhost:3000) e as rotas(/api/listar) que criadas no arquivo rotas.js
* Após validar que a API ta rodando, executar a ação da rota clicando no botão 'Send'
* O Insomnia deve retornar com a mensagem descrita no método GET do nosso arquivo de rotas
