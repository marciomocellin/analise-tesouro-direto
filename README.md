# Análise do Tesouro Direto

Trabalho de conclusão da disciplina **Análise de Dados e Boas Práticas** da especialização em Ciência de Dados da PUC.

## Descrição

Este projeto realiza a análise exploratória e o pré-processamento do dataset público
**Taxas dos Títulos Ofertados pelo Tesouro Direto**, disponibilizado pelo Tesouro Nacional
por meio da plataforma Tesouro Transparente.

O objetivo é percorrer as etapas fundamentais de um projeto de ciência de dados:
definição do problema, entendimento dos dados, análise exploratória (EDA) e
pré-processamento — servindo como relatório técnico e acadêmico.

## Dataset

| Item | Detalhes |
|------|----------|
| **Nome** | Taxas dos Títulos Ofertados pelo Tesouro Direto |
| **Fonte** | [Tesouro Transparente](https://www.tesourotransparente.gov.br) |
| **URL do CSV** | [precotaxatesourodireto.csv](https://www.tesourotransparente.gov.br/ckan/dataset/df56aa42-484a-4a59-8184-7676580c81e3/resource/796d2059-14e9-44e3-80c9-2d9e30b405c1/download/precotaxatesourodireto.csv) |
| **Metadados** | [taxa.pdf](https://www.tesourotransparente.gov.br/ckan/dataset/df56aa42-484a-4a59-8184-7676580c81e3/resource/1a8eb2e3-4902-4a38-a1eb-6410f23d90de/download/taxa.pdf) |
| **Frequência** | Diária |
| **Formato** | CSV (separador `;`, decimal `,`) |

### Atributos principais

| Coluna | Descrição |
|--------|-----------|
| `Tipo Titulo` | Nome do título (ex.: Tesouro Selic, Tesouro IPCA+) |
| `Data Vencimento` | Data de vencimento do título |
| `Data Base` | Data de referência do registro |
| `Taxa Compra Manha` | Taxa de compra registrada no período da manhã (% a.a.) |
| `Taxa Venda Manha` | Taxa de venda registrada no período da manhã (% a.a.) |
| `PU Compra Manha` | Preço unitário de compra — manhã (R$) |
| `PU Venda Manha` | Preço unitário de venda — manhã (R$) |
| `PU Base Manha` | Preço unitário base — manhã (R$) |

## Estrutura do Repositório

```
analise-tesouro-direto/
├── analise_tesouro_direto.ipynb   # Notebook principal (Google Colab)
├── .github/
│   └── copilot-instructions.md   # Instruções para o GitHub Copilot
├── README.md                      # Este arquivo
├── LICENSE
└── .gitignore
```

## Como Executar

1. Acesse o notebook no Google Colab (recomendado) ou em qualquer ambiente Jupyter local.
2. Execute todas as células em sequência (`Runtime → Run all`).
3. Nenhuma dependência local é necessária: o dataset é carregado diretamente da URL pública.

### Dependências Python

As bibliotecas abaixo são pré-instaladas no Google Colab. Para ambiente local, instale com:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

| Biblioteca | Versão mínima | Uso |
|------------|--------------|-----|
| `pandas` | 1.5 | Manipulação de dados |
| `numpy` | 1.23 | Operações numéricas |
| `matplotlib` | 3.6 | Visualizações |
| `seaborn` | 0.12 | Visualizações estatísticas |
| `scikit-learn` | 1.1 | Normalização e pré-processamento |

## Conteúdo do Notebook

1. **Definição do Problema** — contexto, objetivos, hipóteses e atributos do dataset.
2. **Carregamento e Inspeção Inicial** — leitura do CSV, primeiras linhas e tipos de dados.
3. **Análise Exploratória (EDA)**
   - Estatísticas descritivas
   - Análise de valores faltantes e inconsistentes
   - Distribuição dos atributos (histogramas, boxplots)
   - Séries temporais de taxas e preços
   - Correlações entre atributos numéricos
4. **Pré-processamento**
   - Conversão de tipos (datas e numéricos)
   - Tratamento de valores faltantes
   - Normalização (Min-Max Scaling)
   - Padronização (Z-score)
   - Discretização de taxas em faixas
   - One-hot encoding do tipo de título
5. **Conclusão** — resumo dos achados e próximos passos.

## Checklist do Projeto

### Definição do Problema
- [x] Descrição do problema
- [x] Tipo de aprendizado (supervisionado / não supervisionado)
- [x] Hipóteses e premissas
- [x] Restrições para seleção dos dados
- [x] Definição de cada atributo

### Análise de Dados
- [x] Contagem de atributos e instâncias
- [x] Tipos de dados dos atributos
- [x] Verificação das primeiras linhas
- [x] Valores faltantes, discrepantes ou inconsistentes
- [x] Resumo estatístico (mín, máx, mediana, moda, média, desvio-padrão, ausentes)
- [x] Distribuição de cada atributo
- [x] Gráficos com análise textual

### Pré-processamento
- [x] Conversão de tipos
- [x] Tratamento de valores faltantes
- [x] Normalização (Min-Max)
- [x] Padronização (Z-score)
- [x] Discretização
- [x] One-hot encoding

## Licença

Este projeto está licenciado sob os termos da [MIT License](LICENSE).

