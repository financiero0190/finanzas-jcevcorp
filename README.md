[index.html](https://github.com/user-attachments/files/28604392/index.html)
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>JCEVCORP · Control Financiero 2026</title>
<link href="https://fonts.googleapis.com/css2?family=DM+Mono:wght@300;400;500&family=Syne:wght@400;600;700;800&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>
<style>
:root{
  --bg:#0a0c0f;--bg2:#0f1218;--bg3:#151a22;--bg4:#1c232e;
  --border:rgba(255,255,255,0.07);--border2:rgba(255,255,255,0.13);
  --text:#e8eaf0;--text2:#8a93a8;--text3:#4a5568;
  --accent:#4f9eff;--accent2:#7b5ea7;
  --green:#34d399;--red:#f87171;--yellow:#fbbf24;--orange:#fb923c;
  --jcev:#6366f1;--assm:#10b981;--full:#f59e0b;--cred:#06b6d4;--cons:#a78bfa;--mont:#f472b6;--todo:#22d3ee;
  --radius:12px;--radius-sm:8px;
}
*{box-sizing:border-box;margin:0;padding:0}
html,body{height:100%;background:var(--bg);color:var(--text);font-family:'DM Sans',sans-serif;font-size:14px;overflow:hidden}
.shell{display:flex;height:100vh;overflow:hidden}
.sidebar{width:220px;min-width:220px;background:var(--bg2);border-right:1px solid var(--border);display:flex;flex-direction:column;z-index:10}
.main{flex:1;display:flex;flex-direction:column;overflow:hidden}
.topbar{height:56px;min-height:56px;background:var(--bg2);border-bottom:1px solid var(--border);display:flex;align-items:center;padding:0 24px;gap:16px;justify-content:space-between}
.content{flex:1;overflow-y:auto;padding:24px;scroll-behavior:smooth}
.sb-logo{padding:18px 18px 14px;border-bottom:1px solid var(--border)}
.sb-logo-mark{font-family:'Syne',sans-serif;font-weight:800;font-size:16px;color:#fff;letter-spacing:-.5px}
.sb-logo-sub{font-size:10px;color:var(--text3);margin-top:2px;font-family:'DM Mono',monospace;letter-spacing:.5px}
.sb-nav{padding:10px 8px;flex:1;overflow-y:auto}
.sb-sec{font-size:9px;font-family:'DM Mono',monospace;letter-spacing:1.5px;color:var(--text3);padding:10px 8px 4px;text-transform:uppercase}
.nav-item{display:flex;align-items:center;gap:9px;padding:8px 10px;border-radius:var(--radius-sm);cursor:pointer;color:var(--text2);font-size:12.5px;transition:all .2s;margin-bottom:2px;border:none;background:none;width:100%;text-align:left}
.nav-item svg{width:14px;height:14px;flex-shrink:0;opacity:.7}
.nav-item:hover{background:var(--bg3);color:var(--text)}
.nav-item.active{background:linear-gradient(135deg,rgba(79,158,255,.15),rgba(123,94,167,.1));color:#fff;font-weight:500}
.nav-item.active svg{opacity:1}
.nav-item .dot{width:6px;height:6px;border-radius:50%;background:var(--red);margin-left:auto;animation:pulse 2s infinite}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.4}}
.sb-bottom{padding:12px 14px;border-top:1px solid var(--border)}
.sb-date{font-family:'DM Mono',monospace;font-size:10px;color:var(--text3);text-align:center}
.tb-title{font-family:'Syne',sans-serif;font-weight:600;font-size:15px}
.tb-right{display:flex;align-items:center;gap:10px}
.tb-badge{font-size:11px;padding:4px 10px;border-radius:20px;font-family:'DM Mono',monospace;border:1px solid}
.tb-red{background:rgba(248,113,113,.15);color:var(--red);border-color:rgba(248,113,113,.25)}
.tb-yellow{background:rgba(251,191,36,.1);color:var(--yellow);border-color:rgba(251,191,36,.2)}
.btn-refresh{display:flex;align-items:center;gap:7px;background:linear-gradient(135deg,rgba(79,158,255,.18),rgba(123,94,167,.12));border:1px solid rgba(79,158,255,.3);color:var(--accent);font-size:11.5px;padding:7px 15px;border-radius:var(--radius-sm);cursor:pointer;font-family:'DM Mono',monospace;letter-spacing:.3px;transition:all .2s;white-space:nowrap}
.btn-refresh:hover{background:linear-gradient(135deg,rgba(79,158,255,.3),rgba(123,94,167,.22));border-color:rgba(79,158,255,.5)}
.btn-refresh svg{transition:transform .8s}
.btn-refresh.spin svg{animation:rot .8s linear}
@keyframes rot{to{transform:rotate(360deg)}}
.section{display:none;animation:fadeIn .25s ease}
.section.active{display:block}
@keyframes fadeIn{from{opacity:0;transform:translateY(5px)}to{opacity:1;transform:translateY(0)}}
.kpi-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(150px,1fr));gap:12px;margin-bottom:18px}
.kpi{background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius);padding:15px 17px;position:relative;overflow:hidden;transition:border-color .2s}
.kpi:hover{border-color:var(--border2)}
.kpi::before{content:'';position:absolute;top:0;left:0;right:0;height:2px}
.kpi.red::before{background:linear-gradient(90deg,var(--red),transparent)}
.kpi.yellow::before{background:linear-gradient(90deg,var(--yellow),transparent)}
.kpi.green::before{background:linear-gradient(90deg,var(--green),transparent)}
.kpi.blue::before{background:linear-gradient(90deg,var(--accent),transparent)}
.kpi.purple::before{background:linear-gradient(90deg,var(--accent2),transparent)}
.kpi.cyan::before{background:linear-gradient(90deg,var(--cred),transparent)}
.kpi.orange::before{background:linear-gradient(90deg,var(--orange),transparent)}
.kpi-label{font-size:10px;color:var(--text3);font-family:'DM Mono',monospace;letter-spacing:.5px;text-transform:uppercase;margin-bottom:7px}
.kpi-value{font-family:'Syne',sans-serif;font-size:22px;font-weight:700;line-height:1;letter-spacing:-1px}
.kpi-sub{font-size:11px;color:var(--text2);margin-top:4px}
.card{background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius);padding:18px;margin-bottom:14px}
.card-title{font-family:'Syne',sans-serif;font-size:11.5px;font-weight:600;letter-spacing:.4px;margin-bottom:12px;color:var(--text2);text-transform:uppercase}
.grid2{display:grid;grid-template-columns:1fr 1fr;gap:14px;margin-bottom:14px}
@media(max-width:900px){.grid2{grid-template-columns:1fr}}
.alert{display:flex;gap:10px;align-items:flex-start;padding:10px 13px;border-radius:var(--radius-sm);margin-bottom:7px;font-size:12px;line-height:1.5;border:1px solid}
.al-red{background:rgba(248,113,113,.07);border-color:rgba(248,113,113,.2);color:#fca5a5}
.al-yellow{background:rgba(251,191,36,.07);border-color:rgba(251,191,36,.2);color:#fde68a}
.al-green{background:rgba(52,211,153,.07);border-color:rgba(52,211,153,.2);color:#6ee7b7}
.al-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0;margin-top:4px}
.al-red .al-dot{background:var(--red)}.al-yellow .al-dot{background:var(--yellow)}.al-green .al-dot{background:var(--green)}
.tw{overflow-x:auto;border-radius:var(--radius-sm);border:1px solid var(--border)}
table{width:100%;border-collapse:collapse;font-size:12px}
th{text-align:left;padding:8px 12px;font-family:'DM Mono',monospace;font-size:9.5px;letter-spacing:.8px;text-transform:uppercase;color:var(--text3);border-bottom:1px solid var(--border);background:var(--bg3);white-space:nowrap}
td{padding:8px 12px;border-bottom:1px solid rgba(255,255,255,.035);white-space:nowrap;max-width:220px;overflow:hidden;text-overflow:ellipsis}
tr:last-child td{border-bottom:none}
tr:hover td{background:rgba(255,255,255,.02)}
.tag{display:inline-block;padding:2px 7px;border-radius:5px;font-size:10px;font-weight:600;font-family:'DM Mono',monospace;letter-spacing:.3px}
.tj{background:rgba(99,102,241,.2);color:#a5b4fc;border:1px solid rgba(99,102,241,.3)}
.ta{background:rgba(16,185,129,.15);color:#6ee7b7;border:1px solid rgba(16,185,129,.25)}
.tf{background:rgba(245,158,11,.15);color:#fde68a;border:1px solid rgba(245,158,11,.25)}
.tc{background:rgba(6,182,212,.15);color:#67e8f9;border:1px solid rgba(6,182,212,.25)}
.tcs{background:rgba(167,139,250,.15);color:#c4b5fd;border:1px solid rgba(167,139,250,.25)}
.tm{background:rgba(244,114,182,.15);color:#f9a8d4;border:1px solid rgba(244,114,182,.25)}
.tto{background:rgba(34,211,238,.15);color:#67e8f9;border:1px solid rgba(34,211,238,.25)}
.pill{display:inline-block;padding:2px 8px;border-radius:20px;font-size:10px;font-weight:500;font-family:'DM Mono',monospace;border:1px solid}
.pr{background:rgba(248,113,113,.15);color:#fca5a5;border-color:rgba(248,113,113,.25)}
.py{background:rgba(251,191,36,.12);color:#fde68a;border-color:rgba(251,191,36,.2)}
.pg{background:rgba(52,211,153,.12);color:#6ee7b7;border-color:rgba(52,211,153,.2)}
.pgr{background:rgba(255,255,255,.06);color:var(--text3);border-color:var(--border)}
.pb{background:rgba(79,158,255,.12);color:#93c5fd;border-color:rgba(79,158,255,.2)}
.filters{display:flex;gap:8px;flex-wrap:wrap;margin-bottom:12px;align-items:center}
.filters select{background:var(--bg3);border:1px solid var(--border);color:var(--text);font-size:12px;padding:5px 10px;border-radius:var(--radius-sm);font-family:'DM Sans',sans-serif;height:31px;outline:none;transition:border-color .2s}
.filters select:focus{border-color:var(--accent)}
.fl{font-size:11px;color:var(--text3);font-family:'DM Mono',monospace}
.amort-card{background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius);margin-bottom:10px;overflow:hidden;transition:border-color .2s}
.amort-card:hover{border-color:var(--border2)}
.amort-hdr{display:flex;justify-content:space-between;align-items:center;padding:13px 16px;cursor:pointer;user-select:none}
.amort-hdr:hover{background:rgba(255,255,255,.02)}
.amort-body{display:none;border-top:1px solid var(--border)}
.amort-body.open{display:block}
.prog-wrap{height:3px;background:var(--bg4);margin:0 16px 12px}
.prog-fill{height:100%;border-radius:2px;transition:width .6s ease}
.chev{transition:transform .3s;color:var(--text3)}
.chev.open{transform:rotate(180deg)}
.tabs{display:flex;gap:3px;margin-bottom:14px;background:var(--bg3);padding:3px;border-radius:var(--radius-sm);width:fit-content;border:1px solid var(--border)}
.tab-btn{padding:6px 14px;border-radius:5px;border:none;background:none;color:var(--text2);font-size:12px;font-family:'DM Sans',sans-serif;cursor:pointer;transition:all .2s}
.tab-btn.active{background:var(--bg2);color:var(--text);font-weight:500;box-shadow:0 1px 3px rgba(0,0,0,.3)}
.sec-hdr{display:flex;justify-content:space-between;align-items:flex-end;margin-bottom:16px}
.sec-title{font-family:'Syne',sans-serif;font-size:18px;font-weight:700;letter-spacing:-.5px}
.sec-sub{font-size:11px;color:var(--text3);font-family:'DM Mono',monospace;margin-top:2px}
.tot-row{display:flex;gap:14px;padding:9px 12px;background:var(--bg3);border-radius:var(--radius-sm);font-family:'DM Mono',monospace;font-size:11px;color:var(--text2);margin-top:7px;flex-wrap:wrap}
.tot-row strong{color:var(--text)}
.chart-box{position:relative;height:190px;width:100%}
.leg{display:flex;flex-wrap:wrap;gap:8px;margin-top:9px}
.leg-item{display:flex;align-items:center;gap:5px;font-size:11px;color:var(--text2);font-family:'DM Mono',monospace}
.leg-dot{width:7px;height:7px;border-radius:50%;flex-shrink:0}
.gar-grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));gap:11px}
.gar-card{background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius);padding:13px 15px;transition:all .2s;position:relative;overflow:hidden}
.gar-card:hover{border-color:var(--border2);transform:translateY(-1px)}
.gar-card::after{content:'';position:absolute;bottom:0;left:0;right:0;height:2px}
.gar-r::after{background:var(--red)}.gar-y::after{background:var(--yellow)}.gar-g::after{background:var(--green)}.gar-gr::after{background:var(--bg4)}
.cal-row{display:flex;align-items:stretch;margin-bottom:5px;background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius-sm);overflow:hidden;transition:border-color .2s}
.cal-row:hover{border-color:var(--border2)}
.ub{width:3px;align-self:stretch;flex-shrink:0}
.ub-r{background:var(--red)}.ub-y{background:var(--yellow)}.ub-g{background:var(--green)}.ub-b{background:var(--accent)}.ub-gr{background:var(--bg4)}
.cal-date{min-width:56px;background:var(--bg3);padding:9px 7px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:1px;border-right:1px solid var(--border)}
.cal-d{font-family:'Syne',sans-serif;font-size:17px;font-weight:700;line-height:1}
.cal-wd{font-size:8px;font-family:'DM Mono',monospace;color:var(--text3);letter-spacing:.5px;text-transform:uppercase}
.cal-body{flex:1;padding:9px 11px;display:flex;align-items:center;gap:9px;flex-wrap:wrap}
.cal-amt{padding:9px 12px;display:flex;flex-direction:column;align-items:flex-end;justify-content:center;gap:1px}
.cal-amt-v{font-family:'Syne',sans-serif;font-size:13px;font-weight:700;color:#fff;white-space:nowrap}
.cal-month-hdr{display:flex;justify-content:space-between;align-items:center;margin-bottom:9px;padding-bottom:9px;border-bottom:1px solid var(--border)}
.cal-month-name{font-family:'Syne',sans-serif;font-size:14px;font-weight:600}
.cal-month-total{font-family:'DM Mono',monospace;font-size:12px;color:var(--accent)}
.cal-month{margin-bottom:18px}
.ai-wrap{background:var(--bg2);border:1px solid var(--border);border-radius:var(--radius);overflow:hidden}
.ai-hdr{padding:13px 17px;border-bottom:1px solid var(--border);display:flex;align-items:center;gap:9px}
.ai-live{width:8px;height:8px;border-radius:50%;background:var(--green);animation:pulse 2s infinite}
.ai-body{padding:16px}
.ai-iw{display:flex;gap:9px;margin-bottom:12px}
.ai-input{flex:1;background:var(--bg3);border:1px solid var(--border);color:var(--text);font-size:13px;padding:9px 13px;border-radius:var(--radius-sm);font-family:'DM Sans',sans-serif;outline:none;transition:border-color .2s}
.ai-input:focus{border-color:var(--accent)}
.ai-send{background:linear-gradient(135deg,var(--accent),var(--accent2));color:#fff;border:none;padding:9px 17px;border-radius:var(--radius-sm);font-size:13px;cursor:pointer;white-space:nowrap;font-family:'DM Sans',sans-serif}
.ai-resp{min-height:65px;font-size:13px;line-height:1.7;color:var(--text2);background:var(--bg3);border-radius:var(--radius-sm);padding:11px 13px}
.ai-quick{display:flex;flex-wrap:wrap;gap:6px;margin-top:9px}
.ai-qb{background:var(--bg3);border:1px solid var(--border);color:var(--text2);font-size:11px;padding:5px 11px;border-radius:20px;cursor:pointer;transition:all .2s;font-family:'DM Sans',sans-serif}
.ai-qb:hover{border-color:var(--accent);color:var(--accent)}
.ld{display:inline-flex;gap:4px;align-items:center}
.ld span{width:5px;height:5px;border-radius:50%;background:var(--accent);animation:bl 1.2s infinite}
.ld span:nth-child(2){animation-delay:.2s}.ld span:nth-child(3){animation-delay:.4s}
@keyframes bl{0%,80%,100%{opacity:.2}40%{opacity:1}}
::-webkit-scrollbar{width:4px;height:4px}::-webkit-scrollbar-track{background:transparent}::-webkit-scrollbar-thumb{background:var(--bg4);border-radius:2px}
</style>
</head>
<body>
<div class="shell">
<aside class="sidebar">
  <div class="sb-logo">
    <div class="sb-logo-mark">JCEVCORP</div>
    <div class="sb-logo-sub">CONTROL FINANCIERO 2026</div>
  </div>
  <nav class="sb-nav">
    <div class="sb-sec">Principal</div>
    <button class="nav-item active" onclick="nav('resumen')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="3" y="3" width="7" height="7" rx="1"/><rect x="14" y="3" width="7" height="7" rx="1"/><rect x="3" y="14" width="7" height="7" rx="1"/><rect x="14" y="14" width="7" height="7" rx="1"/></svg>
      Resumen <span class="dot" id="dot-alert"></span>
    </button>
    <button class="nav-item" onclick="nav('obligaciones')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M9 12h6M9 16h6M17 21H7a2 2 0 01-2-2V5a2 2 0 012-2h7l5 5v11a2 2 0 01-2 2z"/></svg>
      Obligaciones
    </button>
    <button class="nav-item" onclick="nav('amortizacion')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><polyline points="22 12 18 12 15 21 9 3 6 12 2 12"/></svg>
      Amortización TA
    </button>
    <button class="nav-item" onclick="nav('garantias')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
      Garantías
    </button>
    <div class="sb-sec">Flujos</div>
    <button class="nav-item" onclick="nav('flujos')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><path d="M12 2L2 7l10 5 10-5-10-5zM2 17l10 5 10-5M2 12l10 5 10-5"/></svg>
      Flujos Importación
    </button>
    <div class="sb-sec">Compromisos</div>
    <button class="nav-item" onclick="nav('sri')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="2" y="5" width="20" height="14" rx="2"/><line x1="2" y1="10" x2="22" y2="10"/></svg>
      SRI &amp; Nómina
    </button>
    <button class="nav-item" onclick="nav('proveedores')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><circle cx="9" cy="21" r="1"/><circle cx="20" cy="21" r="1"/><path d="M1 1h4l2.68 13.39a2 2 0 002 1.61h9.72a2 2 0 001.95-1.57l1.65-7.43H6"/></svg>
      Proveedores Nac.
    </button>
    <div class="sb-sec">Control</div>
    <button class="nav-item" onclick="nav('calendario')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><rect x="3" y="4" width="18" height="18" rx="2"/><line x1="16" y1="2" x2="16" y2="6"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="3" y1="10" x2="21" y2="10"/></svg>
      Calendario
    </button>
    <button class="nav-item" onclick="nav('ia')">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.8"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
      Asistente IA
    </button>
  </nav>
  <div class="sb-bottom"><div class="sb-date" id="sb-today"></div></div>
</aside>

<div class="main">
  <div class="topbar">
    <span class="tb-title" id="tb-title">Panel Ejecutivo</span>
    <div class="tb-right">
      <span class="tb-badge tb-yellow" id="tb-warn"></span>
      <span class="tb-badge tb-red" id="tb-urgent" style="display:none"></span>
      <button class="btn-refresh" id="btn-ref" onclick="refreshAll()">
        <svg width="13" height="13" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.2"><path d="M23 4v6h-6"/><path d="M1 20v-6h6"/><path d="M3.51 9a9 9 0 0114.85-3.36L23 10M1 14l4.64 4.36A9 9 0 0020.49 15"/></svg>
        ACTUALIZAR
      </button>
    </div>
  </div>

  <div class="content">

  <!-- RESUMEN -->
  <div id="sec-resumen" class="section active">
    <div class="kpi-grid" id="kpi-res"></div>
    <div id="alertas-div" style="margin-bottom:14px"></div>
    <div class="grid2">
      <div class="card"><div class="card-title">Capital por empresa</div><div class="chart-box"><canvas id="ch-emp"></canvas></div><div class="leg" id="leg-emp"></div></div>
      <div class="card"><div class="card-title">Vencimientos mensuales — Capital</div><div class="chart-box"><canvas id="ch-mes"></canvas></div></div>
    </div>
    <div class="card"><div class="card-title">Distribución por banco</div><div class="chart-box" style="height:155px"><canvas id="ch-ban"></canvas></div></div>
  </div>

  <!-- OBLIGACIONES -->
  <div id="sec-obligaciones" class="section">
    <div class="sec-hdr"><div><div class="sec-title">Obligaciones Financieras</div><div class="sec-sub">Hoja 1 · 20 operaciones activas</div></div></div>
    <div class="filters">
      <span class="fl">Empresa</span>
      <select id="fE" onchange="renderObl()"><option value="">Todas</option><option>JCEVCORP</option><option>ASSEMBLY</option><option>FULLMOTOS</option></select>
      <span class="fl">Banco</span>
      <select id="fB" onchange="renderObl()"><option value="">Todos</option><option>PRODUBANCO</option><option>PICHINCHA PANAMA</option><option>EBNA BANK</option><option>ST GEORGES</option><option>BOLIVARIANO</option><option>PAPEL COMERCIAL</option></select>
      <span class="fl">Tipo</span>
      <select id="fT" onchange="renderObl()"><option value="">Todos</option><option value="TA">TA mensual</option><option value="UNICO">Pago único</option></select>
    </div>
    <div class="tw"><table><thead><tr><th>Empresa</th><th>Banco</th><th>Capital</th><th>Interés</th><th>Total</th><th>Tasa</th><th>Vencimiento</th><th>Días</th><th>Tipo</th></tr></thead><tbody id="tb-obl"></tbody></table></div>
    <div class="tot-row" id="tot-obl"></div>
  </div>

  <!-- AMORTIZACION -->
  <div id="sec-amortizacion" class="section">
    <div class="sec-hdr"><div><div class="sec-title">Tablas de Amortización</div><div class="sec-sub">4 créditos PRODUBANCO · Haga click para expandir</div></div></div>
    <div id="ta-container"></div>
  </div>

  <!-- GARANTIAS -->
  <div id="sec-garantias" class="section">
    <div class="sec-hdr"><div><div class="sec-title">Garantías Bancarias</div><div class="sec-sub">14 garantías vigentes</div></div></div>
    <div class="kpi-grid" style="margin-bottom:16px">
      <div class="kpi green"><div class="kpi-label">Total garantías</div><div class="kpi-value" style="color:var(--green)">14</div><div class="kpi-sub">todas vigentes</div></div>
      <div class="kpi blue"><div class="kpi-label">Valor total</div><div class="kpi-value" style="font-size:18px">$13.26M</div></div>
      <div class="kpi red"><div class="kpi-label">Vencen ≤ 90d</div><div class="kpi-value" id="gar-90" style="color:var(--red)">—</div><div class="kpi-sub">renovar urgente</div></div>
      <div class="kpi yellow"><div class="kpi-label">Vencen 2026</div><div class="kpi-value" style="color:var(--yellow)">3</div><div class="kpi-sub">Produbanco · dic 2026</div></div>
    </div>
    <div class="gar-grid" id="gar-grid"></div>
  </div>

  <!-- FLUJOS -->
  <div id="sec-flujos" class="section">
    <div class="sec-hdr"><div><div class="sec-title">Flujos de Importación</div><div class="sec-sub">EMPRESA · PROVEEDOR · IMPORTACIÓN · VALOR · VENCIMIENTO</div></div></div>
    <div class="tabs">
      <button class="tab-btn active" onclick="showFlujo('cs',this)">JCEV / CONSUREP</button>
      <button class="tab-btn" onclick="showFlujo('cr',this)">CREDIMPORT</button>
      <button class="tab-btn" onclick="showFlujo('as',this)">ASSEMBLY</button>
    </div>
    <div id="flujo-panel"></div>
  </div>

  <!-- SRI & NOMINA -->
  <div id="sec-sri" class="section">
    <div class="sec-hdr"><div><div class="sec-title">SRI &amp; Nómina</div><div class="sec-sub">Obligaciones tributarias y pago de personal · Junio 2026</div></div></div>
    <div class="kpi-grid" id="kpi-sri"></div>
    <div class="grid2">
      <div class="card">
        <div class="card-title">📋 Obligaciones SRI</div>
        <div class="tw"><table><thead><tr><th>Empresa</th><th>Valor SRI</th><th>Fecha Pago</th><th>Estado</th></tr></thead><tbody id="tb-sri"></tbody></table></div>
        <div class="tot-row" id="tot-sri"></div>
      </div>
      <div class="card">
        <div class="card-title">👥 Nómina</div>
        <div class="tw"><table><thead><tr><th>Empresa</th><th>Valor Nómina</th><th>Fecha Pago</th><th>Estado</th></tr></thead><tbody id="tb-nom"></tbody></table></div>
        <div class="tot-row" id="tot-nom"></div>
      </div>
    </div>
  </div>

  <!-- PROVEEDORES -->
  <div id="sec-proveedores" class="section">
    <div class="sec-hdr"><div><div class="sec-title">Proveedores Nacionales</div><div class="sec-sub">Resumen de pagos · Junio 2026</div></div></div>
    <div class="kpi-grid" id="kpi-prov"></div>
    <div class="tw"><table><thead><tr><th>Empresa</th><th>Monto</th><th>Fecha Pago</th><th>Estado</th></tr></thead><tbody id="tb-prov"></tbody></table></div>
    <div class="tot-row" id="tot-prov"></div>
  </div>

  <!-- CALENDARIO -->
  <div id="sec-calendario" class="section">
    <div class="sec-hdr"><div><div class="sec-title">Calendario Consolidado</div><div class="sec-sub">Todas las obligaciones por día · Financiero · TA · Importaciones · SRI · Nómina · Proveedores</div></div></div>
    <div class="filters">
      <span class="fl">Tipo</span>
      <select id="fCalT" onchange="renderCal()"><option value="">Todo</option><option value="FIN">Financiero + TA</option><option value="TA">Solo Cuota TA</option><option value="IMP">Importación</option><option value="SRI">SRI</option><option value="NOM">Nómina</option><option value="PROV">Proveedores</option></select>
      <span class="fl">Empresa</span>
      <select id="fCalE" onchange="renderCal()"><option value="">Todas</option></select>
    </div>
    <div id="cal-div"></div>
  </div>

  <!-- IA -->
  <div id="sec-ia" class="section">
    <div class="sec-hdr"><div><div class="sec-title">Asistente Financiero IA</div><div class="sec-sub">Consulta en lenguaje natural sobre el portafolio del Grupo JCEVCORP</div></div></div>
    <div class="ai-wrap">
      <div class="ai-hdr"><div class="ai-live"></div><span style="font-family:'Syne',sans-serif;font-weight:600;font-size:14px">Analista JCEVCORP · Claude Sonnet</span></div>
      <div class="ai-body">
        <div class="ai-iw">
          <input class="ai-input" id="ai-in" type="text" placeholder="Ej: ¿Cuánto debo pagar en junio sumando todas las obligaciones?" onkeydown="if(event.key==='Enter')askAI()"/>
          <button class="ai-send" onclick="askAI()">Consultar →</button>
        </div>
        <div class="ai-resp" id="ai-resp"><span style="color:var(--text3);font-family:'DM Mono',monospace;font-size:12px">El asistente analizará el portafolio completo y responderá...</span></div>
        <div class="ai-quick">
          <button class="ai-qb" onclick="qk('¿Cuánto debo pagar en total en junio sumando obligaciones, flujos, SRI y nómina?')">Total junio</button>
          <button class="ai-qb" onclick="qk('¿Qué obligaciones financieras vencen en los próximos 30 días?')">Urgentes 30d</button>
          <button class="ai-qb" onclick="qk('¿Cuál es el capital total pendiente por empresa?')">Deuda por empresa</button>
          <button class="ai-qb" onclick="qk('¿Cuáles son las importaciones más grandes de ASSEMBLY?')">Flujo ASSEMBLY</button>
          <button class="ai-qb" onclick="qk('Dame un resumen ejecutivo del estado financiero del grupo')">Resumen ejecutivo</button>
        </div>
      </div>
    </div>
  </div>

  </div>
</div>
</div>

<script>
// ════════════════════════════════════════════════════════
// DATOS — actualiza y presiona ACTUALIZAR
// ════════════════════════════════════════════════════════
function d(s){const[y,m,dd]=s.split('-').map(Number);return new Date(y,m-1,dd);}

// ─ OBLIGACIONES ─
const oblRaw=[
  {emp:'JCEVCORP', ban:'PRODUBANCO',       vd:d('2026-04-22'),cap:1000000,   int:34044.31, tot:1034044.31,tasa:.06,  tipo:'TA'},
  {emp:'ASSEMBLY', ban:'PICHINCHA PANAMA', vd:d('2026-06-11'),cap:490000,    int:15680,    tot:505680,    tasa:.06,  tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'PICHINCHA PANAMA', vd:d('2026-06-22'),cap:478000,    int:8205.67,  tot:486205.67, tasa:.06,  tipo:'UNICO'},
  {emp:'ASSEMBLY', ban:'EBNA BANK',        vd:d('2026-06-22'),cap:180000,    int:5320,     tot:185320,    tasa:.056, tipo:'UNICO'},
  {emp:'ASSEMBLY', ban:'PICHINCHA PANAMA', vd:d('2026-06-24'),cap:387500,    int:6781.25,  tot:394281.25, tasa:.06,  tipo:'UNICO'},
  {emp:'ASSEMBLY', ban:'EBNA BANK',        vd:d('2026-06-29'),cap:314605,    int:9787.73,  tot:324392.73, tasa:.07,  tipo:'UNICO'},
  {emp:'ASSEMBLY', ban:'EBNA BANK',        vd:d('2026-07-01'),cap:556000,    int:18487,    tot:574487,    tasa:.057, tipo:'UNICO'},
  {emp:'ASSEMBLY', ban:'EBNA BANK',        vd:d('2026-07-08'),cap:358494.29, int:10595,    tot:369089.29, tasa:.056, tipo:'UNICO'},
  {emp:'ASSEMBLY', ban:'PICHINCHA PANAMA', vd:d('2026-08-20'),cap:87500,     int:1341.67,  tot:88841.67,  tasa:.06,  tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'ST GEORGES',       vd:d('2026-09-28'),cap:700000,    int:55304.86, tot:755304.86, tasa:.0775,tipo:'UNICO'},
  {emp:'ASSEMBLY', ban:'EBNA BANK',        vd:d('2026-09-30'),cap:180000,    int:5320,     tot:185320,    tasa:.056, tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'BOLIVARIANO',      vd:d('2026-10-05'),cap:521636.28, int:15865.8,  tot:537502.08, tasa:.06,  tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'EBNA BANK',        vd:d('2026-11-05'),cap:200000,    int:20000,    tot:220000,    tasa:.056, tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'PAPEL COMERCIAL',  vd:d('2027-01-11'),cap:750000,    int:41250,    tot:791250,    tasa:.055, tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'PAPEL COMERCIAL',  vd:d('2027-01-19'),cap:500000,    int:27500,    tot:527500,    tasa:.055, tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'PAPEL COMERCIAL',  vd:d('2027-01-21'),cap:750000,    int:41250,    tot:791250,    tasa:.055, tipo:'UNICO'},
  {emp:'JCEVCORP', ban:'PAPEL COMERCIAL',  vd:d('2027-01-25'),cap:2000000,   int:110000,   tot:2110000,   tasa:.055, tipo:'UNICO'},
  {emp:'FULLMOTOS',ban:'PRODUBANCO',        vd:d('2027-05-10'),cap:500000,    int:17644.02, tot:517644.02, tasa:.0625,tipo:'TA'},
  {emp:'ASSEMBLY', ban:'PRODUBANCO',        vd:d('2027-06-05'),cap:100000,    int:3496.05,  tot:103496.05, tasa:.0625,tipo:'TA'},
  {emp:'JCEVCORP', ban:'PRODUBANCO',        vd:d('2027-06-03'),cap:1000000,   int:33734.39, tot:1033734.39,tasa:.06,  tipo:'TA'},
];

// ─ TABLAS DE AMORTIZACIÓN ─
const taData=[
  {id:'ta0',emp:'JCEVCORP',ban:'PRODUBANCO',capital:1000000,tasa:.06,cuotaLabel:'$86,170/mes',vcto:'2027-04-22',
   color:'var(--jcev)',grad:'linear-gradient(90deg,var(--jcev),var(--accent))',
   cuotas:[
    {vd:d('2026-05-22'),cap:81216.19,int:4954.17,cuota:86170.36,est:'CANCELADO'},
    {vd:d('2026-06-22'),cap:81304.63,int:4865.73,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2026-07-22'),cap:81878.28,int:4292.08,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2026-08-22'),cap:81910.66,int:4259.70,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2026-09-22'),cap:82832.79,int:3337.57,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2026-10-22'),cap:83142.22,int:3028.14,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2026-11-22'),cap:83394.85,int:2775.51,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2026-12-22'),cap:84068.21,int:2102.15,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2027-01-22'),cap:84368.44,int:1801.92,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2027-02-22'),cap:84815.24,int:1355.12,cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2027-03-22'),cap:85352.08,int:818.28, cuota:86170.36,est:'PENDIENTE'},
    {vd:d('2027-04-22'),cap:85716.41,int:453.94, cuota:86170.35,est:'PENDIENTE'},
   ]},
  {id:'ta1',emp:'FULLMOTOS',ban:'PRODUBANCO',capital:500000,tasa:.0625,cuotaLabel:'$43,137/mes',vcto:'2027-05-10',
   color:'var(--full)',grad:'linear-gradient(90deg,var(--full),#f97316)',
   cuotas:[
    {vd:d('2026-06-08'),cap:40272.42,int:2864.58,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2026-07-06'),cap:40742.59,int:2394.41,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2026-08-11'),cap:40663.82,int:2473.18,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2026-09-08'),cap:41297.94,int:1839.06,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2026-10-08'),cap:41381.67,int:1755.33,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2026-11-09'),cap:41494.55,int:1642.45,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2026-12-08'),cap:41857.44,int:1279.56,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2027-01-08'),cap:41994.47,int:1142.53,cuota:43137,  est:'PENDIENTE'},
    {vd:d('2027-02-10'),cap:42161.35,int:975.65, cuota:43137,  est:'PENDIENTE'},
    {vd:d('2027-03-08'),cap:42558.62,int:578.38, cuota:43137,  est:'PENDIENTE'},
    {vd:d('2027-04-08'),cap:42676.44,int:460.56, cuota:43137,  est:'PENDIENTE'},
    {vd:d('2027-05-10'),cap:42898.69,int:238.33, cuota:43137.02,est:'PENDIENTE'},
   ]},
  {id:'ta2',emp:'ASSEMBLY',ban:'PRODUBANCO',capital:100000,tasa:.0625,cuotaLabel:'$8,625/mes',vcto:'2027-06-05',
   color:'var(--assm)',grad:'linear-gradient(90deg,var(--assm),#34d399)',
   cuotas:[
    {vd:d('2026-06-08'),cap:8051.75,int:572.92,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2026-07-06'),cap:8177.70,int:446.97,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2026-08-06'),cap:8173.82,int:450.85,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2026-09-07'),cap:8204.69,int:419.98,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2026-10-06'),cap:8285.37,int:339.30,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2026-11-06'),cap:8306.56,int:318.11,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2026-12-07'),cap:8351.27,int:273.40,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2027-01-06'),cap:8403.58,int:221.09,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2027-02-10'),cap:8417.80,int:206.87,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2027-03-08'),cap:8508.99,int:115.68,cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2027-04-06'),cap:8538.48,int:86.19, cuota:8624.67,est:'PENDIENTE'},
    {vd:d('2027-05-06'),cap:8579.99,int:44.69, cuota:8624.68,est:'PENDIENTE'},
   ]},
  {id:'ta3',emp:'JCEVCORP',ban:'PRODUBANCO',capital:1000000,tasa:.06,cuotaLabel:'$86,145/mes',vcto:'2027-06-03',
   color:'var(--accent2)',grad:'linear-gradient(90deg,var(--accent2),var(--accent))',
   cuotas:[
    {vd:d('2026-07-03'),cap:80811.29,int:5333.33,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2026-08-03'),cap:81395.48,int:4749.14,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2026-09-03'),cap:81816.02,int:4328.60,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2026-10-05'),cap:82112.74,int:4031.88,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2026-11-04'),cap:82775.30,int:3368.32,cuota:86143.62,est:'PENDIENTE'},
    {vd:d('2026-12-03'),cap:83287.69,int:2856.93,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2027-01-04'),cap:83436.35,int:2708.27,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2027-02-03'),cap:84022.79,int:2121.83,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2027-03-03'),cap:84556.36,int:1588.26,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2027-04-05'),cap:84737.80,int:1406.82,cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2027-05-03'),cap:85346.40,int:798.22, cuota:86144.62,est:'PENDIENTE'},
    {vd:d('2027-06-03'),cap:85701.78,int:442.79, cuota:86144.57,est:'PENDIENTE'},
   ]},
];

