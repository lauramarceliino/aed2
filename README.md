# 📑 Repositório referente a displina ALGORITMOS E ESTRUTURAS DE DADOS II - 2025.2

---

## 🚀 Projeto referente a primeira unidade

### 📊 Análise de Grafos - Bolsistas de Iniciação Científica

Este repositório contém a exploração e análise de grafos derivados da base de dados de bolsistas de iniciação científica da UFRN.  
O estudo busca compreender as relações entre bolsistas, orientadores e unidades acadêmicas a partir da modelagem em grafos.

#### 🔑 Principais Grafos

- **Co-occurrence Graph** → Ele representa a rede semântica de palavras mais frequentes e suas coocorrências.  
- **Bipartite Graphs** → Conectam dois tipos diferentes de nós, como `Bolsista-Unidade` ou `Discente-Orientador`.  
- **Advisor Collaboration Graph** → Rede de colaboração entre orientadores que compartilham bolsistas.  

#### 🚀 Tecnologias Utilizadas

- **Python** (pandas, numpy)
- **NetworkX** (modelagem e análise de grafos)
- **Plotly** (visualização interativa)
- **NLTK / scikit-learn** (pré-processamento de texto)

#### 📌 Funcionalidades Implementadas

- Pré-processamento dos dados (limpeza e normalização).  
- Criação de diferentes tipos de grafos (direcionados, ponderados, bipartidos, etc.).  
- Projeções de grafos bipartidos para diferentes perspectivas.  
- Cálculo de métricas de redes (grau médio, densidade, assortatividade, centralidade).  
- Inclusão de algoritmos para **detecção de comunidades**.  
- Visualizações otimizadas com **Plotly**.  

#### 📈Resultados

- Distribuição de graus dos grafos.  
- Identificação de orientadores mais centrais na rede.  
- Estrutura de colaboração entre unidades acadêmicas.
 
#

👩‍💻 Desenvolvido por Laura Marcelino no contexto de análise de grafos aplicados a dados de bolsistas de iniciação científica.

#### 📊 Dados

A base de dados utilizada neste projeto está disponível em:

- [Portal de Dados da UFRN - Bolsistas de Iniciação Científica](https://dados.ufrn.br/dataset/bolsistas-de-iniciacao-cientifica/resource/dfee756f-809f-42d2-a88a-db67f3a040bf)  

#### 🚀 Execução no Google Colab

Você pode vizualizar este projeto diretamente no Google Colab:  

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/17jCUpUeRU39X984-LHdd6e9mJluYWDVe)

As células já estão executadas mas caso seja necessário reproduzi-las, no ambiente google colab, baixe o arquivo `bolsistas-iniciacao-cientificia.csv` da pasta`u1/data` e suba na opção *Files* em seguida clique em *Upload session storage*, após fazer isso execute as células, em ordem, normalmente.

#### 📊 Apresentação

A apresentação do projeto pode ser acessada clicando no link abaixo:

