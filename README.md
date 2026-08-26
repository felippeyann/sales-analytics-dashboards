<p align="center">
  <a href="https://felippeyann.github.io/sales-analytics-dashboards/"><img src="docs/banner.svg" alt="Sales & Marketing Analytics Dashboards" width="100%"></a>
</p>

# Sales & Marketing Analytics Dashboards

[![Live demo](https://img.shields.io/badge/live_demo-github_pages-4ade80?style=flat-square)](https://felippeyann.github.io/sales-analytics-dashboards/)
![Stack](https://img.shields.io/badge/stack-vanilla_JS_+_ECharts_6-fbbf24?logo=javascript&logoColor=black&style=flat-square)
![Data](https://img.shields.io/badge/data-100%25_synthetic-2563EB?style=flat-square)

**Live demo: [felippeyann.github.io/sales-analytics-dashboards](https://felippeyann.github.io/sales-analytics-dashboards/)**

Eight interactive analytics dashboards built for the revenue operation of a B2B SaaS company (CRM platform). They ran in production on office TVs and in the browser, used daily by SDR teams, sales managers and marketing.

Everything here is a **demo build**: all data is 100% synthetic (people, emails, deals and metrics were replaced or generated) and the company is anonymized. Each dashboard auto fills with sample data on load, so it renders immediately, and a toolbar at the top lets you refill it, upload your own CSV, or read the exact schema and download a template. See [Data format](#data-format). No install, no backend, no build step.

## Dashboards

Click any preview to open the live dashboard.

<table>
  <tr>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/01_agendamentos.html"><img src="docs/previews/01_agendamentos.webp" alt="Análise de Agendamentos"></a>
      <b>01 · Análise de Agendamentos</b><br>
      Meeting-booking funnel: UTM origin Sankey, squad comparison, time-to-assignment, cross filters, AI insights
    </td>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/02_produtividade_sdr.html"><img src="docs/previews/02_produtividade_sdr.webp" alt="Produtividade SDR"></a>
      <b>02 · Produtividade SDR</b><br>
      Daily SDR productivity: calls, connections, bookings, individual ranking vs team average, configurable goals
    </td>
  </tr>
  <tr>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/03_stage_monitoring.html"><img src="docs/previews/03_stage_monitoring.webp" alt="Stage Monitoring"></a>
      <b>03 · Stage Monitoring</b><br>
      Social-selling pipeline stage changes: flow Sankey, average time per stage, bottleneck detection
    </td>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/04_leadscoring.html"><img src="docs/previews/04_leadscoring.webp" alt="Lead Scoring"></a>
      <b>04 · Lead Scoring</b><br>
      Lead classification (A/B/C/D) and conversion rates by score band
    </td>
  </tr>
  <tr>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/05_primeiro_agendamento.html"><img src="docs/previews/05_primeiro_agendamento.webp" alt="Primeiro Agendamento"></a>
      <b>05 · Primeiro Agendamento</b><br>
      AI vs human SDR benchmark: response time to first meeting
    </td>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/06_newsradar.html"><img src="docs/previews/06_newsradar.webp" alt="NewsRadar Editorial"></a>
      <b>06 · NewsRadar Editorial</b><br>
      Editorial analytics: keyword explorer (word cloud, network, heatmap), theme evolution, sources
    </td>
  </tr>
  <tr>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/07_segmentacao.html"><img src="docs/previews/07_segmentacao.webp" alt="Segmentação"></a>
      <b>07 · Segmentação</b><br>
      Customer and lead segmentation analysis
    </td>
    <td width="50%">
      <a href="https://felippeyann.github.io/sales-analytics-dashboards/08_gradiente_metas.html"><img src="docs/previews/08_gradiente_metas.webp" alt="Gradiente de Metas"></a>
      <b>08 · Gradiente de Metas</b><br>
      Goal-gradient tracking against sales targets
    </td>
  </tr>
</table>

## Tech

- Vanilla JavaScript, one self-contained HTML file per dashboard (no framework, no bundler)
- [Apache ECharts 6](https://echarts.apache.org/) for visualizations: Sankey, heatmaps, word clouds, multi-axis series
- Client-side CSV upload (PapaParse) for loading your own data; nothing leaves the browser
- One-click synthetic data generator per dashboard, plus a downloadable CSV template that matches the documented schema
- Optional AI-generated insights via Gemini (you provide your own API key in the UI)
- UI language: Portuguese (pt-BR)

## Data format

Every dashboard is fed by a CSV exported from a CRM or a spreadsheet, parsed entirely in the browser (PapaParse). Nothing is uploaded anywhere.

A toolbar sits at the top of all eight dashboards:

| Button | What it does |
| --- | --- |
| **Preencher automaticamente** | Generates a synthetic dataset that matches the schema below and renders every chart, table and KPI instantly. No file needed. |
| **Enviar CSV** | Opens the real upload flow and renders your own data. |
| **Como montar o CSV** | Expands a panel with the exact schema per file, one example row per column, and a **Baixar template CSV** button that downloads a CSV with the correct headers plus sample rows. |

If a dashboard loads with no data, it auto fills with the synthetic sample and shows a discreet `dados de exemplo` badge, so the live demo is never blank. Uploading a real CSV replaces the sample and clears the badge.

All sample data is 100% synthetic: people, companies, emails, deals and metrics are generated, never real.

Columns marked with `*` are required. Everything else may be blank.

### 01 · Análise de Agendamentos, `agendamentos.csv`

Export of CRM activities, one row per meeting-booking activity. Only rows with `title = Agendamento de reunião` and `type = SCHEDULE` are considered.

| Column | Type | Meaning |
| --- | --- | --- |
| `title` * | text | Activity title. Must be `Agendamento de reunião`. |
| `type` * | text | Activity type. Must be `SCHEDULE`. |
| `ta_created_at` * | ISO datetime | When the booking activity was created. |
| `deal_created_at` * | ISO datetime | When the deal entered the CRM. Basis of time-to-assignment (TA). |
| `lead_score` | int 0-100 | Lead score. Becomes the A/B/C/D band. |
| `deal_status` | `WON` \| `LOST` \| `OPEN` | Deal outcome. |
| `origin_group_name` | text | Squad or origin group. |
| `sdr` | text | SDR who booked the meeting. |
| `closer` | text | Closer owning the deal. |
| `d_utm_source` | text | Traffic source. Feeds the origin Sankey. |
| `d_utm_campaign` | text | Campaign. |
| `contact_tags` | JSON list or comma separated | Contact tags. |
| `tags_ia` | JSON list or comma separated | Tags from automatic classification. |
| `email` | text | Contact email. The domain splits corporate vs free email. |
| `deal_id` | text | Deal identifier. |
| `contact_id` | text | Contact identifier. |

### 02 · Produtividade SDR, `atividades_sdr.csv`

Export of CRM activities, one row per logged activity. Aggregated by day and by SDR.

| Column | Type | Meaning |
| --- | --- | --- |
| `activity_date` * | date `YYYY-MM-DD` | Day of the activity. |
| `activity_type` * | `CALL` \| `EMAIL` \| `WHATSAPP` \| `TASK` \| `SCHEDULE` | Activity type. |
| `user_id` * | UUID | SDR identifier, translated to a name by the dashboard's user map. |
| `duration` | int (minutes) | Call duration. Use `0` for non-call activities. A call with duration > 0 counts as a connection. |
| `activity_id` | text | Activity identifier. |
| `deal_id` | text | Related deal. |

### 03 · Stage Monitoring, `mudancas_de_stage.csv`

Pipeline movement history, one row per deal entering a stage. The flow Sankey uses `from_stage_label -> stage_label`; the bottleneck chart uses `time_in_stage`.

| Column | Type | Meaning |
| --- | --- | --- |
| `deal_id` * | text | Deal that moved. |
| `stage_label` * | text | Stage the deal entered. |
| `stage_order` * | int | Position in the funnel (1 = top). Defines axis order. |
| `entered_day_sp` * | date `YYYY-MM-DD` | Day of entry (São Paulo timezone). |
| `from_stage_label` | text | Source stage. Blank when the deal entered the funnel directly. |
| `time_in_stage` | interval | Time spent in that stage, as `2 days 5 hours` or `18 hours`. |

### 04 · Lead Scoring, `leads_score.csv`

Export of deals with the lead score, one row per deal. Bands: A >= 80, B 60-79, C 40-59, D < 40.

| Column | Type | Meaning |
| --- | --- | --- |
| `deal_created_at` * | date `YYYY-MM-DD` | Deal creation. Drives the period filters. |
| `ia_score` * | int 0-100 | Lead score. Defines the ABCD band. |
| `deal_status` * | `WON` \| `LOST` \| `OPEN` | Deal outcome. Basis of conversion rate per band. |
| `c_tags` | comma separated | Contact tags. Feeds the tag ranking per band. |
| `origin_name` | text | Lead origin. Feeds the origin x band heatmap. |

Aliases accepted for the same fields: `created_at`, `data_criacao` for the date; `score`, `lead_score`, `pontuacao` for the score; `status`, `situacao` for the outcome; `tags`, `contact_tags` for tags; `origin`, `origem`, `utm_source` for origin.

### 05 · Primeiro Agendamento, `primeiro_agendamento.csv`

Export of deals with the first meeting date, one row per deal. Only deals created in 2024 or 2025, with a booking after creation, are considered.

| Column | Type | Meaning |
| --- | --- | --- |
| `deal_created_at` * | date `YYYY-MM-DD` | Deal creation. Also accepts `created_at`, `data_criacao`, `data_deal`. |
| `data_primeiro_agendamento` * | date `YYYY-MM-DD` | First meeting booked. Also accepts `first_schedule_date`, `data_do_agendamento`, `data_da_call`, `primeira_reuniao`. |
| `sdr` * | email | Who booked it. An email containing `+123` or `+789` is classified as an AI SDR; anything else as human. |
| `ta_created_at` | date `YYYY-MM-DD` | Creation of the booking activity. Feeds the week x weekday heatmap. Also accepts `task_created_at`, `activity_created_at`, `data_atividade`. |
| `deal_id` | text | Deal identifier. |
| `origin_name` | text | Lead origin. |
| `deal_status` | `WON` \| `LOST` \| `OPEN` | Deal outcome. |
| `contact_tags` | comma separated | Contact tags. The tag `Agendado IA` also marks a booking as AI made. |

### 06 · NewsRadar Editorial, `newsradar_artigos.csv`

Export of the editorial monitor, one row per captured article. Deduplication uses `url`, falling back to `titulo` + `data`, keeping the first occurrence.

| Column | Type | Meaning |
| --- | --- | --- |
| `titulo` * | text | Article title. Feeds the word cloud and the keyword network. |
| `data` * | date `DD/MM/YYYY` | Publication date. Articles without a date are dropped. |
| `fonte` * | text | Source outlet. |
| `score` | int 0-100 | Editorial score. |
| `url` | text | Article link. Used as the dedup key. |
| `tags` | comma separated | Article tags. |
| `categoria` | text | Editorial category. Feeds the theme evolution chart. |

### 07 · Segmentação, `base_segmentos.csv` + `dicionario_segmentos.csv`

Two files. The base carries the multiple segment sources of the same deal; the dictionary maps every raw term to an official segment. Terms missing from the dictionary land in the "new terms" queue.

`base_segmentos.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `ID do negócio` * | text | Deal identifier. Rows without it are dropped. |
| `segmento` | text or comma separated | Segment filled in by the sales team. |
| `segmento_1` | text or comma separated | Second segment source (form, enrichment). |
| `segment` | text or comma separated | Segment suggested by automatic classification. |
| `perfil_do_negocio_da` | text or comma separated | Declared business profile (size and industry). When the industry here disagrees with `segmento_1`, the row becomes a conflict. |

`dicionario_segmentos.csv`

| Column | Type | Meaning |
| --- | --- | --- |
| `raw_term` * | text | Raw term as it appears in the CRM. Matching ignores case and accents. |
| `segmento_canonico` * | text | Official segment it maps to. |

### 08 · Gradiente de Metas, `vendas.csv`

Won deals of the month, one row per sale. The dashboard buckets them into weeks (S1 days 1-7, S2 8-14, S3 15-21, S4 22-28, Sprint Final 29 to end of month), compares each week against its target and redistributes the deficit of closed weeks according to the strategy picked in the header.

| Column | Type | Meaning |
| --- | --- | --- |
| `data` * | date `YYYY-MM-DD` | Sale date. Also accepts `DD/MM/YYYY`. The reference month is the one of the most recent sale. |
| `valor` * | number | Sale amount in BRL. Accepts `45000` or `45.000,00`. |
| `closer` | text | Who closed it. Shown in each week's sales list. |
| `meta_mensal` | number | Monthly target. Filling the first row is enough. Blank assumes R$ 1.500.000. |

## Notes

These dashboards were designed for real operational use: cross-filtering, PNG/PDF/CSV export, TV-friendly scaling and per-user goal configuration came from day-to-day demands of a sales floor, not from a tutorial.

Author: [Felippe Yann](https://github.com/felippeyann)
