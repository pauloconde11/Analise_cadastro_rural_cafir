# 📊 Análise de Concentração de Imóveis Rurais no Brasil

## 📌 Sobre o projeto

Este projeto tem como objetivo analisar a distribuição de áreas de imóveis rurais no Brasil, utilizando dados públicos, com foco em identificar padrões de concentração fundiária.

A análise busca responder perguntas como:

* A distribuição de terras é equilibrada?
* Existem imóveis extremamente grandes?
* A área total está concentrada em poucos proprietários?

---

## 🧠 Principais insights

* 🔥 **Top 1% dos imóveis concentram ~37% da área total**
* 🔥 **Top 5% concentram ~66% da área total**
* 📉 **95% dos imóveis ocupam apenas 34% da área**
* ⚖️ A distribuição é altamente desigual

> Esses resultados indicam forte concentração fundiária, com grande parte da área total controlada por um pequeno grupo de propriedades.

---

## 📊 Estatísticas gerais

| Métrica          | Valor aproximado |
| ---------------- | ---------------- |
| Total de imóveis | ~91 mil          |
| Área média       | ~2.000 ha        |
| Mediana          | ~294 ha          |
| Área máxima      | ~1.082.391 ha    |

📌 A grande diferença entre média e mediana indica presença de outliers extremos.

---

## 🧹 Etapas do projeto

### 1. Limpeza de dados

* Conversão de tipos (`id_municipio`)
* Tratamento de valores nulos
* Remoção de duplicatas (dados temporais)

### 2. Preparação

* Seleção do registro mais recente por imóvel
* Criação de dataset consolidado (`df_unique`)

### 3. Análise exploratória

* Distribuição da variável `area`
* Identificação de outliers
* Comparação entre média e mediana

### 4. Análise de concentração

* Top 10 imóveis
* Top 1%
* Top 5%

---

## 📈 Metodologia

A concentração foi medida através da proporção da área total controlada pelos maiores imóveis:

```python
top_5_percent = df_unique.sort_values(by='area', ascending=False)\
                        .head(int(len(df_unique) * 0.05))

valor_bruto_top5 = top_5_percent['area'].sum() / df_unique['area'].sum()
```

---

## 🌎 Possíveis extensões

* Análise por estado (UF)
* Análise por município
* Evolução temporal dos imóveis
* Visualizações (histograma, Lorenz curve)

---

## 🚀 Tecnologias utilizadas

* Python
* Pandas
* Jupyter Notebook

---

## 📌 Conclusão

A análise evidencia uma distribuição altamente desigual da área rural no Brasil, com forte concentração em um pequeno percentual de imóveis.

Esse tipo de estudo pode contribuir para discussões sobre:

* uso da terra
* políticas públicas
* desigualdade estrutural

---

## 👨‍💻 Autor

Paulo Conde Rocha Peña Y Calvo
💼 Desenvolvedor & Analista de Dados
📍 Brasil

---

