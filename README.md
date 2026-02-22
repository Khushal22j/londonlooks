# 🛍️ LondonLooks - Fashion E-Commerce (Static Template)

A basic HTML-only mockup for a fashion e-commerce homepage. Currently contains only the structural layout.

## Project Contents

- `index.html` – Homepage structure

## Usage

```bash
git clone https://github.com/Khushal22j/londonlooks.git
cd londonlooks
open index.html
You can also double-click index.html to view in your browser.

Future Enhancements
CSS styling (responsive layout)

JavaScript for interactivity

Product filters and cart system

License
MIT License





















java -jar backend\target\data-transfer.jar `
--spring.datasource.password=kiit `
--spring.main-datasource.password=kiit `
--spring.control-datasource.password=kiit `
--spring.datasource.hikari.connection-timeout=600000 `
--spring.datasource.hikari.validation-timeout=600000 `
--spring.datasource.hikari.max-lifetime=1800000 `
--spring.datasource.hikari.idle-timeout=600000 `
--spring.datasource.hikari.keepalive-time=300000 `
--spring.datasource.hikari.maximum-pool-size=30 `
--spring.main-datasource.hikari.maximum-pool-size=30 `
--spring.main-datasource.hikari.max-lifetime=1800000 `
--spring.main-datasource.hikari.connection-timeout=600000 `
--spring.main-datasource.hikari.idle-timeout=600000 `
--DB_INTERIM_SCHEMA=kj `
--DB_MAIN_SCHEMA=kj `
--DB_CONTROL_SCHEMA=kj `
--INTERIM_TABLE=interim_table `
--MAIN_TABLE=main_table `
--CONTROL_TABLE=control_table_test311 `
--MIN_ROW_THRESHOLD=10000 `
--BATCH_SIZE=50000 `
--FETCH_SIZE=30000 `
--WRITER_THREADS=16 `
--CPU_THROTTLE_DELAY=50 `
--CPU_THROTTLE=90





















