# Sistema de Recomendação de Roupas — ModCloth Dataset

Este projeto tem como objetivo aplicar conceitos de **Filtragem Colaborativa baseada em Itens e Usuários** na construção de um sistema de recomendação de vestuário. Utilizei um conjunto de dados reais da ModCloth para simular como e-commerces conseguem sugerir roupas que combinam com o estilo de um usuário — e ainda **reduzir devoluções e insatisfação**.

> Acesse o notebook completo no Google Colab: [Clique aqui](https://colab.research.google.com/drive/14mUae5ipAuEg9osWdUSdIX0lXurg69DZ?usp=sharing)

---

## Objetivo do Projeto

Ao longo dessa atividade, meu objetivo foi:

- Compreender o comportamento dos usuários em relação às avaliações de roupas.
- Realizar uma **Análise Exploratória de Dados (AED)** para limpar e entender melhor o dataset.
- Implementar dois modelos de recomendação:
  - **User-Based (baseado na similaridade entre usuários)**
  - **Item-Based (baseado na similaridade entre produtos)**
- Comparar os dois modelos com base no erro médio quadrático (RMSE).
- Refletir sobre aplicações práticas e limitações de cada abordagem.

---

## Etapas do Projeto

### 1. Análise Exploratória de Dados (AED)

Nesta etapa, busquei entender melhor os dados antes de qualquer modelagem. Fiz:

- Leitura e amostragem dos dados.
- Análise de valores ausentes e tratamento adequado:
  - Remoção de colunas com mais de 50% de nulos.
  - Preenchimento de nulos com **mediana** (numéricas) ou **moda** (categóricas).
- Estatísticas descritivas das variáveis `size`, `quality`, entre outras.
- Visualizações (histogramas, mapas de calor e gráficos de barras).
- Identificação e **tratamento de outliers** via *winsorização* (IQR).

Essa etapa foi essencial para garantir que os dados estivessem em boas condições para alimentar os modelos de recomendação.

---

### 2. Sistema de Recomendação — Filtragem Colaborativa

Implementei dois algoritmos diferentes:

#### User-Based Filtering

- Montei uma matriz `usuário x item` com base nas avaliações (nota de qualidade).
- Calculei a similaridade entre usuários com **cosseno**.
- Recomendei produtos que usuários semelhantes também avaliaram bem.
- Avaliei o modelo usando **RMSE** (Root Mean Squared Error).

#### Item-Based Filtering

- Montei uma matriz `item x usuário`.
- Calculei a similaridade entre produtos.
- Recomendação baseada em produtos parecidos com os que o usuário já gostou.
- Novamente, utilizei **RMSE** para avaliar o desempenho.

---

## Comparação dos Modelos

O RMSE obtido para cada modelo foi:

- **User-Based:** `X.XXXX`
- **Item-Based:** `Y.YYYY`

> *Nota: Os valores exatos devem ser preenchidos com os resultados do seu notebook após a execução.*

Ambos os modelos têm seus méritos. O **User-Based** é mais personalizado, mas pode sofrer com falta de dados. O **Item-Based** escala melhor e é mais robusto para catálogos maiores.

---

## Tecnologias e Ferramentas

- Python
- Pandas, NumPy
- Seaborn e Matplotlib (visualização)
- Scikit-Learn (cálculo de similaridade, RMSE)
- Google Colab

---

## Aprendizados

Durante o desenvolvimento deste projeto, aprendi na prática como construir sistemas de recomendação baseados em avaliações, como tratar dados faltantes e outliers de forma eficaz, e como métricas como o RMSE ajudam a comparar modelos quantitativamente.

---

## Execução

Você pode rodar o projeto diretamente no Google Colab clicando no botão abaixo:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/14mUae5ipAuEg9osWdUSdIX0lXurg69DZ?usp=sharing)

---

## 📂 Estrutura do Repositório

```bash
├── README.md
├── Kaua-Ponderada-Semana3.ipynb  # Notebook com todo o código comentado