// ─ FLUJO JCEV / CONSUREP ─
const flujoCS=[
  {emp:'JCEVCORP', prov:'DOWNPAYMENTS',                              imp:'DOWNPAYMENTS',          merc:'ANTICIPO',              val:450000,   vd:d('2026-06-01')},
  {emp:'JCEVCORP', prov:'COBY',                                      imp:'COBY 05-2025',           merc:'PARLANTES',             val:19950,    vd:d('2026-06-01')},
  {emp:'CONSUREP', prov:'KONKA',                                     imp:'KONKA 06-2025',          merc:'PANEL',                 val:264213.8, vd:d('2026-06-02')},
  {emp:'CONSUREP', prov:'KONKA',                                     imp:'KONKA 06-2025',          merc:'INTEREST',              val:3170.56,  vd:d('2026-06-02')},
  {emp:'JCEVCORP', prov:'LG ELECTRONICS',                            imp:'LG 10A-2026/2000046483', merc:'SECADORA',              val:38580,    vd:d('2026-06-04')},
  {emp:'CONSUREP', prov:'ALL DISTRIBUTION PANEL',                    imp:'AD 07-2026/10379',       merc:'PANEL',                 val:101990.33,vd:d('2026-06-04')},
  {emp:'JCEVCORP', prov:'TERCELO TIRE',                              imp:'TRANSMATE 03-2026',      merc:'LLANTAS',               val:64255.66, vd:d('2026-06-05')},
  {emp:'JCEVCORP', prov:'TERCELO TIRE',                              imp:'TRANSMATE 04-2026',      merc:'LLANTAS',               val:68928.9,  vd:d('2026-06-05')},
  {emp:'JCEVCORP', prov:'MEILING',                                   imp:'MEILING 05-2026',        merc:'REFRIGERADORAS',        val:58381,    vd:d('2026-06-05')},
  {emp:'JCEVCORP', prov:'XING',                                      imp:'XING 01-2026',           merc:'VITRINA XLS',           val:7472,     vd:d('2026-06-05')},
  {emp:'JCEVCORP', prov:'HOME ELEMENTS',                             imp:'HOME 02-2026',           merc:'ELECTROMENOR',          val:39172.8,  vd:d('2026-06-06')},
  {emp:'JCEVCORP', prov:'LG ELECTRONICS',                            imp:'LG 11-2026/2000046540',  merc:'LAVADORAS',             val:75600,    vd:d('2026-06-07')},
  {emp:'JCEVCORP', prov:'HOUSEHOLD SOLUTIONS SA',                    imp:'OSTER 26-2025/23-2025',  merc:'REFRIGERADORA 215',     val:38147.5,  vd:d('2026-06-07')},
  {emp:'JCEVCORP', prov:'TAIZHOU QINLI MACHINERY',                   imp:'QINLI 01-2026',          merc:'FUMIGADORAS',           val:42195,    vd:d('2026-06-07')},
  {emp:'JCEVCORP', prov:'HOME ELEMENTS',                             imp:'HOME 04-2026',           merc:'ELECTROMENOR',          val:32140,    vd:d('2026-06-08')},
  {emp:'CONSUREP', prov:'EXPRESS LUCK',                              imp:'EXPRESS LUCK 01-2026',   merc:'TV PARTS',              val:1678023,  vd:d('2026-06-08')},
  {emp:'JCEVCORP', prov:'SHANFENG',                                  imp:'SHANFENG 02-2026',       merc:'REGULADORES',           val:26425,    vd:d('2026-06-10')},
  {emp:'JCEVCORP', prov:'ITT',                                       imp:'ITT 01-2026',            merc:'LAVADORAS',             val:39330,    vd:d('2026-06-10')},
  {emp:'JCEVCORP', prov:'LAMO',                                      imp:'LAMO 01-2026',           merc:'DISPENSADORES',         val:19057.5,  vd:d('2026-06-10')},
  {emp:'JCEVCORP', prov:'MINSHENG',                                  imp:'MINSHENG 01-2026',       merc:'COCINAS',               val:25540.9,  vd:d('2026-06-10')},
  {emp:'JCEVCORP', prov:'HOME ELEMENTS',                             imp:'HOME 03-2026',           merc:'ELECTROMENOR',          val:34299.2,  vd:d('2026-06-10')},
  {emp:'JCEVCORP', prov:'LG ELECTRONICS',                            imp:'LG 12-2026/2000046787',  merc:'LAVADORAS',             val:107100,   vd:d('2026-06-11')},
  {emp:'JCEVCORP', prov:'KONKA',                                     imp:'KONKA 06-2025',          merc:'MB',                    val:90279.2,  vd:d('2026-06-11')},
  {emp:'JCEVCORP', prov:'KONKA',                                     imp:'KONKA 06-2025',          merc:'INTEREST',              val:2166.71,  vd:d('2026-06-11')},
  {emp:'JCEVCORP', prov:'SICUENS',                                   imp:'FEDERAL 02-2026',        merc:'LLANTAS',               val:36456,    vd:d('2026-06-15')},
  {emp:'JCEVCORP', prov:'COMPAÑÍA HULERA',                           imp:'TORNEL 07A-2025',        merc:'LLANTAS',               val:29986.83, vd:d('2026-06-15')},
  {emp:'JCEVCORP', prov:'COMPAÑÍA HULERA',                           imp:'TORNEL 01-2026',         merc:'LLANTAS',               val:106141.9, vd:d('2026-06-15')},
  {emp:'JCEVCORP', prov:'COMPAÑÍA HULERA',                           imp:'TORNEL 02-2026',         merc:'LLANTAS',               val:142372.58,vd:d('2026-06-15')},
  {emp:'JCEVCORP', prov:'LONGSONG',                                  imp:'LONGSONG 01-2026',       merc:'VENTILADORES',          val:17763.48, vd:d('2026-06-15')},
  {emp:'JCEVCORP', prov:'HOME ELEMENTS',                             imp:'HOME 01-2026',           merc:'ELECTROMENOR',          val:27550.5,  vd:d('2026-06-16')},
  {emp:'JCEVCORP', prov:'LG ELECTRONICS',                            imp:'LG 13A-2026/2000047062', merc:'REFRIGERADORA',         val:32900,    vd:d('2026-06-17')},
  {emp:'TODOMOTO', prov:'ALL DISTRIBUTION MB',                       imp:'AD 07-2026/10378',       merc:'MB',                    val:76985.7,  vd:d('2026-06-18')},
  {emp:'JCEVCORP', prov:'MINFU',                                     imp:'MINFU 01-2026',          merc:'PARLANTES',             val:37927.87, vd:d('2026-06-20')},
  {emp:'JCEVCORP', prov:'LG ELECTRONICS',                            imp:'LG 13-2026/2000047237',  merc:'REFRIGERADORA',         val:24000,    vd:d('2026-06-22')},
  {emp:'JCEVCORP', prov:'BEST CHOICE INTL',                         imp:'MAZZINI 03A-2026',       merc:'LLANTAS',               val:131235.54,vd:d('2026-06-22')},
  {emp:'JCEVCORP', prov:'BEST CHOICE INTL',                         imp:'MAZZINI 04-2026',        merc:'LLANTAS',               val:57098.15, vd:d('2026-06-24')},
  {emp:'JCEVCORP', prov:'TAIZHOU GUANGFENG',                        imp:'GUANGFENG 01-2026',      merc:'SEMBRADORAS/FUMIGADORA', val:12608.5,  vd:d('2026-06-24')},
  {emp:'JCEVCORP', prov:'KUMHO',                                     imp:'KUMHO 01A-2026',         merc:'LLANTAS',               val:42360.8,  vd:d('2026-06-26')},
  {emp:'JCEVCORP', prov:'HOUSEHOLD SOLUTIONS SA',                    imp:'OSTER 24-2025',          merc:'DISPENSADOR DE AGUA',   val:25754,    vd:d('2026-06-28')},
  {emp:'JCEVCORP', prov:'XING',                                      imp:'XING 02-2026',           merc:'SD',                    val:19188,    vd:d('2026-06-29')},
  {emp:'JCEVCORP', prov:'TAIZHOU MUGUANG',                          imp:'WINSTAR 01-2026',        merc:'SOLDADORAS',            val:56097,    vd:d('2026-06-30')},
];

