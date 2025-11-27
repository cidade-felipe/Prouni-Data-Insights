# Prouni Data Insights

Uma investigação visual e analítica sobre os dados do Programa Universidade para Todos. O projeto transforma dados públicos de bolsas em insights claros, comparáveis e visualmente intuitivos, permitindo entender quem recebe bolsas no Brasil e como esse cenário evolui ao longo dos anos.

## 🎯 Objetivo

O Prouni Data Insights revela padrões importantes sobre o acesso ao ensino superior no país. A proposta é explorar:

• Diferenças entre bolsas integrais e parciais
• Distribuição por sexo
• Perfil por faixa etária
• Evolução histórica por tipo de bolsa
• Comportamento regional e estadual
• Mapa interativo com distribuição por UF

A análise permite entender não apenas os números, mas o perfil de quem recebe ajuda do governo para estudar.

## 📊 Visualizações disponíveis

As principais visualizações incluem:

• Gráfico comparativo por tipo de bolsa
• Distribuição por sexo ao longo dos anos
• Tendência regional com crescimento percentual
• Mapa interativo do Brasil por estado
• Análise por idade usando faixas de cinco anos

Esses painéis tornam a leitura dos dados mais intuitiva e crítica ao mesmo tempo.

## 🧠 Tecnologias

Este projeto utiliza:

• **Python**
• **Pandas** para manipulação de dados
• **Plotly Express** para gráficos interativos
• **GeoJSON** para o mapa do Brasil
• **Jupyter Notebook** para análise e exploração colaborativa

## 🗂️ Estrutura do Projeto

```
TRABALHO_FINAL/
│
├── data/                      # Dados originais ou tratados
│
├── notebooks/                 # Notebooks de análise e visualização
│   ├── brazil-states.geojson  # Arquivo geográfico usado no mapa
│   ├── preprocessed.ipynb     # Limpeza e tratamento de dados
│   └── prouni_insights.ipynb  # Visualizações e análises finais
│
├── requirements.txt           # Dependências do projeto
└── .gitignore                 # Exclusões, incluindo /venv e arquivos locais
```

## ▶️ Como executar

1. Clone este repositório
2. Crie e ative um ambiente virtual (opcional, mas recomendado)
3. Instale as dependências
4. Abra os notebooks no Jupyter ou VSCode

```bash
pip install -r requirements.txt
```

Depois disso, basta executar as células e aproveitar os dashboards.

## 🚀 Futuras melhorias

Alguns caminhos interessantes para expandir o projeto:

• Dashboard online com **Streamlit**
• Previsões com métodos estatísticos ou Machine Learning
• Inclusão de dados socioeconômicos externos
• Análise comparativa com outras políticas públicas

## 💬 Contribuições

Sugestões, melhorias e novas visualizações são muito bem-vindas. Para contribuir, basta abrir uma issue ou enviar um pull request.
