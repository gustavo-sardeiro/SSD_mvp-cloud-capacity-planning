# Sistema de Suporte à Decisão (SSD) — Expansão de Infraestrutura em Nuvem

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/)

Repositório desenvolvido para a disciplina de **Sistemas de Suporte à Decisão** da **Universidade de Brasília (UnB)**.

---

## 1. Visão Geral do Problema de Decisão
Empresas de custódia e armazenamento de dados em nuvem necessitam planejar a expansão de sua capacidade física de servidores sem incorrer em despesas prematuras de capital (*Capex*) ou risco de ruptura operacional por saturação de armazenamento e estresse térmico.

* **Decisão:** Aprovar o investimento imediato na construção/ativação de uma nova unidade ou postergar a expansão focando em balanceamento de carga da infraestrutura atual.
* **Critérios Analisados:** Custo ($R^2 = 0{,}83$), Risco Operacional ($>85\%$ ocupação) e Prazo (*Lead Time* de 6 meses vs. 14,4 meses de folga).
* **Parecer Técnico:** Postergação da expansão física com foco em balanceamento de carga no curto prazo.

---

## 2. Requisitos do Sistema e Dependências
O projeto foi desenvolvido em linguagem **Python (v3.10+)** dentro do ambiente Google Colab, utilizando os seguintes pacotes:

* `pandas`: Manipulação de dados tabulares e agregações estruturadas.
* `numpy`: Cálculos vetoriais e matriciais.
* `scipy`: Inferência estatística formal, correlação de Pearson e regressão linear.
* `matplotlib` & `seaborn`: Visualização gráfica e diagnósticos visuais de capacidade.

---

## 3. Base de Dados Utilizada
* **Origem:** Kaggle (*Green AI Hyperscale Data Center Telemetry Dataset*).
* **Escopo:** Telemetria de servidores de data center em grande escala contendo métricas de capacidade de armazenamento, consumo elétrico (kW), temperatura de exaustão (°C), PUE e custos computacionais.

---

## 4. Estrutura do Repositório
* `SSD_MVP_Expansao_Datacenter.ipynb`: Caderno executável contendo todas as 4 fases da metodologia analítica e visualizações.
* `README.md`: Documentação executiva, requisitos técnicos e fundamentação da tomada de decisão.
