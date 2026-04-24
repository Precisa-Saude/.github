# Precisa Saúde

Infraestrutura código aberto para dados de saúde no Brasil — padrões clínicos, acesso a dados públicos e avaliação de IA médica.

---

### O ecossistema

```
┌─────────────────────────────────────────────────┐
│          Precisa Saúde (produto)                │  ← captura valor
├─────────────────────────────────────────────────┤
│          medbench-brasil (qualidade)            │  ← mede confiança
├────────────────────────┬────────────────────────┤
│   fhir-brasil          │   datasus-*            │  ← habilita acesso
│   (padrões clínicos)   │   (dados públicos)     │
└────────────────────────┴────────────────────────┘
              fundação open-source
```

---

### Repositórios

#### Padrões clínicos

| Repo | O que faz |
|------|-----------|
| **[fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil)** | Toolkit FHIR R4 — 183+ biomarcadores, LOINC, faixas de referência SBPC/ML, calculadoras clínicas (PhenoAge, BrDMrisc, HOMA-IR). Site: [fhir-brasil.dev.br](https://fhir-brasil.dev.br) |

#### Dados públicos (DATASUS)

| Repo | O que faz |
|------|-----------|
| **[datasus-dbc](https://github.com/Precisa-Saude/datasus-dbc)** | Decoder puro JS de arquivos `.dbc` do DATASUS (PKWARE DCL Implode + xBase DBF). Zero dependências nativas, browser e Node compatível. |
| **[datasus-sdk](https://github.com/Precisa-Saude/datasus-sdk)** | SDK alto-nível — cliente FTP com cache, schemas tipados (CNES, SIA-PA), labeling pt-BR, terminologia (IBGE, CID, CBO, SIGTAP, TUSS, LOINC), ponte LOINC ↔ TUSS ↔ SIGTAP. |
| **[datasus-viz](https://github.com/Precisa-Saude/datasus-viz)** | Visualização interativa de microdados do DATASUS — choropleth por UF/município, séries temporais, atlas de biomarcadores do SUS (2008–2024). |
| **[datasus-parquet](https://github.com/Precisa-Saude/datasus-parquet)** | Arquivo público de microdados DATASUS em formato Parquet, conversão 1:1 a partir dos DBC oficiais com provenance SHA256. |

#### Avaliação de IA médica

| Repo | O que faz |
|------|-----------|
| **[medbench-brasil](https://github.com/Precisa-Saude/medbench-brasil)** | Leaderboard de LLMs em provas médicas brasileiras — dataset Revalida/ENAMED, harness reproduzível, análise de contaminação. Site: [medbench-brasil.ia.br](https://medbench-brasil.ia.br) |

---

### Como os projetos se conectam

- **fhir-brasil** define os biomarcadores (LOINC, faixas de referência, tipos FHIR R4)

- **datasus-sdk** mapeia esses biomarcadores aos códigos de procedimento do SUS via ponte LOINC ↔ SIGTAP e dá acesso aos microdados

- **datasus-dbc** decodifica os arquivos binários que o DATASUS distribui desde os anos 90

- **datasus-viz** transforma tudo em visualizações interativas

- **datasus-parquet** preserva os dados em formato moderno para pesquisa reproduzível

- **medbench-brasil** avalia se a IA que interpreta esses dados é confiável no contexto médico brasileiro.

Juntos, formam um pipeline completo: de dados brutos de saúde pública e resultados laboratoriais até insights de saúde estruturados, em conformidade com FHIR, com referências clínicas verificáveis.

---

### Tecnologia

TypeScript/JavaScript · FHIR R4 · LOINC · SBPC/ML · Apache-2.0

Todos os pacotes no npm: [`@precisa-saude`](https://www.npmjs.com/org/precisa-saude)

---

### Comunidade

Dúvidas, ideias ou problemas? Abra uma [Discussion](https://github.com/orgs/Precisa-Saude/discussions) ou uma issue no repositório relevante.

Cada repositório tem seu próprio `CONTRIBUTING.md` e `CONVENTIONS.md`. PRs são bem-vindos — especialmente novos biomarcadores, novos datasets DATASUS e novos modelos no leaderboard.

---

Mantido por [Precisa Saúde](https://precisa-saude.com.br)
