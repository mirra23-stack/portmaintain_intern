/* PortMaintain CMMS v4.0 — Main Stylesheet */
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:ital,wght@0,400;0,700;1,400&family=Syne:wght@400;500;600;700;800&display=swap');
 
:root {
  --bg: #0a0e1a;
  --bg2: #0f1525;
  --bg3: #141c30;
  --surface: #1a2338;
  --surface2: #1f2b40;
  --border: #253050;
  --border2: #2e3d5e;
  --text: #e8edf5;
  --text2: #8a9bc0;
  --text3: #5a6b8a;
  --accent: #00d4ff;
  --accent2: #0099cc;
  --green: #00e87a;
  --yellow: #ffcc00;
  --orange: #ff8c00;
  --red: #ff3d5a;
  --purple: #9b59ff;
  --font-display: 'Syne', sans-serif;
  --font-mono: 'Space Mono', monospace;
  --nav-width: 220px;
  --header-h: 56px;
  --radius: 8px;
  --radius-lg: 12px;
  --shadow: 0 4px 24px rgba(0,0,0,0.4);
  --shadow-lg: 0 8px 48px rgba(0,0,0,0.6);
  --transition: 0.18s ease;
}
 
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
 
html { font-size: 14px; }
 
body {
  font-family: var(--font-display);
  background: var(--bg);
  color: var(--text);
  min-height: 100vh;
  overflow-x: hidden;
}
 
/* ── SCROLLBAR ─────────────────────────────────── */
::-webkit-scrollbar { width: 6px; height: 6px; }
::-webkit-scrollbar-track { background: var(--bg2); }
::-webkit-scrollbar-thumb { background: var(--border2); border-radius: 3px; }
 
/* ── AUTH SCREEN ───────────────────────────────── */
#auth-screen {
  display: flex; align-items: center; justify-content: center;
  min-height: 100vh;
  background: var(--bg);
  position: relative;
  overflow: hidden;
}
#auth-screen::before {
  content: '';
  position: absolute; inset: 0;
  background:
    radial-gradient(ellipse 80% 60% at 20% 50%, rgba(0,212,255,0.06) 0%, transparent 60%),
    radial-gradient(ellipse 60% 80% at 80% 50%, rgba(0,232,122,0.04) 0%, transparent 60%);
}
.auth-grid {
  position: absolute; inset: 0;
  background-image:
    linear-gradient(var(--border) 1px, transparent 1px),
    linear-gradient(90deg, var(--border) 1px, transparent 1px);
  background-size: 60px 60px;
  opacity: 0.3;
}
.auth-box {
  position: relative; z-index: 1;
  background: var(--surface);
  border: 1px solid var(--border2);
  border-radius: var(--radius-lg);
  padding: 48px 40px;
  width: 420px;
  box-shadow: var(--shadow-lg), 0 0 80px rgba(0,212,255,0.08);
}
.auth-logo {
  display: flex; align-items: center; gap: 12px;
  margin-bottom: 32px;
}
.auth-logo-icon {
  width: 42px; height: 42px;
  background: linear-gradient(135deg, var(--accent), var(--green));
  border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 20px;
}
.auth-logo h1 { font-size: 1.4rem; font-weight: 800; letter-spacing: -0.02em; }
.auth-logo span { color: var(--accent); }
.auth-subtitle { color: var(--text2); font-size: 0.8rem; margin-bottom: 28px; }
.auth-box h2 { font-size: 1.3rem; font-weight: 700; margin-bottom: 8px; }
 
/* ── APP SHELL ──────────────────────────────────── */
#app { display: none; min-height: 100vh; }
#app.visible { display: flex; flex-direction: column; }
 
