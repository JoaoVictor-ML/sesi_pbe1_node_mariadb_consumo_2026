# Backend — Gestão de Consumo Energético | SESI

## Sobre o projeto

O **Backend de Gestão de Consumo Energético** é um projeto acadêmico desenvolvido no curso técnico de Desenvolvimento de Sistemas do SENAI. A proposta consiste em desenvolver uma API para auxiliar o SESI no monitoramento do consumo de energia elétrica em diferentes locais e equipamentos.

O sistema permite registrar os consumos energéticos, identificar os equipamentos monitorados e classificar os níveis de consumo. Com essas informações, busca-se facilitar a identificação de possíveis desperdícios e contribuir para uma gestão mais eficiente dos recursos energéticos.

## Objetivos

- Desenvolver uma API para gerenciamento de usuários e registros de consumo energético.
- Implementar operações CRUD para usuários e consumos.
- Implementar autenticação por login.
- Registrar o consumo em quilowatt-hora (kWh), associado ao local, equipamento e mês de referência.
- Classificar o consumo como baixo, normal ou elevado.
- Calcular a média de consumo energético dos registros cadastrados.
- Modelar a estrutura do sistema por meio de diagramas de banco de dados e de classes.

## Requisitos funcionais

| Código | Requisito | Descrição |
|---|---|---|
| RF001 | CRUD de usuários | Cadastrar, consultar, atualizar e excluir usuários. |
| RF002 | Login | Permitir a autenticação de usuários cadastrados. |
| RF003 | CRUD de consumo | Gerenciar os registros de consumo energético. |
| RF004 | Resumo de consumo | Calcular e apresentar a média de consumo de energia em kWh. |

## Requisito não funcional

**NF001 — Diagrama de Classes:** elaborar o diagrama utilizando o [draw.io](https://app.diagrams.net/) e salvar a imagem no formato PNG dentro da pasta `docs`.

## Modelagem do banco de dados

O banco de dados utilizado é o `gestao_residuos`, conforme definido no script SQL fornecido para a atividade, e possui duas tabelas principais:

- **usuario:** armazena o identificador, nome, e-mail e senha dos usuários.
- **consumo:** registra o usuário responsável, o local monitorado, o equipamento, o consumo em kWh, o mês de referência e a classificação do consumo.

A tabela `consumo` possui uma chave estrangeira (`usuarioId`) que estabelece o relacionamento entre cada registro de consumo e seu respectivo usuário.

### Classificação do consumo

| Campo | Descrição |
|---|---|
| Local | Identifica o ambiente monitorado. |
| Equipamento | Identifica o equipamento elétrico. |
| Consumo (kWh) | Quantidade de energia consumida. |
| Mês de referência | Período ao qual o registro pertence. |
| Status | Baixo, Normal ou Elevado. |

## Tecnologias e ferramentas

- **JavaScript** — implementação da lógica do back-end.
- **Node.js** — ambiente de execução.
- **Express** — criação do servidor e gerenciamento das rotas da API.
- **MySQL** — gerenciamento do banco de dados relacional.
- **SQL** — criação, relacionamento e consulta das tabelas.
- **Visual Studio Code** — ambiente de desenvolvimento.
- **draw.io** — elaboração dos diagramas.
- **Postman** — ferramenta para testar as requisições HTTP.

## Estrutura do projeto

```text
backend_energia/
├── db/
│   └── script.sql
├── docs/
│   ├── der_energia.png
│   └── diagrama_classes.png
├── src/
│   ├── controllers/
│   │   ├── consumo.js
│   │   └── usuario.js
│   ├── db.js
│   └── routes.js
└── server.js
```

## Como executar

1. Instale o [Node.js](https://nodejs.org/) e o [MySQL](https://dev.mysql.com/downloads/).
2. Clone o repositório e acesse a pasta do projeto.
3. Execute o script `db/script.sql` no MySQL para criar e popular o banco de dados.
4. Configure a conexão com o banco de dados no arquivo `src/db.js`.
5. Instale as dependências:

   ```bash
   npm init -y
   npm install express mysql2
   ```

6. Inicie o servidor:

   ```bash
   node server.js
   ```

7. Utilize o Postman ou outra ferramenta compatível para testar as rotas da API.

> **Observação:** os comandos pressupõem uma implementação com Express e o driver `mysql2`. Ajuste-os conforme a estrutura desenvolvida.

