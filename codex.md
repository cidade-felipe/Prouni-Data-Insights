# Memória do projeto — Prouni Data Insights

## Visão geral

Este repositório reúne um fluxo de análise dos dados de bolsas do Programa Universidade para Todos (Prouni) entre 2005 e 2019. O trabalho combina preparação e exploração em notebooks Python com um dashboard de três páginas no Power BI.

Estado atual: projeto analítico funcional e orientado a portfólio, com notebooks, arquivo GeoJSON, relatório `.pbix`, exportação em PDF e capturas das páginas do dashboard. Não há suíte automatizada de testes.

## Fluxo principal

1. `notebooks/preprocessed.ipynb` baixa o dataset `lfarhat/brasil-students-scholarship-prouni-20052019` pelo KaggleHub.
2. O notebook padroniza nomes de colunas, remove registros nulos, exclui CPF, data de nascimento e código e-MEC, limita a idade ao intervalo de 15 a 90 anos e remove bolsas complementares de 25%.
3. O resultado é salvo como `data/processed/prouni_2005_2019_processed.csv`.
4. `notebooks/prouni_insights.ipynb` cria faixas etárias e visualizações interativas com Plotly e ipywidgets, incluindo recortes por tipo de bolsa, sexo, raça, região, período e UF.
5. `reports/prouni-data-report.pbix` concentra a entrega visual final. `reports/pdf/prouni-data-report.pdf` e `reports/images/` oferecem versões de consulta sem o Power BI Desktop.

## Estrutura relevante

- `notebooks/preprocessed.ipynb`: aquisição, limpeza e exportação dos dados.
- `notebooks/prouni_insights.ipynb`: análise exploratória e gráficos interativos.
- `notebooks/brazil-states.geojson`: geometrias estaduais usadas no mapa coroplético.
- `figures/`: ativos visuais e possíveis exportações dos gráficos dos notebooks.
- `reports/prouni-data-report.pbix`: dashboard editável no Power BI Desktop.
- `reports/pdf/prouni-data-report.pdf`: exportação estática do dashboard.
- `reports/images/`: capturas das três páginas do relatório.
- `requirements.txt`: dependências Python fixadas por versão.
- `README.md`: apresentação pública e instruções de uso.

O CSV processado não é versionado: os caminhos correspondentes estão no `.gitignore`.

## Tecnologias e dependências

- Python 3.12, conforme os metadados atuais dos notebooks.
- pandas e NumPy para tratamento e agregação.
- KaggleHub para obtenção do dataset.
- Plotly, Matplotlib, ipywidgets, ipyfilechooser e Kaleido para exploração e exportação de gráficos.
- GeoJSON para o mapa por unidade federativa.
- Power BI Desktop para abrir e editar o relatório `.pbix`.

## Preparação do ambiente

No PowerShell, a partir da raiz do projeto:

```powershell
python -m venv venv
.\venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install -r requirements.txt
```

Todo comando Python do projeto deve usar o interpretador local `venv\Scripts\python.exe`. Não instalar nem executar dependências pelo Python global.

## Execução

1. Ativar o ambiente virtual local.
2. Abrir `notebooks/preprocessed.ipynb` e executar as células em ordem. A última célula cria automaticamente `data/processed/` e seus diretórios-pai, se necessário.
3. Confirmar a geração de `data/processed/prouni_2005_2019_processed.csv`.
4. Ajustar ou disponibilizar o CSV no caminho esperado pelo notebook exploratório, conforme a limitação registrada abaixo.
5. Abrir `notebooks/prouni_insights.ipynb` com o diretório de trabalho em `notebooks/` e executar as células em ordem.
6. Para consultar ou editar o dashboard, abrir `reports/prouni-data-report.pbix` no Power BI Desktop.

## Validação

Não há testes automatizados. Ao alterar o projeto:

- validar a sintaxe JSON dos notebooks sem reexecutá-los;
- conferir se os caminhos relativos continuam coerentes quando os notebooks são abertos a partir de `notebooks/`;
- verificar se os imports usados nos notebooks estão declarados em `requirements.txt`;
- conferir a existência das três páginas do dashboard e das respectivas imagens exportadas;
- revisar links e comandos do `README.md`;
- executar `git diff --check` para detectar problemas textuais.

Não reexecute o download, o tratamento completo ou o Power BI apenas para validar documentação, salvo quando isso for solicitado.

## Convenções e cuidados

- Responder e documentar em português do Brasil.
- Fazer a menor alteração correta possível e preservar mudanças locais não relacionadas.
- Antes de editar arquivos existentes, seguir a skill `city-safe-editor` e criar backup em `Backup/DD_MM_AAAA/`, sem copiar segredos, ambientes virtuais, caches ou artefatos gerados.
- Excluir `Backup/`, `.git/`, `venv/`, `.venv/`, caches e saídas geradas de buscas e análises normais.
- Não versionar o CSV processado nem dados pessoais removidos durante a limpeza.
- Não inventar métricas: números publicados devem ser confirmados pelo dashboard, pelos notebooks ou pelos dados processados.
- Manter o README e este arquivo alinhados quando mudarem arquitetura, dependências, comandos, fontes ou entregáveis.
- Não alterar o `.pbix` nem regenerar PDF ou imagens sem solicitação explícita.

## Limitações conhecidas

- `preprocessed.ipynb` grava o CSV em `data/processed/prouni_2005_2019_processed.csv`, enquanto `prouni_insights.ipynb` procura `data/prouni_2005_2019_processed.csv`. O fluxo exige alinhar esse caminho antes da execução integral.
- A aquisição pelo KaggleHub pode exigir autenticação e acesso à internet.
- O dashboard depende do Power BI Desktop para edição e atualização das fontes; a versão em PDF é somente para consulta.

## Histórico

### 2026-10-01

- Criado o `codex.md` com arquitetura, fluxo, comandos, regras de segurança, validações e limitações verificadas no repositório.
- Documentada a atualização do README para refletir os notebooks, as três páginas do Power BI, as capturas e o PDF atualmente presentes.
- Registrado que o notebook de pré-processamento cria automaticamente `data/processed/` e adicionada a dependência `ipyfilechooser==0.6.0` ao ambiente documentado.