<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>DataBridge — Transfer Control</title>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;500;700&family=DM+Sans:ital,wght@0,300;0,400;0,500;0,700;1,300&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #050a0f;
    --surface: #0a1520;
    --surface2: #0f1e2d;
    --surface3: #152333;
    --border: #1e3347;
    --border2: #243d54;
    --accent: #00d4ff;
    --accent2: #0099cc;
    --accent-dim: rgba(0,212,255,0.12);
    --accent-glow: 0 0 20px rgba(0,212,255,0.3);
    --green: #00ff9d;
    --green-dim: rgba(0,255,157,0.12);
    --yellow: #ffcc00;
    --yellow-dim: rgba(255,204,0,0.12);
    --red: #ff4757;
    --red-dim: rgba(255,71,87,0.12);
    --orange: #ff8c42;
    --text: #c9dde8;
    --text2: #7a9ab0;
    --text3: #4a6a80;
    --mono: 'JetBrains Mono', monospace;
    --sans: 'DM Sans', sans-serif;
  }

  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    background: var(--bg);
    color: var(--text);
    font-family: var(--sans);
    min-height: 100vh;
    overflow-x: hidden;
  }

  body::before {
    content: '';
    position: fixed;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.03) 2px,
      rgba(0,0,0,0.03) 4px
    );
    pointer-events: none;
    z-index: 100;
  }

  /* ─── Header ──────────────────────────────────────────────────── */
  .header {
    background: var(--surface);
    border-bottom: 1px solid var(--border);
    padding: 0 32px;
    height: 64px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: sticky;
    top: 0;
    z-index: 50;
  }

  .logo { display: flex; align-items: center; gap: 12px; }

  .logo-icon {
    width: 36px; height: 36px;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    border-radius: 8px;
    display: flex; align-items: center; justify-content: center;
    font-family: var(--mono); font-weight: 700; font-size: 14px;
    color: #000; box-shadow: var(--accent-glow);
  }

  .logo-text { font-family: var(--mono); font-size: 16px; font-weight: 700; color: var(--accent); letter-spacing: 0.05em; }
  .logo-sub { font-size: 11px; color: var(--text3); font-family: var(--mono); letter-spacing: 0.1em; }

  .header-status { display: flex; align-items: center; gap: 16px; }

  .status-pill {
    display: flex; align-items: center; gap: 8px;
    padding: 6px 14px; border-radius: 20px;
    border: 1px solid var(--border2);
    font-family: var(--mono); font-size: 11px; font-weight: 500; letter-spacing: 0.08em;
    background: var(--surface2); transition: all 0.3s;
  }

  .status-dot { width: 7px; height: 7px; border-radius: 50%; background: var(--text3); }
  .status-dot.idle { background: var(--text3); }
  .status-dot.running { background: var(--accent); animation: pulse 1.2s infinite; }
  .status-dot.completed { background: var(--green); }
  .status-dot.failed { background: var(--red); }
  .status-dot.throttled { background: var(--yellow); animation: pulse 0.6s infinite; }
  .status-dot.cancelled { background: var(--orange); }
  .status-dot.rolling_back { background: var(--orange); animation: pulse 0.8s infinite; }

  @keyframes pulse {
    0%, 100% { opacity: 1; transform: scale(1); }
    50% { opacity: 0.4; transform: scale(1.3); }
  }

  .conn-indicator { display: flex; align-items: center; gap: 6px; font-family: var(--mono); font-size: 10px; color: var(--text3); }
  .conn-dot { width: 6px; height: 6px; border-radius: 50%; background: var(--green); box-shadow: 0 0 6px var(--green); }
  .conn-dot.offline { background: var(--red); box-shadow: 0 0 6px var(--red); }

  /* ─── Layout ──────────────────────────────────────────────────── */
  .layout {
    display: grid;
    grid-template-columns: 280px 1fr;
    min-height: calc(100vh - 64px);
  }

  /* ─── Sidebar ─────────────────────────────────────────────────── */
  .sidebar {
    background: var(--surface);
    border-right: 1px solid var(--border);
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 24px;
    overflow-y: auto;
  }

  .section-label {
    font-family: var(--mono); font-size: 10px; font-weight: 700;
    color: var(--text3); letter-spacing: 0.15em; text-transform: uppercase;
    margin-bottom: 12px;
  }

  /* ─── Mode Selector ───────────────────────────────────────────── */
  .mode-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; }

  .mode-btn {
    padding: 14px 10px; border: 1px solid var(--border2);
    border-radius: 8px; background: var(--surface2); color: var(--text2);
    cursor: pointer; text-align: center; transition: all 0.2s;
    font-family: var(--mono); font-size: 11px; font-weight: 500; letter-spacing: 0.05em;
  }

  .mode-btn:hover { border-color: var(--accent); color: var(--accent); background: var(--accent-dim); }
  .mode-btn.active { border-color: var(--accent); color: var(--accent); background: var(--accent-dim); box-shadow: inset 0 0 20px rgba(0,212,255,0.05); }
  .mode-icon { font-size: 20px; margin-bottom: 6px; }

  /* ─── Partition date ──────────────────────────────────────────── */
  .field { display: flex; flex-direction: column; gap: 6px; }

  .field label {
    font-family: var(--mono); font-size: 10px; color: var(--text3);
    letter-spacing: 0.08em; text-transform: uppercase;
  }

  .field input {
    background: var(--surface3); border: 1px solid var(--border2);
    border-radius: 6px; color: var(--text); font-family: var(--mono);
    font-size: 12px; padding: 8px 12px; outline: none; transition: border-color 0.2s; width: 100%;
  }

  .field input:focus { border-color: var(--accent); box-shadow: 0 0 0 3px var(--accent-dim); }

  .partition-field { display: none; }
  .partition-field.visible { display: flex; }

  /* ─── Action Buttons ──────────────────────────────────────────── */
  .action-section { display: flex; flex-direction: column; gap: 10px; }

  .btn {
    padding: 12px 20px; border-radius: 8px; border: none; cursor: pointer;
    font-family: var(--mono); font-size: 12px; font-weight: 700; letter-spacing: 0.08em;
    transition: all 0.2s; position: relative; overflow: hidden;
  }

  .btn::before {
    content: ''; position: absolute; inset: 0;
    background: linear-gradient(135deg, rgba(255,255,255,0.08) 0%, transparent 60%);
    opacity: 0; transition: opacity 0.2s;
  }
  .btn:hover::before { opacity: 1; }

  .btn-primary { background: linear-gradient(135deg, var(--accent), var(--accent2)); color: #000; box-shadow: 0 4px 20px rgba(0,212,255,0.3); }
  .btn-primary:hover { transform: translateY(-1px); box-shadow: 0 6px 30px rgba(0,212,255,0.4); }
  .btn-primary:active { transform: translateY(0); }

  .btn-danger { background: var(--red-dim); color: var(--red); border: 1px solid var(--red); }
  .btn-danger:hover { background: var(--red); color: #fff; }

  .btn-ghost { background: var(--surface2); color: var(--text2); border: 1px solid var(--border2); }
  .btn-ghost:hover { border-color: var(--text2); color: var(--text); }

  .btn:disabled { opacity: 0.4; cursor: not-allowed; transform: none; box-shadow: none; }

  /* ─── Main Content ────────────────────────────────────────────── */
  .main-content { padding: 24px; display: flex; flex-direction: column; gap: 24px; overflow-y: auto; }

  /* ─── Progress Card ───────────────────────────────────────────── */
  .progress-card {
    background: var(--surface); border: 1px solid var(--border);
    border-radius: 12px; padding: 28px; position: relative; overflow: hidden;
  }

  .progress-card::before {
    content: ''; position: absolute; top: 0; left: 0; right: 0; height: 2px;
    background: linear-gradient(90deg, transparent, var(--accent), transparent);
    opacity: 0; transition: opacity 0.3s;
  }
  .progress-card.active::before { opacity: 1; }

  .progress-header { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 20px; }
  .progress-title { font-family: var(--mono); font-size: 11px; color: var(--text3); letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 4px; }
  .progress-phase { font-size: 18px; font-weight: 500; color: var(--text); }
  .progress-pct { font-family: var(--mono); font-size: 42px; font-weight: 700; color: var(--accent); line-height: 1; text-shadow: var(--accent-glow); }

  .progress-track { height: 6px; background: var(--surface3); border-radius: 3px; margin-bottom: 20px; overflow: hidden; }

  .progress-fill {
    height: 100%; background: linear-gradient(90deg, var(--accent2), var(--accent));
    border-radius: 3px; transition: width 0.8s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative; min-width: 0;
  }

  .progress-fill::after {
    content: ''; position: absolute; right: 0; top: 0; height: 100%; width: 60px;
    background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3));
    animation: shimmer 2s infinite;
  }

  @keyframes shimmer { 0% { opacity: 0; } 50% { opacity: 1; } 100% { opacity: 0; } }

  .progress-stats { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; }

  .stat { background: var(--surface2); border: 1px solid var(--border); border-radius: 8px; padding: 14px; }
  .stat-label { font-family: var(--mono); font-size: 9px; color: var(--text3); letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 6px; }
  .stat-value { font-family: var(--mono); font-size: 18px; font-weight: 700; color: var(--text); line-height: 1; }
  .stat-value.green { color: var(--green); }
  .stat-value.accent { color: var(--accent); }
  .stat-value.yellow { color: var(--yellow); }
  .stat-value.red { color: var(--red); }
  .stat-sub { font-family: var(--mono); font-size: 9px; color: var(--text3); margin-top: 4px; }

  /* ─── Metrics Grid ────────────────────────────────────────────── */
  .metrics-grid { display: grid; grid-template-columns: 1fr 1fr 1fr; gap: 16px; }

  .metric-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 20px; }
  .metric-title { font-family: var(--mono); font-size: 10px; color: var(--text3); letter-spacing: 0.12em; text-transform: uppercase; margin-bottom: 16px; display: flex; align-items: center; gap: 8px; }
  .metric-title .icon { font-size: 14px; }

  .gauge-row { display: flex; align-items: center; gap: 12px; margin-bottom: 10px; }
  .gauge-label { font-family: var(--mono); font-size: 10px; color: var(--text2); min-width: 70px; }
  .gauge-track { flex: 1; height: 5px; background: var(--surface3); border-radius: 3px; overflow: hidden; }
  .gauge-fill { height: 100%; border-radius: 3px; transition: width 0.5s, background 0.5s; }
  .gauge-fill.low { background: var(--green); }
  .gauge-fill.mid { background: var(--yellow); }
  .gauge-fill.high { background: var(--red); }
  .gauge-val { font-family: var(--mono); font-size: 11px; font-weight: 700; min-width: 36px; text-align: right; }

  .pool-item { display: flex; align-items: center; gap: 10px; margin-bottom: 10px; }
  .pool-name { font-family: var(--mono); font-size: 9px; color: var(--text3); min-width: 55px; text-transform: uppercase; letter-spacing: 0.08em; }
  .pool-bar { flex: 1; height: 18px; background: var(--surface3); border-radius: 4px; overflow: hidden; position: relative; display: flex; align-items: center; }
  .pool-bar-fill { height: 100%; background: linear-gradient(90deg, var(--accent2), var(--accent)); border-radius: 4px; transition: width 0.5s; }
  .pool-bar-text { position: absolute; left: 8px; font-family: var(--mono); font-size: 9px; color: #000; font-weight: 700; z-index: 1; }
  .pool-info { font-family: var(--mono); font-size: 9px; color: var(--text2); min-width: 50px; text-align: right; }

  .thread-big { font-family: var(--mono); font-size: 36px; font-weight: 700; color: var(--accent); line-height: 1; margin-bottom: 4px; }
  .thread-row { display: flex; justify-content: space-between; margin-top: 12px; }
  .thread-item { text-align: center; }
  .thread-item .val { font-family: var(--mono); font-size: 14px; font-weight: 700; color: var(--text); }
  .thread-item .lbl { font-family: var(--mono); font-size: 9px; color: var(--text3); text-transform: uppercase; letter-spacing: 0.08em; }

  /* ─── Balance Verification ────────────────────────────────────── */
  .verify-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; padding: 20px; }
  .verify-row { display: flex; align-items: center; gap: 16px; }
  .verify-box { flex: 1; background: var(--surface2); border: 1px solid var(--border); border-radius: 8px; padding: 16px; text-align: center; }
  .verify-num { font-family: var(--mono); font-size: 24px; font-weight: 700; color: var(--text); }
  .verify-lbl { font-family: var(--mono); font-size: 9px; color: var(--text3); text-transform: uppercase; letter-spacing: 0.1em; margin-top: 4px; }
  .verify-arrow { font-size: 20px; color: var(--text3); }
  .verify-status { padding: 8px 16px; border-radius: 20px; font-family: var(--mono); font-size: 11px; font-weight: 700; letter-spacing: 0.08em; }
  .verify-status.balanced { background: var(--green-dim); color: var(--green); border: 1px solid var(--green); }
  .verify-status.unbalanced { background: var(--red-dim); color: var(--red); border: 1px solid var(--red); }
  .verify-status.pending { background: var(--surface2); color: var(--text3); border: 1px solid var(--border); }

  /* ─── Log ─────────────────────────────────────────────────────── */
  .log-card { background: var(--surface); border: 1px solid var(--border); border-radius: 12px; overflow: hidden; }
  .log-header { padding: 14px 20px; border-bottom: 1px solid var(--border); display: flex; align-items: center; justify-content: space-between; }
  .log-header-title { font-family: var(--mono); font-size: 10px; color: var(--text3); letter-spacing: 0.12em; text-transform: uppercase; display: flex; align-items: center; gap: 8px; }
  .log-clear { font-family: var(--mono); font-size: 10px; color: var(--text3); background: none; border: none; cursor: pointer; padding: 4px 10px; border-radius: 4px; transition: all 0.2s; }
  .log-clear:hover { color: var(--accent); background: var(--accent-dim); }
  .log-body { padding: 16px 20px; max-height: 220px; overflow-y: auto; font-family: var(--mono); font-size: 11px; line-height: 1.8; }
  .log-body::-webkit-scrollbar { width: 4px; }
  .log-body::-webkit-scrollbar-track { background: transparent; }
  .log-body::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 2px; }

  .log-line { display: flex; gap: 12px; padding: 2px 0; border-bottom: 1px solid rgba(255,255,255,0.02); animation: fadeIn 0.3s ease; }
  @keyframes fadeIn { from { opacity: 0; transform: translateX(-8px); } to { opacity: 1; transform: none; } }
  .log-time { color: var(--text3); min-width: 70px; }
  .log-msg { color: var(--text2); }
  .log-msg.info { color: var(--text); }
  .log-msg.success { color: var(--green); }
  .log-msg.warn { color: var(--yellow); }
  .log-msg.error { color: var(--red); }

  /* ─── Control Strip ───────────────────────────────────────────── */
  .control-strip { background: var(--surface); border: 1px solid var(--border); border-radius: 10px; padding: 14px 20px; display: flex; align-items: center; gap: 24px; }
  .control-item { display: flex; align-items: center; gap: 8px; }
  .control-label { font-family: var(--mono); font-size: 10px; color: var(--text3); text-transform: uppercase; letter-spacing: 0.1em; }
  .control-value { font-family: var(--mono); font-size: 12px; font-weight: 600; color: var(--text); }
  .control-sep { width: 1px; height: 20px; background: var(--border2); }

  /* ─── Alert ───────────────────────────────────────────────────── */
  .alert { padding: 12px 20px; border-radius: 8px; font-family: var(--mono); font-size: 12px; display: none; align-items: center; gap: 12px; }
  .alert.visible { display: flex; animation: fadeIn 0.3s ease; }
  .alert.success { background: var(--green-dim); color: var(--green); border: 1px solid var(--green); }
  .alert.error { background: var(--red-dim); color: var(--red); border: 1px solid var(--red); }
  .alert.warn { background: var(--yellow-dim); color: var(--yellow); border: 1px solid var(--yellow); }

  @media (max-width: 900px) {
    .layout { grid-template-columns: 1fr; }
    .sidebar { border-right: none; border-bottom: 1px solid var(--border); }
    .metrics-grid { grid-template-columns: 1fr; }
    .progress-stats { grid-template-columns: repeat(2, 1fr); }
  }
