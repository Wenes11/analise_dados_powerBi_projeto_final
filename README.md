# Desafio Power BI: Dashboard de Análise de RH e Projetos

## 1. Visão Geral do Projeto

Este projeto documenta a jornada completa de construção de um dashboard interativo no Power BI. O objetivo foi transformar dados brutos de um banco de dados MySQL em um relatório gerencial que fornece insights sobre a estrutura de colaboradores, departamentos e projetos de uma empresa fictícia.

O desafio abrangeu desde a configuração do ambiente e resolução de problemas técnicos até a aplicação de técnicas avançadas de ETL (Extração, Transformação e Carga) e modelagem de dados.

## 📊 Acesso ao Dashboard Interativo

O relatório final foi publicado no Power BI Service e pode ser acessado de forma interativa através do link abaixo:

**[Clique aqui para visualizar o dashboard online](https://app.powerbi.com/groups/me/reports/7d35a01d-094c-4a9f-b185-9d72c85bb7bc/2ca3d1a76d842f9c63cc?experience=power-bi)**

## 2. A Jornada: Desafios e Aprendizados

### Configuração do Ambiente e Fonte de Dados
A fase inicial do projeto demonstrou a importância da adaptabilidade. O plano original era utilizar o **Azure Database for MySQL**, mas devido a restrições na assinatura, foi necessário pivotar para uma solução com **banco de dados local**.

No **MySQL Workbench**, o script SQL original foi depurado para corrigir inconsistências e erros, incluindo:
* Violação de restrições `CHECK`.
* Falhas de `FOREIGN KEY` em tabelas com auto-relacionamento.
* Ajuste do `SQL_MODE` do servidor para permitir a inserção de dados específicos do script.

### Transformação de Dados (ETL) com Power Query
O coração do projeto foi o processo de ETL no Power Query, onde os dados brutos foram limpos, moldados e enriquecidos. Um desafio significativo de compatibilidade com o **MySQL Connector/.NET** foi contornado através da exportação dos dados para arquivos **CSV**, uma técnica de contingência comum no mercado.

As principais transformações aplicadas foram:

* **Profilagem e Limpeza:** Análise da qualidade e distribuição das colunas, correção de tipos de dados (especialmente valores monetários para **Número Decimal Fixo**) e tratamento estratégico de valores nulos.
* **Modelagem de Dados:** Criação de um modelo relacional dentro do Power BI, estabelecendo as relações corretas entre as 6 tabelas importadas.
* **Enriquecimento dos Dados (Mesclar Consultas / Joins):**
    * A tabela `employee` foi enriquecida com o nome do departamento (`Dname`), vindo da tabela `departament`.
    * Foi realizada uma **auto-mesclagem** (join da tabela com ela mesma) para adicionar os nomes dos supervisores de cada colaborador, uma técnica de modelagem mais avançada.
* **Transformação Estrutural:**
    * **Divisão de Colunas:** A coluna `Address` foi separada em `Rua`, `Cidade` e `Estado`.
    * **Mesclagem de Colunas:** Colunas como `Fname` e `Lname` foram unidas para criar um campo `Nome Completo`, melhorando a usabilidade no relatório.
* **Agrupamento de Dados (Group By):** Foi criada uma nova consulta sumarizada (`Contagem por Supervisor`) através da duplicação da consulta principal, uma boa prática para não destruir a tabela de fatos original.
* **Otimização do Modelo:** Remoção de colunas de ID redundantes para criar um modelo final mais limpo e performático.

### Criação do Dashboard
Com os dados tratados e modelados, a fase final foi a construção do relatório, focando em clareza e interatividade:

* **KPIs:** Cartões com os indicadores principais (Total de Funcionários, Total de Projetos).
* **Gráficos:** Um gráfico de barras para a análise de colaboradores por supervisor.
* **Tabela:** Uma visão detalhada das informações dos departamentos.
* **Interatividade:** Adição de um **Segmentador de Dados** que permite filtrar todo o relatório por cidade.

## 3. Visualização do Dashboard Final

![Dashboard Final](# Desafio Power BI: Dashboard de Análise de RH e Projetos

## 1. Visão Geral do Projeto

Este projeto documenta a jornada completa de construção de um dashboard interativo no Power BI. O objetivo foi transformar dados brutos de um banco de dados MySQL em um relatório gerencial que fornece insights sobre a estrutura de colaboradores, departamentos e projetos de uma empresa fictícia.

O desafio abrangeu desde a configuração do ambiente e resolução de problemas técnicos até a aplicação de técnicas avançadas de ETL (Extração, Transformação e Carga) e modelagem de dados.

## 📊 Acesso ao Dashboard Interativo

O relatório final foi publicado no Power BI Service e pode ser acessado de forma interativa através do link abaixo:

**[Clique aqui para visualizar o dashboard online](https://app.powerbi.com/groups/me/reports/7d35a01d-094c-4a9f-b185-9d72c85bb7bc/2ca3d1a76d842f9c63cc?experience=power-bi)**

## 2. A Jornada: Desafios e Aprendizados

### Configuração do Ambiente e Fonte de Dados
A fase inicial do projeto demonstrou a importância da adaptabilidade. O plano original era utilizar o **Azure Database for MySQL**, mas devido a restrições na assinatura, foi necessário pivotar para uma solução com **banco de dados local**.

No **MySQL Workbench**, o script SQL original foi depurado para corrigir inconsistências e erros, incluindo:
* Violação de restrições `CHECK`.
* Falhas de `FOREIGN KEY` em tabelas com auto-relacionamento.
* Ajuste do `SQL_MODE` do servidor para permitir a inserção de dados específicos do script.

### Transformação de Dados (ETL) com Power Query
O coração do projeto foi o processo de ETL no Power Query, onde os dados brutos foram limpos, moldados e enriquecidos. Um desafio significativo de compatibilidade com o **MySQL Connector/.NET** foi contornado através da exportação dos dados para arquivos **CSV**, uma técnica de contingência comum no mercado.

As principais transformações aplicadas foram:

* **Profilagem e Limpeza:** Análise da qualidade e distribuição das colunas, correção de tipos de dados (especialmente valores monetários para **Número Decimal Fixo**) e tratamento estratégico de valores nulos.
* **Modelagem de Dados:** Criação de um modelo relacional dentro do Power BI, estabelecendo as relações corretas entre as 6 tabelas importadas.
* **Enriquecimento dos Dados (Mesclar Consultas / Joins):**
    * A tabela `employee` foi enriquecida com o nome do departamento (`Dname`), vindo da tabela `departament`.
    * Foi realizada uma **auto-mesclagem** (join da tabela com ela mesma) para adicionar os nomes dos supervisores de cada colaborador, uma técnica de modelagem mais avançada.
* **Transformação Estrutural:**
    * **Divisão de Colunas:** A coluna `Address` foi separada em `Rua`, `Cidade` e `Estado`.
    * **Mesclagem de Colunas:** Colunas como `Fname` e `Lname` foram unidas para criar um campo `Nome Completo`, melhorando a usabilidade no relatório.
* **Agrupamento de Dados (Group By):** Foi criada uma nova consulta sumarizada (`Contagem por Supervisor`) através da duplicação da consulta principal, uma boa prática para não destruir a tabela de fatos original.
* **Otimização do Modelo:** Remoção de colunas de ID redundantes para criar um modelo final mais limpo e performático.

### Criação do Dashboard
Com os dados tratados e modelados, a fase final foi a construção do relatório, focando em clareza e interatividade:

* **KPIs:** Cartões com os indicadores principais (Total de Funcionários, Total de Projetos).
* **Gráficos:** Um gráfico de barras para a análise de colaboradores por supervisor.
* **Tabela:** Uma visão detalhada das informações dos departamentos.
* **Interatividade:** Adição de um **Segmentador de Dados** que permite filtrar todo o relatório por cidade.

## 3. Visualização do Dashboard Final

![Dashboard Final](# Desafio Power BI: Dashboard de Análise de RH e Projetos

## 1. Visão Geral do Projeto

Este projeto documenta a jornada completa de construção de um dashboard interativo no Power BI. O objetivo foi transformar dados brutos de um banco de dados MySQL em um relatório gerencial que fornece insights sobre a estrutura de colaboradores, departamentos e projetos de uma empresa fictícia.

O desafio abrangeu desde a configuração do ambiente e resolução de problemas técnicos até a aplicação de técnicas avançadas de ETL (Extração, Transformação e Carga) e modelagem de dados.

## 📊 Acesso ao Dashboard Interativo

O relatório final foi publicado no Power BI Service e pode ser acessado de forma interativa através do link abaixo:

**[Clique aqui para visualizar o dashboard online](https://app.powerbi.com/groups/me/reports/7d35a01d-094c-4a9f-b185-9d72c85bb7bc/2ca3d1a76d842f9c63cc?experience=power-bi)**

## 2. A Jornada: Desafios e Aprendizados

### Configuração do Ambiente e Fonte de Dados
A fase inicial do projeto demonstrou a importância da adaptabilidade. O plano original era utilizar o **Azure Database for MySQL**, mas devido a restrições na assinatura, foi necessário pivotar para uma solução com **banco de dados local**.

No **MySQL Workbench**, o script SQL original foi depurado para corrigir inconsistências e erros, incluindo:
* Violação de restrições `CHECK`.
* Falhas de `FOREIGN KEY` em tabelas com auto-relacionamento.
* Ajuste do `SQL_MODE` do servidor para permitir a inserção de dados específicos do script.

### Transformação de Dados (ETL) com Power Query
O coração do projeto foi o processo de ETL no Power Query, onde os dados brutos foram limpos, moldados e enriquecidos. Um desafio significativo de compatibilidade com o **MySQL Connector/.NET** foi contornado através da exportação dos dados para arquivos **CSV**, uma técnica de contingência comum no mercado.

As principais transformações aplicadas foram:

* **Profilagem e Limpeza:** Análise da qualidade e distribuição das colunas, correção de tipos de dados (especialmente valores monetários para **Número Decimal Fixo**) e tratamento estratégico de valores nulos.
* **Modelagem de Dados:** Criação de um modelo relacional dentro do Power BI, estabelecendo as relações corretas entre as 6 tabelas importadas.
* **Enriquecimento dos Dados (Mesclar Consultas / Joins):**
    * A tabela `employee` foi enriquecida com o nome do departamento (`Dname`), vindo da tabela `departament`.
    * Foi realizada uma **auto-mesclagem** (join da tabela com ela mesma) para adicionar os nomes dos supervisores de cada colaborador, uma técnica de modelagem mais avançada.
* **Transformação Estrutural:**
    * **Divisão de Colunas:** A coluna `Address` foi separada em `Rua`, `Cidade` e `Estado`.
    * **Mesclagem de Colunas:** Colunas como `Fname` e `Lname` foram unidas para criar um campo `Nome Completo`, melhorando a usabilidade no relatório.
* **Agrupamento de Dados (Group By):** Foi criada uma nova consulta sumarizada (`Contagem por Supervisor`) através da duplicação da consulta principal, uma boa prática para não destruir a tabela de fatos original.
* **Otimização do Modelo:** Remoção de colunas de ID redundantes para criar um modelo final mais limpo e performático.

### Criação do Dashboard
Com os dados tratados e modelados, a fase final foi a construção do relatório, focando em clareza e interatividade:

* **KPIs:** Cartões com os indicadores principais (Total de Funcionários, Total de Projetos).
* **Gráficos:** Um gráfico de barras para a análise de colaboradores por supervisor.
* **Tabela:** Uma visão detalhada das informações dos departamentos.
* **Interatividade:** Adição de um **Segmentador de Dados** que permite filtrar todo o relatório por cidade.

## 3. Visualização do Dashboard Final

![Dashboard Final]())
