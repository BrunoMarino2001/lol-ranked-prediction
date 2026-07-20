# League of Legends - Previsao de Vitoria em Ranked

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.5-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org)
[![XGBoost](https://img.shields.io/badge/XGBoost-2.0-189FDD?style=for-the-badge)](https://xgboost.readthedocs.io)
[![SQLite](https://img.shields.io/badge/SQLite-3-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![Power BI](https://img.shields.io/badge/Power%20BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)](https://powerbi.microsoft.com)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=for-the-badge&logo=jupyter&logoColor=white)](https://jupyter.org)

> **Projeto Final - Curso de Ciencia de Dados**

---

## Sobre o Projeto

**Problema de Negocio:** Prever se o time azul vencera (blueWins) com base nos primeiros 10 minutos de partidas ranqueadas.

| | |
|---|---|
| Tipo de Problema | Classificacao Binaria Supervisionada |
| Dataset | 9.879 partidas x 40 atributos |
| Target | blueWins - balanceado (49.9% vs 50.1%) |
| Modelo Final | Regressao Logistica |
| AUC ROC | 81.06% |
| Acuracia | 73.38% |

---

## Resultados em Destaque

| Metrica | Valor |
|---------|-------|
| CV AUC (5-Fold) | 80.87% |
| AUC ROC Teste | 81.06% |
| Acuracia | 73.38% |
| F1-Score | 73.03% |

---

## Top 5 Insights de Negocio

| # | Insight | Impacto |
|---|---------|---------|
| 1 | Gold Diff e o maior preditor | r = 0.63 com blueWins |
| 2 | First Blood eleva a win rate | 40% -> 60.6% (+20.6 p.p.) |
| 3 | Dragao desempata partidas equilibradas | 38.6% -> 60.5% (+21.9 p.p.) |
| 4 | Q4 de Gold Diff quase garante vitoria | 84.6% de win rate |
| 5 | Problema linearmente separavel | LogReg supera RF, XGB e SVM |

---

## Visualizacoes

### EDA e Storytelling
| Visao Geral | O Ouro Decide |
|:-----------:|:-------------:|
| ![g01](outputs/figures/grafico_01_visao_geral.png) | ![g02](outputs/figures/grafico_02_ouro_decide.png) |

| Early Game | Perfil Vencedor |
|:----------:|:---------------:|
| ![g03](outputs/figures/grafico_03_early_game.png) | ![g04](outputs/figures/grafico_04_perfil_vencedor.png) |

### Pre-Processamento e PCA
| Multicolinearidade | Variancia PCA |
|:-----------------:|:-------------:|
| ![g05](outputs/figures/grafico_05_multicolinearidade_vif.png) | ![g06](outputs/figures/grafico_06_pca_variancia.png) |

### K-Means
| Elbow + Silhouette | Perfil dos Clusters |
|:------------------:|:-------------------:|
| ![g07](outputs/figures/grafico_07_elbow_silhouette.png) | ![g08](outputs/figures/grafico_08_cluster_perfil.png) |

![g09](outputs/figures/grafico_09_silhouette_pca_scatter.png)

### Batalha dos Modelos
![g10](outputs/figures/grafico_10_batalha_modelos.png)

| Duelos | ROC + Ranking |
|:------:|:-------------:|
| ![g11](outputs/figures/grafico_11_duelos_roc.png) | ![g12](outputs/figures/grafico_12_roc_ranking_tabela.png) |

### Avaliacao Final
| Matriz de Confusao + ROC | Feature Importance |
|:------------------------:|:-----------------:|
| ![g13](outputs/figures/grafico_13_confusao_report_roc.png) | ![g14](outputs/figures/grafico_14_feature_importance.png) |

---

## Estrutura do Projeto

```
lol-ranked-prediction/
|
|-- notebooks/
|   |-- fase_01_setup_sql.ipynb
|   |-- fase_02_eda_storytelling.ipynb
|   |-- fase_03_preprocessing_pipeline.ipynb
|   |-- fase_04_kmeans.ipynb
|   |-- fase_05_modelagem.ipynb
|   |-- fase_06_avaliacao.ipynb
|   +-- fase_07_bi_dax.ipynb
|
|-- outputs/
|   |-- figures/    <- 14 graficos
|   +-- data/
|       |-- dataset_tratado_powerbi.csv
|       |-- cluster_profile.csv
|       +-- model_results.csv
|
|-- requirements.txt
|-- .gitignore
+-- README.md
```

---

## Como Executar

```bash
git clone https://github.com/BrunoMarino2001/lol-ranked-prediction.git
cd lol-ranked-prediction
pip install -r requirements.txt
```

---

## Stack Tecnologica

| Categoria | Tecnologia |
|-----------|------------|
| Linguagem | Python 3.10+ |
| Banco de Dados | SQLite3 |
| Manipulacao | Pandas, NumPy |
| Visualizacao | Matplotlib, Seaborn, SciPy |
| Pre-processamento | Scikit-learn (Pipeline, StandardScaler, PCA) |
| Clusterizacao | KMeans, silhouette_score |
| Modelos ML | GaussianNB, LogisticRegression, DecisionTree, RandomForest, SVM, XGBoost |
| Otimizacao | GridSearchCV, StratifiedKFold |
| BI | Power BI + DAX |
| Ambiente | Jupyter Notebook / Google Colab |

---

## Roadmap

```
Fase 1 - Setup, SQLite e Ingestao de Dados
Fase 2 - EDA e Storytelling (14 visualizacoes)
Fase 3 - Pre-Processamento + Checkpoint BI
Fase 4 - K-Means: 4 perfis de partida
Fase 5 - 6 modelos + GridSearchCV
Fase 6 - Avaliacao + Feature Importance
Fase 7 - Plano de BI + 7 Formulas DAX
```

---

*Projeto finalizado | Modelo: Regressao Logistica | AUC ROC: 81.06%*