</style>
</head>
<body>

<header class="header">
  <div class="logo">
    <div class="logo-icon">DB</div>
    <div>
      <div class="logo-text">DATABRIDGE</div>
      <div class="logo-sub">TRANSFER CONTROL SYSTEM</div>
    </div>
  </div>
  <div class="header-status">
    <div class="conn-indicator">
      <div class="conn-dot" id="connDot"></div>
      <span id="connText">Connecting...</span>
    </div>
    <div class="status-pill" id="headerPill">
      <div class="status-dot idle" id="statusDot"></div>
      <span id="statusText">IDLE</span>
    </div>
  </div>
</header>

<div class="layout">

  <!-- ─── Sidebar ──────────────────────────────────────────── -->
  <aside class="sidebar">

    <!-- Mode -->
    <div>
      <div class="section-label">Transfer Mode</div>
      <div class="mode-grid">
        <button class="mode-btn active" id="btnNormal" onclick="setMode('NORMAL')">
          <div class="mode-icon">⚡</div>
          <div>NORMAL</div>
          <div style="font-size:9px;color:var(--text3);margin-top:2px;">Latest batch</div>
        </button>
        <button class="mode-btn" id="btnPartition" onclick="setMode('PARTITION')">
          <div class="mode-icon">🗄️</div>
          <div>PARTITION</div>
          <div style="font-size:9px;color:var(--text3);margin-top:2px;">Old data load</div>
        </button>
      </div>
    </div>

    <!-- Partition date (shown only in PARTITION mode) -->
    <div class="field partition-field" id="partitionField">
      <label>Partition Date</label>
      <input type="date" id="partitionDate" />
    </div>

    <!-- Actions -->
    <div class="action-section">
      <div class="section-label">Actions</div>
      <div id="alertBox" class="alert"></div>
      <button class="btn btn-primary" id="btnStart" onclick="startTransfer()">
        ▶ START TRANSFER
      </button>
      <button class="btn btn-danger" id="btnCancel" onclick="cancelTransfer()" disabled>
        ✕ CANCEL JOB
      </button>
      <button class="btn btn-ghost" onclick="refreshStatus()">
        ↺ REFRESH STATUS
      </button>
    </div>

  </aside>

  <!-- ─── Main ──────────────────────────────────────────────── -->
  <main class="main-content">

    <!-- Control table info -->
    <div class="control-strip">
      <div class="control-item">
        <div class="control-label">Last Run</div>
        <div class="control-value" id="lastRunDate">—</div>
      </div>
      <div class="control-sep"></div>
      <div class="control-item">
        <div class="control-label">Today</div>
        <div class="control-value" id="todayDate">—</div>
      </div>
      <div class="control-sep"></div>
      <div class="control-item">
        <div class="control-label">Today's Run</div>
        <div class="control-value" id="alreadyRan" style="color:var(--green)">—</div>
      </div>
      <div class="control-sep"></div>
      <div class="control-item">
        <div class="control-label">Job ID</div>
        <div class="control-value" id="jobId" style="color:var(--accent)">—</div>
      </div>
      <div class="control-sep"></div>
      <div class="control-item">
        <div class="control-label">Batch ID</div>
        <div class="control-value" id="batchIdDisplay" style="color:var(--text2)">—</div>
      </div>
    </div>

    <!-- Progress -->
    <div class="progress-card" id="progressCard">
      <div class="progress-header">
        <div>
          <div class="progress-title">Transfer Progress</div>
          <div class="progress-phase" id="currentPhase">No job running</div>
        </div>
        <div class="progress-pct" id="progressPct">—</div>
      </div>
      <div class="progress-track">
        <div class="progress-fill" id="progressBar" style="width:0%"></div>
      </div>
      <div class="progress-stats">
        <div class="stat">
          <div class="stat-label">Total Rows</div>
          <div class="stat-value accent" id="totalRows">—</div>
          <div class="stat-sub">interim source</div>
        </div>
        <div class="stat">
          <div class="stat-label">Processed</div>
          <div class="stat-value" id="processedRows">—</div>
          <div class="stat-sub">read from interim</div>
        </div>
        <div class="stat">
          <div class="stat-label">Written</div>
          <div class="stat-value green" id="writtenRows">—</div>
          <div class="stat-sub">to main table</div>
        </div>
        <div class="stat">
          <div class="stat-label">ETA</div>
          <div class="stat-value yellow" id="eta">—</div>
          <div class="stat-sub" id="rowsPerSec">—</div>
        </div>
        <div class="stat">
          <div class="stat-label">Elapsed</div>
          <div class="stat-value" id="elapsed">—</div>
        </div>
        <div class="stat">
          <div class="stat-label">Speed</div>
          <div class="stat-value accent" id="speed">—</div>
          <div class="stat-sub">rows / sec</div>
        </div>
        <div class="stat">
          <div class="stat-label">Failed Rows</div>
          <div class="stat-value red" id="failedRows">0</div>
        </div>
        <div class="stat">
          <div class="stat-label">Mode</div>
          <div class="stat-value" id="modeDisplay">—</div>
        </div>
      </div>
    </div>

    <!-- System Metrics -->
    <div class="metrics-grid">

      <div class="metric-card">
        <div class="metric-title"><span class="icon">⚙️</span> CPU & Memory</div>
        <div class="gauge-row">
          <div class="gauge-label">System CPU</div>
          <div class="gauge-track"><div class="gauge-fill" id="cpuFill" style="width:0%"></div></div>
          <div class="gauge-val" id="cpuVal">—</div>
        </div>
        <div class="gauge-row">
          <div class="gauge-label">Process CPU</div>
          <div class="gauge-track"><div class="gauge-fill" id="procCpuFill" style="width:0%"></div></div>
          <div class="gauge-val" id="procCpuVal">—</div>
        </div>
        <div class="gauge-row" style="margin-top:12px">
          <div class="gauge-label">JVM Memory</div>
          <div class="gauge-track"><div class="gauge-fill" id="memFill" style="width:0%;background:var(--accent)"></div></div>
          <div class="gauge-val" id="memVal">—</div>
        </div>
        <div style="margin-top:8px;font-family:var(--mono);font-size:9px;color:var(--text3)">
          <span id="memDetails">—</span>
        </div>
      </div>

      <div class="metric-card">
        <div class="metric-title"><span class="icon">🗄️</span> Connection Pools</div>
        <div class="pool-item">
          <div class="pool-name">Interim</div>
          <div class="pool-bar">
            <div class="pool-bar-fill" id="interimPoolFill" style="width:0%"></div>
            <div class="pool-bar-text" id="interimPoolText">—</div>
          </div>
          <div class="pool-info" id="interimPoolInfo">—</div>
        </div>
        <div class="pool-item">
          <div class="pool-name">Main</div>
          <div class="pool-bar">
            <div class="pool-bar-fill" id="mainPoolFill" style="width:0%"></div>
            <div class="pool-bar-text" id="mainPoolText">—</div>
          </div>
          <div class="pool-info" id="mainPoolInfo">—</div>
        </div>
        <div class="pool-item">
          <div class="pool-name">Control</div>
          <div class="pool-bar">
            <div class="pool-bar-fill" id="ctrlPoolFill" style="width:0%"></div>
            <div class="pool-bar-text" id="ctrlPoolText">—</div>
          </div>
          <div class="pool-info" id="ctrlPoolInfo">—</div>
        </div>
      </div>

      <div class="metric-card">
        <div class="metric-title"><span class="icon">🧵</span> JVM Threads</div>
        <div class="thread-big" id="threadCount">—</div>
        <div style="font-family:var(--mono);font-size:9px;color:var(--text3)">ACTIVE THREADS</div>
        <div class="thread-row" style="margin-top:16px">
          <div class="thread-item">
            <div class="val" id="peakThreads">—</div>
            <div class="lbl">Peak</div>
          </div>
          <div class="thread-item">
            <div class="val" id="daemonThreads">—</div>
            <div class="lbl">Daemon</div>
          </div>
          <div class="thread-item">
            <div class="val" id="cpuCores">—</div>
            <div class="lbl">CPU Cores</div>
          </div>
        </div>
      </div>
    </div>

    <!-- Balance Verification -->
    <div class="verify-card">
      <div class="section-label" style="margin-bottom:14px">Balance Verification</div>
      <div class="verify-row">
        <div class="verify-box">
          <div class="verify-num" id="interimCount">—</div>
          <div class="verify-lbl">Interim Count</div>
        </div>
        <div class="verify-arrow">→</div>
        <div class="verify-box">
          <div class="verify-num" id="mainCount">—</div>
          <div class="verify-lbl">Main Count</div>
        </div>
        <div style="margin-left:16px">
          <div class="verify-status pending" id="verifyStatus">PENDING</div>
        </div>
      </div>
    </div>

    <!-- Log -->
    <div class="log-card">
      <div class="log-header">
        <div class="log-header-title"><span>📋</span> Activity Log</div>
        <button class="log-clear" onclick="clearLog()">CLEAR</button>
      </div>
      <div class="log-body" id="logBody">
        <div class="log-line">
          <span class="log-time">—</span>
          <span class="log-msg">DataBridge Transfer Control initialized. Select mode and start a job.</span>
        </div>
      </div>
    </div>

  </main>
