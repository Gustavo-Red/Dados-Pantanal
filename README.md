Projeto de análise de dados - Desenvolvimento de Plataforma de Dados Ambientais

# Análise de Dados Ambientais do Pantanal

## Contexto

Este projeto foi desenvolvido como parte de um teste prático para a vaga de bolsista em Desenvolvimento de Plataforma de Dados Ambientais, com o objetivo de avaliar habilidades em manipulação, processamento e visualização de dados.

A análise utiliza um conjunto de dados ambientais do Pantanal contendo informações de temperatura, nível do rio e índice de vegetação (NDVI) ao longo de uma série temporal.

---

## Objetivo

Realizar uma análise exploratória dos dados, incluindo:

* leitura e organização da base de dados;
* tratamento de valores ausentes;
* cálculo de estatísticas básicas;
* visualização temporal das variáveis;
* extração de insights a partir dos dados.

---

## Descrição

Análise exploratória de dados ambientais do Pantanal com foco em tratamento, visualização e interpretação de variáveis ao longo do tempo.

---

## Resultados

### Temperatura
![Temperatura](Temperatura.png)

### Nível do rio
![Nível do rio](Nivel_rio.png)

### NDVI
![NDVI](NDVI.png)

---

## Principais Insights

- **Padrão Térmico Definido:** A temperatura apresenta uma curva clara de aquecimento na primeira metade do período, atingindo o seu ápice de 36.0°C no dia 5 de janeiro, seguido por um resfriamento gradual até o final da série (31.8°C).
- **Resposta Hidrológica (Defasagem):** O nível do rio acompanha a tendência climática com uma defasagem de 24 horas: enquanto a temperatura máxima ocorre no dia 5, o nível do rio atinge seu ápice de 4.8m no dia 6 de janeiro, decaindo suavemente nos dias seguintes.
- **Vigor Vegetativo Estável (NDVI):** O índice de vegetação mantém-se sempre em patamares excelentes para cobertura densa (acima de 0.65), alcançando o seu pico de vigor (0.72) no dia 6 de janeiro, em perfeita sincronia com o nível máximo do rio.

---

## Estrutura do Projeto

- `dados_pantanal.csv` — arquivo com os dados utilizados na análise
- `pantanal.ipynb` — notebook com o processamento, análise e visualizações
- `README.md` — documentação do projeto

---

## Tecnologias Utilizadas

- Python 3
- Pandas
- Plotly Express

---

## Etapas Realizadas

### 1. Leitura dos dados
A base foi carregada a partir do arquivo `dados_pantanal.csv` usando a biblioteca `pandas`.

### 2. Inspeção inicial
Foi utilizada a função `info()` para verificar os tipos de dados e identificar valores ausentes.

### 3. Tratamento de dados ausentes
A coluna de datas foi convertida para o formato `datetime`, permitindo o uso adequado da série temporal.

Em seguida, foi aplicada **interpolação linear** para preencher os valores ausentes nas colunas numéricas.

### 4. Organização da tabela
As colunas foram renomeadas para nomes mais claros e adequados à visualização:
- `data` → `Data`
- `temperatura_c` → `Temperatura (°C)`
- `nivel_rio_m` → `Nível do rio (m)`
- `ndvi` → `Índice de Vegetação (NDVI)`

### 5. Geração de estatísticas
Foram calculadas as médias das variáveis:
- Temperatura
- Nível do rio
- NDVI

### 6. Visualização dos dados
Foram gerados gráficos de linha com a biblioteca Plotly Express para mostrar a evolução temporal das variáveis ambientais.

Um gráfico inicial foi criado para teste da estrutura, seguido da automação dos gráficos para todas as variáveis.

---

## Justificativa do Tratamento dos Dados

A interpolação linear foi escolhida por se tratar de uma série temporal diária. Esse método permite estimar valores faltantes de forma coerente com a continuidade natural dos dados, sem perda significativa de informação.

---

## Como Executar (No VSCode)

1. Instale as dependências:

```bash
pip install pandas plotly

```
2. Abra o notebook:

```bash
jupyter notebook pantanal.ipynb

```

3. Execute as células em ordem ou utilize "Run All"





