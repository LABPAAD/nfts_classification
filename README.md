# Classificação de Coleções de NFTs (Artigo BRACIS)

Este repositório contém os códigos-fonte, notebooks Jupyter e resultados experimentais utilizados no artigo de pesquisa **"NFT Collection Classification: A Multimodal
Approach Integrating Metadata and Textual
Embeddings with Supervised Learning"**, submetido ao BRACIS.

O projeto explora diferentes técnicas de pré-processamento de texto e balanceamento de dados para a classificação de coleções de NFTs em 7 categorias.

---

## O Experimento

O pipeline de pesquisa e experimentação, contido nos notebooks, segue os seguintes passos:

### 1. Preparação dos Dados
- Os dados textuais (descrições das coleções) foram processados com diferentes técnicas (ex: remoção de stopwords, lematização).
- As classes alvo são **7 categorias**:
  ```
     ['art', 'gaming', 'memberships', 'music', 'pfps', 'photography', 'virtual-worlds']
  ```
- Diferentes estratégias de balanceamento de dados foram testadas (ex: SMOTE, oversampling).

### 2. Geração dos Embeddings
- Foi utilizado um modelo de linguagem da biblioteca `sentence-transformers` (como `paraphrase-multilingual-MiniLM-L12-v2` ou similar) para converter as descrições em vetores numéricos (embeddings).

### 3. Treinamento e Avaliação
- Diversos classificadores de machine learning foram treinados e avaliados (Random Forest, SVM, Decision Tree, Logistic Regression).
- Os experimentos foram divididos em três cenários principais, cujos resultados estão nos CSVs:
1.  **`results_only_emb.csv`**: Classificação usando apenas os embeddings de texto.
2.  **`results_only_extra.csv`**: Classificação usando apenas dados estatísticos.
3.  **`results_emb_extra.csv`**: Classificação usando a combinação de embeddings e dados estatísticos.

---

## Estrutura do Repositório

* **/code**: Contém os notebooks Jupyter com todo o fluxo de trabalho.
* `embeddings_code.ipynb`: Notebook principal com o pipeline de pré-processamento, geração de embeddings, treinamento e avaliação dos modelos.
* `Samuel_Embeddings[Exec-Local].ipynb`: Versão do notebook para execução e testes locais.
* **/data/results**: Contém os resultados detalhados dos experimentos.
* `Resultados 7 Categorias (BRACIS 2025) - results_emb_extra.csv`: Métricas (Acurácia, Precisão, Recall, F1, AUROC) para os modelos com embeddings e dados estatísticos.
* `Resultados 7 Categorias (BRACIS 2025) - results_only_emb.csv`: Métricas para os modelos usando apenas embeddings.
* `Resultados 7 Categorias (BRACIS 2025) - results_only_extra.csv`: Métricas para os modelos usando apenas dados estatísticos.

---

## Como Reproduzir os Experimentos

1.  Clone este repositório e entre na pasta:
  ```bash
  git clone [https://github.com/LABPAAD/nfts_classification.git](https://github.com/LABPAAD/nfts_classification.git)
  cd nfts_classification
  ```

2.  Inicie o servidor Jupyter:
  ```bash
  jupyter notebook
  ```

3.  No seu navegador, abra a pasta `/code`. Primeiro, execute o notebook `embeddings_code.ipynb` para processar os dados e gerar os arquivos de embeddings.

4.  Após a conclusão do primeiro notebook, execute o `Samuel_Embeddings[Exec-Local].ipynb` para carregar os embeddings, treinar os classificadores e gerar os CSVs de resultados finais.
   
---

> Confira o Aplicativo Web!
>
> Além desta pesquisa, foi desenvolvido um aplicativo web (Flask) que consome o modelo treinado.
>
> **Acesse o repositório da aplicação: (https://github.com/markesley/NFT-Classifier)**