</div>

<script>
const API_BASE = window.API_BASE || 'http://localhost:8080/api';
let currentMode = 'NORMAL';
let pollInterval = null;
let metricsInterval = null;
let lastStatus = null;

function setMode(mode) {
  currentMode = mode;
  document.getElementById('btnNormal').classList.toggle('active', mode === 'NORMAL');
  document.getElementById('btnPartition').classList.toggle('active', mode === 'PARTITION');
  document.getElementById('partitionField').classList.toggle('visible', mode === 'PARTITION');
}

async function startTransfer() {
  const config = { mode: currentMode };

  if (currentMode === 'PARTITION') {
    const pd = document.getElementById('partitionDate').value;
    if (!pd) { showAlert('Please select a partition date', 'error'); return; }
    config.partitionDate = pd;
  }

  try {
    setButtonState(true);
    showAlert('Starting transfer...', 'warn');
    const resp = await fetch(`${API_BASE}/transfer/start`, {
      method: 'POST',
      headers: { 'Content-Type': 'application/json' },
      body: JSON.stringify(config)
    });
    const data = await resp.json();
    if (!resp.ok) {
      showAlert(data.error || data.message || 'Failed to start', 'error');
      setButtonState(false);
      return;
    }
    showAlert(`Job ${data.jobId} started`, 'success');
    addLog(`Job ${data.jobId} started in ${data.mode} mode`, 'success');
    startPolling();
  } catch (e) {
    showAlert('Cannot connect to API: ' + e.message, 'error');
    setButtonState(false);
  }
}

