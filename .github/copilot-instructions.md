# Instruções do Copilot — analise-tesouro-direto

## Visão Geral do Projeto

Este projeto é um trabalho acadêmico de análise de dados escrito em português para a especialização em *Análise de Dados e Boas Práticas* da PUC. Ele utiliza o conjunto de dados **Taxas dos Títulos Ofertados pelo Tesouro Direto** para demonstrar o pipeline completo de ciência de dados, desde a definição do problema até a análise exploratória e pré-processamento.

## Estrutura do Repositório

```
analise-tesouro-direto/
├── analise_tesouro_direto.ipynb   # Notebook principal do Google Colab (relatório)
├── .github/
│   └── copilot-instructions.md   # Este arquivo
├── README.md
├── LICENSE
└── .gitignore
```

## Linguagem e Ambiente de Execução

- **Linguagem:** Python 3.x
- **Ambiente principal:** Google Colab (compatível com Jupyter)
- **Bibliotecas principais:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`

## Convenções de Codificação

- Seguir o guia de estilo **PEP 8** em todas as células de código.
- Usar **snake_case** para nomes de variáveis e funções.
- Preferir **f-strings** em vez de `%` ou `.format()` para interpolação de strings.
- Cada etapa lógica deve estar em sua própria célula de código.
- Toda célula de código deve ser precedida por uma **célula Markdown** que explica em português o que a célula faz e por quê.
- **Não** usar caminhos de arquivos locais codificados; carregar dados diretamente da URL pública:
  ```
  https://www.tesourotransparente.gov.br/ckan/dataset/df56aa42-484a-4a59-8184-7676580c81e3/resource/796d2059-14e9-44e3-80c9-2d9e30b405c1/download/precotaxatesourodireto.csv
  ```
- Separar imports apenas para exibição dos imports funcionais.
- Importar todas as bibliotecas no topo do notebook em uma única célula dedicada.

## Estrutura do Notebook

1. **Capa / Título** — Título, autor, instituição, data.
2. **Definição do Problema** — Contexto, objetivos, hipóteses, definições de atributos.
3. **Carregamento dos Dados** — Carregar CSV da URL, primeira inspeção.
4. **Análise Exploratória**
   - Estatísticas descritivas (shape, dtypes, `describe()`, valores ausentes)
   - Visualizações com parágrafos de análise após cada gráfico
5. **Pré-processamento**
   - Conversões de tipo, tratamento de valores ausentes, normalização, padronização, discretização, one-hot encoding
6. **Conclusão** — Resumo das descobertas e próximos passos.

## Estilo dos Gráficos

- Usar `matplotlib` e `seaborn` para todos os gráficos.
- Definir o estilo do `seaborn` como `"whitegrid"` e a paleta `"muted"` globalmente no início.
- Sempre rotular os eixos e definir um `title` descritivo.
- Após cada gráfico, escrever um parágrafo de análise em Markdown (em português) resumindo as principais descobertas.

## Idioma da Documentação

Todas as células Markdown/texto devem ser escritas em **português brasileiro**. Comentários no código podem estar em inglês ou português — manter consistência dentro de um arquivo.

## Notas sobre os Dados

- O CSV usa ponto e vírgula (`;`) como separadores e vírgulas (`,`) como separadores decimais.
- Colunas de data (`Data Vencimento`, `Data Base`) devem ser analisadas como objetos `datetime`.
- Colunas numéricas (`Taxa Compra Manha`, etc.) devem ser convertidas para `float` após substituir `,` por `.`.
- O conjunto de dados contém títulos de múltiplos tipos (`Tipo Titulo`) abrangendo muitos anos; sempre filtrar ou agrupar por tipo de título antes da análise de séries temporais.
