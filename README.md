# Classification of NFT Collections

This repository contains the source code, Jupyter notebooks, and experimental results used in the research paper "NFT Collection Classification: A Multimodal Approach Integrating Metadata and Textual Embeddings with Supervised Learning," presented at the 35th Brazilian Conference on Intelligent Systems (Bracis 2025 <link: https://bracis.sbc.org.br/2025/ >).

The project explores different text preprocessing and data balancing techniques for classifying NFT collections into 7 categories.

---

## The Experiment

The research and experimentation pipeline, contained in the notebooks, follows these steps:

### 1. Data Preparation
- Textual data (descriptions of the collections) were processed using different techniques (e.g., stopword removal, lemmatization).

- The target classes are **7 categories**:

```
['art', 'gaming', 'memberships', 'music', 'pfps', 'photography', 'virtual-worlds']
```

- Different data balancing strategies were tested (e.g., SMOTE, oversampling).

### 2. Embedding Generation
- A language model from the `sentence-transformers` library (such as `paraphrase-multilingual-MiniLM-L12-v2` or similar) was used to convert the descriptions into numerical vectors (embeddings).

## 3. Training and Evaluation

- Several machine learning classifiers were trained and evaluated (Random Forest, SVM, Decision Tree, and Logistic Regression).

- The experiments were divided into three main scenarios, the results of which are in the CSVs:
1. **`results_only_emb.csv`**: Classification using only text embeddings.
2. **`results_only_extra.csv`**: Classification using only statistical data.
3. **`results_emb_extra.csv`**: Classification using a combination of embeddings and statistical data.
   
---

## Repository Structure

* **/code**: Contains the Jupyter notebooks with the entire workflow.

* `embeddings_code.ipynb`: Main notebook with the pipeline for preprocessing, embedding generation, model training, and evaluation.
* `Samuel_Embeddings[Exec-Local].ipynb`: Notebook version for local execution and testing.

* **/data/results**: Contains the detailed results of the experiments.

* `Results 7 Categories (BRACIS 2025) - results_emb_extra.csv`: Metrics (Accuracy, Precision, Recall, F1, AUROC) for models with embeddings and statistical data.
* `Results 7 Categories (BRACIS 2025) - results_only_emb.csv`: Metrics for models using only embeddings.
* `Results 7 Categories (BRACIS 2025) - results_only_extra.csv`: Metrics for the models using only statistical data.
  
---

## How to Reproduce the Experiments

1. Clone this repository and enter the folder:
  ```bash
  git clone https://github.com/LABPAAD/nfts_classification.git
  cd nfts_classification
  ```

2.  Start the Jupyter server:
  ```bash
  jupyter notebook
  ```

3. In your browser, open the `/code` folder. First, run the `embeddings_code.ipynb` notebook to process the data and generate the embedding files.

4. After the first notebook is complete, run `Samuel_Embeddings[Exec-Local].ipynb` to load the embeddings, train the classifiers, and generate the final result CSVs.
   
---

## Application

In addition to this research, a web application (Flask) was developed that consumes the trained model.

* Application repository: (https://github.com/markesley/NFT-Classifier)