async function cancelTransfer() {
  try {
    await fetch(`${API_BASE}/transfer/cancel`, { method: 'POST' });
    addLog('Cancellation requested — rolling back partial data...', 'warn');
    showAlert('Cancellation requested — rollback in progress', 'warn');
  } catch (e) {
    showAlert('Failed to cancel: ' + e.message, 'error');
  }
}

function startPolling() {
  if (pollInterval) clearInterval(pollInterval);
  pollInterval = setInterval(refreshStatus, 2500);
  refreshStatus();
}

async function refreshStatus() {
  try {
    const resp = await fetch(`${API_BASE}/transfer/status`);
    if (!resp.ok) return;
    const data = await resp.json();
    updateStatusUI(data);
    const terminal = ['COMPLETED', 'FAILED', 'CANCELLED', 'IDLE'];
    if (terminal.includes(data.status)) {
      if (pollInterval) { clearInterval(pollInterval); pollInterval = null; }
      setButtonState(false);
      fetchControlInfo();
    }
  } catch (e) { /* offline */ }
}

function updateStatusUI(d) {
  if (JSON.stringify(d) === JSON.stringify(lastStatus)) return;
  lastStatus = d;

  const status = d.status || 'IDLE';

  document.getElementById('statusDot').className = 'status-dot ' + status.toLowerCase();
  document.getElementById('statusText').textContent = status;
  document.getElementById('currentPhase').textContent = d.currentPhase || 'No job running';
  document.getElementById('jobId').textContent = d.jobId || '—';
  document.getElementById('batchIdDisplay').textContent = d.batchId || '—';
  document.getElementById('modeDisplay').textContent = d.mode || '—';

  const pct = parseFloat(d.progressPercent) || 0;
  document.getElementById('progressPct').textContent = pct > 0 ? pct.toFixed(1) + '%' : '—';
  document.getElementById('progressBar').style.width = pct + '%';
  document.getElementById('progressCard').classList.toggle('active',
    status === 'RUNNING' || status === 'THROTTLED' || status === 'ROLLING_BACK');

  document.getElementById('totalRows').textContent = fmtNum(d.totalRows);
  document.getElementById('processedRows').textContent = fmtNum(d.processedRows);
  document.getElementById('writtenRows').textContent = fmtNum(d.writtenRows);
  document.getElementById('failedRows').textContent = fmtNum(d.failedRows);
  document.getElementById('eta').textContent = d.etaFormatted || '—';
  document.getElementById('speed').textContent = fmtNum(d.rowsPerSecond);
  document.getElementById('elapsed').textContent = d.elapsedSeconds ? fmtDuration(d.elapsedSeconds) : '—';

  document.getElementById('interimCount').textContent = fmtNum(d.interimCount);
  document.getElementById('mainCount').textContent = fmtNum(d.mainCount);

  const vEl = document.getElementById('verifyStatus');
  if (d.verified) {
    vEl.textContent = '✓ BALANCED'; vEl.className = 'verify-status balanced';
  } else if (status === 'COMPLETED' || status === 'FAILED') {
    vEl.textContent = '✗ UNBALANCED'; vEl.className = 'verify-status unbalanced';
  } else {
    vEl.textContent = 'PENDING'; vEl.className = 'verify-status pending';
  }

  if (status === 'COMPLETED') {
    addLog(`Job ${d.jobId} completed. Written: ${fmtNum(d.writtenRows)} rows. Verified: ${d.verified}`, 'success');
    showAlert('Transfer completed successfully!', 'success');
  } else if (status === 'FAILED') {
    addLog(`Job ${d.jobId} FAILED: ${d.errorMessage || 'Unknown error'}`, 'error');
    showAlert('Transfer FAILED: ' + (d.errorMessage || 'Check logs'), 'error');
  } else if (status === 'THROTTLED') {
    addLog('CPU throttle active — pausing batch writes', 'warn');
  } else if (status === 'ROLLING_BACK') {
    addLog('Rolling back partial data...', 'warn');
  } else if (status === 'CANCELLED') {
    addLog(`Job ${d.jobId} cancelled. ${d.currentPhase || ''}`, 'warn');
  }
}

