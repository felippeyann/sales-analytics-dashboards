<p align="center">
  <a href="https://felippeyann.github.io/sales-analytics-dashboards/"><img src="docs/banner.svg" alt="Sales & Marketing Analytics Dashboards" width="100%"></a>
</p>

# Sales & Marketing Analytics Dashboards

[![Live demo](https://img.shields.io/badge/live_demo-github_pages-4ade80?style=flat-square)](https://felippeyann.github.io/sales-analytics-dashboards/)
![Stack](https://img.shields.io/badge/stack-vanilla_JS_+_ECharts_6-fbbf24?logo=javascript&logoColor=black&style=flat-square)
![Data](https://img.shields.io/badge/data-100%25_synthetic-2563EB?style=flat-square)

**Live demo: [felippeyann.github.io/sales-analytics-dashboards](https://felippeyann.github.io/sales-analytics-dashboards/)**

Eight interactive analytics dashboards built for the revenue operation of a B2B SaaS company (CRM platform). They ran in production on office TVs and in the browser, used daily by SDR teams, sales managers and marketing.

Everything here is a **demo build**: all data is 100% synthetic (people, emails, deals and metrics were replaced or generated) and the company is anonymized. Each dashboard ships with embedded sample data, so it renders immediately. No install, no backend, no build step.

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
- Optional AI-generated insights via Gemini (you provide your own API key in the UI)
- UI language: Portuguese (pt-BR)

## Notes

These dashboards were designed for real operational use: cross-filtering, PNG/PDF/CSV export, TV-friendly scaling and per-user goal configuration came from day-to-day demands of a sales floor, not from a tutorial.

Author: [Felippe Yann](https://github.com/felippeyann)
