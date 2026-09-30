# 📊 Y.Afisha — Análise de Produto, Vendas e Marketing

Análise exploratória e estratégica dos dados da **Y.Afisha**, com foco em compreender o comportamento dos usuários, a evolução das vendas e a eficiência dos investimentos de marketing.  
O projeto integra dados de **visitas, pedidos e custos de marketing** para calcular métricas como **retenção, recorrência, LTV, CAC, ROI e tempo até a primeira compra**.

---

## 🎯 Objetivo do Projeto

O objetivo é transformar os registros operacionais da Y.Afisha em indicadores capazes de responder três perguntas de negócio:

- **Produto:** como os usuários utilizam a plataforma e com que frequência retornam?
- **Vendas:** quando os usuários começam a comprar, quantos pedidos realizam e quanto valor geram?
- **Marketing:** quanto é investido, quanto custa adquirir clientes e qual é o retorno dos investimentos?

A análise também segmenta os resultados por **canal de marketing, dispositivo e período**, permitindo identificar padrões de desempenho ao longo do tempo.

---

## 🧠 Abordagem / Arquitetura Técnica

O notebook segue um fluxo analítico dividido em quatro etapas principais:

### 1. Preparação e otimização dos dados

Os arquivos são inicialmente carregados em pequenas amostras para inspeção e otimização antes da leitura completa.

Principais tratamentos realizados:

- inspeção das primeiras linhas das tabelas;
- análise de tipos e tamanho dos DataFrames em memória;
- padronização dos nomes das colunas;
- otimização de tipos de dados;
- conversão de campos temporais para `datetime`;
- utilização de `category` para variáveis categóricas;
- carregamento dos dados completos após a etapa de preparação.

### 2. Análise do produto

A utilização da plataforma é analisada a partir dos registros de visitas, considerando:

- usuários ativos por dia, semana e mês;
- número de sessões;
- duração das sessões;
- frequência de retorno;
- retenção de usuários;
- comportamento de recorrência.

### 3. Análise de vendas

Os pedidos são utilizados para investigar:

- momento da primeira compra;
- quantidade de pedidos por cliente;
- tamanho médio das compras;
- receita gerada;
- **LTV (Lifetime Value)**;
- tempo entre aquisição e primeira conversão;
- comportamento das coortes ao longo do tempo.

### 4. Análise de marketing

Os dados de custos e aquisição são relacionados às visitas e aos pedidos para avaliar:

- investimento total em marketing;
- distribuição dos gastos por canal;
- evolução mensal dos investimentos;
- **CAC (Custo de Aquisição de Cliente)**;
- **ROI (Return on Investment)**;
- diferenças entre dispositivos `desktop` e `touch`;
- desempenho dos canais ao longo do tempo.

Para a análise de CAC e ROI por dispositivo, os custos são distribuídos proporcionalmente à quantidade de novos clientes de cada dispositivo dentro do canal e mês correspondente.

---

## 📈 Principais Métricas

| Métrica | Objetivo |
|---|---|
| **Retenção** | Avaliar a permanência e o retorno dos usuários ao produto |
| **Recorrência** | Entender a frequência com que os clientes realizam novas compras |
| **LTV** | Estimar o valor gerado pelos clientes ao longo do ciclo de vida |
| **CAC** | Medir o custo associado à aquisição de novos clientes |
| **ROI** | Avaliar o retorno financeiro dos investimentos de marketing |
| **Tempo até a primeira compra** | Compreender a velocidade de conversão dos usuários |

---

## 🗂️ Estrutura do Repositório

```text
y.afisha_entretenimento/
│
├── datasets/
│   ├── costs_us.csv
│   ├── orders_log_us.csv
│   └── visits_log_us.csv
│
├── notebooks/
│   └── notebook.ipynb
│
└── requirements.txt
```

### 📁 Descrição das pastas e arquivos

- `datasets/` — contém os dados utilizados na análise:
  - `visits_log_us.csv`: registros de acesso e navegação dos usuários;
  - `orders_log_us.csv`: registros de pedidos e receitas;
  - `costs_us.csv`: investimentos em marketing.
- `notebooks/` — contém o Jupyter Notebook com todo o processo de análise, tratamento, visualização e interpretação dos dados.
- `requirements.txt` — lista as dependências necessárias para reproduzir o projeto.

---

## 🚀 Instalação e Execução

### 1. Clonar o repositório

```bash
git clone https://github.com/alexpereira951/y.afisha_entretenimento
cd y.afisha_entretenimento
```

### 2. Criar e ativar um ambiente virtual

```bash
python -m venv .venv
```

**Windows:**

```bash
.venv\Scripts\activate
```

**Linux/macOS:**

```bash
source .venv/bin/activate
```

### 3. Instalar as dependências

```bash
pip install -r requirements.txt
```

### 4. Executar o Jupyter Notebook

```bash
jupyter notebook
```

Depois, abra:

```text
notebooks/notebook.ipynb
```

> O notebook utiliza caminhos relativos para os dados, portanto a estrutura de diretórios deve ser mantida conforme apresentada neste README.