// ─ FLUJO CREDIMPORT ─
const flujoCR=[
  {emp:'CREDIMPORT',prov:'DOWNPAYMENTS',imp:'DOWNPAYMENTS',merc:'ANTICIPO',val:350000,vd:d('2026-06-01')},
];

// ─ FLUJO ASSEMBLY ─
const flujoAS=[
  {emp:'ASSEMBLY',prov:'DOWNPAYMENTS',                             imp:'DOWNPAYMENTS',      merc:'ANTICIPO',             val:450000,  vd:d('2026-06-01')},
  {emp:'ASSEMBLY',prov:'MOTORHEAD',                                imp:'MOTORHEAD 18-2025', merc:'DY250 SCORPION',        val:72136,   vd:d('2026-06-04')},
  {emp:'ASSEMBLY',prov:'MOTORHEAD',                                imp:'MOTORHEAD 26-2025', merc:'DY300 TEKKEN DISCOVERY',val:114464,  vd:d('2026-06-04')},
  {emp:'ASSEMBLY',prov:'LIFAN INDUSTRY',                           imp:'LIFAN 02-2025',     merc:'DY180 WORKFORCE',      val:128478,  vd:d('2026-06-06')},
  {emp:'ASSEMBLY',prov:'SENGO LIMITED',                            imp:'SENGO 06-2025',     merc:'DY125 TANQ',           val:40602,   vd:d('2026-06-10')},
  {emp:'ASSEMBLY',prov:'CHONGQING MINFF',                         imp:'MINFF 12-2025',     merc:'DY150 DYNAMIC PRO',    val:69148.8, vd:d('2026-06-10')},
  {emp:'ASSEMBLY',prov:'CHONGQING MINFF',                         imp:'MINFF 01-2026',     merc:'DY200 EAGLE Z',        val:57026.2, vd:d('2026-06-10')},
  {emp:'ASSEMBLY',prov:'SONLINK MOTORCYCLE',                       imp:'SONLINK 50-2025',   merc:'DY150 CRUCERO',        val:66700,   vd:d('2026-06-11')},
  {emp:'ASSEMBLY',prov:'LINXI MOTOR INTL',                        imp:'XIN LIN 02-2025',   merc:'DY200 ARROW',          val:73164,   vd:d('2026-06-13')},
  {emp:'ASSEMBLY',prov:'LINXI MOTOR INTL',                        imp:'XIN LIN 01-2026',   merc:'DY200 WING EVO II',    val:135767,  vd:d('2026-06-13')},
  {emp:'ASSEMBLY',prov:'MOTORHEAD',                                imp:'MOTORHEAD 32-2025', merc:'DY200 SCORPION',        val:123891,  vd:d('2026-06-16')},
  {emp:'ASSEMBLY',prov:'WUXI EAST TECHNOLOGY',                    imp:'EST 02-2026',       merc:'DY370 GP-1 RR',        val:96614,   vd:d('2026-06-20')},
  {emp:'ASSEMBLY',prov:'SONLINK MOTORCYCLE',                       imp:'SONLINK 42-2025',   merc:'DY250 WOLF',           val:86604,   vd:d('2026-06-21')},
  {emp:'ASSEMBLY',prov:'SONLINK MOTORCYCLE',                       imp:'SONLINK 46-2025',   merc:'DY200 CRUCERO',        val:71392,   vd:d('2026-06-21')},
  {emp:'ASSEMBLY',prov:'SONLINK MOTORCYCLE',                       imp:'SONLINK 49-2025',   merc:'DY150 WORKFORCE',      val:216192,  vd:d('2026-06-21')},
  {emp:'ASSEMBLY',prov:'MOTORHEAD',                                imp:'MOTORHEAD 31-2025', merc:'DY200 SCORPION',        val:126800,  vd:d('2026-06-26')},
  {emp:'ASSEMBLY',prov:'MOTORHEAD',                                imp:'MOTORHEAD 33A-2026',merc:'DY250 SCORPION',        val:97950,   vd:d('2026-06-26')},
  {emp:'ASSEMBLY',prov:'CHONGQING XGJAO',                         imp:'VINTO 02-2026',     merc:'DY300 EVEREST',        val:133056,  vd:d('2026-06-26')},
  {emp:'ASSEMBLY',prov:'BASHAN MOTORCYCLE',                        imp:'BASHAN C 18-2025',  merc:'DY200 SHARK',          val:56287.98,vd:d('2026-06-27')},
  {emp:'ASSEMBLY',prov:'CHONGQING MINFF',                         imp:'MINFF 02-2026',     merc:'DY200 EAGLE Z',        val:57349.6, vd:d('2026-06-29')},
  {emp:'ASSEMBLY',prov:'JIANGSU DAELG MOTORCYCLE',                imp:'SUKULI 02-2025',    merc:'CF 450 SR',            val:145530,  vd:d('2026-06-30')},
];

