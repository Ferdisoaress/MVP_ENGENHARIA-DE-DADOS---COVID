MVP – [Sprint: Engenharia de Dados] – Análise da COVID-19
Este MVP visa criar um pipeline de dados na nuvem utilizando o Databricks, com estrutura em modelo estrela, que integre informações sobre casos, mortes e vacinação por país e data, permitindo análises comparativas. Os dados foram coletados do Kaggle e carregados diretamente no Databricks Community Edition.

Objetivo Geral
Desenvolver um MVP de engenharia de dados na nuvem, utilizando o Databricks, para consolidar e analisar dados sobre a pandemia de COVID-19, com foco em compreender os impactos da vacinação na evolução de casos e mortes, através de um modelo de dados analítico em estrela.
Objetivos específicos
1.	Realizar a ingestão, tratamento e transformação dos dados de casos/mortes e vacinação no Databricks.
2.	Modelar os dados utilizando a abordagem dimensional (modelo estrela), com fato e dimensões adequadas.
3.	Integrar as duas bases de dados em um modelo analítico único, utilizando chaves comuns como país e data.
4.	Construir visualizações e análises exploratórias para responder perguntas relevantes sobre a pandemia.
5.	Identificar padrões e possíveis correlações entre o avanço da vacinação e a redução de casos/mortes.
6.	Avaliar a qualidade e integridade dos dados utilizados.

Tecnologias Utilizadas
Databricks Community Edition – Plataforma de desenvolvimento e execução do pipeline de dados.
 Apache Spark / PySpark – Processamento distribuído e manipulação de dados com DataFrames.
Delta Lake – Armazenamento em camadas (Bronze, Silver e Gold), garantindo versionamento e integridade dos dados.
SQL (no Databricks) – Consultas para transformação, análise e validação dos dados.
Conjuntos de dados Kaggle – Bases de dados públicas sobre COVID-19 e vacinação
COVID-19 World Vaccination Progress
Covid Cases and Deaths WorldWide
Licença de uso open.
Modelagem Estrela – Estrutura de dados organizada em fato e dimensões para facilitar análises.
Visualizações com PySpark + Pandas + Matplotlib – Criação de gráficos para interpretação dos dados.

Modelagem e Catálogo de dados
Foi adotado um modelo em estrela, com tabelas factuais consolidadas na camada Gold. As principais tabelas construídas foram:
- vacinas_total_por_pais_fabricante
- casos_mortes_por_pais
- vacinas_casos_mortes_flat
Abaixo segue o Catálogo de Dados contendo os principais atributos das tabelas utilizadas.
**Tabela: vacinas_total_por_pais_fabricante**
- pais (string): Nome do país
- fabricante (string): Nome do fabricante da vacina
- total_vacinas (long): Total de vacinas aplicadas por fabricante no país
**Tabela: casos_mortes_por_pais**
- pais (string): Nome do país
- total_casos (long): Total de casos registrados
- total_mortes (long): Total de mortes registradas
- population (long): População estimada do país
**Tabela: vacinas_casos_mortes_flat**
- pais (string): Nome do país
- fabricante (string): Nome do fabricante da vacina
- total_vacinas (long): Total de vacinas aplicadas
- total_casos (long): Total de casos registrados
- total_mortes (long): Total de mortes registradas
- population (long): População estimada do país

❓ Perguntas e análises que o MVP buscou responder.
1. Como evoluíram os casos e mortes por COVID-19 ao longo do tempo em diferentes países?
Foi possível observar que países como Itália, EUA e Brasil apresentaram picos de casos em momentos distintos, com grande volume de mortes concentradas nos primeiros meses de pandemia. A evolução mostrou uma tendência de queda nos países que avançaram mais rapidamente na vacinação.
2. Qual o impacto do avanço da vacinação na redução de casos e mortes por país ou continente?
Ao relacionar o número total de vacinas aplicadas com o total de mortes, percebemos uma correlação inversa: países com maior vacinação apresentaram tendência de queda mais acentuada nas mortes. Entretanto, essa relação nem sempre se mostrou direta, evidenciando a necessidade de considerar fatores complementares como variantes e medidas de contenção.
3. Quais países apresentaram a maior velocidade de vacinação e como isso refletiu nos indicadores da pandemia?
Israel, Emirados Árabes Unidos e Reino Unido apresentaram altas taxas de vacinação em curto espaço de tempo. Esses países registraram uma queda mais rápida nos indicadores de mortes, o que sugere eficácia nas estratégias de imunização e campanhas públicas.
4. Existe uma defasagem temporal média entre o início da vacinação e a queda nos números de mortes?
Sim. Observou-se que a redução nos indicadores de morte se torna mais visível entre 30 e 60 dias após o início da vacinação em massa, considerando dados agregados por país.
5. Quais países apresentaram comportamento fora da média (casos/mortes altos mesmo com vacinação avançada)?
O Chile e os EUA são exemplos de países com alto volume de vacinação que continuaram enfrentando picos de casos em determinados períodos. Isso reforça a influência de fatores como comportamento da população, presença de variantes e políticas públicas locais.
6. Há países onde os dados de vacinação não coincidem com a queda de casos, indicando outros fatores influenciando?
Sim. Em países como Rússia e Índia, mesmo com avanço na vacinação, os dados de casos e mortes se mantiveram elevados por mais tempo. Fatores como densidade populacional, cobertura real da vacinação e confiabilidade dos dados impactam essa análise.

Caderno

O notebook principal com todo o pipeline de dados está disponível no link abaixo: 

Organização do repositório
•	notebook/: notebook completo com o pipeline e análises
•	dataset/: referência da fonte de dados usada (Kaggle)

Fonte de dados 
Este projeto utiliza o conjunto de dados público do Kaggle

Autoavaliação
Durante a execução do projeto, o objetivo principal foi construir um pipeline de engenharia de dados funcional, aplicar conceitos de transformação com modelo estrela e criar análises de valor com base em dados reais. Com base no trabalho concluído, acredito que os objetivos foram atingidos.

Entre as principais dificuldades enfrentadas, destacam-se:
•	Tratamento de dados inconsistentes: as bases exigiram múltiplas limpezas e conversões, especialmente para garantir integridade nas colunas numéricas.
•	Problemas com schemas e partições: alguns erros no Databricks, como conflitos de schema, exigiram ajustes de configuração e uso de mergeSchema.
•	União de tabelas complexas: por envolver junções de fontes distintas, foi necessário alinhar nome de colunas e formatos para garantir que as queries funcionassem.
Apesar das dificuldades, o aprendizado técnico foi enriquecedor, especialmente no uso do PySpark e do Databricks como ferramenta de processamento em larga escala.

Trabalhos Futuros
Como sugestões para evolução do projeto:
•	Adicionar a dimensão temporal ao modelo, para análise de tendências mais apuradas.
•	Explorar visualizações mais avançadas, com dashboards interativos em Power BI ou Plotly.
•	Incorporar novas variáveis, como lockdowns, taxa de testagem ou mobilidade populacional.
•	Utilizar machine learning para prever evolução de casos com base no histórico por país.