/* ── TOPBAR ─────────────────────────────────────── */
#topbar {
  height: var(--header-h);
  background: var(--bg2);
  border-bottom: 1px solid var(--border);
  display: flex; align-items: center;
  padding: 0 20px 0 0;
  position: sticky; top: 0; z-index: 100;
  gap: 0;
}
.topbar-brand {
  width: var(--nav-width);
  display: flex; align-items: center; gap: 10px;
  padding: 0 20px;
  flex-shrink: 0;
  border-right: 1px solid var(--border);
  height: 100%;
}
.brand-icon {
  width: 28px; height: 28px;
  background: linear-gradient(135deg, var(--accent), var(--green));
  border-radius: 6px;
  display: flex; align-items: center; justify-content: center;
  font-size: 14px;
}
.brand-name { font-size: 0.95rem; font-weight: 800; letter-spacing: -0.01em; }
.brand-name span { color: var(--accent); }
.topbar-title {
  flex: 1; padding-left: 24px;
  font-size: 0.85rem; font-weight: 500; color: var(--text2);
  font-family: var(--font-mono);
}
.topbar-right { display: flex; align-items: center; gap: 12px; margin-left: auto; }
.topbar-badge {
  background: var(--red); color: #fff;
  font-size: 0.65rem; font-weight: 700; font-family: var(--font-mono);
  border-radius: 4px; padding: 2px 6px; letter-spacing: 0.05em;
}
.user-chip {
  display: flex; align-items: center; gap: 8px;
  background: var(--surface); border: 1px solid var(--border);
  border-radius: 20px; padding: 4px 12px 4px 6px;
  cursor: pointer; transition: border-color var(--transition);
}
.user-chip:hover { border-color: var(--accent); }
.user-avatar {
  width: 26px; height: 26px; border-radius: 50%;
  background: linear-gradient(135deg, var(--accent), var(--purple));
  display: flex; align-items: center; justify-content: center;
  font-size: 0.7rem; font-weight: 700;
}
.user-chip-name { font-size: 0.78rem; font-weight: 600; }
.topbar-btn {
  background: transparent; border: 1px solid var(--border);
  color: var(--text2); border-radius: var(--radius);
  padding: 6px 10px; cursor: pointer;
  font-size: 0.75rem; font-family: var(--font-display);
  transition: all var(--transition);
  display: flex; align-items: center; gap: 5px;
}
.topbar-btn:hover { border-color: var(--red); color: var(--red); }
 
/* ── LAYOUT ─────────────────────────────────────── */
.app-body { display: flex; flex: 1; min-height: calc(100vh - var(--header-h)); }
 
