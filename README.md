# Análise de Vendas no Varejo

**X-Análises · Dados que geram resultados**

Projeto de estudo em Ciência de Dados que explora uma base de vendas de varejo com **Python, Pandas e NumPy** e apresenta os indicadores em um dashboard interativo.

[Abrir o dashboard HTML](./dashboard_varejo_x_analises.html) · [Abrir o notebook do projeto](./projeto_pandas_numpy_varejo.ipynb)

## Sobre o projeto

O notebook percorre etapas de exploração e preparação dos dados, cálculo de indicadores e análise de vendas por período, loja, categoria, forma de pagamento e operador. As metas são **individuais por operador**, não uma meta coletiva da equipe.

O dashboard foi criado em HTML, CSS e JavaScript. Ele incorpora os dados e a logo no próprio arquivo, então pode ser aberto diretamente no navegador sem instalar bibliotecas ou iniciar um servidor.

## Funcionalidades

- Indicadores de vendas líquidas, cupons distintos, ticket médio e atingimento de metas individuais.
- Evolução diária e comparação de vendas por loja.
- Ranking e resumo por operador, com vendas, cupons, ticket médio e progresso da meta.
- Análise por categoria e forma de pagamento.
- Filtros por período, loja, operador, categoria e pagamento.
- Exportação da seleção atual e resumo de qualidade da base.
- Tratamento de registros sem operador identificado: permanecem nas vendas totais, mas não entram no ranking individual.

## Dados

O arquivo `vendas_loja_sinteticas.csv` contém **4.865 linhas de itens de venda**, de **1º de agosto a 31 de outubro de 2026**. Os dados são **sintéticos e destinados a estudo**; não representam vendas reais.

| Coluna | Descrição |
| --- | --- |
| `data` | Data da venda |
| `cupom_id` | Identificador do cupom |
| `loja` | Identificação da loja |
| `operador_id` | Identificação do operador |
| `cliente_id` | Identificador fictício do cliente |
| `categoria` | Categoria do produto |
| `produto` | Produto vendido |
| `quantidade` | Unidades do item |
| `preco_unitario` | Preço por unidade antes do desconto |
| `desconto_pct` | Desconto em fração; `0.15` equivale a 15% |
| `forma_pagamento` | Forma de pagamento |
| `meta_mensal` | Meta mensal individual do operador |

### Regras dos indicadores

- **Venda líquida por item:** quantidade × preço unitário × (1 − desconto).
- **Cupons:** contagem distinta de `cupom_id` no recorte selecionado.
- **Ticket médio:** vendas líquidas ÷ cupons distintos.
- **Meta:** cada operador é comparado à própria meta mensal, considerando os meses do período selecionado.
- O painel remove duplicatas exatas e desconsidera registros com quantidade, preço ou desconto inválidos nos cálculos. As categorias também são padronizadas para facilitar a análise.

## Como usar

### Dashboard

Baixe ou clone o repositório e abra `dashboard_varejo_x_analises.html` em um navegador atualizado. O painel funciona localmente, sem dependências externas.

### Notebook

Com Python instalado, crie um ambiente virtual e instale as bibliotecas usadas no projeto:

```bash
python -m venv .venv
```

Ative o ambiente no Windows PowerShell:

```powershell
.\.venv\Scripts\Activate.ps1
```

Ou no macOS/Linux:

```bash
source .venv/bin/activate
```

Instale as dependências e abra o notebook:

```bash
python -m pip install pandas numpy notebook
jupyter notebook projeto_pandas_numpy_varejo.ipynb
```

## Arquivos principais

- `projeto_pandas_numpy_varejo.ipynb` — análise e preparação dos dados.
- `vendas_loja_sinteticas.csv` — base usada pelo dashboard.
- `dashboard_varejo_x_analises.html` — painel interativo independente.
- `logo-x-analises.png` — identidade visual do projeto.

## Tecnologias

Python · Pandas · NumPy · Jupyter Notebook · HTML · CSS · JavaScript

---

Projeto educacional de portfólio — **X-Análises**.
