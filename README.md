<div align="center">

  # Adopet API

  > API RESTful para uma empresa fictícia de adoção de animais, desenvolvido para um Challenge Back-End.

  <a>Potuguese</a> -
  <a href="./docs/en/README_en.md">English</a>

</div>

<div align="center" >

  ![Release](https://img.shields.io/github/v/release/jeff-pedro/api-adopet?display_name=tag&style=flat-square)
  [![Node Version](https://img.shields.io/badge/node-v20.12.2-blueviolet?style=flat-square&logo=node.js)](https://nodejs.org/download/)
  [![Code Style](https://img.shields.io/badge/code_style-eslint-ff69b4.svg?style=flat-square&logo=eslint)](https://eslint.org/)
  [![Code Formatter](https://img.shields.io/badge/code%20formatter-prettier-blue?style=flat-square&logo=prettier)](https://prettier.io/)
</div>

---

## 🤖 Tecnologias
- **Back-End**: API RESTful em NodeJS
- **Banco de Dados**: Postgres
- **ORM**: Sequelize
- **Express** como framework para construção de Aplicações Web

## 📋 Requisitos
- Node.js e NPM
- Banco de dados Postgres
- Docker e docker compose


## ⚙️ API

🧩 [adopet.api.sapituca.site](http://adopet.api.sapituca.site/)

🗂 [Documentação](https://documenter.getpostman.com/view/22093498/2sA35MxyP2)


## 🧑🏽‍💻 Usando

Clonar o repositório
```bash
git clone [repositório]
```

Seguir para o diretório da API
```bash
cd adopet-api/
```

🏗️ **Construindo and executando a aplicação**

Iniciar a API e o bando de dados
```bash
docker compose up --build -d
```

Migrar das tabelas do banco de dados
```bash
docker compose run api npx sequelize-cli db:migrate
```

> A API estará disponível em http://localhost:9000.

💣 **Testando a API**... 🤞🏽

Criar banco de dados de teste
```bash
docker compose run api npx sequelize-cli db:create --env test
```

Realizar a migração das tabelas
```bash
docker compose run api npx sequelize-cli db:migrate --env test
```

Executar todos testes
```bash
docker compose run api npm run test
```

Executar testes de integração
```bash
docker compose run api npm run test:integration
```

📦 **Contruindo uma Imagem**

Construa uma imagem ao executar: 
```shell
docker build -t adopet-api:latest .
```


## ♾️ CI/CD

**Github Actions** foi escolhido como ferramenta no desenvolvimento de CI pela simplicidade na construção de workflows, por estar integrado ao repositório da aplicação e por questões didáticas para explorar a ferramenta.

A escolha do **[Render](https://render.com/)** como plataforma de deploy da API e do Banco de Dados, foi devido a simplicidade na realização de deploys e ao plano gratuito que abrange banco de dados **Postgres**, deploy de **Web Services** construído em **Node.js**, além de dar suporte Continuos Deployment realizando **deploys automáticos** integrado às branchs do **Github**.


### 🧪 **Build e Testes**
Rotinas são executadas para testar a aplicação, construir um imagem do **Docker** e registrá-la no **Docker Hub** no momento que o repositório receber um **Pull Request** para a branch `main`.

### 🚀️ **Deploy**
O Banco de Dados e a API são constrúidos através dos serviços do **Render**, no qual disponibiliza sempre a última versão da aplicação ao realizar deploys automáticos baseados na branch `main` deste repositório.


## 📚 Referências
- [Docker's Node.js guide](https://docs.docker.com/language/nodejs/)
- [Custom Domains | Render Docs](https://docs.render.com/custom-domains#configuring-dns-to-point-to-render)
- [Configuring Namecheap DNS | Render Docs](https://docs.render.com/configure-namecheap-dns)
