# Atividade — Classificação de Sentimentos com NLTK

A proposta desta atividade é realizar a classificação de sentimentos utilizando a biblioteca
NLTK (Natural Language Toolkit) em Python. O notebook demonstra três abordagens:

1. **Corpus Subjectivity** — classifica frases de críticas de cinema como subjetivas ou objetivas com Naive Bayes.
2. **Dataset IMDB** — classifica reviews de filmes como positivas ou negativas com Naive Bayes.
3. **VADER** — aplica o analisador léxico VADER (sem treinamento) no mesmo dataset IMDB e compara os resultados.

## Configuração

### Ambiente Virtual

Crie e ative um ambiente virtual antes de instalar as dependências:

```bash
python -m venv .venv
source .venv/bin/activate      # Linux/Mac
.venv\Scripts\activate         # Windows
```

### Dependências

Instale as dependências listadas em `requirements.txt`:

```bash
pip install -r requirements.txt
```

### Recursos do NLTK

Na primeira execução, baixe os corpora necessários:

```python
import nltk
nltk.download()  # selecione: subjectivity, vader_lexicon
```

### Dataset IMDB (via Kaggle API)

O dataset IMDB é baixado automaticamente pelo notebook via [Kaggle API](https://www.kaggle.com/docs/api). O arquivo **não está incluído no repositório**. Para configurar:

1. Crie uma conta em [kaggle.com](https://www.kaggle.com) e gere um token em **Settings → API → Create New Token**.
2. Salve o arquivo `kaggle.json` em:
   - Linux/Mac: `~/.kaggle/kaggle.json`
   - Windows: `C:\Users\<usuário>\.kaggle\kaggle.json`
3. Execute o notebook — o download (~66 MB) ocorre automaticamente na primeira execução.

## Detalhes do Código

- **Tokenização**: divisão do texto em palavras individuais por `str.split()`.
- **Marcação de negação** (`mark_negation`): palavras após termos negativos recebem o sufixo `_NEG`.
- **Extração de features** (`extract_unigram_feats`): cria um dicionário booleano com as palavras do vocabulário.
- **Naive Bayes**: treinado com `NaiveBayesClassifier` do NLTK.
- **VADER**: analisador léxico pré-construído (`SentimentIntensityAnalyzer`), sem necessidade de treinamento.

## Resultados

| Experimento                        | Modelo      | Accuracy |
|------------------------------------|-------------|----------|
| Subjectivity (subj/obj)            | Naive Bayes | 80%      |
| IMDB (positive/negative)           | Naive Bayes | 77.5%    |
| IMDB (positive/negative)           | VADER       | 71.25%   |

## Fontes

- **NLTK** (Natural Language Toolkit): https://www.nltk.org/
- **Instalação via pip**: https://pypi.org/project/nltk/
- **Corpus Subjectivity** (Pang & Lee, 2004): https://www.nltk.org/nltk_data/
- **IMDB Dataset**: https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews
- **VADER** (Hutto & Gilbert, 2014): https://github.com/cjhutto/vaderSentiment
- **Documentação NLTK Sentiment**: https://www.nltk.org/api/nltk.sentiment.html