# Mapeamento-e-classifica-o-de-cursos-ENAP

# 📚 Extração e Classificação de Cursos ENAP

Este projeto tem como objetivo **extrair informações de cursos da ENAP** (Escola Nacional de Administração Pública) a partir do catálogo online, realizar **pré-processamento textual** das descrições e aplicar **classificação automática de competências** utilizando embeddings de linguagem natural.

## 🛠️ Funcionalidades

1. **Extração de cursos**
   - Coleta dinâmica de todas as páginas do catálogo ENAP.
   - Captura informações básicas de cada curso: ID, nome, link, status, conteudista, carga horária.

2. **Extração detalhada de cursos**
   - Captura conteúdo programático, descrição detalhada, certificador, disponibilidade, idioma e público-alvo.

3. **Pré-processamento de textos**
   - Limpeza básica (remoção de acentos e caracteres especiais).
   - Remoção de pontuação e stopwords.
   - Aplicação de **stemming** e **lemmatization** para normalizar os textos.

4. **Classificação de competências**
   - Geração de embeddings das descrições e de uma lista de competências.
   - Cálculo de similaridade coseno para identificar as competências prováveis de cada curso.
   - Exportação do resultado final em CSV.

## ⚡ Requisitos

```py
- Python 3.10+
- Bibliotecas:

pandas
requests
beautifulsoup4
unidecode
nltk
torch
sentence-transformers
```

- Recursos NLTK necessários:

```python
nltk.download('stopwords')
nltk.download('wordnet')
```

## 📂 Estrutura de arquivos

```py
.
├── cursos_enap.csv           # CSV com informações básicas dos cursos
├── cursos_detalhado.csv      # CSV com informações detalhadas dos cursos
├── correlacao_CursoXCompetencias.csv  # Resultado final com competências prováveis
├── enap_mapping.py           # Codigo do projeto
└── README.md
```

## 🚀 Como usar

1. Clone o repositório ou abra no Google Colab.

2. Instale as dependências:
   
```py
pip install pandas requests beautifulsoup4 unidecode nltk torch sentence-transformers
```

3. Execute o notebook main_notebook.ipynb:

  - Parte 1: Extração de cursos.

  - Parte 2: Extração detalhada.

  - Parte 3: Pré-processamento textual.

  - Parte 4: Classificação de competências.

4. O arquivo final correlacao_CursoXCompetencias.csv será gerado, contendo:

```py
ID, Curso, Descricao, Competencias provaveis
```

## 📝 Observações

  - O projeto utiliza um exemplo de lista de competências, mas pode ser expandida com mais termos para aumentar a precisão da classificação.

  - Para proteger dados sensíveis, não inclua tokens, senhas ou arquivos privados no notebook antes de compartilhar.

  - O pipeline foi projetado para ser modular, podendo ser facilmente adaptado para outros catálogos de cursos ou sistemas de classificação semântica.

## 🔗 Referências

Catálogo ENAP

Sentence Transformers

NLTK Documentation
