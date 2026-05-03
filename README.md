# Fictus — Data-Driven M&A Simulation
### Due Diligence de Aquisição baseada em dados reais

> Um projeto que transforma dados em decisão de investimento.

---

## Sobre o Projeto

O Fictus simula um processo completo de **due diligence para aquisição de empresa**, utilizando o dataset público Olist (2016–2018, deslocado +7 anos para o período 2023–2025).

O projeto foi construído para responder uma única pergunta de negócio:

> **Essa empresa deve ser adquirida — ou não?**

O foco não está na análise em si, mas na decisão que ela suporta. Para isso, o projeto integra três frentes críticas da operação em um Veredito Estratégico unificado:
- Modelei vendas, logística e finanças como em uma due diligence profissional
- Identifiquei riscos invisíveis no crescimento e ineficiências operacionais estruturais
- Gerei um Veredito Estratégico estruturado com apoio de IA a partir dos dados calculados

**Decisão:** aquisição viável — condicionada a intervenção operacional e financeira.

---

## Diferencial do Projeto

Este projeto não se limita à análise descritiva.

Ele implementa um **pipeline analítico completo** — do ETL ao Veredito Estratégico — simulando um processo real de decisão de investimento, onde múltiplas dimensões da operação convergem para uma única recomendação estruturada e rastreável por evidência.

---

## O que este projeto demonstra

- Tradução de dados em decisão de negócio com evidência rastreável
- Estruturação de análises complexas e independentes que convergem para uma conclusão
- Identificação de riscos ocultos em operações aparentemente saudáveis
- Pensamento crítico sobre crescimento versus sustentabilidade
- Comunicação executiva orientada a decisão — não apenas à descrição de dados
- Pipeline de logs estruturados que alimentam uma camada de IA para geração automática de parecer executivo

---

## Natureza do Projeto

Este projeto funciona como um **framework analítico reutilizável**, não como um relatório estático.

- Os **notebooks** encapsulam a lógica de análise — replicável com qualquer dataset compatível
- Os **Summary Logs** consolidam os achados em formato padronizado para consumo por IA
- O **Veredito Estratégico** é gerado dinamicamente a partir dos dados reais calculados

Os resultados refletem o dataset Olist no período simulado e as premissas adotadas na modelagem. Conclusões podem variar conforme contexto, premissas e perfil do comprador.

---

## Executive Snapshot

### Leitura rápida

- **Vendas:** crescimento saudável, mas com churn silencioso em coortes específicas
- **Logística:** modelo próximo do limite operacional — lead time em deterioração progressiva
- **Financeiro:** PMR elevado pressionando o capital de giro

### Scores por Frente Analítica

| Frente | Score | Diagnóstico |
|---|---|---|
| Vendas | 3.0 / 3 | ✅ Motor de receita robusto |
| Logística | 2.0 / 3 | ⚠️ Modelo próximo do limite de escala |
| Financeiro | 2.2 / 3 | ⚠️ Pressão crescente sobre capital de giro |

### Visual Insights