// ─ SRI ─
const sriData=[
  {emp:'ASSEMBLY',  val:350000, vd:d('2026-06-11'), est:'PENDIENTE'},
  {emp:'JCEVCORP',  val:620000, vd:d('2026-06-11'), est:'PENDIENTE'},
  {emp:'CREDIMPORT',val:8291,   vd:d('2026-06-16'), est:'PENDIENTE'},
  {emp:'FULLMOTOS', val:74828,  vd:d('2026-06-16'), est:'PENDIENTE'},
];

// ─ NÓMINA ─
const nominaData=[
  {emp:'ASSEMBLY',  val:13545, vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'ASSEMBLY',  val:20797, vd:d('2026-06-30'), est:'PENDIENTE'},
  {emp:'JCEVCORP',  val:38200, vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'JCEVCORP',  val:95300, vd:d('2026-06-30'), est:'PENDIENTE'},
  {emp:'CREDIMPORT',val:14041, vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'CREDIMPORT',val:31659, vd:d('2026-06-30'), est:'PENDIENTE'},
  {emp:'MONTAZ',    val:8100,  vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'MONTAZ',    val:12350, vd:d('2026-06-30'), est:'PENDIENTE'},
  {emp:'TODOMOTO',  val:5219,  vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'TODOMOTO',  val:7487,  vd:d('2026-06-30'), est:'PENDIENTE'},
  {emp:'CONSUREP',  val:14100, vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'CONSUREP',  val:16500, vd:d('2026-06-30'), est:'PENDIENTE'},
];

