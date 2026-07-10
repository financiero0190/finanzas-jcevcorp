<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>JCEVCORP · Control Financiero 2026</title>
<script src="https://cdn.jsdelivr.net/npm/chart.js@4.4.0/dist/chart.umd.min.js"></script>
<style>
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --bg:#0a0f1e;--bg2:#0f1629;--bg3:#141b2d;--bg4:#1a2235;
  --border:#1e2d4a;--border2:#243352;
  --text:#e2e8f0;--text2:#94a3b8;--text3:#64748b;
  --accent:#3b82f6;--green:#22c55e;--red:#ef4444;--warn:#f59e0b;
  --sidebar:220px;--topbar:52px;
}
body{background:var(--bg);color:var(--text);font-family:'Inter',system-ui,sans-serif;font-size:13px;display:flex;flex-direction:column;height:100vh;overflow:hidden}
/* TOPBAR */
#topbar{height:var(--topbar);background:var(--bg2);border-bottom:1px solid var(--border);display:flex;align-items:center;padding:0 16px;gap:12px;flex-shrink:0;z-index:100}
.tb-brand{font-weight:800;font-size:15px;color:var(--accent);letter-spacing:1px}
.tb-sub{font-size:10px;color:var(--text3);letter-spacing:2px}
#section-title{margin-left:auto;font-size:12px;color:var(--text2);font-weight:600}
.tb-right{display:flex;align-items:center;gap:8px;margin-left:16px}
.badge-warn{background:rgba(245,158,11,.15);color:var(--warn);border:1px solid rgba(245,158,11,.3);border-radius:6px;padding:3px 8px;font-size:11px;font-weight:600}
.badge-danger{background:rgba(239,68,68,.15);color:var(--red);border:1px solid rgba(239,68,68,.3);border-radius:6px;padding:3px 8px;font-size:11px;font-weight:600}
.badge-ok{background:rgba(34,197,94,.15);color:var(--green);border:1px solid rgba(34,197,94,.3);border-radius:6px;padding:3px 8px;font-size:11px;font-weight:600}
.btn-upload{background:var(--accent);color:#fff;border:none;border-radius:6px;padding:5px 12px;font-size:11px;font-weight:600;cursor:pointer;display:flex;align-items:center;gap:6px}
.btn-upload input{display:none}
/* LAYOUT */
#layout{display:flex;flex:1;overflow:hidden}
/* SIDEBAR */
#sidebar{width:var(--sidebar);background:var(--bg2);border-right:1px solid var(--border);display:flex;flex-direction:column;overflow-y:auto;flex-shrink:0}
.logo{padding:16px;border-bottom:1px solid var(--border)}
.logo-brand{font-weight:800;font-size:16px;color:var(--accent)}
.logo-sub{font-size:10px;color:var(--text3);letter-spacing:1.5px;margin-top:2px}
.nav-group{padding:10px 0}
.nav-group-label{padding:4px 14px;font-size:9px;font-weight:700;color:var(--text3);letter-spacing:2px;text-transform:uppercase}
.nav-item{padding:8px 14px;font-size:12px;color:var(--text2);cursor:pointer;border-left:3px solid transparent;transition:all .15s;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.nav-item:hover{background:var(--bg3);color:var(--text)}
.nav-item.active{background:rgba(59,130,246,.1);border-left-color:var(--accent);color:#fff}
/* MAIN */
#main{flex:1;overflow-y:auto;padding:20px}
.section{display:none}
.section.active{display:block}
/* SEC HEADER */
.sec-header{margin-bottom:16px}
.sec-header h2{font-size:17px;font-weight:700;color:var(--text)}
.sec-header .sh-sub{font-size:11px;color:var(--text3);margin-top:2px;display:block}
/* CARDS */
.cards{display:grid;grid-template-columns:repeat(auto-fit,minmax(160px,1fr));gap:12px;margin-bottom:20px}
.card{background:var(--bg2);border:1px solid var(--border);border-radius:10px;padding:14px}
.card.accent{border-color:rgba(59,130,246,.3);background:rgba(59,130,246,.07)}
.card.danger{border-color:rgba(239,68,68,.3);background:rgba(239,68,68,.07)}
.card.warn{border-color:rgba(245,158,11,.3);background:rgba(245,158,11,.07)}
.card.green{border-color:rgba(34,197,94,.3);background:rgba(34,197,94,.07)}
.c-label{font-size:10px;color:var(--text3);text-transform:uppercase;letter-spacing:1px;margin-bottom:6px}
.c-val{font-size:20px;font-weight:800;color:var(--text)}
.c-sub{font-size:10px;color:var(--text2);margin-top:4px}
/* TABLE */
.tbl-wrap{background:var(--bg2);border:1px solid var(--border);border-radius:10px;overflow:hidden;margin-bottom:20px}
.tbl-title{padding:10px 14px;background:var(--bg3);font-weight:700;font-size:12px;color:var(--text2);border-bottom:1px solid var(--border)}
table{width:100%;border-collapse:collapse}
th{padding:9px 10px;text-align:left;font-size:10px;font-weight:700;color:var(--text3);text-transform:uppercase;letter-spacing:.5px;background:var(--bg3);border-bottom:1px solid var(--border);white-space:nowrap}
td{padding:8px 10px;border-bottom:1px solid var(--border);color:var(--text2);font-size:12px;vertical-align:middle}
tr:last-child td{border-bottom:none}
tr:hover td{background:rgba(255,255,255,.02)}
td.num,th.num{text-align:right}
.tot td{font-weight:700;color:var(--text);background:rgba(59,130,246,.05)}
/* CHARTS */
.charts-row{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:16px;margin-bottom:20px}
.chart-box{background:var(--bg2);border:1px solid var(--border);border-radius:10px;padding:16px}
.chart-box h4{font-size:12px;color:var(--text2);margin-bottom:12px;font-weight:600}
/* BADGES */
.st-badge{display:inline-block;padding:2px 8px;border-radius:10px;font-size:10px;font-weight:700}
.st-pend{background:rgba(245,158,11,.15);color:var(--warn)}
.st-canc{background:rgba(100,116,139,.15);color:var(--text3)}
.st-venc{background:rgba(239,68,68,.15);color:var(--red)}
.st-nopag{background:rgba(239,68,68,.15);color:var(--red)}
.ta-badge{background:rgba(168,85,247,.15);color:#a855f7;border:1px solid rgba(168,85,247,.3);border-radius:4px;padding:1px 6px;font-size:10px;font-weight:700}
/* EMP BADGES */
.eb{display:inline-block;padding:2px 7px;border-radius:10px;font-size:10px;font-weight:700;white-space:nowrap}
.eb-jcev{background:rgba(59,130,246,.2);color:#60a5fa}
.eb-asm{background:rgba(34,197,94,.2);color:#4ade80}
.eb-full{background:rgba(168,85,247,.2);color:#c084fc}
.eb-cred{background:rgba(249,115,22,.2);color:#fb923c}
.eb-cons{background:rgba(6,182,212,.2);color:#22d3ee}
.eb-todo{background:rgba(234,179,8,.2);color:#facc15}
.eb-mont{background:rgba(239,68,68,.2);color:#f87171}
/* AMORT */
.amort-block{background:var(--bg2);border:1px solid var(--border);border-radius:10px;overflow:hidden;margin-bottom:16px}
.amort-header{padding:10px 14px;background:var(--bg3);border-bottom:1px solid var(--border);display:flex;justify-content:space-between;align-items:center}
.amort-header h3{font-size:13px;font-weight:700;color:var(--text)}
.amort-header .ah-right{font-size:11px;color:var(--text3)}
/* CALENDAR */
#cal-pills{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:12px}
.pill{background:var(--bg3);border:1px solid var(--border2);border-radius:20px;padding:4px 12px;font-size:11px;color:var(--text2);cursor:pointer;transition:all .15s;user-select:none}
.pill.active{background:var(--accent);color:#fff;border-color:var(--accent)}
.cal-filters{display:flex;gap:10px;margin-bottom:16px;flex-wrap:wrap;align-items:center}
.cal-filters select{background:var(--bg3);border:1px solid var(--border2);border-radius:6px;color:var(--text);padding:6px 10px;font-size:12px;cursor:pointer}
.cal-filters label{font-size:11px;color:var(--text3);display:flex;align-items:center;gap:5px;cursor:pointer}
#cal-body{display:flex;flex-direction:column;gap:14px}
.cal-month{background:var(--bg2);border:1px solid var(--border);border-radius:10px;overflow:hidden}
.cal-month-hdr{padding:10px 16px;background:var(--bg3);border-bottom:1px solid var(--border);display:flex;justify-content:space-between;align-items:center}
.cmh-title{font-weight:700;font-size:13px;color:var(--text)}
.cmh-stats{font-size:11px;color:var(--text3)}
.cal-list{display:flex;flex-direction:column}
.cal-card{display:flex;align-items:center;gap:12px;padding:10px 14px;border-top:1px solid var(--border)}
.cal-card:first-child{border-top:none}
.cal-day-box{display:flex;flex-direction:column;align-items:center;justify-content:center;min-width:46px;background:var(--bg3);border-radius:8px;padding:6px 8px;flex-shrink:0}
.cal-dn{font-size:20px;font-weight:800;line-height:1;color:var(--text)}
.cal-dow{font-size:9px;font-weight:700;color:var(--text3);text-transform:uppercase;margin-top:2px}
.cal-body{flex:1;min-width:0}
.cal-badges{display:flex;gap:5px;flex-wrap:wrap;margin-bottom:4px;align-items:center}
.typ-badge{display:inline-block;padding:2px 7px;border-radius:8px;font-size:10px;font-weight:600;border:1px solid transparent}
.cal-desc{font-size:11px;color:var(--text2);white-space:nowrap;overflow:hidden;text-overflow:ellipsis;max-width:500px}
.cal-amount{font-size:13px;font-weight:700;color:var(--green);white-space:nowrap;margin-left:auto;flex-shrink:0}
/* EMPTY */
.empty-state{text-align:center;padding:50px 20px;color:var(--text3)}
.empty-state .ei{font-size:44px;margin-bottom:10px}
/* TOAST */
#toast{position:fixed;bottom:20px;right:20px;background:var(--bg3);border:1px solid var(--border2);border-radius:8px;padding:10px 16px;font-size:12px;font-weight:600;z-index:999;opacity:0;transform:translateY(10px);transition:all .3s;pointer-events:none}
#toast.show{opacity:1;transform:translateY(0)}
/* SCROLLBAR */
::-webkit-scrollbar{width:5px;height:5px}
::-webkit-scrollbar-track{background:var(--bg)}
::-webkit-scrollbar-thumb{background:var(--border2);border-radius:3px}
/* RESPONSIVE */
@media(max-width:900px){#sidebar{width:180px}.cards{grid-template-columns:repeat(2,1fr)}}
</style>
</head>
<body>
<div id="topbar">
  <div>
    <div class="tb-brand">JCEVCORP</div>
    <div class="tb-sub">CONTROL FINANCIERO 2026</div>
  </div>
  <span id="section-title" style="margin-left:16px;font-size:12px;color:var(--text2);font-weight:600">Resumen General</span>
  <div class="tb-right" style="margin-left:auto">
    <label class="btn-upload">📤 Cargar Excel<input type="file" id="excel-file" accept=".xlsx,.xls" onchange="handleExcel(this)"></label>
  </div>
</div>

<div id="layout">
<nav id="sidebar">
  <div class="logo"><div class="logo-brand">JCEVCORP</div><div class="logo-sub">FINANZAS 2026</div></div>
  <div class="nav-group">
    <div class="nav-group-label">Principal</div>
    <div class="nav-item active" onclick="nav('s-res')">📊 Resumen</div>
  </div>
  <div class="nav-group">
    <div class="nav-group-label">Obligaciones</div>
    <div class="nav-item" onclick="nav('s-obl')">🏦 Obligaciones</div>
    <div class="nav-item" onclick="nav('s-amort')">📉 Amort. TA</div>
  </div>
  <div class="nav-group">
    <div class="nav-group-label">Importaciones</div>
    <div class="nav-item" onclick="nav('s-jcev')">📦 JCEV &amp; CONSUREP</div>
    <div class="nav-item" onclick="nav('s-cred')">🚚 CREDIMPORT</div>
    <div class="nav-item" onclick="nav('s-asm')">🏍️ ASSEMBLY</div>
  </div>
  <div class="nav-group">
    <div class="nav-group-label">Gastos</div>
    <div class="nav-item" onclick="nav('s-sri')">🧾 SRI &amp; Nómina</div>
    <div class="nav-item" onclick="nav('s-prov')">🤝 Proveedores</div>
    <div class="nav-item" onclick="nav('s-imp')">🔒 SENAE</div>
  </div>
  <div class="nav-group">
    <div class="nav-group-label">Control</div>
    <div class="nav-item" onclick="nav('s-cal')">📅 Calendario</div>
  </div>
</nav>

<div id="main">

<!-- RESUMEN -->
<div id="s-res" class="section active">
  <div class="sec-header"><h2>📊 Resumen General</h2><span class="sh-sub">Panorama financiero consolidado · JCEVCORP 2026</span></div>
  <div class="cards">
    <div class="card danger"><div class="c-label">Total Obligaciones</div><div class="c-val">$14,426,549</div><div class="c-sub">24 créditos activos · Capital $13,853,736</div></div>
    <div class="card accent"><div class="c-label">Flujo JCEV &amp; CONSUREP</div><div class="c-val">$4,202,846</div><div class="c-sub">41 importaciones</div></div>
    <div class="card"><div class="c-label">Flujo CREDIMPORT</div><div class="c-val">$350,000</div><div class="c-sub">Anticipo pendiente</div></div>
    <div class="card accent"><div class="c-label">Flujo ASSEMBLY</div><div class="c-val">$2,419,153</div><div class="c-sub">21 importaciones</div></div>
    <div class="card warn"><div class="c-label">SRI Junio 2026</div><div class="c-val">$935,755</div><div class="c-sub">Débito: $377,755 · NC: $558,000</div></div>
    <div class="card"><div class="c-label">Nómina Junio 2026</div><div class="c-val">$277,298</div><div class="c-sub">6 empresas · 2 quincenas</div></div>
    <div class="card"><div class="c-label">Proveedores Nacionales</div><div class="c-val">$800,000</div><div class="c-sub">5 empresas</div></div>
    <div class="card danger"><div class="c-label">Imp. Garantizados SENAE</div><div class="c-val">$901,488</div><div class="c-sub">SENAE · 18 liq · Vence 04/08/2026</div></div>
  </div>
  <div class="charts-row">
    <div class="chart-box"><h4>Obligaciones por Empresa</h4><canvas id="c-obl-emp" height="200"></canvas></div>
    <div class="chart-box"><h4>Importaciones por Empresa</h4><canvas id="c-imp-emp" height="200"></canvas></div>
  </div>
  <div class="charts-row">
    <div class="chart-box"><h4>SRI – Nota Crédito vs Débito</h4><canvas id="c-sri" height="180"></canvas></div>
    <div class="chart-box"><h4>Nómina por Empresa</h4><canvas id="c-nom" height="180"></canvas></div>
  </div>
  <div class="tbl-wrap">
    <div class="tbl-title">⏰ Obligaciones con Vencimiento Próximo (PENDIENTE)</div>
    <table id="tbl-venc"><thead><tr><th>Empresa</th><th>Institución</th><th>Vencimiento</th><th>Tipo</th><th class="num">Capital</th><th class="num">Total</th><th>Estado</th></tr></thead>
    <tbody id="tbody-venc"></tbody></table>
  </div>
</div>

<!-- OBLIGACIONES -->
<div id="s-obl" class="section">
  <div class="sec-header"><h2>🏦 Obligaciones Financieras</h2><span class="sh-sub">24 créditos activos · Solo PENDIENTE</span></div>
  <div class="cards">
    <div class="card danger"><div class="c-label">Total Obligaciones</div><div class="c-val">$14,426,549</div></div>
    <div class="card"><div class="c-label">Capital Total</div><div class="c-val">$13,853,736</div></div>
    <div class="card accent"><div class="c-label">JCEVCORP</div><div class="c-val" id="obl-jcev-total">—</div></div>
    <div class="card"><div class="c-label">ASSEMBLY</div><div class="c-val" id="obl-asm-total">—</div></div>
    <div class="card"><div class="c-label">FULLMOTOS</div><div class="c-val" id="obl-full-total">—</div></div>
  </div>
  <div class="tbl-wrap">
    <table id="tbl-obl">
      <thead><tr><th>Empresa</th><th>Institución</th><th>Vencimiento</th><th>Cuotas</th><th class="num">Capital</th><th class="num">Interés</th><th class="num">Total</th><th>Tasa</th></tr></thead>
      <tbody id="tbody-obl"></tbody>
    </table>
  </div>
</div>

<!-- AMORT TA -->
<div id="s-amort" class="section">
  <div class="sec-header"><h2>📉 Tablas de Amortización TA</h2><span class="sh-sub">8 créditos con tabla de amortización · Solo cuotas PENDIENTE</span></div>
  <div class="cards">
    <div class="card accent"><div class="c-label">Cuotas Mensuales TA</div><div class="c-val" id="amort-sum-total">—</div><div class="c-sub">Suma de todos los créditos TA</div></div>
    <div class="card"><div class="c-label">JCEVCORP (4 créditos)</div><div class="c-val" id="amort-jcev">—</div></div>
    <div class="card"><div class="c-label">ASSEMBLY (2 créditos)</div><div class="c-val" id="amort-asm">—</div></div>
    <div class="card"><div class="c-label">FULLMOTOS (1 crédito)</div><div class="c-val" id="amort-full">—</div></div>
  </div>
  <div id="amort-tables"></div>
</div>

<!-- JCEV CONSUREP -->
<div id="s-jcev" class="section">
  <div class="sec-header"><h2>📦 Flujo JCEV &amp; CONSUREP</h2><span class="sh-sub">41 importaciones · Junio 2026</span></div>
  <div class="cards">
    <div class="card accent"><div class="c-label">Total Flujo</div><div class="c-val">$4,202,846</div></div>
    <div class="card"><div class="c-label">JCEVCORP</div><div class="c-val">$2,078,463</div><div class="c-sub">36 importaciones</div></div>
    <div class="card"><div class="c-label">CONSUREP</div><div class="c-val">$2,047,398</div><div class="c-sub">4 importaciones</div></div>
    <div class="card"><div class="c-label">TODOMOTO</div><div class="c-val">$76,986</div><div class="c-sub">1 importación</div></div>
  </div>
  <div class="tbl-wrap">
    <table>
      <thead><tr><th>Empresa</th><th>Proveedor</th><th>Importación</th><th>Mercadería</th><th class="num">Valor Total</th><th class="num">Anticipo</th><th class="num">A Pagar</th><th>Vencimiento</th><th>Ejecutivo</th></tr></thead>
      <tbody id="tbody-jcev"></tbody>
    </table>
  </div>
</div>

<!-- CREDIMPORT -->
<div id="s-cred" class="section">
  <div class="sec-header"><h2>🚚 Flujo CREDIMPORT</h2><span class="sh-sub">Importaciones CREDIMPORT · Junio 2026</span></div>
  <div class="cards">
    <div class="card accent"><div class="c-label">Total Flujo</div><div class="c-val">$350,000</div></div>
    <div class="card"><div class="c-label">Importaciones</div><div class="c-val">1</div><div class="c-sub">período Junio 2026</div></div>
  </div>
  <div class="tbl-wrap">
    <table>
      <thead><tr><th>Empresa</th><th>Proveedor</th><th>Importación</th><th>Mercadería</th><th class="num">Valor Total</th><th class="num">Anticipo</th><th class="num">A Pagar</th><th>Vencimiento</th><th>Ejecutivo</th></tr></thead>
      <tbody id="tbody-cred"></tbody>
    </table>
  </div>
</div>

<!-- ASSEMBLY -->
<div id="s-asm" class="section">
  <div class="sec-header"><h2>🏍️ Flujo ASSEMBLY</h2><span class="sh-sub">21 importaciones · Motos &amp; Vehículos · Junio 2026</span></div>
  <div class="cards">
    <div class="card accent"><div class="c-label">Total Flujo</div><div class="c-val">$2,419,153</div></div>
    <div class="card"><div class="c-label">Importaciones</div><div class="c-val">21</div><div class="c-sub">período Junio 2026</div></div>
    <div class="card"><div class="c-label">Valor Total (con anticipo)</div><div class="c-val">$2,689,232</div></div>
    <div class="card"><div class="c-label">Anticipos Pagados</div><div class="c-val">$720,079</div></div>
  </div>
  <div class="tbl-wrap">
    <table>
      <thead><tr><th>#</th><th>Proveedor</th><th>Importación</th><th>Modelo</th><th class="num">Valor Total</th><th class="num">Anticipo</th><th class="num">A Pagar</th><th>Vencimiento</th></tr></thead>
      <tbody id="tbody-asm"></tbody>
    </table>
  </div>
</div>

<!-- SRI NOMINA -->
<div id="s-sri" class="section">
  <div class="sec-header"><h2>🧾 SRI &amp; Nómina</h2><span class="sh-sub">Obligaciones tributarias y nómina · Junio 2026</span></div>
  <div class="cards">
    <div class="card warn"><div class="c-label">Total SRI</div><div class="c-val">$935,755</div><div class="c-sub">Nota Crédito: $558,000</div></div>
    <div class="card danger"><div class="c-label">Total a Debitar</div><div class="c-val">$377,755</div><div class="c-sub">Efectivo requerido</div></div>
    <div class="card"><div class="c-label">Total Nómina</div><div class="c-val">$277,298</div><div class="c-sub">6 empresas · 2 quincenas</div></div>
  </div>
  <div class="tbl-wrap">
    <div class="tbl-title">SRI – Declaraciones Junio 2026</div>
    <table>
      <thead><tr><th>Empresa</th><th>SRI Total</th><th>Nota Crédito</th><th class="num">Débito Bancario</th><th>Banco</th><th>Fecha Pago</th></tr></thead>
      <tbody id="tbody-sri"></tbody>
    </table>
  </div>
  <div class="tbl-wrap" style="border-color:rgba(245,158,11,.3)">
    <div class="tbl-title" style="color:var(--warn)">⚠ SRI – Julio 2026 (pendiente de datos)</div>
    <div style="padding:16px;color:var(--text3);font-size:12px">
      Las declaraciones SRI de julio 2026 no están en el Excel actual. 
      Una vez que cargues el archivo actualizado, esta sección se completará con los montos de débito y nota crédito por empresa.
    </div>
  </div>
  <div class="tbl-wrap">
    <div class="tbl-title">Nómina – Junio 2026 (1ª y 2ª Quincena)</div>
    <table>
      <thead><tr><th>Empresa</th><th>Quincena</th><th class="num">Monto</th><th>Fecha Pago</th></tr></thead>
      <tbody id="tbody-nom"></tbody>
    </table>
  </div>
</div>

<!-- PROVEEDORES -->
<div id="s-prov" class="section">
  <div class="sec-header"><h2>🤝 Proveedores Nacionales</h2><span class="sh-sub">Pagos a proveedores · Junio 2026</span></div>
  <div class="cards">
    <div class="card accent"><div class="c-label">Total Proveedores</div><div class="c-val">$800,000</div></div>
    <div class="card"><div class="c-label">Empresas</div><div class="c-val">5</div><div class="c-sub">Fecha: 15/06/2026</div></div>
  </div>
  <div class="tbl-wrap">
    <table>
      <thead><tr><th>Empresa</th><th class="num">Monto</th><th>Fecha Pago</th></tr></thead>
      <tbody id="tbody-prov"></tbody>
    </table>
  </div>
</div>

<!-- IMPUESTOS -->
<div id="s-imp" class="section">
  <div class="sec-header"><h2>🔒 Impuestos Garantizados SENAE</h2><span class="sh-sub">CORPORACION JCEVCORP CIA. LTDA. · 18 liquidaciones · Vencimiento 04/08/2026</span></div>
  <div class="cards">
    <div class="card danger"><div class="c-label">Total a Pagar</div><div class="c-val">$901,488.15</div><div class="c-sub">18 liquidaciones SENAE · NO PAGADO</div></div>
    <div class="card warn"><div class="c-label">Fecha Liquidación</div><div class="c-val" style="font-size:16px">31/07/2026</div><div class="c-sub">Vencimiento: 04/08/2026</div></div>
    <div class="card"><div class="c-label">Contribuyente</div><div class="c-val" style="font-size:12px">CORPORACION JCEVCORP</div><div class="c-sub">CIA. LTDA.</div></div>
  </div>
  <div class="tbl-wrap">
    <table>
      <thead><tr><th>#</th><th>N° Liquidación</th><th>Estado</th><th>Fecha Liq.</th><th>Contribuyente</th><th class="num">Valor Liquidado</th><th>Vencimiento</th></tr></thead>
      <tbody id="tbody-imp"></tbody>
    </table>
  </div>
</div>

<!-- CALENDARIO -->
<div id="s-cal" class="section">
  <div class="sec-header"><h2>📅 Calendario Consolidado</h2><span class="sh-sub">Todos los pagos y vencimientos</span></div>
  <div id="cal-pills">
    <span class="pill active" data-val="" onclick="togglePill(this)">Todos</span>
    <span class="pill" data-val="Obligación" onclick="togglePill(this)">🏦 Obligación</span>
    <span class="pill" data-val="Amort. TA" onclick="togglePill(this)">📉 Amort. TA</span>
    <span class="pill" data-val="Imp. JCEV" onclick="togglePill(this)">📦 Imp. JCEV</span>
    <span class="pill" data-val="Imp. CONSUREP" onclick="togglePill(this)">📦 Imp. CONSUREP</span>
    <span class="pill" data-val="Imp. TODOMOTO" onclick="togglePill(this)">📦 Imp. TODOMOTO</span>
    <span class="pill" data-val="Imp. CREDIMPORT" onclick="togglePill(this)">🚚 Imp. CREDIMPORT</span>
    <span class="pill" data-val="Imp. ASSEMBLY" onclick="togglePill(this)">🏍️ Imp. ASSEMBLY</span>
    <span class="pill" data-val="SRI" onclick="togglePill(this)">🧾 SRI</span>
    <span class="pill" data-val="Nómina" onclick="togglePill(this)">👥 Nómina</span>
    <span class="pill" data-val="Proveedores" onclick="togglePill(this)">🤝 Proveedores</span>
    <span class="pill" data-val="Imp. Garantizado" onclick="togglePill(this)">🔒 SENAE</span>
  </div>
  <div class="cal-filters">
    <select id="f-emp" onchange="renderCal()">
      <option value="">Todas las empresas</option>
      <option>JCEVCORP</option><option>ASSEMBLY</option><option>FULLMOTOS</option>
      <option>CREDIMPORT</option><option>CONSUREP</option><option>TODOMOTO</option><option>MONTAZ</option>
    </select>
    <select id="f-mes" onchange="renderCal()">
      <option value="">Todos los meses</option>
      <option value="2026-06">Junio 2026</option><option value="2026-07">Julio 2026</option>
      <option value="2026-08">Agosto 2026</option><option value="2026-09">Septiembre 2026</option>
      <option value="2026-10">Octubre 2026</option><option value="2026-11">Noviembre 2026</option>
      <option value="2026-12">Diciembre 2026</option><option value="2027-01">Enero 2027</option>
      <option value="2027-02">Febrero 2027</option><option value="2027-03">Marzo 2027</option>
      <option value="2027-04">Abril 2027</option><option value="2027-05">Mayo 2027</option>
      <option value="2027-06">Junio 2027</option>
    </select>
  </div>
  <div id="cal-body"></div>
</div>

</div><!-- /main -->
</div><!-- /layout -->

<div id="toast"></div>

<script>
// ============================================================
// DATA
// ============================================================
const oblData=[{"empresa": "JCEVCORP", "inst": "PRODUBANCO", "vcto": "2026-04-22", "capital": 1000000, "cuotas": "TA", "int": 34044.31, "total": 1034044.31, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "PICHINCHA PANAMA", "vcto": "2026-06-11", "capital": 490000, "cuotas": 490000, "int": 15680, "total": 505680, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PICHINCHA PANAMA", "vcto": "2026-06-22", "capital": 478000, "cuotas": 478000, "int": 8205.67, "total": 486205.67, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "EBNA BANK", "vcto": "2026-06-22", "capital": 180000, "cuotas": 180000, "int": 5320, "total": 185320, "tasa": 5.6, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "PICHINCHA PANAMA", "vcto": "2026-06-24", "capital": 387500, "cuotas": 387500, "int": 6781.25, "total": 394281.25, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "EBNA BANK", "vcto": "2026-06-29", "capital": 314605, "cuotas": 314605, "int": 9787.73, "total": 324392.73, "tasa": 7.0, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "EBNA BANK", "vcto": "2026-07-01", "capital": 556000, "cuotas": 556000, "int": 18487, "total": 574487, "tasa": 5.7, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "EBNA BANK", "vcto": "2026-07-08", "capital": 358494.29, "cuotas": 358494.29, "int": 10595, "total": 369089.29, "tasa": 5.6, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "PICHINCHA PANAMA", "vcto": "2026-08-20", "capital": 87500, "cuotas": 87500, "int": 1341.67, "total": 88841.67, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "ST GEORGES", "vcto": "2026-09-28", "capital": 700000, "cuotas": 700000, "int": 55304.86, "total": 755304.86, "tasa": 7.75, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "EBNA BANK", "vcto": "2026-09-30", "capital": 180000, "cuotas": 180000, "int": 5320, "total": 185320, "tasa": 5.6, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "BOLIVARIANO", "vcto": "2026-10-05", "capital": 521636.28, "cuotas": 521636.28, "int": 15865.8, "total": 537502.08, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "EBNA BANK", "vcto": "2026-11-05", "capital": 200000, "cuotas": 200000, "int": 20000, "total": 220000, "tasa": 5.6, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PAPEL COMERCIAL", "vcto": "2027-01-11", "capital": 750000, "cuotas": 750000, "int": 41250, "total": 791250, "tasa": 5.5, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PAPEL COMERCIAL", "vcto": "2027-01-19", "capital": 500000, "cuotas": 500000, "int": 27500, "total": 527500, "tasa": 5.5, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PAPEL COMERCIAL", "vcto": "2027-01-21", "capital": 750000, "cuotas": 750000, "int": 41250, "total": 791250, "tasa": 5.5, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PAPEL COMERCIAL", "vcto": "2027-01-25", "capital": 2000000, "cuotas": 2000000, "int": 110000, "total": 2110000, "tasa": 5.5, "estado": "PENDIENTE"}, {"empresa": "FULLMOTOS", "inst": "PRODUBANCO", "vcto": "2027-05-10", "capital": 500000, "cuotas": "TA", "int": 17644.02, "total": 517644.02, "tasa": 6.25, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "PRODUBANCO", "vcto": "2027-06-05", "capital": 100000, "cuotas": "TA", "int": 3496.05, "total": 103496.05, "tasa": 6.25, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PRODUBANCO", "vcto": "2027-06-03", "capital": 1000000, "cuotas": "TA", "int": 33734.39, "total": 1033734.39, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "INTERNACIONAL", "vcto": "2027-06-03", "capital": 500000, "cuotas": "TA", "int": 16147.45, "total": 516147.45, "tasa": 6.06, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PICHINCHA", "vcto": "2027-06-09", "capital": 800000, "cuotas": "TA", "int": 24968.75, "total": 824968.75, "tasa": 5.7, "estado": "PENDIENTE"}, {"empresa": "ASSEMBLY", "inst": "PRODUBANCO", "vcto": "2027-06-08", "capital": 500000, "cuotas": "TA", "int": 16710.62, "total": 516710.62, "tasa": 6.0, "estado": "PENDIENTE"}, {"empresa": "JCEVCORP", "inst": "PRODUBANCO", "vcto": "2027-06-11", "capital": 1000000, "cuotas": "TA", "int": 33378.93, "total": 1033378.93, "tasa": 6.0, "estado": "PENDIENTE"}];
const amortData=[{"id": "T1", "empresa": "JCEVCORP", "inst": "PRODUBANCO", "monto": 1000000, "vcto": "2027-04-22", "rows": [{"fecha": "2026-06-22", "capital": 81304.63, "int": 4865.73, "cuota": 86170.36}, {"fecha": "2026-07-22", "capital": 81878.28, "int": 4292.08, "cuota": 86170.36}, {"fecha": "2026-08-22", "capital": 81910.66, "int": 4259.7, "cuota": 86170.36}, {"fecha": "2026-09-22", "capital": 82832.79, "int": 3337.57, "cuota": 86170.36}, {"fecha": "2026-10-22", "capital": 83142.22, "int": 3028.14, "cuota": 86170.36}, {"fecha": "2026-11-22", "capital": 83394.85, "int": 2775.51, "cuota": 86170.36}, {"fecha": "2026-12-22", "capital": 84068.21, "int": 2102.15, "cuota": 86170.36}, {"fecha": "2027-01-22", "capital": 84368.44, "int": 1801.92, "cuota": 86170.36}, {"fecha": "2027-02-22", "capital": 84815.24, "int": 1355.12, "cuota": 86170.36}, {"fecha": "2027-03-22", "capital": 85352.08, "int": 818.28, "cuota": 86170.36}, {"fecha": "2027-04-22", "capital": 85716.41, "int": 453.94, "cuota": 86170.35}]}, {"id": "T2", "empresa": "FULLMOTOS", "inst": "PRODUBANCO", "monto": 500000, "vcto": "2027-05-10", "rows": [{"fecha": "2026-07-06", "capital": 40742.59, "int": 2394.41, "cuota": 43137.0}, {"fecha": "2026-08-11", "capital": 40663.82, "int": 2473.18, "cuota": 43137.0}, {"fecha": "2026-09-08", "capital": 41297.94, "int": 1839.06, "cuota": 43137.0}, {"fecha": "2026-10-08", "capital": 41381.67, "int": 1755.33, "cuota": 43137.0}, {"fecha": "2026-11-09", "capital": 41494.55, "int": 1642.45, "cuota": 43137.0}, {"fecha": "2026-12-08", "capital": 41857.44, "int": 1279.56, "cuota": 43137.0}, {"fecha": "2027-01-08", "capital": 41994.47, "int": 1142.53, "cuota": 43137.0}, {"fecha": "2027-02-10", "capital": 42161.35, "int": 975.65, "cuota": 43137.0}, {"fecha": "2027-03-08", "capital": 42558.62, "int": 578.38, "cuota": 43137.0}, {"fecha": "2027-04-08", "capital": 42676.44, "int": 460.56, "cuota": 43137.0}, {"fecha": "2027-05-10", "capital": 42898.69, "int": 238.33, "cuota": 43137.02}]}, {"id": "T3", "empresa": "ASSEMBLY", "inst": "PRODUBANCO", "monto": 100000, "vcto": "2027-06-05", "rows": [{"fecha": "2026-06-08", "capital": 8051.75, "int": 572.92, "cuota": 8624.67}, {"fecha": "2026-07-06", "capital": 8177.7, "int": 446.97, "cuota": 8624.67}, {"fecha": "2026-08-06", "capital": 8173.82, "int": 450.85, "cuota": 8624.67}, {"fecha": "2026-09-07", "capital": 8204.69, "int": 419.98, "cuota": 8624.67}, {"fecha": "2026-10-06", "capital": 8285.37, "int": 339.3, "cuota": 8624.67}, {"fecha": "2026-11-06", "capital": 8306.56, "int": 318.11, "cuota": 8624.67}, {"fecha": "2026-12-07", "capital": 8351.27, "int": 273.4, "cuota": 8624.67}, {"fecha": "2027-01-06", "capital": 8403.58, "int": 221.09, "cuota": 8624.67}, {"fecha": "2027-02-10", "capital": 8417.8, "int": 206.87, "cuota": 8624.67}, {"fecha": "2027-03-08", "capital": 8508.99, "int": 115.68, "cuota": 8624.67}, {"fecha": "2027-04-06", "capital": 8538.48, "int": 86.19, "cuota": 8624.67}, {"fecha": "2027-05-06", "capital": 8579.99, "int": 44.69, "cuota": 8624.68}]}, {"id": "T4", "empresa": "JCEVCORP", "inst": "PRODUBANCO", "monto": 1000000, "vcto": "2027-06-03", "rows": [{"fecha": "2026-07-03", "capital": 80811.29, "int": 5333.33, "cuota": 86144.62}, {"fecha": "2026-08-03", "capital": 81395.48, "int": 4749.14, "cuota": 86144.62}, {"fecha": "2026-09-03", "capital": 81816.02, "int": 4328.6, "cuota": 86144.62}, {"fecha": "2026-10-05", "capital": 82112.74, "int": 4031.88, "cuota": 86144.62}, {"fecha": "2026-11-04", "capital": 82775.3, "int": 3368.32, "cuota": 86143.62}, {"fecha": "2026-12-03", "capital": 83287.69, "int": 2856.93, "cuota": 86144.62}, {"fecha": "2027-01-04", "capital": 83436.35, "int": 2708.27, "cuota": 86144.62}, {"fecha": "2027-02-03", "capital": 84022.79, "int": 2121.83, "cuota": 86144.62}, {"fecha": "2027-03-03", "capital": 84556.36, "int": 1588.26, "cuota": 86144.62}, {"fecha": "2027-04-05", "capital": 84737.8, "int": 1406.82, "cuota": 86144.62}, {"fecha": "2027-05-03", "capital": 85346.4, "int": 798.22, "cuota": 86144.62}, {"fecha": "2027-06-03", "capital": 85701.78, "int": 442.79, "cuota": 86144.57}]}, {"id": "T5", "empresa": "JCEVCORP", "inst": "INTERNACIONAL", "monto": 500000, "vcto": "2027-06-03", "rows": [{"fecha": "2026-07-03", "capital": 40564.63, "int": 2458.33, "cuota": 43022.96}, {"fecha": "2026-08-03", "capital": 40764.07, "int": 2258.89, "cuota": 43022.96}, {"fecha": "2026-09-03", "capital": 40895.88, "int": 2127.08, "cuota": 43022.96}, {"fecha": "2026-10-05", "capital": 41227.48, "int": 1795.48, "cuota": 43022.96}, {"fecha": "2026-11-04", "capital": 41368.27, "int": 1654.59, "cuota": 43022.86}, {"fecha": "2026-12-03", "capital": 41474.91, "int": 1548.05, "cuota": 43022.96}, {"fecha": "2027-01-04", "capital": 41858.74, "int": 1164.22, "cuota": 43022.96}, {"fecha": "2027-02-03", "capital": 41981.38, "int": 1041.58, "cuota": 43022.96}, {"fecha": "2027-03-03", "capital": 42187.79, "int": 835.17, "cuota": 43022.96}, {"fecha": "2027-04-05", "capital": 42374.29, "int": 648.67, "cuota": 43022.96}, {"fecha": "2027-05-03", "capital": 42617.54, "int": 405.42, "cuota": 43022.96}, {"fecha": "2027-06-03", "capital": 42685.02, "int": 209.87, "cuota": 42894.89}]}, {"id": "T6", "empresa": "JCEVCORP", "inst": "PICHINCHA", "monto": 800000, "vcto": "2027-06-09", "rows": [{"fecha": "2026-07-09", "capital": 64942.88, "int": 3800.0, "cuota": 68742.88}, {"fecha": "2026-08-08", "capital": 65251.36, "int": 3491.52, "cuota": 68742.88}, {"fecha": "2026-09-07", "capital": 65561.3, "int": 3181.58, "cuota": 68742.88}, {"fecha": "2026-10-07", "capital": 65872.72, "int": 2870.16, "cuota": 68742.88}, {"fecha": "2026-11-06", "capital": 66185.62, "int": 2557.27, "cuota": 68742.89}, {"fecha": "2026-12-06", "capital": 66500.0, "int": 2242.89, "cuota": 68742.89}, {"fecha": "2027-01-05", "capital": 66815.87, "int": 1927.01, "cuota": 68742.88}, {"fecha": "2027-02-04", "capital": 67133.25, "int": 1609.63, "cuota": 68742.88}, {"fecha": "2027-03-03", "capital": 67452.13, "int": 1290.75, "cuota": 68742.88}, {"fecha": "2027-04-05", "capital": 67772.53, "int": 970.35, "cuota": 68742.88}, {"fecha": "2027-05-05", "capital": 68094.45, "int": 648.43, "cuota": 68742.88}, {"fecha": "2027-06-09", "capital": 68417.89, "int": 379.15, "cuota": 68797.04}]}, {"id": "T7", "empresa": "ASSEMBLY", "inst": "PRODUBANCO", "monto": 500000, "vcto": "2027-06-08", "rows": [{"fecha": "2026-07-08", "capital": 40559.22, "int": 2500.0, "cuota": 43059.22}, {"fecha": "2026-08-11", "capital": 40455.72, "int": 2603.5, "cuota": 43059.22}, {"fecha": "2026-09-08", "capital": 41103.96, "int": 1955.26, "cuota": 43059.22}, {"fecha": "2026-10-08", "capital": 41169.81, "int": 1889.41, "cuota": 43059.22}, {"fecha": "2026-11-09", "capital": 41263.43, "int": 1795.79, "cuota": 43059.22}, {"fecha": "2026-12-08", "capital": 41631.22, "int": 1428.0, "cuota": 43059.22}, {"fecha": "2027-01-08", "capital": 41747.83, "int": 1311.39, "cuota": 43059.22}, {"fecha": "2027-02-10", "capital": 41892.84, "int": 1166.38, "cuota": 43059.22}, {"fecha": "2027-03-08", "capital": 42321.79, "int": 737.43, "cuota": 43059.22}, {"fecha": "2027-04-08", "capital": 42398.64, "int": 660.58, "cuota": 43059.22}, {"fecha": "2027-05-10", "capital": 42603.46, "int": 455.76, "cuota": 43059.22}, {"fecha": "2027-06-08", "capital": 42852.08, "int": 207.12, "cuota": 43059.2}]}, {"id": "T8", "empresa": "JCEVCORP", "inst": "PRODUBANCO", "monto": 1000000, "vcto": "2027-06-11", "rows": [{"fecha": "2026-07-13", "capital": 80781.58, "int": 5333.33, "cuota": 86114.91}, {"fecha": "2026-08-11", "capital": 81672.02, "int": 4442.89, "cuota": 86114.91}, {"fecha": "2026-09-11", "capital": 81787.59, "int": 4327.32, "cuota": 86114.91}, {"fecha": "2026-10-12", "capital": 82210.16, "int": 3904.75, "cuota": 86114.91}, {"fecha": "2026-11-11", "capital": 82747.17, "int": 3367.74, "cuota": 86114.91}, {"fecha": "2026-12-11", "capital": 83160.9, "int": 2954.01, "cuota": 86114.91}, {"fecha": "2027-01-11", "capital": 83492.1, "int": 2622.81, "cuota": 86114.91}, {"fecha": "2027-02-11", "capital": 83923.48, "int": 2191.43, "cuota": 86114.91}, {"fecha": "2027-03-11", "capital": 84527.19, "int": 1587.72, "cuota": 86114.91}, {"fecha": "2027-04-13", "capital": 84708.57, "int": 1406.34, "cuota": 86114.91}, {"fecha": "2027-05-11", "capital": 85316.96, "int": 797.95, "cuota": 86114.91}, {"fecha": "2027-06-11", "capital": 85672.28, "int": 442.64, "cuota": 86114.92}]}];
const jcevData=[{"empresa": "JCEVCORP", "prov": "DOWNPAYMENTS", "imp": "DOWNPAYMENTS", "merch": "ANTICIPO", "total": 0, "anticipo": 0, "valor": 450000, "vcto": "2026-06-01", "ejec": "DOWNPAYMENT"}, {"empresa": "JCEVCORP", "prov": "COBY", "imp": "COBY 05-2025", "merch": "PARLANTES", "total": 28500, "anticipo": 8550, "valor": 19950, "vcto": "2026-06-01", "ejec": "GS"}, {"empresa": "CONSUREP", "prov": "KONKA", "imp": "KONKA 06-2025", "merch": "PANEL", "total": 264213.8, "anticipo": 0, "valor": 264213.8, "vcto": "2026-06-02", "ejec": "AH"}, {"empresa": "CONSUREP", "prov": "KONKA", "imp": "KONKA 06-2025", "merch": "INTEREST", "total": 3170.56, "anticipo": 0, "valor": 3170.56, "vcto": "2026-06-02", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "LG ELECTRONICS", "imp": "LG 10A-2026/2000046483", "merch": "SECADORA", "total": 38580, "anticipo": 0, "valor": 38580, "vcto": "2026-06-04", "ejec": "RLL"}, {"empresa": "CONSUREP", "prov": "ALL DISTRIBUTION PANEL", "imp": "AD 07-2026/10379", "merch": "PANEL", "total": 551073.09, "anticipo": 449082.76, "valor": 101990.33, "vcto": "2026-06-04", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "TERCELO TIRE", "imp": "TRANSMATE 03-2026", "merch": "LLANTAS", "total": 91793.8, "anticipo": 27538.14, "valor": 64255.66, "vcto": "2026-06-05", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "TERCELO TIRE", "imp": "TRANSMATE 04-2026", "merch": "LLANTAS", "total": 98469.8, "anticipo": 29540.9, "valor": 68928.9, "vcto": "2026-06-05", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "MEILING", "imp": "MEILING 05-2026", "merch": "REFRIGERADORAS", "total": 78534, "anticipo": 20153, "valor": 58381, "vcto": "2026-06-05", "ejec": "GS"}, {"empresa": "JCEVCORP", "prov": "XING", "imp": "XING 01-2026", "merch": "VITRINA XLS", "total": 9342, "anticipo": 1870, "valor": 7472, "vcto": "2026-06-05", "ejec": "GS"}, {"empresa": "JCEVCORP", "prov": "HOME ELEMENTS", "imp": "HOME 02-2026", "merch": "ELECTROMENOR", "total": 39172.8, "anticipo": 0, "valor": 39172.8, "vcto": "2026-06-06", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "LG ELECTRONICS", "imp": "LG 11-2026/2000046540", "merch": "LAVADORAS", "total": 75600, "anticipo": 0, "valor": 75600, "vcto": "2026-06-07", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "HOUSEHOLD SOLUTIONS", "imp": "OSTER 26-2025/23-2025", "merch": "REFRIGERADORA 215", "total": 54497, "anticipo": 16349.5, "valor": 38147.5, "vcto": "2026-06-07", "ejec": "GS"}, {"empresa": "JCEVCORP", "prov": "TAIZHOU QINLI MACHINERY", "imp": "QINLI 01-2026", "merch": "FUMIGADORAS", "total": 52195, "anticipo": 10000, "valor": 42195, "vcto": "2026-06-07", "ejec": ""}, {"empresa": "JCEVCORP", "prov": "HOME ELEMENTS", "imp": "HOME 04-2026", "merch": "ELECTROMENOR", "total": 32140, "anticipo": 0, "valor": 32140, "vcto": "2026-06-08", "ejec": "RLL"}, {"empresa": "CONSUREP", "prov": "EXPRESS LUCK", "imp": "EXPRESS LUCK 01-2026", "merch": "TV PARTS", "total": 3879473.5, "anticipo": 2201450.5, "valor": 1678023, "vcto": "2026-06-08", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "SHANFENG", "imp": "SHANFENG 02-2026", "merch": "REGULADORES", "total": 37750, "anticipo": 11325, "valor": 26425, "vcto": "2026-06-10", "ejec": "GS"}, {"empresa": "JCEVCORP", "prov": "ITT", "imp": "ITT 01-2026", "merch": "LAVADORAS", "total": 43800, "anticipo": 4470, "valor": 39330, "vcto": "2026-06-10", "ejec": "GS"}, {"empresa": "JCEVCORP", "prov": "LAMO", "imp": "LAMO 01-2026", "merch": "DISPENSADORES", "total": 27225, "anticipo": 8167.5, "valor": 19057.5, "vcto": "2026-06-10", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "MINSHENG", "imp": "MINSHENG 01-2026", "merch": "COCINAS", "total": 36487, "anticipo": 10946.1, "valor": 25540.9, "vcto": "2026-06-10", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "HOME ELEMENTS", "imp": "HOME 03-2026", "merch": "ELECTROMENOR", "total": 34299.2, "anticipo": 0, "valor": 34299.2, "vcto": "2026-06-10", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "LG ELECTRONICS", "imp": "LG 12-2026/2000046787", "merch": "LAVADORAS", "total": 107100, "anticipo": 0, "valor": 107100, "vcto": "2026-06-11", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "KONKA", "imp": "KONKA 06-2025", "merch": "MB", "total": 180559.2, "anticipo": 90280, "valor": 90279.2, "vcto": "2026-06-11", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "KONKA", "imp": "KONKA 06-2025", "merch": "INTEREST", "total": 2166.71, "anticipo": 0, "valor": 2166.71, "vcto": "2026-06-11", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "SICUENS", "imp": "FEDERAL 02-2026", "merch": "LLANTAS", "total": 52080, "anticipo": 15624, "valor": 36456, "vcto": "2026-06-15", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "COMPA\u00d1IA HULERA", "imp": "TORNEL 07A-2025", "merch": "LLANTAS", "total": 42838.33, "anticipo": 12851.5, "valor": 29986.83, "vcto": "2026-06-15", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "COMPA\u00d1IA HULERA", "imp": "TORNEL 01-2026", "merch": "LLANTAS", "total": 151631.28, "anticipo": 45489.38, "valor": 106141.9, "vcto": "2026-06-15", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "COMPA\u00d1IA HULERA", "imp": "TORNEL 02-2026", "merch": "LLANTAS", "total": 203389.4, "anticipo": 61016.82, "valor": 142372.58, "vcto": "2026-06-15", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "LONGSONG", "imp": "LONGSONG 01-2026", "merch": "VENTILADORES", "total": 25376.4, "anticipo": 7612.92, "valor": 17763.48, "vcto": "2026-06-15", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "HOME ELEMENTS", "imp": "HOME 01-2026", "merch": "ELECTROMENOR", "total": 27550.5, "anticipo": 0, "valor": 27550.5, "vcto": "2026-06-16", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "LG ELECTRONICS", "imp": "LG 13A-2026/2000047062", "merch": "REFRIGERADORA", "total": 32900, "anticipo": 0, "valor": 32900, "vcto": "2026-06-17", "ejec": "RLL"}, {"empresa": "TODOMOTO", "prov": "ALL DISTRIBUTION MB", "imp": "AD 07-2026/10378", "merch": "MB", "total": 183695.44, "anticipo": 106709.74, "valor": 76985.7, "vcto": "2026-06-18", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "MINFU", "imp": "MINFU 01-2026", "merch": "PARLANTES", "total": 54974.98, "anticipo": 17047.11, "valor": 37927.87, "vcto": "2026-06-20", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "LG ELECTRONICS", "imp": "LG 13-2026/2000047237", "merch": "REFRIGERADORA", "total": 24000, "anticipo": 0, "valor": 24000, "vcto": "2026-06-22", "ejec": "RLL"}, {"empresa": "JCEVCORP", "prov": "BEST CHOICE INT'L", "imp": "MAZZINI 03A-2026", "merch": "LLANTAS", "total": 131235.54, "anticipo": 0, "valor": 131235.54, "vcto": "2026-06-22", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "BEST CHOICE INT'L", "imp": "MAZZINI 04-2026", "merch": "LLANTAS", "total": 57098.15, "anticipo": 0, "valor": 57098.15, "vcto": "2026-06-24", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "TAIZHOU GUANGFENG PLASTIC", "imp": "GUANGFENG 01-2026", "merch": "SEMBRADORAS/FUMIGADORA", "total": 17995, "anticipo": 5386.5, "valor": 12608.5, "vcto": "2026-06-24", "ejec": ""}, {"empresa": "JCEVCORP", "prov": "KUMHO", "imp": "KUMHO 01A-2026", "merch": "LLANTAS", "total": 42360.8, "anticipo": 0, "valor": 42360.8, "vcto": "2026-06-26", "ejec": "AH"}, {"empresa": "JCEVCORP", "prov": "HOUSEHOLD SOLUTIONS", "imp": "OSTER 24-2025", "merch": "DISPENSADOR DE AGUA", "total": 36792, "anticipo": 11038, "valor": 25754, "vcto": "2026-06-28", "ejec": "GS"}, {"empresa": "JCEVCORP", "prov": "XING", "imp": "XING 02-2026", "merch": "SD", "total": 23988, "anticipo": 4800, "valor": 19188, "vcto": "2026-06-29", "ejec": "GS"}, {"empresa": "JCEVCORP", "prov": "TAIZHOU MUGUANG", "imp": "WINSTAR 01-2026", "merch": "SOLDADORAS", "total": 62330, "anticipo": 6233, "valor": 56097, "vcto": "2026-06-30", "ejec": ""}];
const credData=[{"empresa": "CREDIMPORT", "prov": "DOWNPAYMENTS", "imp": "DOWNPAYMENTS", "merch": "ANTICIPO", "total": 0, "anticipo": 0, "valor": 350000, "vcto": "2026-06-01", "ejec": "DOWNPAYMENT"}];
const asmData=[{"empresa": "ASSEMBLY", "prov": "DOWNPAYMENTS", "imp": "DOWNPAYMENTS", "merch": "ANTICIPO", "total": 0, "anticipo": 0, "valor": 450000, "vcto": "2026-06-01", "ejec": "DOWNPAYMENT"}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MOTORHEAD", "imp": "MOTORHEAD 18-2025", "merch": "DY250 SCORPION", "total": 102136, "anticipo": 30000, "valor": 72136, "vcto": "2026-06-04", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MOTORHEAD", "imp": "MOTORHEAD 26-2025", "merch": "DY300 TEKKEN DISCOVERY", "total": 160464, "anticipo": 46000, "valor": 114464, "vcto": "2026-06-04", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "LIFAN INDUSTRY", "imp": "LIFAN 02-2025", "merch": "DY180 WORKFORCE", "total": 183540, "anticipo": 55062, "valor": 128478, "vcto": "2026-06-06", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "SENGO LIMITED", "imp": "SENGO 06-2025", "merch": "DY125 TANQ", "total": 60602, "anticipo": 20000, "valor": 40602, "vcto": "2026-06-10", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MINFF", "imp": "MINFF 12-2025", "merch": "DY150 DYNAMIC PRO", "total": 98784, "anticipo": 29635.2, "valor": 69148.8, "vcto": "2026-06-10", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MINFF", "imp": "MINFF 01-2026", "merch": "DY200 EAGLE Z", "total": 81466, "anticipo": 24439.8, "valor": 57026.2, "vcto": "2026-06-10", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "SONLINK MOTORCYCLE", "imp": "SONLINK 50-2025", "merch": "DY150 CRUCERO", "total": 86700, "anticipo": 20000, "valor": 66700, "vcto": "2026-06-11", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "LINXI MOTOR INT'L", "imp": "XIN LIN 02-2025", "merch": "DY200 ARROW", "total": 104520, "anticipo": 31356, "valor": 73164, "vcto": "2026-06-13", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "LINXI MOTOR INT'L", "imp": "XIN LIN 01-2026", "merch": "DY200 WING EVO II", "total": 193952, "anticipo": 58185, "valor": 135767, "vcto": "2026-06-13", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MOTORHEAD", "imp": "MOTORHEAD 32-2025", "merch": "DY200 SCORPION", "total": 175891, "anticipo": 52000, "valor": 123891, "vcto": "2026-06-16", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "WUXI EAST TECHNOLOGY", "imp": "EST 02-2026", "merch": "DY370 GP-1 RR", "total": 138020, "anticipo": 41406, "valor": 96614, "vcto": "2026-06-20", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "SONLINK MOTORCYCLE", "imp": "SONLINK 42-2025", "merch": "DY250 WOLF", "total": 106604, "anticipo": 20000, "valor": 86604, "vcto": "2026-06-21", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "SONLINK MOTORCYCLE", "imp": "SONLINK 46-2025", "merch": "DY200 CRUCERO", "total": 91392, "anticipo": 20000, "valor": 71392, "vcto": "2026-06-21", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "SONLINK MOTORCYCLE", "imp": "SONLINK 49-2025", "merch": "DY150 WORKFORCE", "total": 276192, "anticipo": 60000, "valor": 216192, "vcto": "2026-06-21", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MOTORHEAD", "imp": "MOTORHEAD 31-2025", "merch": "DY200 SCORPION", "total": 178800, "anticipo": 52000, "valor": 126800, "vcto": "2026-06-26", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MOTORHEAD", "imp": "MOTORHEAD 33A-2026", "merch": "DY250 SCORPION", "total": 97950, "anticipo": 0, "valor": 97950, "vcto": "2026-06-26", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING XGJAO", "imp": "VINTO 02-2026", "merch": "DY300 EVEREST", "total": 190080, "anticipo": 57024, "valor": 133056, "vcto": "2026-06-26", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "BASHAN MOTORCYCLE", "imp": "BASHAN C 18-2025", "merch": "DY200 SHARK", "total": 72310.98, "anticipo": 16023, "valor": 56287.98, "vcto": "2026-06-27", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "CHONGQING MINFF", "imp": "MINFF 02-2026", "merch": "DY200 EAGLE Z", "total": 81928, "anticipo": 24578.4, "valor": 57349.6, "vcto": "2026-06-29", "ejec": ""}, {"empresa": "ASSEMBLY", "prov": "JIANGSU DAELG MOTORCYCLE", "imp": "SUKULI 02-2025", "merch": "CF 450 SR", "total": 207900, "anticipo": 62370, "valor": 145530, "vcto": "2026-06-30", "ejec": ""}];
const sriData=[{"empresa": "ASSEMBLY", "sri": 220636, "fecha": "2026-06-11", "nc": 132000, "debito": 88636, "banco": "PICHINCHA"}, {"empresa": "JCEVCORP", "sri": 632000, "fecha": "2026-06-11", "nc": 378000, "debito": 254000, "banco": "PRODUBANCO"}, {"empresa": "CREDIMPORT", "sri": 8291, "fecha": "2026-06-16", "nc": 4000, "debito": 4291, "banco": "PICHINCHA"}, {"empresa": "FULLMOTOS", "sri": 74828, "fecha": "2026-06-16", "nc": 44000, "debito": 30828, "banco": "PICHINCHA"}];
const nominaData=[{"empresa": "ASSEMBLY", "monto": 13545, "fecha": "2026-06-15", "quincena": "1Q"}, {"empresa": "ASSEMBLY", "monto": 20797, "fecha": "2026-06-30", "quincena": "2Q"}, {"empresa": "JCEVCORP", "monto": 38200, "fecha": "2026-06-15", "quincena": "1Q"}, {"empresa": "JCEVCORP", "monto": 95300, "fecha": "2026-06-30", "quincena": "2Q"}, {"empresa": "CREDIMPORT", "monto": 14041, "fecha": "2026-06-15", "quincena": "1Q"}, {"empresa": "CREDIMPORT", "monto": 31659, "fecha": "2026-06-30", "quincena": "2Q"}, {"empresa": "MONTAZ", "monto": 8100, "fecha": "2026-06-15", "quincena": "1Q"}, {"empresa": "MONTAZ", "monto": 12350, "fecha": "2026-06-30", "quincena": "2Q"}, {"empresa": "TODOMOTO", "monto": 5219, "fecha": "2026-06-15", "quincena": "1Q"}, {"empresa": "TODOMOTO", "monto": 7487, "fecha": "2026-06-30", "quincena": "2Q"}, {"empresa": "CONSUREP", "monto": 14100, "fecha": "2026-06-15", "quincena": "1Q"}, {"empresa": "CONSUREP", "monto": 16500, "fecha": "2026-06-30", "quincena": "2Q"}];
const provData=[{"empresa": "ASSEMBLY", "monto": 220000, "fecha": "2026-06-15"}, {"empresa": "JCEVCORP", "monto": 350000, "fecha": "2026-06-15"}, {"empresa": "CREDIMPORT", "monto": 60000, "fecha": "2026-06-15"}, {"empresa": "FULLMOTOS", "monto": 150000, "fecha": "2026-06-15"}, {"empresa": "CONSUREP", "monto": 20000, "fecha": "2026-06-15"}];
const impData=[{"liq": "51491806", "val": 21222.22}, {"liq": "51499011", "val": 70585.47}, {"liq": "51495571", "val": 95507.12}, {"liq": "51515029", "val": 162831.24}, {"liq": "51621013", "val": 65199.04}, {"liq": "51633589", "val": 299.36}, {"liq": "51590012", "val": 71996.43}, {"liq": "51589160", "val": 103593.97}, {"liq": "51581279", "val": 47581.9}, {"liq": "51597652", "val": 21111.97}, {"liq": "51576806", "val": 40448.24}, {"liq": "51588854", "val": 13134.04}, {"liq": "51562749", "val": 8509.37}, {"liq": "51554949", "val": 62137.66}, {"liq": "51632574", "val": 6447.01}, {"liq": "51624222", "val": 6020.1}, {"liq": "51632776", "val": 25025.02}, {"liq": "51560613", "val": 79837.99}];

// ============================================================
// UTILS
// ============================================================
const MES={
  '2026-04':'Abril 2026','2026-05':'Mayo 2026','2026-06':'Junio 2026',
  '2026-07':'Julio 2026','2026-08':'Agosto 2026','2026-09':'Septiembre 2026',
  '2026-10':'Octubre 2026','2026-11':'Noviembre 2026','2026-12':'Diciembre 2026',
  '2027-01':'Enero 2027','2027-02':'Febrero 2027','2027-03':'Marzo 2027',
  '2027-04':'Abril 2027','2027-05':'Mayo 2027','2027-06':'Junio 2027'
};
const DOWS=['DOM','LUN','MAR','MIÉ','JUE','VIE','SÁB'];

function fmt(v){if(!v&&v!==0)return'—';return'$'+Number(v).toLocaleString('es-EC',{minimumFractionDigits:0,maximumFractionDigits:0});}
function fmtd(v){if(!v&&v!==0)return'—';return'$'+Number(v).toLocaleString('es-EC',{minimumFractionDigits:2,maximumFractionDigits:2});}
function fmtD(s){if(!s)return'—';const[y,m,d]=s.split('-');return d+'/'+m+'/'+y;}
function daysDiff(iso){const t=new Date(iso+'T12:00:00');const n=new Date();return Math.round((t-n)/86400000);}

function empBadge(e){
  const map={'JCEVCORP':'eb-jcev','ASSEMBLY':'eb-asm','FULLMOTOS':'eb-full',
    'CREDIMPORT':'eb-cred','CONSUREP':'eb-cons','TODOMOTO':'eb-todo','MONTAZ':'eb-mont'};
  return`<span class="eb ${map[e]||'eb-jcev'}">${e}</span>`;
}
function stBadge(s){
  if(!s)return'';
  if(s==='CANCELADO')return`<span class="st-badge st-canc">CANCELADO</span>`;
  if(s==='PENDIENTE'){const d=Date.now();return`<span class="st-badge st-pend">PENDIENTE</span>`;}
  return`<span class="st-badge">${s}</span>`;
}

const TIPO_COL={
  'Obligación':'#3b82f6','Amort. TA':'#a855f7',
  'Imp. JCEV':'#22c55e','Imp. CONSUREP':'#06b6d4','Imp. TODOMOTO':'#eab308',
  'Imp. CREDIMPORT':'#f97316','Imp. ASSEMBLY':'#ec4899',
  'SRI':'#f59e0b','Nómina':'#10b981','Proveedores':'#8b5cf6','Imp. Garantizado':'#ef4444'
};

function typBadge(t){const c=TIPO_COL[t]||'#3b82f6';return`<span class="typ-badge" style="background:${c}22;color:${c};border-color:${c}44">${t}</span>`;}

function showToast(msg,ok=true){
  const t=document.getElementById('toast');
  t.textContent=msg;t.style.borderColor=ok?'rgba(34,197,94,.4)':'rgba(239,68,68,.4)';
  t.style.color=ok?'#4ade80':'#f87171';
  t.classList.add('show');setTimeout(()=>t.classList.remove('show'),3000);
}

// ============================================================
// NAVIGATION
// ============================================================
const TITLES={'s-res':'Resumen General','s-obl':'Obligaciones Financieras',
  's-amort':'Amortización TA','s-jcev':'Flujo JCEV & CONSUREP',
  's-cred':'Flujo CREDIMPORT','s-asm':'Flujo ASSEMBLY',
  's-sri':'SRI & Nómina','s-prov':'Proveedores Nacionales',
  's-imp':'Impuestos Garantizados SENAE','s-cal':'Calendario Consolidado'};

function nav(id){
  document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
  document.getElementById(id).classList.add('active');
  document.querySelectorAll('.nav-item').forEach(n=>{
    n.classList.toggle('active', n.getAttribute('onclick')===`nav('${id}')`);
  });
  document.getElementById('section-title').textContent=TITLES[id]||'';
}

// ============================================================
// RENDER OBLIGACIONES
// ============================================================
function renderObl(){
  const tb=document.getElementById('tbody-obl');
  const sorted=[...oblData].sort((a,b)=>a.vcto.localeCompare(b.vcto));
  let jcevT=0,asmT=0,fullT=0;
  tb.innerHTML=sorted.map(o=>{
    if(o.empresa==='JCEVCORP')jcevT+=o.total;
    if(o.empresa==='ASSEMBLY')asmT+=o.total;
    if(o.empresa==='FULLMOTOS')fullT+=o.total;
    const isTA=o.cuotas==='TA';
    const d=daysDiff(o.vcto);
    const rowCls=d<0?'style="background:rgba(239,68,68,0.05)"':d<30?'style="background:rgba(245,158,11,0.03)"':'';
    return`<tr ${rowCls}><td>${empBadge(o.empresa)}</td><td>${o.inst}</td><td>${fmtD(o.vcto)}</td>
      <td>${isTA?'<span class="ta-badge">TA</span>':'Bullet'}</td>
      <td class="num">${fmt(o.capital)}</td><td class="num">${fmtd(o.int)}</td>
      <td class="num" style="font-weight:700;color:var(--text)">${fmtd(o.total)}</td>
      <td>${(o.tasa).toFixed(2)}%</td></tr>`;
  }).join('');
  document.getElementById('obl-jcev-total').textContent=fmt(jcevT);
  document.getElementById('obl-asm-total').textContent=fmt(asmT);
  document.getElementById('obl-full-total').textContent=fmt(fullT);
}

// ============================================================
// RENDER AMORT TABLES
// ============================================================
function renderAmort(){
  let sumAll=0,jcevT=0,asmT=0,fullT=0;
  const container=document.getElementById('amort-tables');
  container.innerHTML='';
  amortData.forEach(t=>{
    const total=t.rows.reduce((s,r)=>s+r.cuota,0);
    sumAll+=total;
    if(t.empresa==='JCEVCORP')jcevT+=total;
    if(t.empresa==='ASSEMBLY')asmT+=total;
    if(t.empresa==='FULLMOTOS')fullT+=total;

    const div=document.createElement('div');
    div.className='amort-block';
    const rows=t.rows.map((r,i)=>`<tr>
      <td style="color:var(--text3)">${i+1}</td>
      <td>${fmtD(r.fecha)}</td>
      <td class="num">${fmtd(r.capital)}</td>
      <td class="num">${fmtd(r.int)}</td>
      <td class="num" style="font-weight:700;color:var(--green)">${fmtd(r.cuota)}</td>
    </tr>`).join('');
    div.innerHTML=`<div class="amort-header">
      <h3>${t.id} · ${empBadge(t.empresa)} ${t.inst} &nbsp;<span style="font-size:11px;color:var(--text3)">Monto: ${fmt(t.monto)} · Vence: ${fmtD(t.vcto)}</span></h3>
      <span class="ah-right">${t.rows.length} cuotas PENDIENTE · Total: ${fmtd(total)}</span>
    </div>
    <table><thead><tr><th>#</th><th>Fecha</th><th class="num">Capital</th><th class="num">Interés</th><th class="num">Cuota</th></tr></thead>
    <tbody>${rows}</tbody>
    <tfoot><tr class="tot"><td colspan="2">TOTAL</td><td class="num">${fmtd(t.rows.reduce((s,r)=>s+r.capital,0))}</td><td class="num">${fmtd(t.rows.reduce((s,r)=>s+r.int,0))}</td><td class="num">${fmtd(total)}</td></tr></tfoot>
    </table>`;
    container.appendChild(div);
  });
  document.getElementById('amort-sum-total').textContent=fmtd(sumAll);
  document.getElementById('amort-jcev').textContent=fmt(jcevT);
  document.getElementById('amort-asm').textContent=fmt(asmT);
  document.getElementById('amort-full').textContent=fmt(fullT);
}

// ============================================================
// RENDER IMPORT TABLES
// ============================================================
function importRow(r,i){
  return`<tr><td>${empBadge(r.empresa)}</td><td style="max-width:150px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap" title="${r.prov}">${r.prov}</td>
    <td style="max-width:150px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap" title="${r.imp}">${r.imp}</td>
    <td>${r.merch}</td>
    <td class="num">${r.total?fmtd(r.total):'—'}</td>
    <td class="num">${r.anticipo?fmtd(r.anticipo):'—'}</td>
    <td class="num" style="font-weight:700;color:var(--green)">${fmtd(r.valor)}</td>
    <td>${fmtD(r.vcto)}</td>
    <td style="color:var(--text3)">${r.ejec||'—'}</td></tr>`;
}
function renderJcev(){
  const tb=document.getElementById('tbody-jcev');
  tb.innerHTML=jcevData.map(importRow).join('');
}
function renderCred(){
  const tb=document.getElementById('tbody-cred');
  tb.innerHTML=credData.map(importRow).join('');
}
function renderAsm(){
  const tb=document.getElementById('tbody-asm');
  tb.innerHTML=asmData.map((r,i)=>`<tr>
    <td style="color:var(--text3)">${i+1}</td>
    <td style="max-width:160px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap" title="${r.prov}">${r.prov}</td>
    <td>${r.imp}</td><td>${r.merch}</td>
    <td class="num">${fmtd(r.total)}</td>
    <td class="num">${r.anticipo?fmtd(r.anticipo):'—'}</td>
    <td class="num" style="font-weight:700;color:var(--green)">${fmtd(r.valor)}</td>
    <td>${fmtD(r.vcto)}</td></tr>`).join('');
}
function renderSri(){
  document.getElementById('tbody-sri').innerHTML=sriData.map(r=>`<tr>
    <td>${empBadge(r.empresa)}</td>
    <td class="num">${fmtd(r.sri)}</td>
    <td class="num" style="color:var(--green)">${fmtd(r.nc)}</td>
    <td class="num" style="color:var(--red);font-weight:700">${fmtd(r.debito)}</td>
    <td>${r.banco}</td><td>${fmtD(r.fecha)}</td></tr>`).join('');
  // nomina grouped
  const nomByEmp={};
  nominaData.forEach(r=>{
    if(!nomByEmp[r.empresa])nomByEmp[r.empresa]={q1:0,q2:0};
    if(r.quincena==='1Q')nomByEmp[r.empresa].q1=r.monto;
    else nomByEmp[r.empresa].q2=r.monto;
  });
  document.getElementById('tbody-nom').innerHTML=nominaData.map(r=>`<tr>
    <td>${empBadge(r.empresa)}</td>
    <td><span class="st-badge" style="background:rgba(59,130,246,.15);color:#60a5fa">${r.quincena==='1Q'?'1ª Quincena':'2ª Quincena'}</span></td>
    <td class="num" style="font-weight:700">${fmtd(r.monto)}</td>
    <td>${fmtD(r.fecha)}</td></tr>`).join('');
}
function renderProv(){
  document.getElementById('tbody-prov').innerHTML=provData.map(r=>`<tr>
    <td>${empBadge(r.empresa)}</td>
    <td class="num" style="font-weight:700;color:var(--green)">${fmtd(r.monto)}</td>
    <td>${fmtD(r.fecha)}</td></tr>`).join('');
}
function renderImp(){
  document.getElementById('tbody-imp').innerHTML=impData.map((r,i)=>`<tr>
    <td style="color:var(--text3)">${i+1}</td>
    <td style="font-weight:600">${r.liq}</td>
    <td><span class="st-badge st-nopag">NO PAGADO</span></td>
    <td>31/07/2026</td>
    <td>CORPORACION JCEVCORP CIA. LTDA.</td>
    <td class="num" style="font-weight:700;color:var(--red)">${fmtd(r.val)}</td>
    <td>04/08/2026</td></tr>`).join('')
  +`<tr class="tot"><td colspan="5" style="text-align:right;color:var(--text2)">TOTAL</td><td class="num" style="color:var(--red)">$901,488.15</td><td></td></tr>`;
}

// ============================================================
// RENDER VENCIMIENTOS (Resumen)
// ============================================================
function renderVenc(){
  const today=new Date();
  const limit=new Date();limit.setDate(limit.getDate()+120);
  const rows=oblData.filter(o=>{
    const d=new Date(o.vcto+'T12:00:00');
    return d>=today&&d<=limit;
  }).sort((a,b)=>a.vcto.localeCompare(b.vcto));
  const tb=document.getElementById('tbody-venc');
  if(!rows.length){tb.innerHTML='<tr><td colspan="7" style="text-align:center;color:var(--text3);padding:20px">Sin vencimientos próximos</td></tr>';return;}
  tb.innerHTML=rows.map(o=>{
    const d=daysDiff(o.vcto);
    const cls=d<0?'color:var(--red)':d<30?'color:var(--warn)':'color:var(--green)';
    return`<tr>
      <td>${empBadge(o.empresa)}</td><td>${o.inst}</td>
      <td>${fmtD(o.vcto)}</td>
      <td>${o.cuotas==='TA'?'<span class="ta-badge">TA</span>':'Bullet'}</td>
      <td class="num">${fmt(o.capital)}</td>
      <td class="num" style="font-weight:700">${fmtd(o.total)}</td>
      <td><span class="st-badge st-pend">PENDIENTE</span> <span style="${cls};font-size:10px;font-weight:700">(${d<0?'Vencida '+Math.abs(d)+'d':d+' días'})</span></td>
    </tr>`;
  }).join('');
}

// ============================================================
// CALENDAR
// ============================================================
let allTx=[];
function buildAllTx(){
  allTx=[];
  // Obligaciones directas (no TA)
  oblData.filter(o=>o.cuotas!=='TA').forEach(o=>{
    allTx.push({iso:o.vcto,empresa:o.empresa,tipo:'Obligación',desc:o.inst+' · '+fmt(o.capital),monto:o.total});
  });
  // Amort TA
  amortData.forEach(t=>{
    t.rows.forEach(r=>{
      allTx.push({iso:r.fecha,empresa:t.empresa,tipo:'Amort. TA',desc:t.id+' · '+t.inst+' · '+fmt(r.capital),monto:r.cuota});
    });
  });
  // JCEV imports
  jcevData.forEach(r=>{
    const tipo='Imp. '+(r.empresa==='JCEVCORP'?'JCEV':r.empresa);
    allTx.push({iso:r.vcto,empresa:r.empresa,tipo,desc:r.prov+' · '+r.merch,monto:r.valor});
  });
  // CRED
  credData.forEach(r=>{allTx.push({iso:r.vcto,empresa:'CREDIMPORT',tipo:'Imp. CREDIMPORT',desc:r.prov+' · '+r.merch,monto:r.valor});});
  // ASM
  asmData.forEach(r=>{allTx.push({iso:r.vcto,empresa:'ASSEMBLY',tipo:'Imp. ASSEMBLY',desc:r.imp+' · '+r.merch,monto:r.valor});});
  // SRI
  sriData.forEach(r=>{allTx.push({iso:r.fecha,empresa:r.empresa,tipo:'SRI',desc:'SRI '+r.empresa+' · Débito: '+fmt(r.debito),monto:r.sri});});
  // Nomina
  nominaData.forEach(r=>{allTx.push({iso:r.fecha,empresa:r.empresa,tipo:'Nómina',desc:'Nómina '+r.quincena+' · '+r.empresa,monto:r.monto});});
  // Proveedores
  provData.forEach(r=>{allTx.push({iso:r.fecha,empresa:r.empresa,tipo:'Proveedores',desc:'Prov. '+r.empresa,monto:r.monto});});
  // Impuestos Garantizados
  impData.forEach(r=>{allTx.push({iso:'2026-08-04',empresa:'JCEVCORP',tipo:'Imp. Garantizado',desc:'Liq. '+r.liq+' · SENAE',monto:r.val});});
}

let activePills=new Set();
function togglePill(el){
  const v=el.dataset.val;
  if(v===''){
    activePills.clear();
    document.querySelectorAll('#cal-pills .pill').forEach(p=>{p.classList.toggle('active',p.dataset.val==='');});
  } else {
    document.querySelector('#cal-pills .pill[data-val=""]').classList.remove('active');
    if(activePills.has(v)){activePills.delete(v);el.classList.remove('active');}
    else{activePills.add(v);el.classList.add('active');}
    if(activePills.size===0){
      document.querySelector('#cal-pills .pill[data-val=""]').classList.add('active');
    }
  }
  renderCal();
}

function renderCal(){
  const fEmp=document.getElementById('f-emp').value;
  const fMes=document.getElementById('f-mes').value;
  let data=[...allTx];
  if(activePills.size>0) data=data.filter(t=>activePills.has(t.tipo));
  if(fEmp) data=data.filter(t=>t.empresa===fEmp);
  if(fMes) data=data.filter(t=>t.iso&&t.iso.startsWith(fMes));
  data.sort((a,b)=>(a.iso||'').localeCompare(b.iso||''));

  const byMonth={};
  data.forEach(t=>{
    if(!t.iso||typeof t.iso!=='string')return;
    const m=t.iso.slice(0,7);
    if(!byMonth[m])byMonth[m]=[];
    byMonth[m].push(t);
  });

  const container=document.getElementById('cal-body');
  container.innerHTML='';
  const months=Object.keys(byMonth).sort();

  if(!months.length){
    container.innerHTML='<div class="empty-state"><div class="ei">📅</div><p>Sin transacciones para los filtros seleccionados.</p></div>';
    return;
  }

  months.forEach(ym=>{
    const txs=byMonth[ym];
    const total=txs.reduce((s,t)=>s+(t.monto||0),0);
    const div=document.createElement('div');
    div.className='cal-month';
    let html=`<div class="cal-month-hdr">
      <span class="cmh-title">${MES[ym]||ym}</span>
      <span class="cmh-stats">${txs.length} pagos · ${fmt(total)}</span>
    </div><div class="cal-list">`;
    txs.forEach(t=>{
      const d=new Date(t.iso+'T12:00:00');
      const dn=String(d.getDate()).padStart(2,'0');
      const dow=DOWS[d.getDay()];
      html+=`<div class="cal-card">
        <div class="cal-day-box"><span class="cal-dn">${dn}</span><span class="cal-dow">${dow}</span></div>
        <div class="cal-body">
          <div class="cal-badges">${empBadge(t.empresa)}${typBadge(t.tipo)}</div>
          <div class="cal-desc" title="${t.desc}">${t.desc}</div>
        </div>
        <div class="cal-amount">${fmtd(t.monto)}</div>
      </div>`;
    });
    html+='</div>';
    div.innerHTML=html;
    container.appendChild(div);
  });
}

// ============================================================
// CHARTS
// ============================================================
let charts={};
function destroyCharts(){Object.values(charts).forEach(c=>{try{c.destroy();}catch(e){}});charts={};}
const COLORS=['#3b82f6','#22c55e','#a855f7','#f97316','#06b6d4','#eab308','#ef4444','#ec4899'];

function buildCharts(){
  destroyCharts();
  // Obligaciones por empresa
  const oblEmp={};
  oblData.forEach(o=>{oblEmp[o.empresa]=(oblEmp[o.empresa]||0)+o.total;});
  charts.oblEmp=new Chart(document.getElementById('c-obl-emp'),{
    type:'doughnut',
    data:{labels:Object.keys(oblEmp),datasets:[{data:Object.values(oblEmp),backgroundColor:COLORS,borderWidth:0}]},
    options:{plugins:{legend:{labels:{color:'#94a3b8',font:{size:11}}}},cutout:'60%'}
  });
  // Importaciones por empresa
  const impEmp={JCEVCORP:0,CONSUREP:0,TODOMOTO:0,CREDIMPORT:0,ASSEMBLY:0};
  jcevData.forEach(r=>{impEmp[r.empresa]=(impEmp[r.empresa]||0)+r.valor;});
  credData.forEach(r=>{impEmp.CREDIMPORT+=r.valor;});
  asmData.forEach(r=>{impEmp.ASSEMBLY+=r.valor;});
  charts.impEmp=new Chart(document.getElementById('c-imp-emp'),{
    type:'bar',
    data:{
      labels:Object.keys(impEmp),
      datasets:[{label:'A Pagar ($)',data:Object.values(impEmp),backgroundColor:COLORS,borderRadius:5}]
    },
    options:{plugins:{legend:{display:false}},scales:{y:{ticks:{color:'#64748b',callback:v=>'$'+v.toLocaleString()},grid:{color:'#1e2d4a'}},x:{ticks:{color:'#94a3b8'},grid:{display:false}}}}
  });
  // SRI
  charts.sri=new Chart(document.getElementById('c-sri'),{
    type:'bar',
    data:{
      labels:sriData.map(r=>r.empresa),
      datasets:[
        {label:'Nota Crédito',data:sriData.map(r=>r.nc),backgroundColor:'#22c55e88',borderRadius:4},
        {label:'Débito',data:sriData.map(r=>r.debito),backgroundColor:'#ef444488',borderRadius:4}
      ]
    },
    options:{plugins:{legend:{labels:{color:'#94a3b8',font:{size:10}}}},scales:{y:{ticks:{color:'#64748b',callback:v=>'$'+v.toLocaleString()},grid:{color:'#1e2d4a'}},x:{ticks:{color:'#94a3b8'},grid:{display:false}}}}
  });
  // Nómina
  const nomEmp={};
  nominaData.forEach(r=>{nomEmp[r.empresa]=(nomEmp[r.empresa]||0)+r.monto;});
  charts.nom=new Chart(document.getElementById('c-nom'),{
    type:'bar',
    data:{
      labels:Object.keys(nomEmp),
      datasets:[{label:'Nómina ($)',data:Object.values(nomEmp),backgroundColor:'#a855f788',borderRadius:4}]
    },
    options:{plugins:{legend:{display:false}},scales:{y:{ticks:{color:'#64748b',callback:v=>'$'+v.toLocaleString()},grid:{color:'#1e2d4a'}},x:{ticks:{color:'#94a3b8',font:{size:10}},grid:{display:false}}}}
  });
}

// ============================================================
// EXCEL UPLOAD
// ============================================================
function handleExcel(input){
  const f=input.files[0];if(!f)return;
  showToast('✓ Archivo recibido: '+f.name+' · Los datos del dashboard son del Excel analizado.',true);
  input.value='';
}

// ============================================================
// INIT
// ============================================================
function init(){
  buildAllTx();
  renderObl();
  renderAmort();
  renderJcev();
  renderCred();
  renderAsm();
  renderSri();
  renderProv();
  renderImp();
  renderVenc();
  buildCharts();
  renderCal();
}
window.addEventListener('DOMContentLoaded',init);
</script>
</body>
</html>
