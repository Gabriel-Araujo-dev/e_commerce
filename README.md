# 🛒 E-commerce — Integração de Dados com SQL

Projeto desenvolvido durante a formação **Profissão: Cientista de Dados da EBAC**, com foco em **SQL, integração de tabelas e preparação de dados para análise e visualização**.

---

## 🎯 Objetivo

Consolidar dados transacionais e cadastrais de um e-commerce por meio de **SQL**, preparando uma base estruturada para análises de vendas, perfil dos clientes e visualizações em ferramentas de Business Intelligence.

O projeto foi desenvolvido como etapa de preparação de dados para construção de um dashboard interativo em ferramentas como **Looker Studio** ou **Power BI**.

---

## 📊 Sobre os dados

O projeto utiliza duas tabelas principais:

- **Tabela de Transações:** informações relacionadas às compras realizadas;
- **Tabela de Clientes:** informações cadastrais e demográficas dos clientes.

As tabelas são relacionadas por meio da chave:

```text
ID_CLIENT
```

---

## 🛠️ Tecnologias e ferramentas

- Python
- Pandas
- SQLite
- SQL
- Looker Studio
- Power BI
- Jupyter Notebook

---

## 🔎 Etapas do projeto

### 1. 📥 Carregamento das bases

As tabelas foram carregadas a partir de arquivos CSV:

```python
df_transacoes = pd.read_csv(
    "TB_TRANSACOES_PROJETO_ECOMM.csv",
    delimiter=";"
)

df_clientes = pd.read_csv(
    "TB_CLIENTES_PROJETO_ECOMM.csv",
    delimiter=";"
)
```

---

### 2. 🗄️ Modelagem e integração com SQLite

As duas bases foram utilizadas em um banco de dados SQLite para permitir a realização da integração por meio de consultas SQL.

A relação entre as tabelas foi estabelecida pela coluna `ID_CLIENT`.

---

### 3. 🔗 Escolha do JOIN

Foi utilizado um **INNER JOIN**.

A escolha foi baseada no objetivo do projeto: disponibilizar para o dashboard apenas os registros que possuíam simultaneamente informações de transação e cadastro do cliente.

A análise das bases identificou:

- 367 registros de transações;
- 241 IDs de clientes distintos nas transações;
- 175 clientes cadastrados;
- 71 transações associadas a clientes sem cadastro;
- 5 clientes cadastrados sem transações;
- 296 registros resultantes do `INNER JOIN`.

Dessa forma, a base final prioriza a consistência das informações utilizadas nas análises demográficas e geográficas.

---

### 4. 📤 Exportação da base consolidada

Após a integração das tabelas, os dados resultantes foram preparados para exportação em formato CSV.

Essa etapa permite utilizar a base consolidada em ferramentas de visualização e Business Intelligence.

---

### 5. 📊 Visualização e dashboard

A base consolidada foi preparada para utilização em ferramentas como:

- **Looker Studio**
- **Power BI**

Entre as análises propostas para o dashboard estão:

- Total de vendas;
- Número de transações;
- Distribuição geográfica dos clientes;
- Perfil demográfico;
- Informações relacionadas às vendas.

> **Nota:** o foco do notebook enviado está principalmente na integração e preparação dos dados. A construção visual do dashboard é uma etapa posterior realizada a partir da base consolidada.

---

## 💡 Pontos importantes

Como um mesmo cliente pode realizar múltiplas transações, métricas relacionadas à quantidade de clientes devem considerar a utilização de `DISTINCT` quando necessário, evitando a contagem duplicada de clientes.

Outro ponto importante foi a escolha do `INNER JOIN`: embora essa abordagem exclua transações sem cadastro correspondente, ela produz uma base mais consistente para análises que dependem de informações demográficas e geográficas.

---

## 🧠 Principais aprendizados

Este projeto permitiu praticar:

- Leitura e organização de dados;
- Modelagem de banco de dados relacional;
- SQL;
- `JOIN`;
- `INNER JOIN`;
- Integração de múltiplas tabelas;
- Exportação de dados para CSV;
- Preparação de dados para BI;
- Conceitos de métricas e granularidade;
- Integração entre Python, SQLite e ferramentas de visualização.

---

## 📂 Estrutura sugerida do repositório

```text
ecommerce-sql-dashboard/
│
├── data/
│   ├── TB_TRANSACOES_PROJETO_ECOMM.csv
│   ├── TB_CLIENTES_PROJETO_ECOMM.csv
│   └── base_consolidada.csv
│
├── notebooks/
│   └── M26_Ecommerce_SQL_Dashboard.ipynb
│
├── dashboard/
│   └── README.md
│
└── README.md
```

---

## 📚 Formação

Projeto desenvolvido durante a formação **Profissão: Cientista de Dados — EBAC**.

## 👤 Autor

**Antônio Gabriel Vieira Araújo**

[GitHub](https://github.com/Gabriel-Araujo-dev) · [LinkedIn](https://www.linkedin.com/in/gabrielaraujo05/)
