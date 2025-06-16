# Baobá - Scripts de Processamento e Visualização de Dados de Monitoramentos

Este repositório reúne scripts e notebooks para análise de dados de monitoramentos temáticos, com foco em métricas de **ocorrências** e **interações**. O objetivo é viabilizar comparações entre períodos, análises por categoria e geração de gráficos automatizados com base em dados estruturados.

## Estrutura do Repositório

- `baoba_compara_monitoramentos_por_periodo.py`\
  Classe `ComparadorMonitoramentoPoPeriodo` realiza comparação gráfica de ocorrências e interações entre dois períodos. Gera visualizações lado a lado e destaca variações percentuais.

- `baoba_processamento_dados_geral.py`\
  Script para tratamento e visualização de dados agregados. Permite gerar gráficos por categoria, serviço e linha do tempo (ocorrências e interações).

- `baoba_processamento_dados_por_monitoramento.py`\
  Foca na análise de um monitoramento específico. Permite destacar picos, anotar eventos e visualizar distribuição de interações por plataforma.

- `dropdown_utils.py`\
  Conjunto de funções utilitárias que criam widgets Dropdown para filtrar DataFrames de modo interativo em notebooks Jupyter ou Google Colab.

- `COLAB _Baoba_gera_grafico_comparativo_1.2.ipynb`\
  Notebook interativo que permite gerar gráficos comparativos entre dois períodos diretamente no Google Colab.

- `COLAB _Baoba_relatorio_geral_1.4.ipynb`\
  Notebook para geração de análises agregadas, com foco na comparação entre categorias temáticas.

- `COLAB _Baoba_relatorio_por_tema_1.3.ipynb`\
  Notebook que permite analisar monitoramentos de forma individual, com visualizações específicas por tema.

## Pré-requisitos

- Python ≥ 3.9
- Bibliotecas:
  - `pandas`
  - `matplotlib`
  - `seaborn`
  - `plotly`
  - `notebook`
  - `ipywidgets`

Instale os pacotes necessários com:

```bash
pip install -r requirements_colab_jupyter.txt
```

## Como Usar

1. **Clone o repositório com token (obrigatório no Colab)**\
   Gere primeiro o PAT seguindo a seção [Clonagem com Personal Access Token (PAT)](#clonagem-com-personal-access-token-pat). Em seguida execute:

   ```bash
   git clone https://oauth2:SEU_TOKEN@git.ibict.br/data_science/baoba.git
   ```

   Caso prefira esconder o token, configure um arquivo `.netrc` conforme mostrado na mesma seção.

2. Navegue até a pasta:

   ```bash
   cd baoba
   ```

3. Execute os scripts conforme necessário, adaptando para os seus arquivos CSV ou DataFrames.

## Licença

Este repositório está licenciado sob os termos da [MIT License](LICENSE), salvo indicação contrária nos notebooks.

## Clonagem com Personal Access Token (PAT)

Este repositório é privado, por isso qualquer tentativa de clonar via HTTPS sem autenticação vai falhar com o erro **HTTP Basic: Access denied**. Você precisa gerar um Personal Access Token (PAT) no GitLab e passá‑lo ao `git`.

### Gerar o token

1. Entre no repositório do projeto baoba e clique em Settings.
2. No menu esquerdo escolha **Access Tokens**.
3. Preencha **Name** (ex: `colab-clone`) e defina **Expires at** se quiser limitar a validade.
4. Marque **read_repository**. Qualquer outro escopo é opcional.
5. Clique **Create personal access token** e **copie** o valor exibido – ele não aparecerá de novo.

### Clonar com o token

#### Opção rápida (token na URL)

```bash
git clone https://oauth2:SEU_TOKEN@git.ibict.br/data_science/baoba.git
```

- Deixe `oauth2:` exatamente como está – é o usuário que o GitLab espera.

### Mantendo o repositório atualizado

Depois do primeiro clone, basta:

```bash
cd baoba
git pull
```

Sem o token configurado (via URL) o `git pull` também falhará.