async function fetchMetrics() {
  try {
    const resp = await fetch(`${API_BASE}/monitor/metrics`);
    if (!resp.ok) return;
    const d = await resp.json();

    const cpu = d.cpu || {}, mem = d.memory || {}, threads = d.threads || {}, pools = d.pools || {};

    setCpuGauge('cpuFill', 'cpuVal', cpu.systemPercent || 0);
    setCpuGauge('procCpuFill', 'procCpuVal', cpu.processPercent || 0);

    const memPct = mem.usedPercent || 0;
    const memFill = document.getElementById('memFill');
    memFill.style.width = memPct + '%';
    memFill.className = 'gauge-fill ' + getLevel(memPct);
    document.getElementById('memVal').textContent = memPct.toFixed(0) + '%';
    document.getElementById('memDetails').textContent = `${mem.usedMB || 0}MB / ${mem.maxMB || 0}MB`;

    document.getElementById('threadCount').textContent = threads.active || '—';
    document.getElementById('peakThreads').textContent = threads.peak || '—';
    document.getElementById('daemonThreads').textContent = threads.daemon || '—';
    document.getElementById('cpuCores').textContent = cpu.availableProcessors || '—';

    renderPool('interimPool', pools.interim || {});
    renderPool('mainPool', pools.main || {});
    renderPool('ctrlPool', pools.control || {});

    document.getElementById('connDot').className = 'conn-dot';
    document.getElementById('connText').textContent = 'Connected';
  } catch (e) {
    document.getElementById('connDot').className = 'conn-dot offline';
    document.getElementById('connText').textContent = 'Offline';
  }
}

