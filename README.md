# PLAD-Petrophysic-logs-anomaly-detector



Este repositório contém um pipeline avançado em Python para detecção, classificação e auditoria de anomalias em dados de perfis geofísicos de poço. O foco principal é diferenciar falhas de aquisição (ruído/bad hole) de eventos geológicos reais (camadas finas/heterogeneidades).



## 🚀 Funcionalidades Principais



*   **Leitura de Dados Industriais:** Integração total com arquivos `.LAS` via biblioteca `lasio`.

*   **Estatística Robusta:** Utiliza o estimador **Minimum Covariance Determinant (MCD)** para calcular a Distância de Mahalanobis, permitindo identificar quebras de correlação física entre curvas de forma multivariada.

*   **Sistema de 4 Flags:** Classificação hierárquica das anomalias:

    *   **Flag 1 (Vermelha):** Anomalia Não Correlacionada (Provável Ruído/Outlier Univariado).

    *   **Flag 2 (Verde):** Anomalia Correlacionada (Forte indício geológico/Quebra de correlação).

    *   **Flag 3 (Roxa):** Anomalia Estruturada Sutil (Eventos de baixa amplitude).

    *   **Flag -1:** Dado não classificado por ausência de contexto.

*   **Visualização Diagnóstica:** Geração automática de *strip logs* (PDF/PNG) com tracks de litologia integrados e crossplots de elipses de tolerância.

*   **Auditoria de Integridade:** Módulos de teste estatístico (Jaccard, Permutação e Injeção Sintética) para validar a precisão do modelo.



## 🛠️ Estrutura do Pipeline



1.  **Configuração:** Instalação de dependências e montagem de ambiente.

2.  **Pré-processamento:** Limpeza de nulos, padronização de mnêmicos e sincronização de profundidade.

3.  **Core Estatístico:** Funções para Z-Score Robusto (Mediana/MAD) e Mahalanobis Multigrupo.

4.  **Integração Geológica:** Mapeamento de litofácies a partir de arquivos externos para validação de contexto.

5.  **Relatórios:** Exportação de matrizes de flags em CSV e pacotes de gráficos consolidados.



## 📦 Requisitos



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



1.  Faça o upload dos seus dados `.las` e planilhas de litologia para o diretório indicado no notebook.

2.  Configure os grupos de interesse no dicionário `grupos_mahalanobis` (ex: Petrofísica Básica, Espectral, etc.).

3.  Execute as células sequencialmente.

4.  O sistema gerará um arquivo `.zip` contendo o relatório forense completo e as tabelas de anomalias prontas para uso em outros softwares (como Petrel ou Techlog).



## 🎓 Referência



Este script foi desenvolvido como parte de uma pesquisa técnica focada em **Qualidade de Dados e Detecção de Outliers em Perfis de Poço**, aplicando métodos de estatística multivariada robusta para reservatórios complexos. 

