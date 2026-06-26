# Análise Exploratória da Arrecadação Federal (2024)

Estudo de caso desenvolvido no **MBA em Analytics e Inteligência Artificial da FIA**, com foco em análise exploratória de dados (EDA) aplicada à arrecadação tributária federal por natureza jurídica.

---

## 🎯 Objetivo

Explorar a base de arrecadação federal para entender **como os diferentes tributos se distribuem e se relacionam** entre as naturezas jurídicas, identificando padrões, concentrações e correlações relevantes — e traduzindo achados estatísticos em leitura de negócio.

## 📊 Base utilizada

Dados de arrecadação federal de 2024, organizados por **natureza jurídica** (código, descrição e escopo) e detalhados por tipo de tributo (Imposto de Importação, IPI, IRPJ, COFINS, PIS/PASEP, CSLL, Contribuição Previdenciária, entre outros).

> *Fonte: dados de arrecadação federal, adaptado a partir de: https://basedosdados.org*

## ❓ Missão da análise

Uma consultoria tributária deseja entender o comportamento da arrecadação federal para subsidiar análises de risco fiscal e planejamento tributário. As seguintes questões devem ser respondidas:

- Como se distribui a arrecadação total entre os diferentes tributos e naturezas jurídicas?
- Existe correlação entre diferentes tributos dentro de uma mesma natureza jurídica?
- Há registros com valores atípicos que mereçam investigação mais detalhada?

## 🔍 Principais análises

- **Unicidade e preenchimento** dos registros (tratamento de valores ausentes)
- **Análise univariada** das distribuições de cada tributo
- **Detecção de outliers** (boxplots + critério de intervalo interquartílico)
- **Análise bivariada** com matriz de correlação de **Spearman** (escolhida por causa da forte assimetria da base) e gráficos de dispersão.

## 💡 Principais insights

- A arrecadação é **extremamente concentrada**: na Contribuição Previdenciária, a média (~R$ 4,9 bi) é cerca de **35x a mediana** (~R$ 138 mi) — Poucas grandes naturezas empresariais respondem pela maior parte do total.
- Os **valores extremos não são erro**, e sim materialidade real (Sociedades Limitadas e S.A.), o que reforça a importância de tratá-los como segmento, não como ruído.
- A matriz de correlação revelou **blocos coerentes** de tributos que se movem juntos — ligados a lucro, comércio exterior e folha de pagamento.
- A escolha entre **Pearson e Spearman** é decisiva em bases assimétricas: Pearson se deixa dominar pelos extremos, enquanto Spearman trabalha com a ordem dos valores e revela a relação real.

## 🛠️ Ferramentas utilizadas

- **Python**
- **pandas** — manipulação e análise de dados
- **matplotlib** e **seaborn** — visualização
- **Google Colab Notebook** — ambiente de desenvolvimento

---

## 📁 Estrutura do repositório

```
.
├── analise_arrecadacao_federal.ipynb   # notebook com a análise completa
├── Estudo_Caso_1_Base_I_Dados.txt      # base de dados 
└── README.md
```

## ▶️ Como executar

1. Clone o repositório ou baixe o `.ipynb`
2. Abra no Google Colab ou Jupyter Notebook
3. Garanta que o arquivo de dados esteja no caminho esperado
4. Execute as células na ordem

---

*Case desenvolvido em grupo. Agradecimentos ao time e à orientação do MBA em Analytics e IA da FIA.*
