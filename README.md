# 📊 Análise do Censo IBGE 2022 — Benevides/PA com Projeções Futuras

<a href="https://colab.research.google.com/github/jottaene13/An-lise-do-Censo-IBGE-2022---Benevides-PA-com-Proje-es-Futuras/blob/main/TCC_VERS%C3%83O_FINAL.ipynb" target="_parent">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

---

## 🎓 Sobre o Projeto

Este trabalho é o **Trabalho de Conclusão de Curso (TCC)** de **João Pinheiro dos Santos Neto**, que apresenta uma análise abrangente dos dados do **Censo Demográfico 2022 do IBGE** aplicada ao município de **Benevides, estado do Pará**.

Utilizando técnicas de **Ciência de Dados** e **Estatística Computacional**, o projeto investiga as dimensões demográfica, educacional e habitacional do município, produzindo **projeções até o ano de 2042** fundamentadas em modelos estatísticos e nas tendências históricas dos censos anteriores do IBGE.

---

## 🗺️ Sobre Benevides/PA

Benevides é um município da **Região Metropolitana de Belém**, no estado do Pará, conhecido pelo crescimento populacional acelerado impulsionado pela proximidade com a capital paraense. A análise deste censo revela os desafios e oportunidades que esse crescimento traz para o planejamento urbano e as políticas públicas locais.

---

## 🔍 Estrutura da Análise

| # | Seção | Descrição |
|---|---|---|
| 1️⃣ | **Análise Exploratória (EDA)** | Inspeção dos dados brutos: valores nulos, estatísticas descritivas e visualização das séries históricas |
| 2️⃣ | **Crescimento Populacional** | Três modelos de projeção comparados com métricas de avaliação (R², RMSE, IC 95%) |
| 3️⃣ | **Pirâmide Etária** | Evolução da estrutura etária com fatores de ajuste demográfico por faixa |
| 4️⃣ | **Educação** | Taxa de alfabetização e nível de instrução com projeções baseadas em tendências nacionais |
| 5️⃣ | **Domicílios** | Características e composição domiciliar com projeções empíricas |
| 6️⃣ | **Conclusões** | Síntese dos principais achados e implicações para o planejamento municipal |

---

## 🤖 Modelos Utilizados

### 📈 Crescimento Populacional
- **Regressão Linear** — assume crescimento constante por período
- **Regressão Polinomial (grau 2)** — captura aceleração ou desaceleração no ritmo de crescimento
- **ARIMA(1,1,0)** ⭐ — modelo de série temporal com autocorrelação e intervalo de confiança de 95% (modelo preferencial)

### 👥 Pirâmide Etária
- Taxa de crescimento anual histórica (~2,5% a.a.) com **fatores de ajuste demográfico** por faixa etária, baseados na transição demográfica do IBGE:

| Faixa | Fator | Motivo |
|---|---|---|
| 0–14 anos | 75% da média | Declínio da fecundidade |
| 15–59 anos | 100% da média | Crescimento na média |
| 60+ anos | 150% da média | Envelhecimento populacional |

### 🎓 Educação
- Projeções baseadas nas **tendências nacionais IBGE 2010→2022**: +2 pp por década na alfabetização; ajustes por categoria de escolaridade

### 🏠 Domicílios
- Taxa de melhoria de **+0,67 pp/ano**, derivada da variação média dos municípios do Pará entre os Censos 2010 e 2022

---

## 📂 Arquivos de Dados

O projeto utiliza os seguintes arquivos CSV (não incluídos no repositório — obtidos via IBGE):

| Arquivo | Conteúdo |
|---|---|
| `crescimento_populacional_benevides.csv` | Série histórica da população por ano |
| `pirâmide etária.csv` | População por faixa etária e sexo (2022) |
| `alfabetização.csv` | Percentual de alfabetizados e não alfabetizados |
| `nível de instrução.csv` | Distribuição da população por nível de escolaridade |
| `características dos domicílios.csv` | Acesso a serviços básicos (água, energia, esgoto, etc.) |
| `composição domiciliar.csv` | Arranjos domiciliares (unipessoal, casal com filhos, etc.) |

---

## 🛠️ Tecnologias Utilizadas

| Biblioteca | Finalidade |
|---|---|
| `pandas` | Manipulação e análise de dados |
| `numpy` | Operações numéricas e vetoriais |
| `matplotlib` | Visualizações e gráficos |
| `seaborn` | Gráficos estatísticos avançados |
| `statsmodels` | Modelagem ARIMA |
| `scikit-learn` | Regressão linear e polinomial, métricas |

---

## 🚀 Como Executar

### ☁️ Opção 1 — Google Colab (recomendado, sem instalação)

1. Clique no badge **Open in Colab** no topo deste README
2. No painel lateral esquerdo, faça upload dos arquivos CSV via ícone de pasta
3. Execute tudo com **Runtime → Run all** (`Ctrl+F9`)

### 💻 Opção 2 — Execução Local

**1. Clone o repositório:**
```bash
git clone https://github.com/jottaene13/An-lise-do-Censo-IBGE-2022---Benevides-PA-com-Proje-es-Futuras.git
cd An-lise-do-Censo-IBGE-2022---Benevides-PA-com-Proje-es-Futuras
```

**2. Instale as dependências:**
```bash
pip install -r requirements.txt
```

**3. Adicione os arquivos CSV** na pasta raiz do projeto.

**4. Inicie o Jupyter:**
```bash
jupyter notebook
```

**5.** Abra `TCC_VERSÃO_FINAL.ipynb` e execute **Kernel → Restart & Run All**.

---

## 📋 Requisitos

- Python 3.10 ou superior
- Dependências listadas em [`requirements.txt`](requirements.txt)

---

## 📌 Metodologia e Reprodutibilidade

Todos os resultados são **100% reprodutíveis**: a semente aleatória está fixada em `RANDOM_SEED = 42`. As projeções são fundamentadas em fontes primárias do IBGE, sem uso de fatores arbitrários ou variáveis aleatórias sem justificativa estatística.

---

## 📚 Fonte dos Dados

> **IBGE — Instituto Brasileiro de Geografia e Estatística**  
> Censo Demográfico 2022 — Resultados do Universo  
> Disponível em: [https://www.ibge.gov.br/censo2022](https://www.ibge.gov.br/censo2022)

---

## 👨‍💻 Autor

**João Pinheiro dos Santos Neto**  
Trabalho de Conclusão de Curso  
📧 pinheironeto2025@gmail.com
