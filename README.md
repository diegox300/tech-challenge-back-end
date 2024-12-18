# BACK END DE BLOGGER V 1.1

BACK END DE BLOGGER V 1.1 é uma API em NodeJS que integra um Banco de Dados MongoDB, desenvolvida como atividade que integra os conhecimentos adquiridos durante o módulo de Backend e Qualidade de software da Pós Tech FIAP Full Stack Development do Grupo 1 Turma 2FSDT.

## Objetivo

O objetivo desta API é gerenciar postagens de blog por meio de operações de CRUD (Criar, Ler, Atualizar e Deletar), facilitando a gestão de conteúdo para administradores e autores.

## Relato de experiências e desafios

Desde o início, o grupo decidiu versionar o código diretamente no GitHub, o que permitiu uma organização eficiente da estrutura inicial e dos padrões do projeto. A cada etapa da implementação da API, todos os integrantes eram notificados sobre novos Pull Requests (PRs) abertos na branch principal, garantindo a colaboração contínua e a revisão conjunta do código.

As aulas da Fase 2 foram fundamentais para o desenvolvimento do projeto, fornecendo a base necessária para avançarmos com confiança. Sempre que surgiam dúvidas ou obstáculos, reassistir as aulas ou buscar soluções na internet tornou o processo de resolução de problemas mais ágil e eficaz.

Além disso, os encontros semanais de todo o grupo desempenharam um papel crucial, promovendo discussões e alinhamentos que contribuíram para o progresso contínuo e a conclusão bem-sucedida do projeto.

---

## Video de apresentação da API