/* ── SIDEBAR ────────────────────────────────────── */
#sidebar {
  width: var(--nav-width);
  background: var(--bg2);
  border-right: 1px solid var(--border);
  flex-shrink: 0;
  overflow-y: auto;
  padding: 12px 0;
  position: sticky;
  top: var(--header-h);
  height: calc(100vh - var(--header-h));
}
.nav-section { padding: 12px 14px 4px; }
.nav-section-label {
  font-size: 0.6rem; font-weight: 700; letter-spacing: 0.12em;
  color: var(--text3); text-transform: uppercase;
  font-family: var(--font-mono);
}
.nav-item {
  display: flex; align-items: center; gap: 10px;
  padding: 8px 14px; border-radius: var(--radius);
  margin: 1px 8px; cursor: pointer;
  font-size: 0.82rem; font-weight: 500;
  color: var(--text2); transition: all var(--transition);
  text-decoration: none; position: relative;
}
.nav-item:hover { background: var(--surface); color: var(--text); }
.nav-item.active {
  background: rgba(0,212,255,0.1);
  color: var(--accent);
  border: 1px solid rgba(0,212,255,0.2);
}
.nav-item.active::before {
  content: ''; position: absolute; left: -9px; top: 50%;
  transform: translateY(-50%);
  width: 3px; height: 60%; background: var(--accent);
  border-radius: 0 2px 2px 0;
}
.nav-icon { font-size: 1rem; width: 18px; text-align: center; }
.nav-badge {
  margin-left: auto; background: var(--red);
  color: #fff; font-size: 0.6rem; font-weight: 700;
  font-family: var(--font-mono); border-radius: 3px; padding: 1px 5px;
}
.nav-badge.yellow { background: var(--yellow); color: #000; }
.nav-badge.green { background: var(--green); color: #000; }
 
/* ── MAIN CONTENT ───────────────────────────────── */
#main-content {
  flex: 1; overflow-y: auto;
  padding: 24px;
  background: var(--bg);
}
.page { display: none; animation: fadeIn 0.2s ease; }
.page.active { display: block; }
 
@keyframes fadeIn { from { opacity:0; transform:translateY(6px); } to { opacity:1; transform:translateY(0); } }
 
/* ── PAGE HEADER ────────────────────────────────── */
.page-header {
  display: flex; align-items: flex-start; justify-content: space-between;
  margin-bottom: 24px; gap: 16px;
}
.page-header-left h2 {
  font-size: 1.6rem; font-weight: 800; letter-spacing: -0.03em;
}
.page-header-left p { color: var(--text2); font-size: 0.82rem; margin-top: 3px; }
.page-actions { display: flex; gap: 8px; align-items: center; flex-wrap: wrap; }
 
/* ── STAT CARDS ─────────────────────────────────── */
.stat-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  gap: 12px; margin-bottom: 24px;
}
.stat-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-lg);
  padding: 18px;
  position: relative; overflow: hidden;
  transition: border-color var(--transition), transform var(--transition);
}
.stat-card:hover { border-color: var(--border2); transform: translateY(-1px); }
.stat-card::before {
  content: ''; position: absolute; top: 0; left: 0; right: 0;
  height: 2px; background: var(--accent-color, var(--accent));
}
.stat-card.green { --accent-color: var(--green); }
.stat-card.yellow { --accent-color: var(--yellow); }
.stat-card.red { --accent-color: var(--red); }
.stat-card.purple { --accent-color: var(--purple); }
.stat-card.orange { --accent-color: var(--orange); }
 
.stat-icon { font-size: 1.4rem; margin-bottom: 10px; }
.stat-label { font-size: 0.72rem; font-weight: 500; color: var(--text2); letter-spacing: 0.06em; text-transform: uppercase; font-family: var(--font-mono); }
.stat-value { font-size: 1.8rem; font-weight: 800; line-height: 1; margin: 4px 0 2px; }
.stat-sub { font-size: 0.72rem; color: var(--text3); }
 
