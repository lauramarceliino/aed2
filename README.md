# 🚀 Projeto referen a primeira unidade da displina ALGORITMOS E ESTRUTURAS DE DADOS II

# 📊 Análise de Grafos - Bolsistas de Iniciação Científica

Este repositório contém a exploração e análise de grafos derivados da base de dados de bolsistas de iniciação científica da UFRN.  
O estudo busca compreender as relações entre bolsistas, orientadores e unidades acadêmicas a partir da modelagem em grafos.

## 🔑 Principais Grafos

- **Co-occurrence Graph** → Ele representa a rede semântica de palavras mais frequentes e suas coocorrências.  
- **Bipartite Graphs** → Conectam dois tipos diferentes de nós, como `Bolsista-Unidade` ou `Discente-Orientador`.  
- **Advisor Collaboration Graph** → Rede de colaboração entre orientadores que compartilham bolsistas.  

## 🚀 Tecnologias Utilizadas

- **Python** (pandas, numpy)
- **NetworkX** (modelagem e análise de grafos)
- **Plotly** (visualização interativa)
- **NLTK / scikit-learn** (pré-processamento de texto)

## 📌 Funcionalidades Implementadas

- Pré-processamento dos dados (limpeza e normalização).  
- Criação de diferentes tipos de grafos (direcionados, ponderados, bipartidos, etc.).  
- Projeções de grafos bipartidos para diferentes perspectivas.  
- Cálculo de métricas de redes (grau médio, densidade, assortatividade, centralidade).  
- Inclusão de algoritmos para **detecção de comunidades**.  
- Visualizações otimizadas com **Plotly**.  

## 📈Resultados

- Distribuição de graus dos grafos.  
- Identificação de orientadores mais centrais na rede.  
- Estrutura de colaboração entre unidades acadêmicas.  

---
👩‍💻 Desenvolvido por Laura Marcelino no contexto de análise de grafos aplicados a dados de bolsistas de iniciação científica.

## 📊 Dados

A base de dados utilizada neste projeto está disponível em:

- [Portal de Dados da UFRN - Bolsistas de Iniciação Cientifica](https://dados.ufrn.br/dataset/bolsistas-de-iniciacao-cientifica/resource/dfee756f-809f-42d2-a88a-db67f3a040bf)  

## 🚀 Execução no Google Colab

Você pode executar este projeto diretamente no Google Colab:  

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/17jCUpUeRU39X984-LHdd6e9mJluYWDVe)

As células já estão executadas mas caso seja necessário reproduzi-las, no ambiente google colab, baixe o arquivo `bolsistas-iniciacao-cientificia.csv` da pasta`u1/data` e suba na opção *Files* em seguida clique em *Upload session storage*, após fazer isso execute as células, em ordem, normalmente.

