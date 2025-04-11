# 🧪 MVP – [Sprint: Engenharia de Dados] – Análise da COVID-19

Este MVP visa criar um pipeline de dados na nuvem utilizando o **Databricks**, com estrutura em **modelo estrela**, que integre informações sobre **casos**, **mortes** e **vacinação** por país e data, permitindo **análises comparativas**. Os dados foram coletados do **Kaggle** e carregados diretamente no **Databricks Community Edition**.

---

## 🎯 Objetivo Geral

Desenvolver um MVP de engenharia de dados na nuvem, utilizando o **Databricks**, para consolidar e analisar dados sobre a pandemia de **COVID-19**, com foco em compreender os impactos da vacinação na evolução de casos e mortes, através de um modelo de dados analítico em **estrela**.

### ✅ Objetivos Específicos

1. Realizar a ingestão, tratamento e transformação dos dados de casos/mortes e vacinação no Databricks.  
2. Modelar os dados utilizando a abordagem dimensional (modelo estrela), com fato e dimensões adequadas.  
3. Integrar as duas bases de dados em um modelo analítico único, utilizando chaves comuns como país e data.  
4. Construir visualizações e análises exploratórias para responder perguntas relevantes sobre a pandemia.  
5. Identificar padrões e possíveis correlações entre o avanço da vacinação e a redução de casos/mortes.  
6. Avaliar a qualidade e integridade dos dados utilizados.  

---

## 💻 Tecnologias Utilizadas

- **Databricks Community Edition** – Plataforma para desenvolvimento do pipeline de dados.  
- **Apache Spark / PySpark** – Processamento distribuído e manipulação de dados com DataFrames.  
- **Delta Lake** – Armazenamento em camadas (Bronze, Silver e Gold).  
- **SQL (no Databricks)** – Consultas para transformação e análise dos dados.  
- **Kaggle Datasets**:
  - *COVID-19 World Vaccination Progress*  
  - *Covid Cases and Deaths WorldWide*  
- **Visualizações**: PySpark + Pandas + Matplotlib  
- **Modelo Estrela**: Estrutura com tabelas fato e dimensão  

---

## 🧱 Modelagem Estrela & Catálogo de Dados

Foi adotado um modelo dimensional com **camadas Delta Lake**. As tabelas principais da **camada Gold** são:

### 🟨 `vacinas_total_por_pais_fabricante`
| Coluna       | Tipo   | Descrição                                |
|--------------|--------|------------------------------------------|
| pais         | string | Nome do país                             |
| fabricante   | string | Nome do fabricante da vacina             |
| total_vacinas| long   | Total de vacinas aplicadas               |

### 🟨 `casos_mortes_por_pais`
| Coluna       | Tipo   | Descrição                                |
|--------------|--------



