# Atividade — Classificação de Sentimentos com NLTK

A proposta desta atividade é realizar a classificação de sentimentos utilizando a biblioteca
NLTK (Natural Language Toolkit) em Python. O objetivo é treinar um modelo de classificação
de sentimentos para identificar se um texto expressa uma opinião positiva ou negativa.

## Passos para a Atividade

1. **Execute o Jupyter Notebook**: Abra o arquivo `nltk.ipynb` em seu ambiente de desenvolvimento.
2. **Importe as bibliotecas necessárias**: As bibliotecas utilizadas são `nltk`, `pandas` e `csv`.
3. **Carregue o conjunto de dados**: O notebook utiliza dois corpora:
   - `subjectivity` (disponível no NLTK): classifica textos como subjetivos ou objetivos.
   - `IMDB_Dataset.csv` (disponível na pasta `data`): classifica reviews de filmes como positivos ou negativos.

## Detalhes do Código

O código utiliza técnicas de NLP para treinar um modelo Naive Bayes. O processo inclui:

- **Tokenização**: divisão do texto em palavras individuais.
- **Marcação de negação** (`mark_negation`): palavras após termos negativos recebem o sufixo `_NEG`.
- **Extração de features** (`extract_unigram_feats`): cria um dicionário booleano com as palavras do vocabulário.
- **Treinamento**: utiliza o `NaiveBayesClassifier` do NLTK.

## Resultados

| Experimento              | Accuracy |
|--------------------------|----------|
| Subjectivity (subj/obj)  | 80%      |
| IMDB (positive/negative) | 77.5%    |

## Fontes

- **NLTK** (Natural Language Toolkit): https://www.nltk.org/
- **Instalação via pip**: https://pypi.org/project/nltk/
- **Corpus Subjectivity** (disponível no NLTK Data): https://www.nltk.org/nltk_data/
- **IMDB Dataset**: https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
- **Documentação NLTK Sentiment**: https://www.nltk.org/api/nltk.sentiment.html