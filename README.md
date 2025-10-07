# 💣 Machine Learning para Predição de Incidentes de Grupos Terroristas

## Visão Geral do Projeto

Este projeto teve como objetivo desenvolver um sistema de classificação de Machine Learning para prever o grupo terrorista responsável por um ataque com base em diversas características históricas. Utilizando o rico Global Terrorism Database (GTD), exploramos padrões em ataques passados para criar um modelo preditivo de alta precisão que pode ser uma ferramenta valiosa para a segurança pública e a formulação de políticas de defesa.

O foco é em responder a uma questão central:

- Quais fatores influenciam o tipo de ataque e o grupo responsável por ele, e como podemos usar essas informações para prever futuros ataques com alta precisão?

## 🛠️ Metodologia Utilizada: CRISP-DM

A estrutura do projeto seguiu a metodologia **CRISP-DM (Cross-Industry Standard Process for Data Mining)** para garantir uma abordagem estruturada e eficaz:

1. **Compreensão do Negócio**

    - **Objetivo**: Prever o grupo responsável pelo ataque e identificar padrões nos grupos terroristas para melhorar a segurança global.

    - **Métricas**: Acurácia, Precisão, Recall e F1-Score.

2. **Entendimento dos Dados**

    - **Fonte**: [Global Terrorism Database (GTD)](https://www.start.umd.edu/research-projects/global-terrorism-database-gtd) - Mais de 200 mil registros com mais de 100 features.

- **Análise Exploratória**:

    - **Ataques por Ano**: Os dados mostram uma tendência de aumento significativo no número de ataques terroristas ao longo dos anos, com picos notáveis.

    - **Top 10 Grupos**: Foi identificado o ranking dos 10 grupos mais ativos, com o grupo Taliban sendo o principal, seguido por Shining Path e Provisional Irish Republican Army (com base no chunk de dados analisado).

    - **Geolocalização (2016-2020)**: A visualização global dos ataques mostra as áreas de maior concentração e risco.

    - **Vítimas (Mortos/Feridos)**: A análise dos outliers para o número de mortos e feridos confirmou a presença de eventos extremos reais, que foram mantidos nos dados por serem representativos da realidade do terrorismo.

    - **Sucesso vs. Suicida**: A maioria dos ataques são bem-sucedidos, independentemente de serem ataques suicidas ou não, embora os ataques não-suicidas sejam a vasta maioria.

3. **Preparação dos Dados**

- **Seleção de Features**: Foram selecionadas as 28 colunas mais relevantes, incluindo: data (```iyear```, ```imonth```, ```iday```), localização (```country```, ```region```, ```latitude```, ```longitude```), tipo de ataque e arma, sucesso, se foi suicida (```suicide```), se foi reivindicado (```claimed```), entre outras.

- **Tratamento de Dados Ausentes**:

    - **Numéricos**: Preenchidos com a mediana.

    - **Categóricos**: Preenchidos com a moda.

## 📈 Resultados e Conclusão

O modelo Random Forest demonstrou a melhor performance, atingindo uma Acurácia de 97% e um F1-Score de 95% no conjunto de testes.

A alta pontuação das métricas sugere que as features selecionadas (como localização, ano, tipo de ataque e arma) são extremamente preditivas para a identificação do grupo terrorista responsável, validando o objetivo principal do projeto.


**Observação**: O projeto foi executado em partes (com um chunk_size de 25.000 linhas) devido ao tamanho da base de dados original e à complexidade da codificação One-Hot para as variáveis categóricas com alta cardinalidade (como city e provstate), o que resultou em um grande número de features (6894 no X_train). O desempenho do Random Forest sugere que ele foi capaz de lidar com essa alta dimensionalidade de forma eficaz.
