# Desafio de Ciência de Dados - Análise Cinematográfica para PProductions

## Descrição do Projeto

Este projeto foi desenvolvido como solução para o Desafio de Cientista de Dados da Indicium Lighthouse. O objetivo é realizar uma análise detalhada sobre um banco de dados cinematográfico para orientar um estúdio de Hollywood, a PProductions, sobre qual tipo de filme desenvolver em seu próximo projeto.

A análise abrange desde a limpeza e enriquecimento dos dados até uma análise exploratória aprofundada para identificar fatores de sucesso, culminando na construção de um modelo de Machine Learning para prever a nota do IMDB de um filme.
## Visão Geral do Projeto

* **Limpeza e Preparação dos Dados:** Tratamento de valores ausentes, correção de inconsistências e conversão de tipos de dados.
* **Enriquecimento de Dados:** Adição de dados externos de inflação para permitir uma análise financeira justa e comparável ao longo das décadas.
* **Análise Exploratória de Dados (EDA):** Geração de visualizações e estatísticas para descobrir padrões e responder a perguntas de negócio chave.
* **Engenharia de Features:** Criação de novas variáveis, como a harmonização das classificações etárias, para melhorar a qualidade da análise e do modelo.
* **Modelagem Preditiva:** Desenvolvimento e avaliação de um modelo de Machine Learning para prever a nota do IMDB de um filme com base em suas características.

#### Modelagem Preditiva
Para prever a nota do IMDB, foi desenvolvido um pipeline de Machine Learning robusto.

* **Tipo de Problema:** Foi definido como um problema de **Regressão**, pois o alvo (`IMDB_Rating`) é uma variável numérica contínua.
* **Modelo Final:** Após comparar 5 algoritmos diferentes com seus hiperparâmetros otimizados via `GridSearchCV`, o modelo **XGBoost Regressor** foi escolhido por apresentar a melhor performance.
* **Métrica de Performance:** A métrica escolhida foi o **RMSE (Root Mean Squared Error)**, que indicou um erro médio de previsão de apenas **~0.20 pontos** na escala de 1 a 10 do IMDB.


## Fontes dos Dados

* **Dataset Principal:** O arquivo `desafio_indicium_imdb.csv`, contendo informações sobre 1000 filmes, foi fornecido como parte do enunciado do desafio. 
* **Dados de Inflação:** Para a análise de faturamento, o dataset foi enriquecido com a série de dados "Consumer Price Index for All Urban Consumers" (`CPIAUCNS.csv`), obtida através do FRED (Federal Reserve Economic Data).

## Estrutura do Repositório

* **/data**: Contém os datasets brutos utilizados no projeto.
* **analise_filmes.ipynb**: É o Jupyter Notebook, com o relatório completo da análise.
* **modelo_previsao_imdb_otimizado.pkl**: É o modelo de previsão final treinado e salvo .
* **README.md**: Este arquivo, com a documentação do projeto.
* **requirements.txt**: Lista de todas as dependências Python necessárias para executar o projeto.

## Como Executar o Projeto

**1. Pré-requisitos:**
* Git
* Python 3.9+

**2. Clone o Repositório:**
```bash
git clone [https://github.com/jrsm-hub/desafio-indicium-lighthouse.git]
cd [desafio-indicium-lighthouse]
```

**3. Crie e Ative o Ambiente Virtual:**
```bash
# Windows
python -m venv .venv
.\.venv\Scripts\activate

# macOS / Linux
python3 -m venv .venv
source .venv/bin/activate
```

**4. Instale as Dependências:**
```bash
pip install -r requirements.txt
```

**5. Execute a Análise:**
Toda a análise está contida no Jupyter Notebook `notebooks/analise_filmes.ipynb`. Abra-o em um ambiente compatível (como o VS Code, Jupyter Lab ou Jupyter Notebook) e execute as células na ordem apresentada.

**6. Ferramentas e Bibliotecas**

* **Python 3.10**
* **Pandas & NumPy:** Para manipulação e análise de dados.
* **Matplotlib & Seaborn:** Para visualização de dados.
* **Scikit-learn:** Para o pipeline de Machine Learning (pré-processamento, modelagem e avaliação).
* **XGBoost:** Para o modelo final de regressão.
* **TextBlob & WordCloud:** Para a análise de Processamento de Linguagem Natural (NLP).
* **Git & GitHub:** Para versionamento de código.