// ─ PROVEEDORES ─
const provData=[
  {emp:'ASSEMBLY',  val:220000, vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'JCEVCORP',  val:350000, vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'CREDIMPORT',val:60000,  vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'FULLMOTOS', val:150000, vd:d('2026-06-15'), est:'PENDIENTE'},
  {emp:'CONSUREP',  val:20000,  vd:d('2026-06-15'), est:'PENDIENTE'},
];

// ─ GARANTÍAS ─
const garRaw=[
  {ban:'Guayaquil',  tipo:'Prenda Inventario',prop:'JCEVCORP / ASSEMBLYMOTOS',monto:1034007, vd:d('2025-07-21')},
  {ban:'Guayaquil',  tipo:'Bien Inmueble',    prop:'Juan Carlos Espinoza',    monto:1987467, vd:d('2025-07-21')},
  {ban:'Internacional',tipo:'Bien Inmueble',  prop:'JCEVCORP',                monto:297260,  vd:d('2028-08-12')},
  {ban:'Internacional',tipo:'Bien Inmueble',  prop:'Juan Carlos Espinoza',    monto:263948,  vd:d('2028-08-12')},
  {ban:'Internacional',tipo:'Prenda Inventario',prop:'ASSEMBLYMOTOS',         monto:400334,  vd:d('2027-03-18')},
  {ban:'Internacional',tipo:'Prenda Inventario',prop:'ASSEMBLYMOTOS',         monto:735479,  vd:d('2025-10-27')},
  {ban:'Internacional',tipo:'Prenda Inventario',prop:'ASSEMBLYMOTOS',         monto:417215,  vd:d('2026-01-26')},
  {ban:'Internacional',tipo:'Prenda Inventario',prop:'ASSEMBLYMOTOS',         monto:947215,  vd:d('2026-02-19')},
  {ban:'Pichincha',  tipo:'Prenda Inventario',prop:'JCEVCORP / ASSEMBLYMOTOS',monto:2000354, vd:d('2026-02-05')},
  {ban:'Pichincha',  tipo:'Bien Inmueble',    prop:'JCEVCORP',                monto:539977,  vd:d('2025-12-11')},
  {ban:'Pichincha',  tipo:'Bien Inmueble',    prop:'JCEVCORP',                monto:1569675, vd:d('2027-06-05')},
  {ban:'Produbanco', tipo:'Bien Inmueble',    prop:'Juan Carlos Espinoza',    monto:765685,  vd:d('2026-01-27')},
  {ban:'Produbanco', tipo:'Bien Inmueble',    prop:'JCEVCORP',                monto:1958303, vd:d('2026-01-27')},
  {ban:'Produbanco', tipo:'Bien Inmueble',    prop:'FULLMOTOS',               monto:1296597, vd:d('2026-01-27')},
];

