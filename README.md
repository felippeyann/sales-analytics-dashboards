# Sales & Marketing Analytics Dashboards

**Live demo: [felippeyann.github.io/sales-analytics-dashboards](https://felippeyann.github.io/sales-analytics-dashboards/)**

Eight interactive analytics dashboards built for the revenue operation of a B2B SaaS company (CRM platform). They ran in production on office TVs and in the browser, used daily by SDR teams, sales managers and marketing.

Everything here is a **demo build**: all data is 100% synthetic (people, emails, deals and metrics were replaced or generated) and the company is anonymized. Each dashboard ships with embedded sample data, so it renders immediately. No install, no backend, no build step.

## Dashboards

| # | Dashboard | What it shows |
|---|-----------|---------------|
| 01 | [Análise de Agendamentos](01_agendamentos.html) | Meeting-booking funnel: UTM origin Sankey, squad comparison, time-to-assignment, cross filters, AI insights |
| 02 | [Produtividade SDR](02_produtividade_sdr.html) | Daily SDR productivity: calls, connections, bookings, WhatsApp, individual ranking vs team average, configurable goals |
| 03 | [Stage Monitoring](03_stage_monitoring.html) | Social-selling pipeline stage changes: flow Sankey, average time per stage, bottleneck detection |
| 04 | [Lead Scoring](04_leadscoring.html) | Lead classification (A/B/C/D) and conversion rates by score band |
| 05 | [Primeiro Agendamento](05_primeiro_agendamento.html) | AI vs human SDR benchmark: response time to first meeting |
| 06 | [NewsRadar Editorial](06_newsradar.html) | Editorial analytics: keyword explorer (word cloud, network, heatmap), theme evolution, sources |
| 07 | [Segmentação](07_segmentacao.html) | Customer and lead segmentation analysis |
| 08 | [Gradiente de Metas](08_gradiente_metas.html) | Goal-gradient tracking against sales targets |

## Tech

- Vanilla JavaScript, one self-contained HTML file per dashboard (no framework, no bundler)
- [Apache ECharts 6](https://echarts.apache.org/) for visualizations: Sankey, heatmaps, word clouds, multi-axis series
- Client-side CSV upload (PapaParse) for loading your own data; nothing leaves the browser
- Optional AI-generated insights via Gemini (you provide your own API key in the UI)
- UI language: Portuguese (pt-BR)

## Notes

These dashboards were designed for real operational use: cross-filtering, PNG/PDF/CSV export, TV-friendly scaling and per-user goal configuration came from day-to-day demands of a sales floor, not from a tutorial.

Author: [Felippe Yann](https://github.com/felippeyann)
