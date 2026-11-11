#  Circuito Terê Verde - API Back-End


O **Circuito Terê Verde** é um sistema web desenvolvido para centralizar a divulgação e o gerenciamento de atrativos turísticos, trilhas, cachoeiras e eventos na região de Teresópolis - RJ. 

Este repositório contém a **API Back-End** do MVP (Produto Mínimo Viável), responsável por fornecer e gerenciar os dados de forma estruturada, segura e eficiente para a aplicação Front-End.

---

##  Sumário
- [Arquitetura e Padrões](#-arquitetura-e-padrões)
- [Funcionalidades (MVP)](#-funcionalidades-mvp)
- [Tecnologias Utilizadas](#️-tecnologias-utilizadas)
- [Estrutura do Projeto](#-estrutura-do-projeto)
- [Documentação da API](#-documentação-da-api)
- [Instalação e Uso](#-instalação-e-uso)
- [Equipe](#-equipe)

---

##  Arquitetura e Padrões

O projeto segue os princípios de separação de responsabilidades (MTV/MVC), isolando as rotas, regras de negócio (controladores) e o acesso ao banco de dados para garantir a manutenibilidade e escalabilidade do código.

---

##  Funcionalidades (MVP)


-- 
##  Segurança & Acesso
- **Autenticação de Administradores:** Verificação de credenciais (login e senha) para liberação de acesso às funções administrativas.

##  Gestão de Eventos
- **Listagem Pública (GET):** Retorno de todos os eventos cadastrados em formato JSON.
- **Cadastro de Eventos (POST):** Recebimento e validação de dados (título, data, local, descrição e imagem). O servidor recusa requisições com campos obrigatórios vazios.
- **Exclusão de Eventos (DELETE):** Remoção de eventos através do ID (eventos fixos não podem ser apagados).
- **Upload de Imagens:** Armazenamento local de imagens diretamente na estrutura do servidor.

---

##  Tecnologias Utilizadas

- **Linguagem / Plataforma:** Node.js
- **Framework:** NestJS / Express
- **Banco de Dados:** SQLite (banco relacional leve, ideal para o MVP sem depender de servidores externos complexos)
- **ORM:** Prisma
- **Controle de Versão:** Git & GitHub

---

##  Estrutura do Projeto

A organização segue a divisão clara de pastas e responsabilidades exigida pelos requisitos não-funcionais:

```text
circuito-tere-verde-backend/
├── docs/
│   └── Requisitos MVP Terê Verde - Back End.pdf
├── src/
│   ├── controllers/      # Lógica de negócio e coordenação de respostas
│   ├── routes/           # Definição dos endpoints da API REST
│   ├── models/           # Representação dos dados (Schema do Prisma)
│   ├── middlewares/      # Interceptadores (ex: validação, autenticação, upload)
│   └── index.js          # Ponto de entrada da aplicação
├── uploads/              # Armazenamento local das imagens de eventos
├── prisma/               # Migrations e schema do banco
├── .env.example          # Exemplo de variáveis de ambiente
├── package.json          # Dependências do projeto
└── README.md             # Documentação do projeto