// ════════════════════════════════════════════════════════
// HELPERS
// ════════════════════════════════════════════════════════
let HOY=new Date();
const fmtUSD=(n,c)=>{if(c&&Math.abs(n)>=1e6)return'$'+(n/1e6).toFixed(2)+'M';if(c&&Math.abs(n)>=1000)return'$'+(n/1000).toFixed(0)+'K';return'$'+Math.round(n).toLocaleString('es-EC');};
const fmtD=(dt,s)=>dt?dt.toLocaleDateString('es-EC',s?{day:'2-digit',month:'short',year:'numeric'}:{weekday:'short',day:'2-digit',month:'short',year:'numeric'}):'—';
const diasQ=(dt)=>dt?Math.round((dt-HOY)/86400000):null;
const fmtP=(n)=>(n*100).toFixed(2)+'%';
const empClr={JCEVCORP:'#6366f1',ASSEMBLY:'#10b981',FULLMOTOS:'#f59e0b',CREDIMPORT:'#06b6d4',CONSUREP:'#a78bfa',MONTAZ:'#f472b6',TODOMOTO:'#22d3ee'};
const empTag={JCEVCORP:'tj',ASSEMBLY:'ta',FULLMOTOS:'tf',CREDIMPORT:'tc',CONSUREP:'tcs',MONTAZ:'tm',TODOMOTO:'tto'};
const etag=(e)=>`<span class="tag ${empTag[e]||'tj'}">${e}</span>`;
function pillD(dt,est){
  if(est==='CANCELADO'||est==='PAGADO')return'<span class="pill pgr">✓ Pagado</span>';
  if(!dt)return'<span class="pill pgr">Sin fecha</span>';
  const di=diasQ(dt);
  if(di===null)return'';
  if(di<0)return`<span class="pill pr">Vencido</span>`;
  if(di<=7)return`<span class="pill pr">⚡ ${di}d</span>`;
  if(di<=30)return`<span class="pill pr">${di}d</span>`;
  if(di<=90)return`<span class="pill py">${di}d</span>`;
  return`<span class="pill pg">${di}d</span>`;
}
function ubClass(dt,est){
  if(!dt||est==='CANCELADO'||est==='PAGADO')return'ub-gr';
  const di=diasQ(dt);
  if(di===null||di<0)return'ub-r';
  if(di<=30)return'ub-r';
  if(di<=90)return'ub-y';
  return'ub-g';
}

// ════════════════════════════════════════════════════════
// RESUMEN
// ════════════════════════════════════════════════════════
function renderResumen(){
  const d30=oblRaw.filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>=0&&diasQ(r.vd)<=30);
  const d90=oblRaw.filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>30&&diasQ(r.vd)<=90);
  const taPend=taData.flatMap(t=>t.cuotas.filter(c=>c.est==='PENDIENTE')).length;
  const totFlujo=[...flujoCS,...flujoCR,...flujoAS].reduce((s,r)=>s+r.val,0);
  const totNom=nominaData.reduce((s,r)=>s+r.val,0);
  const totSRI=sriData.reduce((s,r)=>s+r.val,0);
  const totProv=provData.reduce((s,r)=>s+r.val,0);
  const totCap=oblRaw.reduce((s,r)=>s+r.cap,0);

  document.getElementById('kpi-res').innerHTML=`
    <div class="kpi blue"><div class="kpi-label">Capital Financiero</div><div class="kpi-value">${fmtUSD(totCap,true)}</div><div class="kpi-sub">${oblRaw.length} obligaciones</div></div>
    <div class="kpi red"><div class="kpi-label">Vence ≤ 30 días</div><div class="kpi-value" style="color:var(--red)">${d30.length?fmtUSD(d30.reduce((s,r)=>s+r.cap,0),true):'$0'}</div><div class="kpi-sub">${d30.length} operaciones</div></div>
    <div class="kpi yellow"><div class="kpi-label">Vence ≤ 90 días</div><div class="kpi-value" style="color:var(--yellow)">${d90.length?fmtUSD(d90.reduce((s,r)=>s+r.cap,0),true):'$0'}</div><div class="kpi-sub">${d90.length} operaciones</div></div>
    <div class="kpi purple"><div class="kpi-label">Cuotas TA Pend.</div><div class="kpi-value">${taPend}</div><div class="kpi-sub">${taData.length} créditos activos</div></div>
    <div class="kpi cyan"><div class="kpi-label">Flujos Importación</div><div class="kpi-value" style="font-size:17px">${fmtUSD(totFlujo,true)}</div><div class="kpi-sub">${flujoCS.length+flujoCR.length+flujoAS.length} operaciones</div></div>
    <div class="kpi orange"><div class="kpi-label">SRI + Nómina Jun</div><div class="kpi-value" style="font-size:17px">${fmtUSD(totSRI+totNom,true)}</div><div class="kpi-sub">Prov. ${fmtUSD(totProv,true)}</div></div>
  `;

  let html='';
  d30.forEach(r=>{html+=`<div class="alert al-red"><div class="al-dot"></div><div><strong>URGENTE:</strong> ${etag(r.emp)} ${r.ban} — ${fmtUSD(r.cap)} vence <strong>${fmtD(r.vd,true)}</strong> (${diasQ(r.vd)} días)</div></div>`;});
  d90.forEach(r=>{html+=`<div class="alert al-yellow"><div class="al-dot"></div><div>${etag(r.emp)} ${r.ban} — ${fmtUSD(r.cap)} vence <strong>${fmtD(r.vd,true)}</strong> (${diasQ(r.vd)} días)</div></div>`;});
  const flujoUrg=[...flujoCS,...flujoCR,...flujoAS].filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>=0&&diasQ(r.vd)<=7);
  if(flujoUrg.length)html+=`<div class="alert al-red"><div class="al-dot"></div><div><strong>${flujoUrg.length} importaciones</strong> vencen en los próximos 7 días — ${fmtUSD(flujoUrg.reduce((s,r)=>s+r.val,0))}</div></div>`;
  const sriUrg=sriData.filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>=0&&diasQ(r.vd)<=7);
  sriUrg.forEach(r=>{html+=`<div class="alert al-red"><div class="al-dot"></div><div>SRI ${etag(r.emp)} — ${fmtUSD(r.val)} vence <strong>${fmtD(r.vd,true)}</strong></div></div>`;});
  if(!html)html='<div class="alert al-green"><div class="al-dot"></div>No hay vencimientos críticos en los próximos 30 días.</div>';
  document.getElementById('alertas-div').innerHTML=html;

  const u=document.getElementById('tb-urgent');
  u.textContent=d30.length?`🔴 ${d30.length} vence ≤30d`:'';
  u.style.display=d30.length?'':'none';
  document.getElementById('tb-warn').textContent=`⚠ ${d90.length} vencen ≤90d`;
}

// ════════════════════════════════════════════════════════
// CHARTS
// ════════════════════════════════════════════════════════
const CI={};
function dc(id){if(CI[id]){CI[id].destroy();delete CI[id];}}
function initCharts(){
  Chart.defaults.color='#4a5568';Chart.defaults.borderColor='rgba(255,255,255,0.05)';
  dc('ch-emp');dc('ch-mes');dc('ch-ban');

  const byEmp={};oblRaw.forEach(r=>{byEmp[r.emp]=(byEmp[r.emp]||0)+r.cap;});
  const ek=Object.keys(byEmp),ev=Object.values(byEmp),ec=ek.map(k=>empClr[k]||'#4f9eff');
  CI['ch-emp']=new Chart(document.getElementById('ch-emp'),{type:'doughnut',
    data:{labels:ek,datasets:[{data:ev,backgroundColor:ec,borderWidth:0,hoverOffset:8}]},
    options:{responsive:true,maintainAspectRatio:false,cutout:'65%',plugins:{legend:{display:false},tooltip:{callbacks:{label:c=>` ${c.label}: ${fmtUSD(c.raw)}`}}}}});
  document.getElementById('leg-emp').innerHTML=ek.map((k,i)=>`<div class="leg-item"><div class="leg-dot" style="background:${ec[i]}"></div>${k}: <strong style="color:var(--text)">${fmtUSD(ev[i],true)}</strong></div>`).join('');

  const mM={};
  oblRaw.filter(r=>r.tipo!=='TA').forEach(r=>{const k=r.vd.getFullYear()+'-'+String(r.vd.getMonth()+1).padStart(2,'0');mM[k]=(mM[k]||0)+r.cap;});
  taData.forEach(t=>t.cuotas.filter(c=>c.est==='PENDIENTE').forEach(c=>{const k=c.vd.getFullYear()+'-'+String(c.vd.getMonth()+1).padStart(2,'0');mM[k]=(mM[k]||0)+c.cap;}));
  const ks=Object.keys(mM).sort().slice(0,14);
  const mN={'01':'Ene','02':'Feb','03':'Mar','04':'Abr','05':'May','06':'Jun','07':'Jul','08':'Ago','09':'Sep','10':'Oct','11':'Nov','12':'Dic'};
  const lbs=ks.map(k=>{const[y,m]=k.split('-');return mN[m]+(y!=='2026'?'\''+y.slice(2):'');});
  const vals=ks.map(k=>mM[k]);const mx=Math.max(...vals);
  CI['ch-mes']=new Chart(document.getElementById('ch-mes'),{type:'bar',
    data:{labels:lbs,datasets:[{data:vals,backgroundColor:vals.map(v=>v===mx?'#f87171':v>1000000?'#fbbf24':'#4f9eff'),borderRadius:5,borderSkipped:false}]},
    options:{responsive:true,maintainAspectRatio:false,plugins:{legend:{display:false},tooltip:{callbacks:{label:c=>` ${fmtUSD(c.raw)}`}}},
      scales:{x:{ticks:{color:'#4a5568',font:{size:10}},grid:{display:false}},y:{ticks:{color:'#4a5568',font:{size:10},callback:v=>v>=1e6?(v/1e6).toFixed(1)+'M':v>=1000?(v/1000).toFixed(0)+'K':v},grid:{color:'rgba(255,255,255,0.04)'}}}}});

  const bM={};oblRaw.forEach(r=>{bM[r.ban]=(bM[r.ban]||0)+r.cap;});
  const bE=Object.entries(bM).sort((a,b)=>b[1]-a[1]);
  CI['ch-ban']=new Chart(document.getElementById('ch-ban'),{type:'bar',
    data:{labels:bE.map(e=>e[0]),datasets:[{data:bE.map(e=>e[1]),backgroundColor:['#4f9eff','#6366f1','#f59e0b','#10b981','#a78bfa','#34d399','#f87171'],borderRadius:5,borderSkipped:false}]},
    options:{indexAxis:'y',responsive:true,maintainAspectRatio:false,plugins:{legend:{display:false},tooltip:{callbacks:{label:c=>` ${fmtUSD(c.raw)}`}}},
      scales:{x:{ticks:{color:'#4a5568',font:{size:10},callback:v=>v>=1e6?(v/1e6).toFixed(1)+'M':v>=1000?(v/1000).toFixed(0)+'K':v},grid:{color:'rgba(255,255,255,0.04)'}},y:{ticks:{color:'#8a93a8',font:{size:10}},grid:{display:false}}}}});
}

// ════════════════════════════════════════════════════════
// OBLIGACIONES
// ════════════════════════════════════════════════════════
function renderObl(){
  const fE=document.getElementById('fE').value,fB=document.getElementById('fB').value,fT=document.getElementById('fT').value;
  const data=oblRaw.filter(r=>(!fE||r.emp===fE)&&(!fB||r.ban===fB)&&(!fT||(fT==='TA'?r.tipo==='TA':r.tipo==='UNICO'))).sort((a,b)=>a.vd-b.vd);
  document.getElementById('tb-obl').innerHTML=data.map(r=>`<tr>
    <td>${etag(r.emp)}</td><td style="color:var(--text2)">${r.ban}</td>
    <td style="font-family:'DM Mono',monospace;font-weight:500">${fmtUSD(r.cap)}</td>
    <td style="font-family:'DM Mono',monospace;color:var(--text3)">${fmtUSD(r.int)}</td>
    <td style="font-family:'DM Mono',monospace">${fmtUSD(r.tot)}</td>
    <td style="font-family:'DM Mono',monospace;color:var(--yellow)">${fmtP(r.tasa)}</td>
    <td style="font-family:'DM Mono',monospace;font-weight:500">${fmtD(r.vd,true)}</td>
    <td>${pillD(r.vd,null)}</td>
    <td>${r.tipo==='TA'?'<span class="pill pb">TA mensual</span>':'<span class="pill pgr">Pago único</span>'}</td>
  </tr>`).join('');
  const tC=data.reduce((s,r)=>s+r.cap,0),tT=data.reduce((s,r)=>s+r.tot,0);
  document.getElementById('tot-obl').innerHTML=`<span>${data.length} registros</span><span>Capital: <strong>${fmtUSD(tC)}</strong></span><span>Total c/interés: <strong>${fmtUSD(tT)}</strong></span>`;
}