![Dashboard](https://raw.githubusercontent.com/DataLufi/fictus/main/exports/dashboard.png)

> Painel executivo consolidando os principais sinais da operação. Inclui receita mensal, scores por frente, evolução do lead time e curva de Lorenz de concentração de receita.

### Principais Sinais Identificados

**📈 Crescimento vs. Sustentabilidade**
Receita de R$ 13,2M em expansão consistente ao longo do período, com concentração de clientes revelada pela curva de Lorenz e indícios de churn silencioso em coortes de retenção — um risco que não aparece no faturamento bruto.
![churn](https://github.com/DataLufi/fictus/blob/main/exports/11_retencao_churn.png)

**🚚 Operação Logística**
Lead time médio em deterioração progressiva (11 → 14 dias), com SLA pressionado em picos sazonais. O modelo terceirizado absorveu o crescimento histórico, mas os dados apontam esgotamento da capacidade sem reestruturação. 
![leadtime](https://github.com/DataLufi/fictus/blob/main/exports/02_lead_time_volume.png)

**💳 Estrutura Financeira**
PMR elevado por dependência de parcelamento em cartão de crédito, gerando R$ 1,14M em capital em aberto. Spread capturado por intermediários financeiros representa uma alavanca de valor — ou um passivo, dependendo do modelo adotado pelo comprador.  
![mixpagamento](https://github.com/DataLufi/fictus/blob/main/exports/01_mix_pagamento.png)

### Diagnóstico Final

A empresa apresenta **capacidade real de geração de valor**, com motor de receita validado e base de sellers diversificada. O desafio está em sustentar esse crescimento com eficiência operacional e disciplina financeira.

**O Veredito Estratégico Fictus:** aquisição viável — com condições.

---

## As Três Frentes Analíticas

### Frente 1 — Análise de Vendas
> *A empresa está crescendo — mas esse crescimento é sustentável ou está mascarando uma deterioração silenciosa?*

11 análises distribuídas em 5 blocos: viabilidade econômica, motor de receita, escalabilidade operacional, riscos ocultos e cenários de sobrevivência. Inclui curva de Lorenz, coeficiente de Gini, coorte de retenção e decomposição de cancelamentos.

**Impacto:** determina se o crescimento observado gera valor ou apenas aumenta a exposição ao risco.

---

### Frente 2 — Análise Logística
> *O modelo operacional atual aguenta escalar — ou já chegou no limite e está destruindo valor sem que ninguém perceba?*

Diagnóstico completo do modelo terceirizado, análise make-or-buy (terceirizado vs. próprio vs. híbrido), impacto do SLA na satisfação do cliente, escalabilidade sob picos sazonais e custo de reversão documentado com benchmarks de mercado (ILOS, ABCOMM, McKinsey).

**Impacto:** revela o ponto exato em que o modelo logístico atual começa a destruir margem — e qual alternativa sustenta o crescimento.

---

### Frente 3 — Análise Financeira
> *Quem está financiando o crescimento desta empresa — ela mesma ou os intermediários financeiros?*

Perfil de pagamentos e capital em aberto, risco de crédito latente via proxies analíticos, spread líquido após custo do risco, escalabilidade da estrutura de recebimento e cenários de reestruturação.

**Impacto:** identifica dependências estruturais e riscos financeiros que o comprador herdaria na aquisição.

---

## Estrutura do Repositório

```
fictus/
├── inicializar_projeto.ipynb    ← rode primeiro: cria toda a estrutura
├── README.md
├── requirements.txt
├── .gitignore
│
├── data/
│   ├── externos/                ← arquivos do IBGE (geolocalização)
│   ├── originais/               ← CSVs do Olist (não versionados)
│   ├── pre-tratados/            ← gerado pelo ETL de Vendas
│   ├── logistics/               ← gerado pelo ETL de Logística
│   └── finance/                 ← gerado pelo ETL de Finanças
│
├── notebooks/
│   ├── vendas/                  ← 00_ETL + 01 a 05
│   ├── logistica/               ← 00_ETL + 01 a 05
│   └── financas/                ← 00_ETL + 01 a 05
│
├── exports/                     ← gráficos gerados (.png)
├── summary_logs/                ← outputs automáticos para o Veredito Estratégico
└── fictus_veredito_estrategico.md
```

---

## Como Rodar o Projeto

### Pré-requisitos

```bash
pip install -r requirements.txt
```

### 1. Inicializar o projeto

Execute `inicializar_projeto.ipynb` uma única vez. Ele cria toda a estrutura de pastas, o `.gitignore` configurado e os arquivos base — nenhuma configuração manual necessária.

### 2. Baixar o dataset

Baixe o [Olist E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce) no Kaggle e salve os CSVs em `data/originais/`. Consulte `data/README_dados.md` para a lista completa de arquivos necessários.

### 3. Ordem de execução

```
notebooks/vendas/00_ETL_analise_vendas.ipynb       ← ponto de entrada
notebooks/vendas/01 ao 05                           ← análise de vendas
notebooks/logistica/00_ETL_analise_logistica.ipynb
notebooks/logistica/01 ao 05                        ← análise logística
notebooks/financas/00_ETL_analise_financeira.ipynb
notebooks/financas/01 ao 05                         ← análise financeira
```

> ⏱️ Tempo estimado de execução completa: 20–40 minutos

Ao final de cada frente, a última célula gera automaticamente um arquivo `.txt` em `summary_logs/` — sem nenhuma ação manual necessária.

---

## Como Usar o Veredito Estratégico Fictus

1. Execute todos os notebooks até o final
2. Abra `fictus_veredito_estrategico.md` e cole na IA de sua preferência
3. Escolha o perfil de tese: **Conservadora**, **Moderada** ou **Arrojada**
4. Abra a pasta `summary_logs/` — os 3 arquivos `.txt` já estarão lá
5. Anexe os 3 arquivos `.txt` diretamente na conversa com a IA **ou** copie e cole o conteúdo nos campos indicados
6. Receba o parecer executivo completo

O Veredito Estratégico Fictus cobre 11 seções obrigatórias: resumo executivo, saúde geral, resultados por frente, mapa de riscos, projeção de 3/5/10 anos, valuation operacional, plano de 100 dias e recomendação final com nível de confiança.

---

## Stack Tecnológica

| Camada | Tecnologia |
|---|---|
| Linguagem | Python 3.10+ |
| Manipulação de dados | pandas, numpy |
| Visualização | matplotlib, seaborn |
| Estatística | scipy |
| Estrutura analítica | ETL + EDA + geração de logs estruturados + pipeline orientado a decisão |
| Ambiente | Jupyter Lab |
| Veredito Estratégico | Claude / ChatGPT / Gemini via prompt |
| Dataset | Olist E-Commerce Public Dataset (Kaggle) |

---

## Evolução Planejada

- Modelagem dimensional formal (Star Schema) com chaves substitutas
- Migração das agregações principais para SQL
- Dashboard executivo interativo (Streamlit ou Power BI)
- Automação do pipeline de ETL → análise → log → Veredito Estratégico

---

## Sobre o Autor

Engenheiro de Produção em transição para a área de dados, com foco em análise orientada a decisão de negócio. Construído para demonstrar que análise de dados não é só código: é raciocínio estruturado com evidência.

www.linkedin.com/in/filholuiz

---

## Licença

MIT License — livre para uso, estudo e adaptação com atribuição.
