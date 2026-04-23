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
│   fhir-brasil          │   datasus-brasil       │  ← habilita acesso
│   (padrões clínicos)   │   (dados públicos)     │
└────────────────────────┴────────────────────────┘
              fundação open-source
```
---

### Repositórios

| Repo | O que faz |
|------|-----------|
| **[fhir-brasil](https://github.com/Precisa-Saude/fhir-brasil)** | Toolkit FHIR R4 — 183+ biomarcadores, LOINC, faixas de referência SBPC/ML, calculadoras clínicas (PhenoAge, BrDMrisc, HOMA-IR). Site: [fhir-brasil.dev.br](https://fhir-brasil.dev.br) |
| **[datasus-brasil](https://github.com/Precisa-Saude/datasus-brasil)** | Decoder DBC puro JS, cliente FTP, schemas CNES, labeling pt-BR, ponte terminológica LOINC ↔ TUSS ↔ SIGTAP |
| **[medbench-brasil](https://github.com/Precisa-Saude/medbench-brasil)** | Leaderboard de LLMs em provas médicas brasileiras — dataset Revalida/ENAMED, harness reproduzível, análise de contaminação. Site: [medbench-brasil.ia.br](https://medbench-brasil.ia.br) |

---

### Como os projetos se conectam

- **fhir-brasil** define os biomarcadores (LOINC, faixas de referência, tipos FHIR R4)
- **datasus-brasil** mapeia esses biomarcadores aos códigos de procedimento do SUS (SIGTAP/TUSS) e dá acesso aos microdados do DATASUS
- **medbench-brasil** avalia se a IA que interpreta esses dados é confiável no contexto médico brasileiro.

Juntos, formam um pipeline completo: de dados brutos de saúde pública e resultados laboratoriais até insights de saúde estruturados, em conformidade com FHIR, com referências clínicas verificáveis.

---

### Tecnologia

TypeScript/JavaScript · FHIR R4 · LOINC · SBPC/ML · Apache-2.0

Todos os pacotes no npm: [`@precisa-saude`](https://www.npmjs.com/org/precisa-saude)

---

### Contribuindo

Cada repositório tem seu próprio `CONTRIBUTING.md` e `CONVENTIONS.md`. Issues e PRs são bem-vindos.

Mantido por [Precisa Saúde](https://precisa-saude.com.br)