// ════════════════════════════════════════════════════════
// AMORTIZACIÓN
// ════════════════════════════════════════════════════════
function renderTA(){
  document.getElementById('ta-container').innerHTML=taData.map((t,i)=>{
    const tot=t.cuotas.length,can=t.cuotas.filter(c=>c.est==='CANCELADO').length;
    const pct=Math.round(can/tot*100);
    const nxt=t.cuotas.find(c=>c.est==='PENDIENTE');
    return`<div class="amort-card">
      <div class="amort-hdr" onclick="toggleTA('tb${i}','ic${i}')">
        <div style="display:flex;align-items:center;gap:10px;flex-wrap:wrap">
          ${etag(t.emp)}
          <span style="font-family:'Syne',sans-serif;font-weight:600;font-size:13px">${t.ban}</span>
          <span style="font-family:'DM Mono',monospace;font-size:12px;color:${t.color}">${fmtUSD(t.capital)}</span>
          <span class="pill pb">${fmtP(t.tasa)} anual</span>
        </div>
        <div style="display:flex;align-items:center;gap:10px">
          <span style="font-family:'DM Mono',monospace;font-size:10px;color:var(--text3)">${tot} cuotas · ${t.cuotaLabel} · Vcto ${t.vcto}</span>
          <svg class="chev" id="ic${i}" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="6 9 12 15 18 9"/></svg>
        </div>
      </div>
      <div class="amort-body" id="tb${i}">
        <div style="padding:12px 16px 0">
          <div style="display:flex;justify-content:space-between;font-family:'DM Mono',monospace;font-size:10px;color:var(--text3);margin-bottom:4px">
            <span>Progreso</span><span>${can}/${tot} pagadas (${pct}%)${nxt?' · Próxima: '+fmtD(nxt.vd,true):''}</span>
          </div>
          <div class="prog-wrap"><div class="prog-fill" style="width:${pct}%;background:${t.grad}"></div></div>
        </div>
        <div class="tw" style="margin:0 16px 16px;border-radius:6px">
          <table><thead><tr><th>Fecha pago</th><th>Capital</th><th>Interés</th><th>Cuota total</th><th>Estado</th></tr></thead>
          <tbody>${t.cuotas.map(c=>{
            const di=diasQ(c.vd);
            let pill=c.est==='CANCELADO'?'<span class="pill pgr">✓ Pagado</span>':di<0?'<span class="pill pr">Vencida</span>':di<=30?`<span class="pill pr">${di}d</span>`:di<=90?`<span class="pill py">${di}d</span>`:`<span class="pill pg">${di}d</span>`;
            return`<tr style="${c.est==='CANCELADO'?'opacity:.38':''}">
              <td style="font-family:'DM Mono',monospace;font-weight:500">${fmtD(c.vd)}</td>
              <td style="font-family:'DM Mono',monospace">${fmtUSD(c.cap)}</td>
              <td style="font-family:'DM Mono',monospace;color:var(--text3)">${fmtUSD(c.int)}</td>
              <td style="font-family:'DM Mono',monospace;font-weight:600">${fmtUSD(c.cuota)}</td>
              <td>${pill}</td>
            </tr>`;
          }).join('')}</tbody></table>
        </div>
      </div>
    </div>`;
  }).join('');
}
function toggleTA(id,ic){const b=document.getElementById(id),v=document.getElementById(ic);const o=b.classList.toggle('open');v.classList.toggle('open',o);}

// ════════════════════════════════════════════════════════
// GARANTÍAS
// ════════════════════════════════════════════════════════
function renderGar(){
  const sorted=garRaw.slice().sort((a,b)=>(a.vd?diasQ(a.vd):99999)-(b.vd?diasQ(b.vd):99999));
  document.getElementById('gar-grid').innerHTML=sorted.map(r=>{
    const di=r.vd?diasQ(r.vd):null;
    let cls,pill;
    if(!di){cls='gar-gr';pill='<span class="pill pgr">Sin fecha</span>';}
    else if(di<=30){cls='gar-r';pill=`<span class="pill pr">${di}d — URGENTE</span>`;}
    else if(di<=90){cls='gar-y';pill=`<span class="pill py">${di}d</span>`;}
    else{cls='gar-g';pill=`<span class="pill pg">${di}d</span>`;}
    return`<div class="gar-card ${cls}">
      <div style="font-size:10px;font-family:'DM Mono',monospace;letter-spacing:.8px;color:var(--text3);text-transform:uppercase;margin-bottom:4px">${r.ban}</div>
      <div style="font-size:13px;font-weight:500;margin-bottom:3px">${r.tipo}</div>
      <div style="font-size:11px;color:var(--text2);margin-bottom:9px">${r.prop}</div>
      <div style="font-family:'Syne',sans-serif;font-size:18px;font-weight:700;margin-bottom:6px;letter-spacing:-.5px">${fmtUSD(r.monto)}</div>
      <div style="display:flex;justify-content:space-between;align-items:center">
        <span style="font-size:11px;color:var(--text2);font-family:'DM Mono',monospace">${r.vd?fmtD(r.vd,true):'Sin fecha'}</span>
        ${pill}
      </div>
    </div>`;
  }).join('');
  document.getElementById('gar-90').textContent=garRaw.filter(r=>r.vd&&diasQ(r.vd)>=0&&diasQ(r.vd)<=90).length||'0';
}

// ════════════════════════════════════════════════════════
// FLUJOS
// ════════════════════════════════════════════════════════
let activeFlujo='cs';
function showFlujo(name,btn){activeFlujo=name;document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));btn.classList.add('active');renderFlujo();}
function renderFlujo(){
  const map={cs:flujoCS,cr:flujoCR,as:flujoAS};
  const data=(map[activeFlujo]||[]).sort((a,b)=>a.vd-b.vd);
  const totV=data.reduce((s,r)=>s+r.val,0);
  const v7=data.filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>=0&&diasQ(r.vd)<=7);
  const v30=data.filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>7&&diasQ(r.vd)<=30);
  document.getElementById('flujo-panel').innerHTML=`
    <div class="kpi-grid" style="margin-bottom:14px">
      <div class="kpi blue"><div class="kpi-label">Total a pagar</div><div class="kpi-value" style="font-size:18px">${fmtUSD(totV,true)}</div><div class="kpi-sub">${data.length} importaciones</div></div>
      <div class="kpi red"><div class="kpi-label">Vence ≤ 7d</div><div class="kpi-value" style="color:var(--red)">${v7.length}</div><div class="kpi-sub">${fmtUSD(v7.reduce((s,r)=>s+r.val,0),true)}</div></div>
      <div class="kpi yellow"><div class="kpi-label">Vence 8–30d</div><div class="kpi-value" style="color:var(--yellow)">${v30.length}</div><div class="kpi-sub">${fmtUSD(v30.reduce((s,r)=>s+r.val,0),true)}</div></div>
      <div class="kpi green"><div class="kpi-label">Proveedores únicos</div><div class="kpi-value">${[...new Set(data.map(r=>r.prov))].length}</div></div>
    </div>
    <div class="tw"><table>
      <thead><tr><th>Empresa</th><th>Proveedor</th><th>Importación</th><th>Mercadería</th><th>Valor</th><th>Vencimiento</th><th>Días</th></tr></thead>
      <tbody>${data.map(r=>`<tr>
        <td>${etag(r.emp)}</td>
        <td style="color:var(--text2)" title="${r.prov}">${r.prov}</td>
        <td style="font-family:'DM Mono',monospace;font-size:11px;color:var(--accent)" title="${r.imp}">${r.imp}</td>
        <td style="font-size:11px;color:var(--text3)">${r.merc}</td>
        <td style="font-family:'DM Mono',monospace;font-weight:600">${fmtUSD(r.val)}</td>
        <td style="font-family:'DM Mono',monospace">${fmtD(r.vd,true)}</td>
        <td>${pillD(r.vd,'PENDIENTE')}</td>
      </tr>`).join('')}</tbody>
    </table></div>
    <div class="tot-row"><span>${data.length} registros</span><span>Total: <strong>${fmtUSD(totV)}</strong></span></div>
  `;
}

// ════════════════════════════════════════════════════════
// SRI & NÓMINA
// ════════════════════════════════════════════════════════
function renderSRI(){
  const tS=sriData.reduce((s,r)=>s+r.val,0),tN=nominaData.reduce((s,r)=>s+r.val,0);
  const s7=sriData.filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>=0&&diasQ(r.vd)<=7).length;
  const n7=nominaData.filter(r=>diasQ(r.vd)!==null&&diasQ(r.vd)>=0&&diasQ(r.vd)<=7).length;
  document.getElementById('kpi-sri').innerHTML=`
    <div class="kpi red"><div class="kpi-label">Total SRI</div><div class="kpi-value" style="font-size:18px">${fmtUSD(tS,true)}</div><div class="kpi-sub">${sriData.length} empresas · ${s7>0?s7+' urgentes':'al día'}</div></div>
    <div class="kpi purple"><div class="kpi-label">Total Nómina</div><div class="kpi-value" style="font-size:18px">${fmtUSD(tN,true)}</div><div class="kpi-sub">${nominaData.length} pagos · ${n7>0?n7+' urgentes':'al día'}</div></div>
    <div class="kpi blue"><div class="kpi-label">Total Compromisos</div><div class="kpi-value" style="font-size:18px">${fmtUSD(tS+tN,true)}</div><div class="kpi-sub">SRI + Nómina junio</div></div>
  `;
  document.getElementById('tb-sri').innerHTML=sriData.sort((a,b)=>a.vd-b.vd).map(r=>`<tr>
    <td>${etag(r.emp)}</td>
    <td style="font-family:'DM Mono',monospace;font-weight:600;color:var(--red)">${fmtUSD(r.val)}</td>
    <td style="font-family:'DM Mono',monospace">${fmtD(r.vd,true)}</td>
    <td>${pillD(r.vd,r.est)}</td>
  </tr>`).join('');
  document.getElementById('tot-sri').innerHTML=`<span>Total SRI: <strong>${fmtUSD(tS)}</strong></span>`;
  document.getElementById('tb-nom').innerHTML=nominaData.sort((a,b)=>a.vd-b.vd).map(r=>`<tr>
    <td>${etag(r.emp)}</td>
    <td style="font-family:'DM Mono',monospace;font-weight:600;color:var(--assm)">${fmtUSD(r.val)}</td>
    <td style="font-family:'DM Mono',monospace">${fmtD(r.vd,true)}</td>
    <td>${pillD(r.vd,r.est)}</td>
  </tr>`).join('');
  document.getElementById('tot-nom').innerHTML=`<span>Total Nómina: <strong>${fmtUSD(tN)}</strong></span>`;
}