/* ── BUTTONS ────────────────────────────────────── */
.btn {
  display: inline-flex; align-items: center; gap: 6px;
  padding: 8px 16px; border-radius: var(--radius);
  font-family: var(--font-display); font-size: 0.8rem; font-weight: 600;
  cursor: pointer; border: 1px solid transparent;
  transition: all var(--transition); text-decoration: none;
  white-space: nowrap;
}
.btn-primary { background: var(--accent); color: var(--bg); border-color: var(--accent); }
.btn-primary:hover { background: #00bfe8; }
.btn-success { background: var(--green); color: var(--bg); border-color: var(--green); }
.btn-success:hover { background: #00d070; }
.btn-danger { background: var(--red); color: #fff; border-color: var(--red); }
.btn-danger:hover { background: #e0002f; }
.btn-warning { background: var(--yellow); color: var(--bg); border-color: var(--yellow); }
.btn-outline { background: transparent; color: var(--text2); border-color: var(--border2); }
.btn-outline:hover { border-color: var(--accent); color: var(--accent); }
.btn-ghost { background: transparent; color: var(--text2); border-color: transparent; }
.btn-ghost:hover { color: var(--text); background: var(--surface2); }
.btn-sm { padding: 5px 10px; font-size: 0.74rem; }
.btn-xs { padding: 3px 8px; font-size: 0.68rem; }
.btn:disabled { opacity: 0.4; pointer-events: none; }
 
/* ── FORMS ──────────────────────────────────────── */
.form-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 14px; }
.form-grid-3 { grid-template-columns: 1fr 1fr 1fr; }
.form-full { grid-column: 1 / -1; }
.form-group { display: flex; flex-direction: column; gap: 5px; }
.form-label { font-size: 0.73rem; font-weight: 600; color: var(--text2); font-family: var(--font-mono); letter-spacing: 0.04em; }
.form-control {
  background: var(--bg2); border: 1px solid var(--border2);
  color: var(--text); border-radius: var(--radius);
  padding: 8px 12px; font-family: var(--font-display); font-size: 0.82rem;
  transition: border-color var(--transition);
  width: 100%;
}
.form-control:focus { outline: none; border-color: var(--accent); box-shadow: 0 0 0 2px rgba(0,212,255,0.12); }
.form-control::placeholder { color: var(--text3); }
select.form-control option { background: var(--bg2); }
textarea.form-control { resize: vertical; min-height: 80px; }
 
/* ── FILTERS BAR ────────────────────────────────── */
.filters-bar {
  display: flex; gap: 8px; align-items: center;
  flex-wrap: wrap; margin-bottom: 16px;
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-lg); padding: 10px 14px;
}
.filter-group { display: flex; gap: 6px; align-items: center; }
.filter-label { font-size: 0.7rem; color: var(--text3); font-family: var(--font-mono); }
.filter-select {
  background: var(--bg2); border: 1px solid var(--border);
  color: var(--text2); border-radius: var(--radius);
  padding: 5px 8px; font-size: 0.75rem; font-family: var(--font-display);
  cursor: pointer;
}
.search-input {
  background: var(--bg2); border: 1px solid var(--border);
  color: var(--text); border-radius: var(--radius);
  padding: 6px 10px; font-size: 0.8rem; font-family: var(--font-display);
  width: 220px;
}
.search-input:focus { outline: none; border-color: var(--accent); }
 
/* ── TABLE ──────────────────────────────────────── */
.table-wrap {
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-lg); overflow: hidden;
}
.data-table { width: 100%; border-collapse: collapse; font-size: 0.8rem; }
.data-table th {
  background: var(--bg2); padding: 10px 14px;
  text-align: left; font-size: 0.68rem; font-weight: 700;
  color: var(--text3); letter-spacing: 0.08em; text-transform: uppercase;
  font-family: var(--font-mono); border-bottom: 1px solid var(--border);
  white-space: nowrap;
}
.data-table td {
  padding: 10px 14px; border-bottom: 1px solid var(--border);
  vertical-align: middle;
}
.data-table tr:last-child td { border-bottom: none; }
.data-table tbody tr { transition: background var(--transition); }
.data-table tbody tr:hover { background: var(--surface2); }
 
/* ── BADGES / CHIPS ─────────────────────────────── */
.badge {
  display: inline-flex; align-items: center;
  padding: 2px 8px; border-radius: 4px;
  font-size: 0.68rem; font-weight: 700; font-family: var(--font-mono);
  letter-spacing: 0.04em; white-space: nowrap;
}
.badge-open { background: rgba(0,212,255,0.12); color: var(--accent); }
.badge-progress { background: rgba(255,204,0,0.12); color: var(--yellow); }
.badge-completed { background: rgba(0,232,122,0.12); color: var(--green); }
.badge-cancelled { background: rgba(255,61,90,0.12); color: var(--red); }
.badge-critical { background: rgba(255,61,90,0.12); color: var(--red); }
.badge-high { background: rgba(255,140,0,0.12); color: var(--orange); }
.badge-medium { background: rgba(255,204,0,0.12); color: var(--yellow); }
.badge-low { background: rgba(0,232,122,0.12); color: var(--green); }
.badge-ok { background: rgba(0,232,122,0.12); color: var(--green); }
.badge-warn { background: rgba(255,204,0,0.12); color: var(--yellow); }
.badge-alert { background: rgba(255,61,90,0.12); color: var(--red); }
.badge-offline { background: rgba(90,107,138,0.12); color: var(--text3); }
.badge-corrective { background: rgba(0,212,255,0.1); color: var(--accent); }
.badge-preventive { background: rgba(155,89,255,0.12); color: var(--purple); }
.badge-inspection { background: rgba(0,232,122,0.12); color: var(--green); }
.badge-emergency { background: rgba(255,61,90,0.15); color: var(--red); }
.badge-project { background: rgba(255,140,0,0.12); color: var(--orange); }
.badge-active { background: rgba(0,232,122,0.12); color: var(--green); }
.badge-inactive { background: rgba(90,107,138,0.12); color: var(--text3); }
.badge-decommissioned { background: rgba(255,61,90,0.12); color: var(--red); }
.badge-auto { background: rgba(155,89,255,0.12); color: var(--purple); border: 1px dashed rgba(155,89,255,0.3); }
.badge-due { background: rgba(255,204,0,0.12); color: var(--yellow); }
.badge-overdue { background: rgba(255,61,90,0.12); color: var(--red); }
 
/* ── MODAL ──────────────────────────────────────── */
.modal-overlay {
  display: none; position: fixed; inset: 0;
  background: rgba(0,0,0,0.7); backdrop-filter: blur(4px);
  z-index: 1000; align-items: center; justify-content: center;
  padding: 20px;
}
.modal-overlay.open { display: flex; animation: fadeIn 0.15s ease; }
.modal {
  background: var(--surface);
  border: 1px solid var(--border2);
  border-radius: var(--radius-lg);
  width: 100%; max-width: 620px;
  max-height: 90vh; display: flex; flex-direction: column;
  box-shadow: var(--shadow-lg);
}
.modal-lg { max-width: 820px; }
.modal-header {
  display: flex; align-items: center; justify-content: space-between;
  padding: 18px 20px; border-bottom: 1px solid var(--border);
  flex-shrink: 0;
}
.modal-title { font-size: 1rem; font-weight: 700; }
.modal-close {
  background: transparent; border: none; color: var(--text3);
  cursor: pointer; font-size: 1.2rem; padding: 4px; line-height: 1;
  transition: color var(--transition);
}
.modal-close:hover { color: var(--red); }
.modal-body { padding: 20px; overflow-y: auto; flex: 1; }
.modal-footer {
  padding: 14px 20px; border-top: 1px solid var(--border);
  display: flex; justify-content: flex-end; gap: 8px; flex-shrink: 0;
}
 
/* ── TOAST ──────────────────────────────────────── */
#toast-container {
  position: fixed; bottom: 20px; right: 20px; z-index: 9999;
  display: flex; flex-direction: column; gap: 8px;
  pointer-events: none;
}
.toast {
  background: var(--surface2); border: 1px solid var(--border2);
  border-radius: var(--radius); padding: 12px 16px;
  font-size: 0.8rem; font-weight: 500; max-width: 320px;
  box-shadow: var(--shadow); pointer-events: all;
  animation: slideUp 0.2s ease;
  display: flex; align-items: center; gap: 8px;
}
.toast.success { border-left: 3px solid var(--green); }
.toast.error { border-left: 3px solid var(--red); }
.toast.warning { border-left: 3px solid var(--yellow); }
.toast.info { border-left: 3px solid var(--accent); }
@keyframes slideUp { from { transform: translateY(12px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
 
/* ── CONFIRM DIALOG ─────────────────────────────── */
.confirm-overlay {
  display: none; position: fixed; inset: 0;
  background: rgba(0,0,0,0.7); backdrop-filter: blur(4px);
  z-index: 2000; align-items: center; justify-content: center;
}
.confirm-overlay.open { display: flex; }
.confirm-box {
  background: var(--surface2); border: 1px solid var(--border2);
  border-radius: var(--radius-lg); padding: 24px; max-width: 360px; width: 90%;
  box-shadow: var(--shadow-lg); text-align: center;
}
.confirm-box h3 { font-size: 1rem; margin-bottom: 8px; }
.confirm-box p { font-size: 0.82rem; color: var(--text2); margin-bottom: 20px; }
.confirm-actions { display: flex; gap: 8px; justify-content: center; }
 
/* ── CARDS ──────────────────────────────────────── */
.card {
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-lg); padding: 20px;
}
.card-header {
  display: flex; align-items: center; justify-content: space-between;
  margin-bottom: 16px;
}
.card-title { font-size: 0.9rem; font-weight: 700; }
 
/* ── GRID LAYOUTS ───────────────────────────────── */
.grid-2 { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }
.grid-3 { display: grid; grid-template-columns: repeat(3, 1fr); gap: 16px; }
.grid-4 { display: grid; grid-template-columns: repeat(4, 1fr); gap: 16px; }
.grid-auto { display: grid; grid-template-columns: repeat(auto-fill, minmax(280px, 1fr)); gap: 16px; }
 
/* ── CODE / MONO ELEMENTS ───────────────────────── */
.mono { font-family: var(--font-mono); font-size: 0.78rem; }
.code-tag {
  font-family: var(--font-mono); font-size: 0.7rem;
  background: var(--bg); border: 1px solid var(--border);
  border-radius: 4px; padding: 1px 6px; color: var(--text2);
}
 
/* ── PROGRESS ───────────────────────────────────── */
.progress-bar { background: var(--bg2); border-radius: 4px; height: 6px; overflow: hidden; }
.progress-fill { height: 100%; border-radius: 4px; transition: width 0.4s ease; }
 
/* ── IOT METRIC DISPLAY ─────────────────────────── */
.metric-chip {
  display: inline-flex; align-items: center; gap: 6px;
  background: var(--bg2); border: 1px solid var(--border);
  border-radius: var(--radius); padding: 5px 10px;
  font-family: var(--font-mono); font-size: 0.72rem;
}
.metric-chip.warn { border-color: rgba(255,204,0,0.3); color: var(--yellow); }
.metric-chip.alert { border-color: rgba(255,61,90,0.3); color: var(--red); }
 
/* ── EMPTY STATE ────────────────────────────────── */
.empty-state {
  text-align: center; padding: 60px 20px; color: var(--text3);
}
.empty-state .empty-icon { font-size: 2.5rem; margin-bottom: 12px; }
.empty-state p { font-size: 0.82rem; }
 
/* ── PAGINATION ─────────────────────────────────── */
.pagination {
  display: flex; align-items: center; justify-content: space-between;
  padding: 12px 16px; border-top: 1px solid var(--border);
  font-size: 0.78rem;
}
.pagination-info { color: var(--text2); }
.pagination-btns { display: flex; gap: 4px; }
.page-btn {
  background: var(--bg2); border: 1px solid var(--border);
  color: var(--text2); border-radius: var(--radius);
  padding: 5px 10px; cursor: pointer; font-size: 0.74rem;
  transition: all var(--transition);
}
.page-btn:hover, .page-btn.active { border-color: var(--accent); color: var(--accent); }
 
/* ── DETAIL VIEW ────────────────────────────────── */
.detail-grid {
  display: grid; grid-template-columns: 1fr 1fr;
  gap: 16px;
}
.detail-field { }
.detail-field-label { font-size: 0.68rem; font-weight: 700; color: var(--text3); text-transform: uppercase; letter-spacing: 0.08em; font-family: var(--font-mono); margin-bottom: 3px; }
.detail-field-value { font-size: 0.85rem; font-weight: 500; }
 
/* ── ZONE MAP ───────────────────────────────────── */
.map-container {
  background: var(--bg2); border: 1px solid var(--border);
  border-radius: var(--radius-lg); overflow: hidden; position: relative;
  aspect-ratio: 16/9;
}
.map-svg { width: 100%; height: 100%; }
.zone-rect { cursor: pointer; rx: 4; transition: opacity 0.2s; }
.zone-rect:hover { opacity: 0.8; }
.zone-label { font-family: var(--font-mono); font-size: 10px; fill: rgba(255,255,255,0.8); pointer-events: none; }
 
/* ── RESPONSIVE ─────────────────────────────────── */
@media (max-width: 900px) {
  :root { --nav-width: 200px; }
  .form-grid { grid-template-columns: 1fr; }
  .grid-2, .grid-3, .grid-4 { grid-template-columns: 1fr; }
}
@media (max-width: 700px) {
  #sidebar { display: none; }
  #main-content { padding: 16px; }
}
 
/* ── DASHBOARD SPECIFIC ─────────────────────────── */
.activity-feed { display: flex; flex-direction: column; gap: 0; }
.activity-item {
  display: flex; gap: 12px; padding: 10px 0;
  border-bottom: 1px solid var(--border);
}
.activity-item:last-child { border-bottom: none; }
.activity-dot {
  width: 8px; height: 8px; border-radius: 50%;
  background: var(--accent); flex-shrink: 0; margin-top: 5px;
}
.activity-dot.red { background: var(--red); }
.activity-dot.green { background: var(--green); }
.activity-dot.yellow { background: var(--yellow); }
.activity-text { font-size: 0.78rem; color: var(--text2); line-height: 1.4; }
.activity-time { font-size: 0.68rem; color: var(--text3); font-family: var(--font-mono); margin-top: 2px; }
 
/* ── SENSOR CARD ────────────────────────────────── */
.sensor-card {
  background: var(--surface); border: 1px solid var(--border);
  border-radius: var(--radius-lg); padding: 16px;
  transition: all var(--transition); cursor: default;
}
.sensor-card.alert { border-color: rgba(255,61,90,0.3); box-shadow: 0 0 12px rgba(255,61,90,0.08); }
.sensor-card.warn { border-color: rgba(255,204,0,0.25); }
.sensor-card.ok { border-color: rgba(0,232,122,0.2); }
.sensor-header { display: flex; justify-content: space-between; align-items: flex-start; margin-bottom: 12px; }
.sensor-name { font-weight: 700; font-size: 0.88rem; }
.sensor-code { font-family: var(--font-mono); font-size: 0.68rem; color: var(--text3); margin-top: 1px; }
.sensor-metrics { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 8px; }
 
/* ── INVENTORY STOCK BAR ────────────────────────── */
.stock-bar-wrap { display: flex; align-items: center; gap: 8px; }
.stock-level {
  flex: 1; height: 5px; background: var(--bg2);
  border-radius: 3px; overflow: hidden;
}
.stock-level-fill {
  height: 100%; border-radius: 3px; transition: width 0.3s;
}
.stock-level-fill.good { background: var(--green); }
.stock-level-fill.low { background: var(--yellow); }
.stock-level-fill.out { background: var(--red); }
 
/* ── SECTION DIVIDER ────────────────────────────── */
.section-divider {
  display: flex; align-items: center; gap: 12px;
  margin: 20px 0 16px; color: var(--text3);
  font-size: 0.68rem; font-weight: 700; text-transform: uppercase;
  letter-spacing: 0.1em; font-family: var(--font-mono);
}
.section-divider::before, .section-divider::after {
  content: ''; flex: 1; height: 1px; background: var(--border);
}
 
/* ── STATUS DOT ─────────────────────────────────── */
.status-dot {
  display: inline-block; width: 7px; height: 7px;
  border-radius: 50%; margin-right: 5px;
  vertical-align: middle;
}
.status-dot.green { background: var(--green); box-shadow: 0 0 6px var(--green); }
.status-dot.red { background: var(--red); box-shadow: 0 0 6px var(--red); }
.status-dot.yellow { background: var(--yellow); }
.status-dot.gray { background: var(--text3); }
