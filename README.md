# ifood-case
#  Solução para o case técnico de Data Science do iFood

Este projeto foi desenvolvido como parte de um processo seletivo para a vaga de Cientista de Dados no iFood. O desafio consiste em propor uma solução baseada em dados para otimizar a distribuição de cupons e ofertas aos clientes.

---

##  Objetivo

Criar uma estratégia de distribuição de ofertas personalizada por cliente, maximizando o engajamento e o retorno das campanhas de marketing, com base em:

- Perfis demográficos e financeiros dos clientes.
- Histórico de transações.
- Características das ofertas disponíveis.

---

##  Estrutura do Repositório

```
ifood-case/
├── data/
│   ├── raw/
│   └── processed/
├── notebooks/
│   ├── 1_data_processing.ipynb
│   └── 2_modeling.ipynb
├── presentation/
│   └── ifood_case_slides.pdf
├── src/
├── requirements.txt
└── README.md
```

---
##  Sobre os Dados

O case fornece três arquivos principais em formato `.json`:

- `offers.json`: metadados das ofertas.
- `profile.json`: características dos clientes.
- `transactions.json`: eventos como transações e recebimento de ofertas.

---

##  Etapas do Projeto

1. **Exploração e tratamento de dados**:
   - Unificação de transações, perfis e ofertas
   - Criação de variáveis como `foi_visualizada`, `foi_completada`, `tempo_ate_visualizacao`, etc.
   - Normalização e encoding de variáveis

2. **Modelagem preditiva**:
   - Modelos treinados: `Random Forest` e `XGBoost`
   - Comparação de desempenho por acurácia, ROC-AUC e validação cruzada
   - Avaliação de importância das variáveis
   - Escolha do melhor modelo

3. **Geração de entregáveis**:
   - Apresentação executiva com resultados e impacto projetado
   - Salvamento do modelo final `.pkl`

---

##  Modelagem

O notebook `2_modeling.ipynb` contém o processo de modelagem para prever a probabilidade de um cliente completar uma oferta.

### Modelos Avaliados:
- `Random Forest`
- `XGBoost`

####  Avaliação

| Métrica                      | Random Forest | XGBoost |
|-----------------------------|---------------|---------|
| AUC ROC (teste)             | **0.92**      | 0.85    |
| AUC ROC (validação cruzada) | 0.7856        | **0.8397** |
| Acurácia                    | 0.85          | 0.81    |

####  Interpretação

- **Random Forest** teve melhor desempenho no conjunto de teste e boa diversidade nas variáveis relevantes (`age`, `limit`, `discount`, etc.).
- **XGBoost** foi mais estável em validação cruzada, mas dependente demais da variável `discount_value`.

####  Decisão

> O modelo final escolhido foi o **Random Forest**, por apresentar melhor equilíbrio entre desempenho, interpretabilidade e estabilidade.

O modelo foi salvo em:  
`/models/model_random_forest.pkl`

---

## Como Executar o Projeto

### 1. Clone o repositório:

```bash
git clone https://github.com/luisabecegato/ifood-case.git
cd ifood-case

