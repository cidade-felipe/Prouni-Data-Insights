# Prouni Data Insights

Análise de dados do Programa Universidade para Todos (Prouni) com preparação em Python e dashboard final em Power BI. O projeto organiza, trata e apresenta a evolução das bolsas entre 2005 e 2019, destacando recortes por tipo de bolsa, gênero, raça, região, estado e modalidade de ensino.

## Objetivo

O projeto foi desenvolvido para transformar dados públicos do Prouni em uma leitura visual clara sobre:

- crescimento das bolsas ao longo do tempo;
- diferença entre bolsas integrais e bolsas parciais de 50%;
- distribuição regional e estadual;
- perfil demográfico dos beneficiários;
- participação por sexo, raça e modalidade de ensino.

## Dashboard em Power BI

O principal entregável analítico do repositório é o arquivo [reports/prouni-data-report.pbix](reports/prouni-data-report.pbix), estruturado em três páginas principais:

### 1. Visão Geral

- indicadores consolidados de bolsas concedidas;
- comparação anual entre total de bolsas, bolsas integrais e bolsas parciais;
- distribuição total por região;
- participação entre ensino presencial e EaD;
- filtros por tipo de bolsa e ano.

### 2. Detalhes População

- evolução anual das bolsas por gênero;
- evolução anual por raça;
- análise com filtro de idade;
- combinação de filtros por tipo de bolsa e ano.

### 3. Detalhes Regiões

- crescimento das bolsas por ano e por região;
- mapa coroplético com total de bolsas concedidas por estado;
- exploração temporal entre 2005 e 2019;
- filtro por tipo de bolsa.

## Principais insights explorados

- o Sudeste concentra o maior volume de bolsas no período analisado;
- bolsas integrais representam a maior parcela do total concedido;
- o dashboard permite observar crescimento acumulado do programa ao longo da série histórica;
- os recortes demográficos ajudam a comparar a evolução do acesso ao ensino superior entre diferentes grupos.

## Tecnologias utilizadas

- Python
- Pandas
- Jupyter Notebook
- Plotly
- Matplotlib
- KaggleHub
- Power BI
- GeoJSON para visualização geográfica por UF

## Estrutura do projeto

```text
Prouni-Data-Insights/
├── data/
│   └── processed/
│       └── prouni_2005_2019_processed.csv
├── figures/
│   └── ... # Exportações gráficas geradas na análise exploratória
├── notebooks/
│   ├── brazil-states.geojson
│   ├── preprocessed.ipynb
│   └── prouni_insights.ipynb
├── reports/
│   ├── prouni-data-report.pbix
│   └── image/
│       ├── borracha.png
│       ├── fundo.png
│       └── logo.png
├── requirements.txt
├── LICENSE
└── README.md
```

## Como executar a preparação dos dados

1. Clone o repositório.
2. Crie um ambiente virtual, se desejar.
3. Instale as dependências.
4. Abra os notebooks em `notebooks/`.
5. Execute o fluxo de tratamento e análise exploratória.

```bash
pip install -r requirements.txt
```

Observação: o dataset pode ser obtido via `kagglehub` durante a execução dos notebooks, dependendo do fluxo usado na sua máquina.

## Como abrir o dashboard

1. Abra o arquivo `reports/prouni-data-report.pbix` no Power BI Desktop.
2. Atualize as fontes de dados, se necessário.
3. Navegue entre as páginas `Visão Geral`, `Detalhes População` e `Detalhes Regiões`.

## Possíveis evoluções

- publicar o dashboard no Power BI Service;
- adicionar métricas socioeconômicas complementares;
- criar uma camada de storytelling com insights por página;
- automatizar o pipeline de atualização dos dados.

## Licença

Este projeto está sob a licença MIT. Consulte [LICENSE](LICENSE).

## Autor

Desenvolvido por **Felipe Cidade**.

- [LinkedIn](https://www.linkedin.com/in/cidadefelipe/)
- [GitHub](https://github.com/cidade-felipe)