[Ver apresentação no Canva](https://www.canva.com/design/DAGzJpx-3dM/FZRI1eylc88T51enXIlYNw/view)

---

## 🚀 Projeto referente segunda unidade

### 📊 PARTE 1 - Comparação de Performance: Dijkstra Clássico vs Dijkstra com Min-Heap

#### 🚀 Visão Geral do Projeto

Este projeto tem como objetivo realizar uma **análise comparativa aprofundada** do desempenho e da **pegada de carbono ($\text{CO}_{2}$)** de diferentes implementações do algoritmo de caminho mínimo de Dijkstra.

O foco é contrastar as implementações baseadas em diferentes estruturas de dados e complexidades teóricas: a **versão clássica $O(V^2)$** e a **versão otimizada com Min-Heap $O((V+E) \log V)$**, utilizando a implementação nativa do **NetworkX** como referência.

#### Objetivos Principais

* **Avaliar a Complexidade Prática:** Medir como o tempo de execução e as emissões de $\text{CO}_{2}$ escalam em função do número de nós ($V$).
* **Comparar Eficiência Energética:** Utilizar a biblioteca **CodeCarbon** para quantificar a pegada de carbono de cada abordagem.
* **Validação Estatística:** Coletar dados de forma robusta e calcular o Intervalo de Confiança (95%) para garantir a validade dos resultados.

#

#### 🛠️ Tecnologias e Dependências

O projeto é executado em um ambiente Python e depende das seguintes bibliotecas:

| Biblioteca | Propósito |
| :--- | :--- |
| **`networkx`** | Geração dos grafos aleatórios (G(n, p)) e algoritmo de referência. |
| **`numpy`**, **`pandas`** | Manipulação de dados, cálculos e análise estatística. |
| **`matplotlib`** | Geração dos gráficos de comparação de desempenho. |
| **`tqdm`** | Barras de progresso para monitorar o loop de experimentos. |
| **`codecarbon`** | Medição da pegada de carbono (kg CO</sub>₂e) de cada execução do algoritmo. |
| **`scipy.stats`** | Cálculo dos Intervalos de Confiança (distribuição *t* de Student). |

As implementações de Dijkstra (Clássico e Min-Heap) são carregadas de notebooks externos (`dijsktra.ipynb` e `dijsktra_min_heap.ipynb`, presentes na pasta `u2/p1/algoritmos`).

#

### ⚙️ Configuração Experimental

O experimento é projetado para garantir robustez estatística e reprodutibilidade:

#### Parâmetros

* **Tamanhos de Grafo ($V$):** `[100, 500, 1.000, 5.000, 10.000, 50.000, 100.000]` (Ajuste a lista `TAMANHOS` conforme a capacidade do seu ambiente).
* **Probabilidade de Aresta ($p$):** A probabilidade de arestas é ajustada dinamicamente de acordo com o tamanho do grafo usando a função edge_prob_ideal, baseada em log(N)/N.
* **Repetições por Tamanho:** 15 a 20 repetições.
* **Nós Fonte por Repetição:** 5 nós aleatórios.
* **Reprodutibilidade:** Sementes (`SEED`) fixadas para `random` e `numpy`.

#### Metodologia

1.  **Geração do Grafo:** Para cada tamanho $V$, um grafo ponderado e **conectado** é gerado.
2.  **Medição:** Para cada repetição e cada nó fonte, o tempo de execução e o $\text{CO}_{2}$ são medidos para:
    * Dijkstra Clássico (O(V²))  
    * Dijkstra Min-Heap (O((V+E) log V))
    * NetworkX Referência
3.  **Coleta de Dados Brutos:** Os resultados de todas as execuções são agregados no arquivo `resultados_brutos.csv`.

#

### 📈 Resultados e Análise

O notebook gera dois tipos de saídas para análise:

#### 1. Tabelas de Resumo

| Arquivo | Conteúdo |
| :--- | :--- |
| `resultados_brutos.csv` | Registros de Tempo (s) e $\text{CO}_{2}$ (kg) para cada execução individual (Tamanho, Repetição, Algoritmo). |
| `estatisticas_resumo.csv` | Resumo estatístico, incluindo **Média**, **Desvio Padrão** e **Intervalo de Confiança (95%)** para Tempo e $\text{CO}_{2}$, agrupados por Tamanho e Algoritmo. |

#### 2. Gráficos Comparativos

Os gráficos (com eixos logarítmicos) demonstram a relação entre o tamanho do grafo ($V$) e as métricas de desempenho/sustentabilidade, utilizando o Desvio Padrão ($\sigma$) como barra de erro.

* **`tempo_comparacao.png`**: Compara o **Tempo Médio de Execução (s)** dos três algoritmos.
* **`co2_comparacao.png`**: Compara a **Pegada de Carbono Média (kg CO</sub>₂e)** dos três algoritmos.

#

#### 💡 Como Executar o Projeto

1.  **Pré-requisitos:** Certifique-se de que as implementações de Dijkstra de aula (`dijsktra.ipynb` e `dijsktra_min_heap.ipynb`) estão disponíveis e que as dependências do `pip` foram instaladas.
2.  **Configuração:** Ajuste a lista `TAMANHOS` (Célula 2) e o número de repetições (`N_REPETICOES`) conforme a capacidade do seu ambiente.
3.  **Execução:** Execute todas as células do notebook **em ordem**.
4.  **Análise:** Inspecione os arquivos `.csv` e `.png` gerados para tirar conclusões sobre o *trade-off* entre a complexidade teórica e o consumo de recursos (tempo e energia) na prática.

Você pode vizualizar este projeto diretamente no Google Colab:  

[![Abrir no Colab](https://colab.research.google.com/assets/colab-badge.svg)](1OmM-qgyFcoKV45iblqERNerNB6wD-Zpk)

#### 🎥 Apresentação / Vídeo

O projeto também conta com um vídeo explicativo mostrando:  

- Algoritmos e diferenças de complexidade  
- Execução dos notebooks  
- Gráficos e análise de resultados  

[![Assista no YouTube](https://img.shields.io/badge/YouTube-Assistir-red?logo=youtube)](LINK_DO_VIDEO)

#### 📊 Referências

- [NetworkX Documentation](https://networkx.org/documentation/stable/)  
- [CodeCarbon](https://codecarbon.io)  
