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

##  Sobre os Dados

O case fornece três arquivos principais em formato `.json`:

- `offers.json`: metadados das ofertas.
- `profile.json`: características dos clientes.
- `transactions.json`: eventos como transações e recebimento de ofertas.

---

##  Pipeline do Projeto

1. **Exploração e limpeza dos dados** com PySpark.
2. **Criação de features** representando comportamento do cliente e interação com ofertas.
3. **Construção de um dataset unificado** por cliente + oferta.
4. **Modelagem preditiva** para determinar a probabilidade de uma oferta resultar em conversão.
5. **Geração de recomendações personalizadas**.
6. **Apresentação executiva** com resultados e impacto projetado.

---

## 🏗 Estrutura do Repositório
'''
ifood-case/
├── data/
│ ├── raw/
│ └── processed/
├── notebooks/
│ ├── 1_data_processing.ipynb
│ └── 2_modeling.ipynb
├── presentation/
│ └── ifood_case_slides.pdf
├── src/
├── requirements.txt
└── README.md

'''