function setCpuGauge(fillId, valId, val) {
  const fill = document.getElementById(fillId);
  fill.style.width = Math.min(100, val) + '%';
  fill.className = 'gauge-fill ' + getLevel(val);
  document.getElementById(valId).textContent = val.toFixed(1) + '%';
  document.getElementById(valId).style.color = val > 75 ? 'var(--red)' : val > 50 ? 'var(--yellow)' : 'var(--green)';
}

function getLevel(pct) {
  return pct >= 80 ? 'high' : pct >= 50 ? 'mid' : 'low';
}

function renderPool(prefix, pool) {
  const active = pool.active || 0, total = pool.maxSize || pool.total || 10;
  const pct = Math.min(100, (active / total) * 100);
  document.getElementById(prefix + 'Fill').style.width = pct + '%';
  document.getElementById(prefix + 'Text').textContent = `${active}/${total}`;
  document.getElementById(prefix + 'Info').textContent = `idle:${pool.idle || 0} wait:${pool.waiting || 0}`;
}

async function fetchControlInfo() {
  try {
    const resp = await fetch(`${API_BASE}/transfer/control-info`);
    if (!resp.ok) return;
    const d = await resp.json();
    document.getElementById('lastRunDate').textContent = d.lastRunDate || '—';
    document.getElementById('todayDate').textContent = d.todayDate || '—';
    const el = document.getElementById('alreadyRan');
    el.textContent = d.alreadyRanToday ? 'YES ✓' : 'NO';
    el.style.color = d.alreadyRanToday ? 'var(--green)' : 'var(--text2)';
  } catch (e) { /* offline */ }
}