---

## 🛠️ Stack Tecnológica

- 🐍 **Python**
- 🐼 **Pandas** — manipulação, transformação e agregação dos dados
- 🔢 **NumPy** — operações numéricas
- 📊 **Matplotlib** — visualizações estáticas
- 🎨 **Seaborn** — heatmaps e visualizações estatísticas
- 📈 **Plotly Express** — visualizações interativas
- 📓 **Jupyter Notebook** — desenvolvimento e documentação da análise

---

## 🔎 Principais Resultados

A análise identificou diferenças relevantes entre os canais de marketing e também mudanças no desempenho ao longo do período analisado.

### Marketing

- Os **Canais 1 e 2** apresentaram CAC relativamente baixo em diversos períodos e alguns dos maiores valores de ROI observados.
- O **Canal 3** recebeu o maior volume de investimento entre os canais analisados, mas apresentou ROI predominantemente negativo ao longo da série histórica.
- O investimento em **Desktop** representou aproximadamente **74,3%** do orçamento analisado, enquanto **Touch** representou **25,7%**.
- Os investimentos apresentaram concentração relevante nos **Canais 1, 2 e 3**.
- Foi identificado um pico de investimento em **novembro e dezembro de 2017**.
- A análise temporal indica **deterioração da eficiência em 2018**, com aumento do CAC e redução do ROI em diversos canais.

### Vendas e comportamento dos clientes

- A análise de LTV indica crescimento do valor gerado pelos clientes ao longo do ciclo de vida.
- A recorrência e a retenção apresentam pontos importantes de atenção, especialmente nas coortes mais recentes.
- A primeira compra pode ocorrer rapidamente para parte dos usuários, mas a janela de **8 a 30 dias** apresenta relevância no volume de conversões por coorte.

---

## 📊 Visualizações

O notebook utiliza diferentes representações gráficas para explorar os dados, incluindo:

- gráficos de evolução temporal;
- gráficos de barras para investimentos;
- gráficos de linha para acompanhamento mensal;
- histogramas;
- boxplots;
- heatmaps de **CAC**;
- heatmaps de **ROI**;
- análises segmentadas por canal e dispositivo.

---

## 💡 Insights de Negócio

Os resultados apontam para a necessidade de acompanhar a eficiência do orçamento de marketing de forma contínua, combinando métricas de aquisição e de valor do cliente.

Entre os principais pontos identificados estão:

1. **Canais 1 e 2** apresentam indicadores historicamente favoráveis de CAC e ROI.
2. O **Canal 3** combina alto investimento com ROI predominantemente negativo, justificando uma investigação detalhada de sua eficiência.
3. A diferença entre **2017 e 2018** indica uma mudança relevante no desempenho dos investimentos de marketing.
4. A análise de **retenção e recorrência** mostra que aumentar o valor gerado pela base existente é uma frente importante.
5. A jornada de conversão deve ser acompanhada em diferentes horizontes de tempo, considerando tanto conversões rápidas quanto aquelas que acontecem semanas após o primeiro contato.

---

## ⚠️ Limitações

O projeto apresenta algumas limitações que devem ser consideradas na interpretação dos resultados:

1. **Distribuição dos custos por dispositivo:** para calcular CAC e ROI por dispositivo, os custos de marketing são distribuídos proporcionalmente ao número de novos clientes de cada dispositivo dentro de cada canal e mês. Essa é uma hipótese analítica e não necessariamente representa o custo real atribuído a cada dispositivo.

2. **Atribuição da origem do cliente:** a origem e o dispositivo utilizados na análise de aquisição são associados à primeira visita identificada para cada usuário. Esse critério não contempla modelos de atribuição multicanal ou interações posteriores com outras fontes.

3. **Dados históricos e cobertura temporal:** os resultados refletem o período disponível nos arquivos analisados. Mudanças posteriores nas campanhas, comportamento dos usuários, estratégia comercial ou ambiente competitivo não estão contempladas.

4. **Interpretação de causalidade:** as análises são predominantemente descritivas e exploratórias. Relações entre investimento, CAC, ROI, retenção e receita não devem ser interpretadas automaticamente como relações causais sem experimentos ou análises adicionais.

---

## 📌 Conclusão

A análise da Y.Afisha demonstra como dados de **produto, vendas e marketing** podem ser integrados para construir uma visão mais completa da eficiência do negócio.

O acompanhamento conjunto de **ROI, CAC, LTV, retenção, recorrência e conversão por coorte** permite avaliar não apenas o custo de aquisição, mas também o valor gerado após a entrada do cliente na base.

Os resultados históricos destacam diferenças importantes entre os canais de marketing e uma deterioração de eficiência em 2018, fornecendo uma base analítica para investigações posteriores sobre alocação de orçamento, aquisição e retenção.

---

## 👤 Autor

Projeto desenvolvido como estudo de **Análise de Dados / Data Analytics**, com foco em transformação de dados, métricas de negócio, visualização e geração de insights para tomada de decisão.