[Assista ao vídeo de apresentação aqui](https://youtu.be/51WeIR_iRRY)

---

## Tecnologias utilizadas

- Node.js
- TypeScript
- MongoDB
- Express
- Jest
- Swagger
- Docker

---

## Ambientes

Produção

A branch Main reflete diretamente na API em produção, que está hospedada na Vercel. Qualquer atualização ou merge realizado nessa branch será automaticamente refletido na API em ambiente de produção, portanto, é essencial que o código seja revisado cuidadosamente antes de ser integrado para garantir a estabilidade do sistema.

---

## Ambiente de Produção

Branch Principal: Utilizamos a branch Main como nossa branch padrão para o ambiente de [produção](https://tech-challenge-back-end.vercel.app/api-docs/)

Deploy: O deployment das aplicações é realizado através da plataforma [Vercel](https://vercel.com/)

Banco de Dados: Para o armazenamento de dados em produção, utilizamos o banco de dados [MongoDB](https://www.mongodb.com/)

---

## Ambiente de Desenvolvimento

Para utilizar a API local:

- Clonar código no GitHub:

```bash
git clone https://github.com/diegox300/Back-End-Blogger-Fiap.git
```

## Instalação da aplicação

Este projeto está pronto para ser executado em um ambiente Docker. Por este motivo, será necessária apenas a instalação do Docker, não sendo necessária a instalação manual do projeto. Também não será necessária a instalação manual do banco de dados (MongoDB).

Caso não tenha o Docker instalado, siga as instruções para seu sistema operacional na [documentação oficial do Docker](https://docs.docker.com/get-started/get-docker/).

- Subir a aplicação utilizando Docker:

```bash
docker-compose up --build
```

##### Conferir os ENDPOINTS da api:

Para facilitar a integração e uso da nossa API, disponibilizamos uma documentação detalhada através do **Swagger**. Nela, você encontrará todos os endpoints disponíveis, métodos suportados, exemplos de requisições e respostas, bem como informações sobre parâmetros necessários.

```bash
http://localhost:8000/api-docs
```

---

##### Executando Testes Unitários Local:

Para garantir que todas as funcionalidades da API estejam funcionando corretamente, é recomendado executar os testes unitários. Siga as etapas abaixo para executar os testes:

```bash
npm install
npm test
```

---

Duvidas e feedback:

Para dúvidas ou sugestões, entre em contato:
• Email: postechfiap4@gmail.com

---

## Estrutura do Projeto - Padrão MVC

Este projeto segue uma abordagem baseada no padrão MVC (Model-View-Controller), adaptada para o desenvolvimento da API.

A estrutura do projeto está organizada da seguinte forma:

Model (Camada de Modelos): é responsável pela representação e manipulação dos dados. Aqui, as definições de schemas, entidades e as interações com o banco de dados são implementadas. Exemplo: validação e persistência dos dados no MongoDB.

Controller (Camada de Controladores): é responsável por receber as requisições HTTP, processá-las, invocar a lógica de negócios no Model, e devolver a resposta apropriada ao cliente. A lógica dos endpoints da API é centralizada nos controladores, que garantem que as requisições sejam tratadas adequadamente.

Routes (Rotas): definem os endpoints da API e mapeiam as URLs para os controladores correspondentes. Elas permitem que as requisições HTTP sejam direcionadas para os controladores corretos com base no endpoint acessado.

- Estrutura Básica do Projeto

```markdown
src
├── app.ts
├── config
│ └── cloudinary.ts
├── db
│ └── database.ts
├── docs
│ ├── Padroes_de_commits(Commit_Patterns).pdf
│ ├── por_que_utilizar_mongoDB.pdf
│ └── versionamento_semantico_2.0.0.pdf
├── env
│ └── index.ts
├── errors
│ ├── EmailAlreadyExistsError.ts
│ ├── InvalidCredentialsError.ts
│ └── UserNotFoundError.ts
├── http
│ └── controllers
│ ├── post
│ │ ├── create-post.ts
│ │ ├── deletePostById.ts
│ │ ├── find-post.ts
│ │ ├── find-posts-by-letter.ts
│ │ ├── get-all-posts-pagination.ts
│ │ ├── get-all-posts.ts
│ │ └── update-post.ts
│ └── user
│ ├── create-user.ts
│ ├── get-all-users.ts
│ ├── get-user-by-email.ts
│ ├── get-user-by-id.ts
│ └── login-user.ts
├── middleware
│ ├── asyncHandler.ts
│ ├── auth.ts
│ ├── error.ts
│ ├── swagger.ts
│ ├── upload.ts
│ ├── validateEmail.ts
│ └── validateObjectId.ts
├── models
│ ├── post.model.ts
│ └── user.model.ts
├── repositories
│ ├── post.repository.ts
│ └── user.repository.ts
├── routes
│ ├── index.ts
│ ├── post.routes.ts
│ └── user.routes.ts
├── server.ts
├── swagger
│ └── swagger.json
├── tests
│ ├── db
│ │ └── database.test.ts
│ ├── env
│ │ └── index.test.ts
│ ├── http
│ │ └── controllers
│ │ └── post
│ │ ├── create-post.test.ts
│ │ ├── deletePostById.test.ts
│ │ ├── find-post.test.ts
│ │ ├── get-all-posts.test.ts
│ │ └── update-post.test.ts
│ ├── middleware
│ │ └── validateObjectId.test.ts
│ ├── post.model.test.ts
│ ├── post.repository.test.ts
│ ├── post.routes.test.ts
│ ├── server
│ │ └── server.test.ts
│ ├── swagger
│ │ └── swagger.test.ts
│ └── use-cases
│ ├── delete-post-usecase.test.ts
│ ├── find-posts-usecase.test.ts
│ ├── get-all-posts-usecase.test.ts
│ └── update-post-usecase.test.ts
└── use-cases
├── factory
│ ├── posts
│ │ ├── make-create-posts-usecase.ts
│ │ ├── make-delete-post-usecase.ts
│ │ ├── make-find-posts-by-letter-usecase.ts
│ │ ├── make-find-posts-usecase.ts
│ │ ├── make-get-all-posts-pagination-usecase.ts
│ │ ├── make-get-all-posts-usecase.ts
│ │ └── make-update-post-usecase.ts
│ └── user
│ ├── make-create-user-usecase.ts
│ ├── make-find-user-by-email-usecase.ts
│ ├── make-find-user-by-id-usecase.ts
│ ├── make-get-all-users-usecase.ts
│ ├── make-get-user-usecase.ts
│ └── make-login-user-usecase.ts
├── posts
│ ├── create-posts-usecase.ts
│ ├── delete-post-usecase.ts
│ ├── find-posts-by-letter-usecase.ts
│ ├── find-posts-usecase.ts
│ ├── get-all-posts-pagination-usecase.ts
│ ├── get-all-posts-usecase.ts
│ └── update-post-usecase.ts
└── user
├── create-user-usecase.ts
├── find-user-by-email-usecase.ts
├── find-user-by-id-usecase.ts
├── get-all-users-usecase.ts
├── get-user-usecase.ts
└── login-user-usecase.ts
```

A API foca na gestão de dados e respostas via JSON, onde a camada View não é necessária, já que não há rendering de interfaces.

No projeto, foi aplicada a Inversão de Dependência (DIP) para desacoplar módulos de alto e baixo nível, permitindo maior flexibilidade na troca de implementações e facilitando a manutenção e testes. Com o uso de injeção de dependência, a aplicação torna-se mais modular e pronta para crescer.

Além disso, os outros princípios do SOLID foram seguidos para garantir escalabilidade:

- SRP: Cada classe tem uma única responsabilidade,
- OCP: O código está aberto para extensões sem precisar de modificações,
- LSP: Classes derivadas podem substituir as classes base sem alterar o comportamento,
- ISP: Interfaces específicas evitam dependências desnecessárias.

Esses princípios juntos promovem um design flexível e escalável, facilitando a adição de novas funcionalidades sem comprometer a estrutura existente.

---