// ════════════════════════════════════════════════════════
// PROVEEDORES
// ════════════════════════════════════════════════════════
function renderProv(){
  const tot=provData.reduce((s,r)=>s+r.val,0);
  document.getElementById('kpi-prov').innerHTML=`
    <div class="kpi blue"><div class="kpi-label">Total Prov. Nacionales</div><div class="kpi-value" style="font-size:18px">${fmtUSD(tot,true)}</div><div class="kpi-sub">${provData.length} empresas</div></div>
    <div class="kpi yellow"><div class="kpi-label">Fecha de pago</div><div class="kpi-value" style="font-size:14px;color:var(--yellow)">15 Jun 2026</div><div class="kpi-sub">todos vencen el mismo día</div></div>
    <div class="kpi red"><div class="kpi-label">Días restantes</div><div class="kpi-value" style="color:var(--red)">${diasQ(d('2026-06-15'))!==null?Math.max(0,diasQ(d('2026-06-15')))+' d':'—'}</div></div>
  `;
  document.getElementById('tb-prov').innerHTML=provData.map(r=>`<tr>
    <td>${etag(r.emp)}</td>
    <td style="font-family:'DM Mono',monospace;font-weight:600">${fmtUSD(r.val)}</td>
    <td style="font-family:'DM Mono',monospace">${fmtD(r.vd,true)}</td>
    <td>${pillD(r.vd,r.est)}</td>
  </tr>`).join('');
  document.getElementById('tot-prov').innerHTML=`<span>Total: <strong>${fmtUSD(tot)}</strong></span>`;
}

// ════════════════════════════════════════════════════════
// CALENDARIO
// ════════════════════════════════════════════════════════
function renderCal(){
  const fT=document.getElementById('fCalT').value;
  const fE=document.getElementById('fCalE').value;
  const mMap={};
  const add=(dt,emp,desc,val,tipo)=>{
    // "FIN" filter shows both pago único (FIN) AND cuotas TA (TA)
    if(fT==='FIN'&&tipo!=='FIN'&&tipo!=='TA')return;
    else if(fT&&fT!=='FIN'&&fT!==tipo)return;
    if(fE&&fE!==emp)return;
    if(!dt||isNaN(dt.getTime()))return;
    const k=dt.getFullYear()+'-'+String(dt.getMonth()+1).padStart(2,'0');
    if(!mMap[k])mMap[k]=[];
    mMap[k].push({dt,emp,desc,val,tipo});
  };
  oblRaw.filter(r=>r.tipo!=='TA').forEach(r=>add(r.vd,r.emp,r.ban+' · Pago único',r.tot,'FIN'));
  taData.forEach(t=>t.cuotas.filter(c=>c.est==='PENDIENTE').forEach(c=>add(c.vd,t.emp,t.ban+' · Cuota TA',c.cuota,'TA')));
  [...flujoCS,...flujoCR,...flujoAS].forEach(r=>add(r.vd,r.emp,r.prov+' · '+r.imp,r.val,'IMP'));
  sriData.forEach(r=>add(r.vd,r.emp,'SRI',r.val,'SRI'));
  nominaData.forEach(r=>add(r.vd,r.emp,'Nómina',r.val,'NOM'));
  provData.forEach(r=>add(r.vd,r.emp,'Proveedores Nacionales',r.val,'PROV'));

  const tipoLbl={FIN:'Financiero',TA:'Cuota TA',IMP:'Importación',SRI:'SRI',NOM:'Nómina',PROV:'Proveedor'};
  const tipoCls={FIN:'pb',TA:'pb',IMP:'py',SRI:'pr',NOM:'pg',PROV:'pgr'};
  const mNom={1:'Enero',2:'Febrero',3:'Marzo',4:'Abril',5:'Mayo',6:'Junio',7:'Julio',8:'Agosto',9:'Septiembre',10:'Octubre',11:'Noviembre',12:'Diciembre'};
  const wdays=['DOM','LUN','MAR','MIÉ','JUE','VIE','SÁB'];

  if(!Object.keys(mMap).length){
    document.getElementById('cal-div').innerHTML='<div class="alert al-green"><div class="al-dot"></div>No hay obligaciones para los filtros seleccionados.</div>';return;
  }
  document.getElementById('cal-div').innerHTML=Object.keys(mMap).sort().map(k=>{
    const regs=mMap[k].sort((a,b)=>a.dt-b.dt);
    const[y,m]=k.split('-');
    const totM=regs.reduce((s,r)=>s+r.val,0);
    return`<div class="cal-month">
      <div class="cal-month-hdr">
        <div><span class="cal-month-name">${mNom[parseInt(m)]} ${y}</span><span style="font-size:11px;color:var(--text3);margin-left:10px;font-family:'DM Mono',monospace">${regs.length} eventos</span></div>
        ${totM>0?`<span class="cal-month-total">${fmtUSD(totM,true)} total</span>`:''}
      </div>
      ${regs.map(r=>`
        <div class="cal-row">
          <div class="ub ${ubClass(r.dt,'PENDIENTE')}"></div>
          <div class="cal-date">
            <div class="cal-d">${String(r.dt.getDate()).padStart(2,'0')}</div>
            <div class="cal-wd">${wdays[r.dt.getDay()]}</div>
          </div>
          <div class="cal-body">
            ${etag(r.emp)}
            <span style="color:var(--text2);font-size:12px" title="${r.desc}">${r.desc.length>48?r.desc.slice(0,48)+'…':r.desc}</span>
            <span class="pill ${tipoCls[r.tipo]||'pgr'}" style="font-size:9.5px">${tipoLbl[r.tipo]||r.tipo}</span>
            ${pillD(r.dt,'PENDIENTE')}
          </div>
          ${r.val>0?`<div class="cal-amt"><div class="cal-amt-v">${fmtUSD(r.val)}</div></div>`:''}
        </div>`).join('')}
    </div>`;
  }).join('');
}

function initCalFilters(){
  const all=[...new Set([...oblRaw.map(r=>r.emp),...taData.map(t=>t.emp),...flujoCS.map(r=>r.emp),...flujoCR.map(r=>r.emp),...flujoAS.map(r=>r.emp),...sriData.map(r=>r.emp),...nominaData.map(r=>r.emp),...provData.map(r=>r.emp)])].sort();
  document.getElementById('fCalE').innerHTML='<option value="">Todas</option>'+all.map(e=>`<option>${e}</option>`).join('');
}

// ════════════════════════════════════════════════════════
// NAVEGACIÓN
// ════════════════════════════════════════════════════════
const SEC_TITLES={resumen:'Panel Ejecutivo',obligaciones:'Obligaciones Financieras',amortizacion:'Tablas de Amortización TA',garantias:'Garantías Bancarias',flujos:'Flujos de Importación',sri:'SRI & Nómina',proveedores:'Proveedores Nacionales',calendario:'Calendario Consolidado',ia:'Asistente Financiero IA'};
const SEC_IDS=Object.keys(SEC_TITLES);
function nav(name){
  document.querySelectorAll('.nav-item').forEach((b,i)=>b.classList.toggle('active',SEC_IDS[i]===name));
  document.querySelectorAll('.section').forEach(s=>s.classList.remove('active'));
  const sec=document.getElementById('sec-'+name);if(sec)sec.classList.add('active');
  document.getElementById('tb-title').textContent=SEC_TITLES[name]||name;
}

// ════════════════════════════════════════════════════════
// REFRESH
// ════════════════════════════════════════════════════════
function refreshAll(){
  HOY=new Date();
  const btn=document.getElementById('btn-ref');btn.classList.add('spin');
  document.getElementById('sb-today').textContent=HOY.toLocaleDateString('es-EC',{weekday:'long',day:'numeric',month:'long',year:'numeric'});
  renderResumen();renderObl();renderTA();renderGar();renderFlujo();renderSRI();renderProv();renderCal();
  setTimeout(()=>{initCharts();btn.classList.remove('spin');},80);
}

// ════════════════════════════════════════════════════════
// IA
// ════════════════════════════════════════════════════════
const AI_CTX=`Eres analista financiero del Grupo JCEVCORP (Ecuador). Fecha hoy: ${new Date().toLocaleDateString('es-EC')}.
EMPRESAS: JCEVCORP, ASSEMBLY, FULLMOTOS, CREDIMPORT, CONSUREP, MONTAZ, TODOMOTO.
OBLIGACIONES: 20 operaciones (~$11M capital). 4 TAs activas (JCEVCORP $1M 6%, FULLMOTOS $500K 6.25%, ASSEMBLY $100K 6.25%, JCEVCORP $1M 6% nueva). Próximas: ASSEMBLY/PICHINCHA PANAMA $490K (11 jun), JCEVCORP/PICHINCHA PANAMA $478K (22 jun), ASSEMBLY/EBNA $180K (22 jun), etc.
FLUJOS JUNIO: CONSUREP: 41 importaciones $3.8M+ (destacan Express Luck $1.68M, Tornel $278K, Downpayments $450K). CREDIMPORT: $350K downpayment. ASSEMBLY: 21 motos $2.2M+ (Sonlink, Motorhead, Lifan, etc).
SRI JUNIO: ASSEMBLY $350K (11 jun), JCEVCORP $620K (11 jun), CREDIMPORT $8.3K (16 jun), FULLMOTOS $74.8K (16 jun). TOTAL: $1.05M.
NÓMINA JUNIO: 6 empresas, pagos 15 y 30 jun. Total: ~$277K.
PROVEEDORES NACIONALES 15 jun: ASSEMBLY $220K, JCEVCORP $350K, CREDIMPORT $60K, FULLMOTOS $150K, CONSUREP $20K. TOTAL: $800K.
Responde en español, conciso, máximo 200 palabras, orientado a la acción.`;

async function askAI(){
  const inp=document.getElementById('ai-in');const q=inp.value.trim();if(!q)return;
  const rd=document.getElementById('ai-resp');
  rd.innerHTML='<div class="ld"><span></span><span></span><span></span></div> Analizando...';inp.value='';
  try{
    const r=await fetch('https://api.anthropic.com/v1/messages',{method:'POST',headers:{'Content-Type':'application/json'},
      body:JSON.stringify({model:'claude-sonnet-4-20250514',max_tokens:800,system:AI_CTX,messages:[{role:'user',content:q}]})});
    const dd=await r.json();
    rd.innerHTML='<div style="line-height:1.75">'+(dd.content?.map(b=>b.text||'').join('')||'Sin respuesta.').replace(/\n/g,'<br>')+'</div>';
  }catch(e){rd.innerHTML='<span style="color:var(--red)">Error al consultar.</span>';}
}
function qk(p){nav('ia');document.getElementById('ai-in').value=p;askAI();}

// ════════════════════════════════════════════════════════
// BOOT
// ════════════════════════════════════════════════════════
(function(){
  document.getElementById('sb-today').textContent=HOY.toLocaleDateString('es-EC',{weekday:'long',day:'numeric',month:'long',year:'numeric'});
  initCalFilters();
  renderResumen();renderObl();renderTA();renderGar();renderFlujo();renderSRI();renderProv();renderCal();
  setTimeout(initCharts,100);
})();
</script>
</body>
</html>
