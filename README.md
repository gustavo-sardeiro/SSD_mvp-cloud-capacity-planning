# Sistema de Suporte à Decisão (SSD) — Expansão de Infraestrutura em Nuvem

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/gustavo-sardeiro/SSD_mvp-cloud-capacity-planning/blob/main/SSD_MVP_Expansao_Datacenter.ipynb)

Repositório desenvolvido para a disciplina de **Sistemas de Suporte à Decisão** da **Universidade de Brasília (UnB)**.

---

## 1. Visão Geral do Problema de Decisão
Empresas de custódia e armazenamento de dados em nuvem necessitam planejar a expansão de sua capacidade física de servidores sem incorrer em despesas prematuras de capital (*Capex*) ou risco de ruptura operacional por saturação de armazenamento e estresse térmico.

* **Decisão:** Aprovar o investimento imediato na construção/ativação de uma nova unidade ou postergar a expansão focando em otimização e balanceamento de carga da infraestrutura atual.
* **Critérios Analisados:** Custo, Risco Operacional (saturação de armazenamento e estresse térmico) e Margem Temporal de Manobra (*Lead Time* de expansão vs. *Runway* operacional).
* **Parecer Técnico:** Postergação da expansão física imediata, recomendando-se o balanceamento de carga e a mitigação de pontos críticos de capacidade e eficiência energética no curto prazo.

---

## 2. Metodologia e Estrutura dos Dados
O projeto segue o framework estruturado de Ciência de Dados em 6 Fases (Perguntar, Preparar, Processar, Analisar, Compartilhar e Agir):

* **Coleta Automatizada:** Autenticação via API do Kaggle com controle de credenciais (`chmod 600`) para reprodutibilidade integral.
* **Higienização de Viés:** Tratamento explícito de dados com isolamento e remoção da amostragem de servidores legados/obsoletos (>9 anos).
* **Modelagem Econométrica:** Regressão linear avaliando o impacto marginal do consumo de energia elétrica sobre os custos computacionais operacionais.
* **Matriz Prescritiva:** Algoritmo decisório parametrizado com base nos limites críticos de ocupação ($\ge 85\%$), alerta térmico ($\ge 45^\circ\text{C}$) e janelas temporais de *Lead Time*.

---

## 3. Requisitos do Sistema e Dependências
O projeto foi desenvolvido em linguagem **Python (v3.10+)** dentro do ambiente Google Colab, utilizando os seguintes pacotes:

* `pandas`: Manipulação de dados tabulares, limpeza e agregações estruturadas.
* `numpy`: Operações vetoriais e suporte a processamento numérico.
* `scipy`: Inferência estatística, testes de hipóteses e modelagem de regressão.
* `matplotlib` & `seaborn`: Construção de visualizações gráficas e diagnósticos de capacidade.

---

## 4. Base de Dados Utilizada
* **Origem:** Kaggle (*Green AI Hyperscale Data Center Telemetry Dataset*).
* **Escopo:** Telemetria de infraestrutura de data centers contendo métricas de uso de armazenamento (TB/PB), demanda de energia (kW), eficiências operacionais (PUE), temperatura ambiente/exaustão (°C) e custos associados.

---

## 5. Estrutura do Repositório
* `SSD_MVP_Expansao_Datacenter.ipynb`: Caderno executável contendo o fluxo completo de ingestão via API, higienização, análise exploratória, econometria e algoritmo prescritivo.
* `README.md`: Documentação executiva, diretrizes técnicas e fundamentação da tomada de decisão.
