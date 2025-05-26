# Sistema ERP - Gestão Empresarial Integrada

![Status](https://img.shields.io/badge/status-em%20desenvolvimento-yellow)

Um sistema de Planejamento de Recursos Empresariais (ERP) completo, construído com tecnologias modernas para ser robusto, escalável e de fácil manutenção. Este projeto visa criar uma solução integrada para gestão de vendas, estoque, finanças e clientes.

---

## 📖 Tabela de Conteúdos

* [Sobre o Projeto](#-sobre-o-projeto)
* [🚀 Tecnologias Utilizadas](#-tecnologias-utilizadas)
* [▶️ Como Começar](#️-como-começar)
* [⚙️ Rodando a Aplicação](#️-rodando-a-aplicação)
* [🗺️ Roadmap](#️-roadmap)
* [📜 Licença](#-licença)
* [✍️ Autor](#️-autor)

---

## 💻 Sobre o Projeto

O objetivo deste projeto é desenvolver um sistema ERP modular do zero, aplicando as melhores práticas de desenvolvimento de software, arquitetura e gestão de banco de dados. A aplicação está sendo construída para ser uma API RESTful robusta, pronta para ser consumida por qualquer front-end (web ou mobile).

---

## 🚀 Tecnologias Utilizadas

Este projeto é construído com as seguintes tecnologias:

* **Back-end:**
    * [Node.js](https://nodejs.org/)
    * [TypeScript](https://www.typescriptlang.org/)
    * [NestJS](https://nestjs.com/)
* **Banco de Dados:**
    * [PostgreSQL](https://www.postgresql.org/)
    * [Prisma ORM](https://www.prisma.io/)
* **Ambiente:**
    * [Docker](https://www.docker.com/)

---

## ▶️ Como Começar

Para rodar este projeto no seu ambiente de desenvolvimento, siga os passos abaixo.

### **Pré-requisitos**

* Você precisa ter o [Node.js](https://nodejs.org/) (versão 18 ou superior) instalado.
* Você precisa ter o [Docker](https://www.docker.com/) e o Docker Compose instalados e rodando.
* Você precisa ter o [Git](https://git-scm.com/) instalado.

### **Instalação**

1.  **Clone o repositório:**
    ```bash
    git clone [https://github.com/mauricio-py/Sistema-ERP.git](https://github.com/mauricio-py/Sistema-ERP.git)
    cd Sistema-ERP
    ```

2.  **Inicie o banco de dados com Docker:**
    O banco de dados PostgreSQL roda em um contêiner Docker. Para iniciá-lo, use o seguinte comando (lembre-se de criar o contêiner como fizemos, ou adicione um `docker-compose.yml` no futuro).
    ```bash
    # Exemplo do comando que usamos para iniciar o banco
    docker run -d --name erp-db -e POSTGRES_PASSWORD=sua-senha-aqui -p 5432:5432 -v postgres_data:/var/lib/postgresql/data postgres
    ```

3.  **Instale as dependências do projeto:**
    ```bash
    npm install
    ```

4.  **Configure as Variáveis de Ambiente:**
    Existe um arquivo chamado `.env.example`. Renomeie-o para `.env` e preencha a `DATABASE_URL` com suas credenciais do PostgreSQL.
    ```env
    # .env
    DATABASE_URL="postgresql://postgres:sua-senha-aqui@localhost:5432/postgres"
    ```

5.  **Aplique as Migrations do Banco de Dados:**
    Este comando irá criar as tabelas do banco de dados de acordo com o schema do Prisma.
    ```bash
    npx prisma migrate dev
    ```

---

## ⚙️ Rodando a Aplicação

### **Modo de Desenvolvimento**

Para iniciar o servidor em modo de desenvolvimento com "hot-reload" (reinicia automaticamente ao salvar alterações):

```bash
npm run start:dev