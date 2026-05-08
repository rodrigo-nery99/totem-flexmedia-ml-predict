# 📈 Previsão de Fluxo para o Totem Inteligente FlexMedia

Este projeto faz parte da **Sprint 3** da disciplina de Machine Learning. O objetivo principal é utilizar métodos de *Ensemble* para prever o fluxo de visitantes com base em dados históricos, gerando insights para a otimização da interface e recursos do projeto **FlexMedia**.

## 🚀 Contexto do Negócio
O sistema **FlexMedia** é um totem inteligente que adapta conteúdos de mídia conforme o engajamento e contexto de uso. Para que essa adaptação seja proativa e não apenas reativa, este modelo foi desenvolvido para prever dias de **Alto Fluxo**, permitindo que o sistema:
* Ajuste a densidade de informações na UI (User Interface).
* Otimize escalas de manutenção de hardware.
* Adapte campanhas de marketing conforme o volume de público esperado.

## 📊 O Dataset
Utilizou-se o dataset `zoo_visitors_2023_consolidada.xlsx`, que contém registros diários de visitação. As variáveis incluem:
- **Temporais:** Mês, Ano, Dia da Semana.
- **Contextuais:** Feriados (`is_holiday`) e Finais de Semana (`is_weekend`).
- **Alvo:** `alto_fluxo` (Classificação binária baseada na mediana de visitantes).

## 🛠️ Tecnologias e Metodologia
A estrutura do projeto seguiu o framework **CRISP-DM**:
1. Compreensão do Negócio
2. Compreensão dos Dados
3. Preparação dos Dados (Feature Engineering e Encoding)
4. Modelagem (Ensemble Methods)
5. Avaliação Experimental

**Modelos Utilizados:**
- Random Forest (Otimizado via GridSearchCV)
- Gradient Boosting
- XGBoost

## 🏆 Resultados e Comparação
O modelo **Random Forest** apresentou o melhor desempenho para este cenário:

| Modelo | Acurácia | F1-Score |
| :--- | :--- | :--- |
| **Random Forest** | **0.86** | **0.86** |
| Gradient Boosting | 0.82 | 0.82 |
| XGBoost | 0.79 | 0.79 |

O Random Forest mostrou-se mais estável contra *overfitting*, lidando melhor com variáveis categóricas de calendário em um dataset de médio porte.

## 💡 Insights Gerados
* **Sazonalidade:** Finais de semana e feriados são os preditores mais fortes de alto fluxo.
* **Ação Prática:** O modelo permite que o totem ative um "Modo de Alta Performance" automaticamente em dias previstos como lotados, simplificando a navegação para reduzir filas.
