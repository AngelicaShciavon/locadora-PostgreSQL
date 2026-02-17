# Locadora - Banco de Dados

Projeto de banco de dados para gerenciamento de uma locadora de filmes/séries (ou DVDs, Blu-rays, etc.).  
Inclui scripts de criação de schema, inserção de dados iniciais e consultas de exemplo (simples e complexas), compatíveis com **MySQL** e **PostgreSQL**.

## Tecnologias Utilizadas

- **SGBDs**: MySQL e PostgreSQL
- **Ferramentas de modelagem**: MySQL Workbench (.mwb)
- **Linguagem**: SQL puro

## Estrutura do Projeto
locadora/
├── README.md                  ← Este arquivo
├── .gitignore
│
├── docs/                      ← Documentação visual
│   ├── locadora_v1.pdf
│   └── locadora_v2.png
│
├── model/                     ← Modelagem do banco
│   └── locadora.mwb
│
├── mysql/                     ← Scripts específicos para MySQL
│   ├── schema/
│   │   ├── v1.sql             ← Versão inicial
│   │   └── v2.sql             ← Versão atualizada (melhorias, correções)
│   ├── data/
│   │   └── insert_dados_iniciais.sql
│   └── queries/
│       ├── consultas_simples.sql
│       └── consultas_complexas.sql
│
└── postgres/                  ← Scripts específicos para PostgreSQL
├── schema/
│   ├── v1.sql
│   └── v2.sql
├── data/
│   └── insert_dados_iniciais.sql
└── queries/
├── consultas_simples.sql
└── consultas_complexas.sql
text## Como Usar / Rodar o Projeto

1. **Crie o banco de dados**  
   - MySQL: `CREATE DATABASE locadora;`
   - PostgreSQL: `CREATE DATABASE locadora;`

2. **Execute o schema (ordem importa!)**  
   - Rode primeiro o arquivo de schema da versão desejada (ex: `v2.sql`)  
     MySQL → `mysql -u seu_usuario -p locadora < mysql/schema/v2.sql`  
     PostgreSQL → `psql -U seu_usuario -d locadora -f postgres/schema/v2.sql`

3. **Insira os dados iniciais**  
   Rode o script de seed:  
   - MySQL → `mysql -u seu_usuario -p locadora < mysql/data/insert_dados_iniciais.sql`  
   - PostgreSQL → `psql -U seu_usuario -d locadora -f postgres/data/insert_dados_iniciais.sql`

4. **Teste as consultas**  
   Abra os arquivos em `queries/` e execute as SELECTs no seu cliente SQL favorito (DBeaver, pgAdmin, MySQL Workbench, etc.).

## Conteúdo Principal do Banco

- Tabelas principais: cliente, filme, locacao, genero, etc. (ver model/locadora.mwb para o diagrama completo)
- Dados de exemplo: alguns clientes, filmes clássicos e locações fictícias
- Consultas prontas: buscas simples (listar filmes por gênero) e complexas (relatórios com joins, agregações, subqueries)

## Próximos Passos / Melhorias Futuras

- Adicionar procedures e functions
- Triggers (ex: atualizar estoque ao locar/devolver)
- Views para relatórios frequentes
- Scripts de backup e restore
- Migração para versionamento com Flyway / Liquibase (pastas numeradas 001_, 002_...)

## Licença

MIT License – sinta-se à vontade para usar, modificar e compartilhar!

Feito em Santa Ernestina-SP  
Última atualização: Fevereiro 2026