function addLog(msg, type = 'info') {
  const body = document.getElementById('logBody');
  const line = document.createElement('div');
  line.className = 'log-line';
  const now = new Date().toLocaleTimeString('en-GB', { hour12: false });
  line.innerHTML = `<span class="log-time">${now}</span><span class="log-msg ${type}">${msg}</span>`;
  body.appendChild(line);
  body.scrollTop = body.scrollHeight;
  while (body.children.length > 100) body.removeChild(body.firstChild);
}

function clearLog() { document.getElementById('logBody').innerHTML = ''; }

let alertTimeout;
function showAlert(msg, type) {
  const el = document.getElementById('alertBox');
  el.textContent = msg;
  el.className = `alert visible ${type}`;
  if (alertTimeout) clearTimeout(alertTimeout);
  alertTimeout = setTimeout(() => el.classList.remove('visible'), 6000);
}

function fmtNum(n) {
  if (n == null || n === '') return '—';
  return Number(n).toLocaleString();
}

function fmtDuration(sec) {
  if (!sec) return '—';
  const m = Math.floor(sec / 60), s = sec % 60;
  return m > 0 ? `${m}m ${s}s` : `${s}s`;
}

function setButtonState(running) {
  document.getElementById('btnStart').disabled = running;
  document.getElementById('btnCancel').disabled = !running;
}

fetchControlInfo();
fetchMetrics();
refreshStatus();
metricsInterval = setInterval(fetchMetrics, 4000);
setInterval(fetchControlInfo, 30000);
addLog('Dashboard initialized. API: ' + API_BASE, 'info');
</script>
</body>
</html>
