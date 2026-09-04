# PLAD-Petrophysic-logs-anomaly-detector
(Detector de anomalias em Logs petrofísicos


🇧🇷 Este repositório contém um pipeline avançado em Python para detecção, classificação e auditoria de anomalias em dados de perfis geofísicos de poço. O foco principal é diferenciar falhas de aquisição (ruído/bad hole) de eventos geológicos reais (camadas finas/heterogeneidades).
🇺🇸 This repository contains an advanced Python pipeline for anomaly detection, classification, and auditing in geophysical well log data. The main focus is to differentiate acquisition failures (noise/bad hole) from true geological events (thin beds/heterogeneities).


## 🚀 Funcionalidades Principais
## 🚀 Main Features

🇧🇷

*   **Leitura de Dados Industriais:** Integração total com arquivos `.LAS` via biblioteca `lasio`.
*   **Estatística Robusta:** Utiliza o estimador **Minimum Covariance Determinant (MCD)** para calcular a Distância de Mahalanobis, permitindo identificar quebras de correlação física entre curvas de forma multivariada.
*   **Sistema de 4 Flags:** Classificação hierárquica das anomalias:
*   
    *   **Flag 1 (Vermelha):** Anomalia Não Correlacionada (Provável Ruído/Outlier Univariado).
    *   **Flag 2 (Verde):** Anomalia Correlacionada (Forte indício geológico/Quebra de correlação).
    *   **Flag 3 (Roxa):** Anomalia Estruturada Sutil (Eventos de baixa amplitude).
    *   **Flag -1:** Dado não classificado por ausência de contexto.

*   **Visualização Diagnóstica:** Geração automática de *strip logs* (PDF/PNG) com tracks de litologia integrados e crossplots de elipses de tolerância.
*   **Auditoria de Integridade:** Módulos de teste estatístico (Jaccard, Permutação e Injeção Sintética) para validar a precisão do modelo.

🇺🇸

*   **Industrial Data Reading:** Full integration with `.LAS` files via the `lasio` library.
*   **Robust Statistics:** Utilizes the **Minimum Covariance Determinant (MCD)** estimator to calculate the Mahalanobis Distance, allowing the identification of physical correlation breaks between curves in a multivariate way.
*   **4-Flag System:** Hierarchical anomaly classification:
*   
    *   **Flag 1 (Red):** Uncorrelated Anomaly (Probable Noise/Univariate Outlier).
    *   **Flag 2 (Green):** Correlated Anomaly (Strong geological indicator/Correlation break).
    *   **Flag 3 (Purple):** Subtle Structured Anomaly (Low-amplitude events).
    *   **Flag -1:** Unclassified data due to lack of context.
      
*   **Diagnostic Visualization:** Automatic generation of *strip logs* (PDF/PNG) with integrated lithology tracks and tolerance ellipse crossplots.
*   **Integrity Auditing:** Statistical testing modules (Jaccard, Permutation, and Synthetic Injection) to validate model accuracy.




## 🛠️ Estrutura do Pipeline
## 🛠️ Pipeline Structure

🇧🇷

1.  **Configuração:** Instalação de dependências e montagem de ambiente.
2.  **Pré-processamento:** Limpeza de nulos, padronização de mnêmicos e sincronização de profundidade.
3.  **Core Estatístico:** Funções para Z-Score Robusto (Mediana/MAD) e Mahalanobis Multigrupo.
4.  **Integração Geológica:** Mapeamento de litofácies a partir de arquivos externos para validação de contexto.
5.  **Relatórios:** Exportação de matrizes de flags em CSV e pacotes de gráficos consolidados.

🇺🇸

1.  **Configuration:** Dependency installation and environment setup.
2.  **Preprocessing:** Null cleaning, mnemonic standardization, and depth synchronization.
3.  **Statistical Core:** Functions for Robust Z-Score (Median/MAD) and Multigroup Mahalanobis.
4.  **Geological Integration:** Lithofacies mapping from external files for context validation.
5.  **Reports:** Export of flag matrices in CSV and consolidated chart packages.

## 📦 Requisitos
## 📦 Requirements

```python

pandas

numpy

lasio

scikit-learn

scipy

matplotlib

plotly

ipytest

```



## 📖 Como Usar
## 📖 How to Use

🇧🇷

1.  Faça o upload dos seus dados `.las` e planilhas de litologia para o diretório indicado no notebook.

2.  Configure os grupos de interesse no dicionário `grupos_mahalanobis` (ex: Petrofísica Básica, Espectral, etc.).

3.  Execute as células sequencialmente.

4.  O sistema gerará um arquivo `.zip` contendo o relatório forense completo e as tabelas de anomalias prontas para uso em outros softwares (como Petrel ou Techlog).

🇺🇸

1.  Upload your .las data and lithology spreadsheets to the directory indicated in the notebook.

2.  Configure the interest groups in the grupos_mahalanobis dictionary (e.g., Basic Petrophysics, Spectral, etc.).

3.  Execute the cells sequentially.

4.  The system will generate a .zip file containing the complete forensic report and anomaly tables ready for use in other software (such as Petrel or Techlog).

## 🎓 Referência
## 🎓 Reference

🇧🇷

Este script foi desenvolvido como parte de uma pesquisa técnica focada em **Qualidade de Dados e Detecção de Outliers em Perfis de Poço**, aplicando métodos de estatística multivariada robusta para reservatórios complexos. 

🇺🇸

This script was developed as part of a technical research focused on Data Quality and Outlier Detection in Well Logs, applying robust multivariate statistics methods for complex reservoirs.

