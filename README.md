### Haris Zafar Bhatti

**I build the data layer and the AI on top** — ETL pipelines, warehouses, and dashboards, plus the automation and agents that run on them.

Most AI problems turn out to be data problems. Most automation projects fail because nobody modelled the data underneath. I do both halves.

Currently the sole engineer on a Doha commerce operation: ~1,400 workflow executions a week at under one failure a fortnight, order handling down from 11 minutes to 40 seconds, and a customer-facing assistant resolving 61% of conversations with no human handoff.

Current architecture — everything below is running except the Looker Studio ops dashboard.

```mermaid
flowchart LR
  A[Shopify · Ads · Sheets · APIs]
  subgraph DL[The data layer]
    B[Ingestion · n8n · Python] --> C[(BigQuery)] --> D[dbt · tests · docs · CI]
  end
  subgraph AI[The AI on top]
    E[Looker Studio · BI — not live yet]
    F[Agents · RAG · LangChain]
    G[Langfuse · evals]
  end
  A --> B
  D --> E
  D --> F
  F --> G
  G -.->|regression gates| F
```

#### Shipped

- dbt transformation layer on BigQuery with tests, docs, and CI
- Langfuse eval harness with a versioned eval set and LLM-as-judge regression gates

#### Building next

- n8n execution metrics into BigQuery, behind a public Looker Studio ops dashboard
- Contribution margin model, CM1 through CM4
- Server-side GTM and Meta CAPI with event_id deduplication and consent mode

#### Stack

**Data** — Python · SQL · BigQuery · dbt · Looker Studio · Postgres · Supabase

**AI** — LangChain · OpenAI · Gemini · Claude · Groq · RAG · Langfuse

**Platform** — n8n · REST · webhooks · OAuth2 · Docker · GitHub Actions · AWS · GCP

#### Elsewhere

[Portfolio](https://hariszafar.lovable.app) · [LinkedIn](https://linkedin.com/in/hariszb)
