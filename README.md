[index (1).html](https://github.com/user-attachments/files/26871609/index.1.html)
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>Shrishti's JEE Master Planner 2027</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700&family=Syne:wght@400;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
<style>
  :root {
    --bg: #0a0a0f;
    --bg2: #111118;
    --bg3: #1a1a24;
    --bg4: #22222f;
    --border: #2a2a3a;
    --text: #e8e8f0;
    --text2: #9090a8;
    --text3: #5a5a72;
    --accent: #7c6fff;
    --accent2: #ff6fa8;
    --accent3: #6fffd4;
    --gold: #ffd166;
    --phy: #60a5fa;
    --che: #4ade80;
    --mat: #fb923c;
    --danger: #f87171;
    --card: #14141e;
    --card2: #1c1c28;
  }

  * { box-sizing: border-box; margin: 0; padding: 0; }

  body {
    font-family: 'Space Grotesk', sans-serif;
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* HEADER */
  .header {
    background: linear-gradient(135deg, #0a0a0f 0%, #141420 50%, #0a0a0f 100%);
    border-bottom: 1px solid var(--border);
    padding: 14px 20px;
    display: flex;
    align-items: center;
    justify-content: space-between;
    position: sticky; top: 0; z-index: 100;
    backdrop-filter: blur(20px);
  }
  .header-logo {
    font-family: 'Syne', sans-serif;
    font-weight: 800;
    font-size: 1.1rem;
    background: linear-gradient(135deg, var(--accent), var(--accent2));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }
  .header-sub { font-size: 0.7rem; color: var(--text3); font-family: 'JetBrains Mono', monospace; }
  .streak-badge {
    background: linear-gradient(135deg, #ff6b35, #f7c59f);
    color: #1a0a00;
    font-weight: 700;
    font-size: 0.8rem;
    padding: 6px 12px;
    border-radius: 20px;
    display: flex; align-items: center; gap: 4px;
    font-family: 'Syne', sans-serif;
  }

  /* TAB NAV */
  .tab-nav {
    position: fixed;
    bottom: 0; left: 0; right: 0;
    background: var(--bg2);
    border-top: 1px solid var(--border);
    display: flex;
    z-index: 200;
    padding-bottom: env(safe-area-inset-bottom);
  }
  .tab-btn {
    flex: 1;
    display: flex; flex-direction: column; align-items: center;
    padding: 8px 4px 6px;
    background: none; border: none; cursor: pointer;
    color: var(--text3);
    font-size: 0.55rem;
    font-family: 'Space Grotesk', sans-serif;
    transition: all 0.2s;
    gap: 2px;
  }
  .tab-btn .ti { font-size: 1.3rem; transition: transform 0.2s; }
  .tab-btn.active { color: var(--accent); }
  .tab-btn.active .ti { transform: scale(1.1); }
  .tab-btn:hover { color: var(--text); }

  /* MAIN CONTENT */
  .main { padding: 16px 16px 80px; max-width: 900px; margin: 0 auto; }

  /* PAGES */
  .page { display: none; animation: fadeUp 0.3s ease; }
  .page.active { display: block; }
  @keyframes fadeUp { from { opacity:0; transform:translateY(8px); } to { opacity:1; transform:translateY(0); } }

  /* CARDS */
  .card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 16px;
    margin-bottom: 14px;
  }
  .card2 {
    background: var(--card2);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 12px;
    margin-bottom: 10px;
  }

  /* SECTION TITLES */
  .section-title {
    font-family: 'Syne', sans-serif;
    font-size: 1rem;
    font-weight: 700;
    color: var(--text);
    margin-bottom: 12px;
    display: flex; align-items: center; gap: 8px;
  }
  .section-title span { color: var(--text3); font-size: 0.75rem; font-weight: 400; font-family: 'Space Grotesk', sans-serif; }

  /* PROGRESS BAR */
  .prog-wrap { background: var(--bg4); border-radius: 100px; height: 8px; overflow: hidden; }
  .prog-fill { height: 100%; border-radius: 100px; transition: width 0.6s ease; }
  .prog-phy { background: linear-gradient(90deg, #3b82f6, #60a5fa); }
  .prog-che { background: linear-gradient(90deg, #16a34a, #4ade80); }
  .prog-mat { background: linear-gradient(90deg, #ea580c, #fb923c); }
  .prog-all { background: linear-gradient(90deg, var(--accent), var(--accent2)); }

  /* STAT GRID */
  .stat-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 10px; }
  .stat-box {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 14px;
    text-align: center;
  }
  .stat-num { font-family: 'Syne', sans-serif; font-size: 1.6rem; font-weight: 800; }
  .stat-lbl { font-size: 0.7rem; color: var(--text3); margin-top: 2px; }

  /* SCHEDULE BLOCKS */
  .day-tabs {
    display: flex; gap: 6px; overflow-x: auto; margin-bottom: 14px;
    scrollbar-width: none; padding-bottom: 4px;
  }
  .day-tabs::-webkit-scrollbar { display: none; }
  .day-tab {
    min-width: 56px;
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 8px 10px;
    text-align: center;
    cursor: pointer;
    font-size: 0.7rem;
    font-weight: 600;
    transition: all 0.2s;
    color: var(--text2);
  }
  .day-tab.active {
    background: var(--accent);
    border-color: var(--accent);
    color: white;
  }
  .day-tab .d-name { font-family: 'Syne', sans-serif; font-size: 0.85rem; font-weight: 700; }

  .block {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 12px 14px;
    margin-bottom: 8px;
    cursor: pointer;
    transition: all 0.2s;
    position: relative;
    overflow: hidden;
  }
  .block::before {
    content: '';
    position: absolute; left: 0; top: 0; bottom: 0;
    width: 3px;
  }
  .block.phy::before { background: var(--phy); }
  .block.che::before { background: var(--che); }
  .block.mat::before { background: var(--mat); }
  .block.break::before { background: var(--text3); }
  .block.coaching::before { background: var(--accent2); }
  .block.personal::before { background: var(--gold); }
  .block.sleep::before { background: #6366f1; }
  .block.done { opacity: 0.6; }
  .block.done .block-title { text-decoration: line-through; }

  .block-cb {
    width: 20px; height: 20px;
    border: 2px solid var(--border);
    border-radius: 6px;
    background: transparent;
    cursor: pointer;
    flex-shrink: 0;
    margin-top: 1px;
    display: flex; align-items: center; justify-content: center;
    transition: all 0.2s;
    font-size: 0.85rem;
  }
  .block-cb.checked { background: var(--accent); border-color: var(--accent); color: white; }

  .block-body { flex: 1; min-width: 0; }
  .block-time { font-family: 'JetBrains Mono', monospace; font-size: 0.65rem; color: var(--text3); margin-bottom: 2px; }
  .block-title { font-weight: 600; font-size: 0.9rem; }
  .block-sub { font-size: 0.72rem; color: var(--text2); margin-top: 2px; }

  .block-tag {
    font-size: 0.6rem;
    font-weight: 700;
    padding: 2px 7px;
    border-radius: 6px;
    align-self: flex-start;
    text-transform: uppercase;
    letter-spacing: 0.5px;
    white-space: nowrap;
  }
  .tag-phy { background: rgba(96,165,250,0.15); color: var(--phy); }
  .tag-che { background: rgba(74,222,128,0.15); color: var(--che); }
  .tag-mat { background: rgba(251,146,60,0.15); color: var(--mat); }
  .tag-break { background: rgba(144,144,168,0.1); color: var(--text3); }
  .tag-coaching { background: rgba(255,111,168,0.15); color: var(--accent2); }
  .tag-personal { background: rgba(255,209,102,0.15); color: var(--gold); }
  .tag-sleep { background: rgba(99,102,241,0.15); color: #818cf8; }

  /* MODAL */
  .modal-bg {
    position: fixed; inset: 0;
    background: rgba(0,0,0,0.75);
    z-index: 500;
    display: none;
    align-items: flex-end;
    justify-content: center;
    backdrop-filter: blur(4px);
  }
  .modal-bg.open { display: flex; }
  .modal {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 24px 24px 0 0;
    width: 100%; max-width: 600px;
    padding: 24px;
    max-height: 90vh;
    overflow-y: auto;
    animation: slideUp 0.3s ease;
  }
  @keyframes slideUp { from { transform: translateY(30px); opacity: 0; } to { transform: translateY(0); opacity: 1; } }
  .modal-handle { width: 36px; height: 4px; background: var(--border); border-radius: 2px; margin: 0 auto 20px; }
  .modal h3 { font-family: 'Syne', sans-serif; font-size: 1.1rem; margin-bottom: 16px; }

  /* INPUTS */
  .input-group { margin-bottom: 14px; }
  .input-label { font-size: 0.75rem; color: var(--text2); margin-bottom: 6px; display: block; font-weight: 500; }
  input[type=text], input[type=number], input[type=date], select, textarea {
    width: 100%;
    background: var(--bg3);
    border: 1px solid var(--border);
    border-radius: 10px;
    color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    font-size: 0.9rem;
    padding: 10px 12px;
    outline: none;
    transition: border-color 0.2s;
  }
  input:focus, select:focus, textarea:focus { border-color: var(--accent); }
  textarea { resize: vertical; min-height: 70px; }
  select option { background: var(--bg3); }

  .marks-row { display: grid; grid-template-columns: 1fr auto 1fr; gap: 8px; align-items: center; }
  .marks-sep { text-align: center; color: var(--text3); font-size: 1.2rem; }

  /* BUTTONS */
  .btn {
    display: inline-flex; align-items: center; justify-content: center; gap: 6px;
    padding: 10px 20px;
    border: none; border-radius: 10px;
    cursor: pointer;
    font-family: 'Space Grotesk', sans-serif;
    font-size: 0.85rem;
    font-weight: 600;
    transition: all 0.2s;
  }
  .btn-primary { background: var(--accent); color: white; }
  .btn-primary:hover { background: #6a5de8; transform: translateY(-1px); }
  .btn-danger { background: rgba(248,113,113,0.15); color: var(--danger); border: 1px solid rgba(248,113,113,0.3); }
  .btn-danger:hover { background: rgba(248,113,113,0.25); }
  .btn-ghost { background: var(--bg4); color: var(--text2); }
  .btn-ghost:hover { background: var(--bg3); color: var(--text); }
  .btn-full { width: 100%; }

  /* STARS */
  .star-row { display: flex; gap: 6px; }
  .star { font-size: 1.3rem; cursor: pointer; opacity: 0.4; transition: all 0.15s; }
  .star.active { opacity: 1; }

  /* TEST CARDS */
  .test-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 14px;
    padding: 16px;
    margin-bottom: 10px;
    cursor: pointer;
    transition: all 0.2s;
  }
  .test-card:hover { border-color: var(--accent); transform: translateY(-1px); }
  .test-card-header { display: flex; align-items: flex-start; justify-content: space-between; margin-bottom: 10px; }
  .test-card-title { font-family: 'Syne', sans-serif; font-weight: 700; font-size: 0.95rem; }
  .test-card-meta { font-size: 0.7rem; color: var(--text3); font-family: 'JetBrains Mono', monospace; }
  .test-card-scores { display: flex; gap: 10px; flex-wrap: wrap; margin-bottom: 8px; }
  .score-chip { font-size: 0.72rem; font-weight: 600; padding: 3px 8px; border-radius: 6px; }
  .score-phy { background: rgba(96,165,250,0.15); color: var(--phy); }
  .score-che { background: rgba(74,222,128,0.15); color: var(--che); }
  .score-mat { background: rgba(251,146,60,0.15); color: var(--mat); }
  .score-total { background: rgba(124,111,255,0.15); color: var(--accent); font-size: 0.85rem; }

  /* CHART */
  .chart-wrap { overflow-x: auto; }
  svg.bar-chart { width: 100%; }

  /* REVISION CHAPTER CARDS */
  .rev-card {
    background: var(--card);
    border: 1px solid var(--border);
    border-radius: 12px;
    padding: 14px;
    margin-bottom: 8px;
    transition: all 0.2s;
  }
  .rev-card:hover { border-color: var(--border); }
  .rev-card-header { display: flex; align-items: center; gap: 8px; margin-bottom: 8px; }
  .subj-tag { font-size: 0.6rem; font-weight: 700; padding: 2px 7px; border-radius: 6px; text-transform: uppercase; letter-spacing: 0.5px; }
  .subj-phy { background: rgba(96,165,250,0.15); color: var(--phy); }
  .subj-che { background: rgba(74,222,128,0.15); color: var(--che); }
  .subj-mat { background: rgba(251,146,60,0.15); color: var(--mat); }
  .imp-tag { font-size: 0.6rem; padding: 2px 6px; border-radius: 6px; }
  .imp-high { background: rgba(248,113,113,0.15); color: #f87171; }
  .imp-med { background: rgba(251,191,36,0.15); color: #fbbf24; }
  .imp-low { background: rgba(74,222,128,0.15); color: var(--che); }

  .rev-title { font-weight: 600; font-size: 0.9rem; flex: 1; }
  .rev-controls { display: flex; gap: 8px; align-items: center; flex-wrap: wrap; }

  .status-btn {
    font-size: 0.72rem; font-weight: 600;
    padding: 5px 10px; border-radius: 8px;
    cursor: pointer; border: none;
    transition: all 0.2s;
    font-family: 'Space Grotesk', sans-serif;
  }
  .status-0 { background: rgba(90,90,114,0.2); color: var(--text3); }
  .status-1 { background: rgba(251,191,36,0.15); color: #fbbf24; }
  .status-2 { background: rgba(74,222,128,0.15); color: var(--che); }
  .status-3 { background: rgba(248,113,113,0.15); color: var(--danger); }

  .pyq-cb { accent-color: var(--accent); width: 14px; height: 14px; cursor: pointer; }
  .quality-row { display: flex; gap: 5px; margin-top: 8px; }
  .q-btn { font-size: 0.7rem; padding: 3px 8px; border-radius: 6px; cursor: pointer; border: 1px solid var(--border); background: var(--bg3); color: var(--text2); transition: all 0.2s; }
  .q-btn.active { border-color: var(--accent); color: var(--accent); background: rgba(124,111,255,0.1); }

  .rev-notes { width: 100%; background: var(--bg3); border: 1px solid var(--border); border-radius: 8px; color: var(--text); font-family: 'Space Grotesk', sans-serif; font-size: 0.78rem; padding: 7px 10px; margin-top: 8px; resize: none; outline: none; min-height: 50px; transition: border-color 0.2s; }
  .rev-notes:focus { border-color: var(--accent); }

  /* FILTER ROW */
  .filter-row { display: flex; gap: 6px; overflow-x: auto; margin-bottom: 14px; padding-bottom: 4px; scrollbar-width: none; }
  .filter-row::-webkit-scrollbar { display: none; }
  .filter-chip {
    padding: 5px 12px; border-radius: 20px;
    font-size: 0.72rem; font-weight: 600;
    cursor: pointer;
    border: 1px solid var(--border);
    background: var(--bg3);
    color: var(--text2);
    white-space: nowrap;
    transition: all 0.2s;
    font-family: 'Space Grotesk', sans-serif;
  }
  .filter-chip.active { background: var(--accent); border-color: var(--accent); color: white; }

  .search-input {
    width: 100%; background: var(--bg3); border: 1px solid var(--border);
    border-radius: 10px; color: var(--text);
    font-family: 'Space Grotesk', sans-serif;
    font-size: 0.85rem; padding: 10px 14px;
    outline: none; margin-bottom: 12px;
    transition: border-color 0.2s;
  }
  .search-input:focus { border-color: var(--accent); }

  /* DATES KEY */
  .date-item { display: flex; gap: 12px; align-items: flex-start; padding: 12px 0; border-bottom: 1px solid var(--border); }
  .date-item:last-child { border-bottom: none; }
  .date-badge { background: var(--bg3); border: 1px solid var(--border); border-radius: 10px; padding: 6px 10px; text-align: center; min-width: 50px; }
  .date-badge .d-num { font-family: 'Syne', sans-serif; font-size: 1.2rem; font-weight: 800; }
  .date-badge .d-mon { font-size: 0.65rem; color: var(--text3); text-transform: uppercase; }
  .date-info h4 { font-weight: 600; font-size: 0.9rem; }
  .date-info p { font-size: 0.75rem; color: var(--text3); margin-top: 3px; }
  .days-left { font-size: 0.7rem; background: rgba(124,111,255,0.1); color: var(--accent); padding: 2px 7px; border-radius: 6px; display: inline-block; margin-top: 4px; font-weight: 600; }

  /* GITHUB GUIDE */
  .step-card {
    background: var(--bg3);
    border: 1px solid var(--border);
    border-left: 3px solid var(--accent);
    border-radius: 0 12px 12px 0;
    padding: 14px;
    margin-bottom: 10px;
  }
  .step-num { font-family: 'JetBrains Mono', monospace; font-size: 0.7rem; color: var(--accent); font-weight: 700; }
  .step-card h4 { font-size: 0.9rem; font-weight: 600; margin: 4px 0 6px; }
  .step-card p, .step-card li { font-size: 0.8rem; color: var(--text2); line-height: 1.6; }
  .step-card ul { padding-left: 16px; }
  code { background: var(--bg4); padding: 2px 6px; border-radius: 4px; font-family: 'JetBrains Mono', monospace; font-size: 0.8rem; color: var(--accent3); }

  /* DONUT */
  .donut-wrap { display: flex; justify-content: center; margin: 10px 0; }

  /* ANNOUNCEMENT BAR */
  .announce {
    background: linear-gradient(135deg, rgba(124,111,255,0.1), rgba(255,111,168,0.1));
    border: 1px solid rgba(124,111,255,0.2);
    border-radius: 12px;
    padding: 12px 16px;
    margin-bottom: 14px;
    font-size: 0.8rem;
    color: var(--text2);
  }
  .announce strong { color: var(--text); }

  /* DIVIDER */
  .divider { border: none; border-top: 1px solid var(--border); margin: 16px 0; }

  /* WARNING BOX */
  .warn-box { background: rgba(251,191,36,0.08); border: 1px solid rgba(251,191,36,0.2); border-radius: 10px; padding: 10px 12px; font-size: 0.78rem; color: #fbbf24; display: flex; gap: 8px; align-items: flex-start; }
  .ok-box { background: rgba(74,222,128,0.08); border: 1px solid rgba(74,222,128,0.2); border-radius: 10px; padding: 10px 12px; font-size: 0.78rem; color: var(--che); display: flex; gap: 8px; align-items: flex-start; }

  /* Tooltip label */
  .tip-lbl { font-size: 0.68rem; color: var(--text3); margin-top: 4px; }

  /* Responsive */
  @media(min-width:600px) {
    .stat-grid { grid-template-columns: repeat(4, 1fr); }
    .main { padding: 20px 24px 90px; }
  }
</style>
</head>
<body>

<!-- HEADER -->
<div class="header">
  <div>
    <div class="header-logo">✦ Shrishti's Planner</div>
    <div class="header-sub">JEE 2027 · CGBSE 12th · PW Online</div>
  </div>
  <div class="streak-badge" id="streakBadge">🔥 <span id="streakNum">0</span> day streak</div>
</div>

<!-- MAIN -->
<div class="main">

  <!-- ===== SCHEDULE PAGE ===== -->
  <div class="page active" id="page-schedule">
    <div class="announce">
      🌞 <strong>Summer Holidays!</strong> No school for 2 months — maximum JEE prep time. Coaching: Mon–Sat 7–10:30 PM.
    </div>
    <!-- Daily Progress -->
    <div class="card" style="margin-bottom:14px;">
      <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:10px;">
        <div class="section-title" style="margin:0;">Today's Progress</div>
        <div style="font-family:'JetBrains Mono',monospace;font-size:0.8rem;color:var(--accent);" id="progPct">0%</div>
      </div>
      <div class="prog-wrap"><div class="prog-fill prog-all" id="progBar" style="width:0%"></div></div>
      <div style="margin-top:8px;font-size:0.72rem;color:var(--text3);" id="progLbl">0 of 0 tasks done</div>
    </div>

    <!-- Day Tabs -->
    <div class="day-tabs" id="dayTabs"></div>

    <!-- Schedule Blocks -->
    <div id="scheduleBlocks"></div>
    <button class="btn btn-ghost" style="width:100%;margin-top:6px;" onclick="openAddBlock()">+ Add custom block</button>
  </div>

  <!-- ===== STATS PAGE ===== -->
  <div class="page" id="page-stats">
    <div class="section-title">📊 Weekly Stats</div>
    <div class="stat-grid" style="margin-bottom:14px;">
      <div class="stat-box"><div class="stat-num" id="s-total">0</div><div class="stat-lbl">Total Tasks Done</div></div>
      <div class="stat-box"><div class="stat-num" id="s-streak">0</div><div class="stat-lbl">Day Streak 🔥</div></div>
      <div class="stat-box"><div class="stat-num" id="s-tests">0</div><div class="stat-lbl">Tests Logged</div></div>
      <div class="stat-box"><div class="stat-num" id="s-rev">0</div><div class="stat-lbl">Chapters Done</div></div>
    </div>
    <div class="card">
      <div class="section-title">Hours by Subject (This Week)</div>
      <div style="margin-bottom:12px;">
        <div style="display:flex;justify-content:space-between;font-size:0.75rem;margin-bottom:4px;"><span style="color:var(--phy);">🔵 Physics</span><span id="hrs-phy">0h</span></div>
        <div class="prog-wrap"><div class="prog-fill prog-phy" id="bar-phy" style="width:0%"></div></div>
      </div>
      <div style="margin-bottom:12px;">
        <div style="display:flex;justify-content:space-between;font-size:0.75rem;margin-bottom:4px;"><span style="color:var(--che);">🟢 Chemistry</span><span id="hrs-che">0h</span></div>
        <div class="prog-wrap"><div class="prog-fill prog-che" id="bar-che" style="width:0%"></div></div>
      </div>
      <div>
        <div style="display:flex;justify-content:space-between;font-size:0.75rem;margin-bottom:4px;"><span style="color:var(--mat);">🟠 Maths</span><span id="hrs-mat">0h</span></div>
        <div class="prog-wrap"><div class="prog-fill prog-mat" id="bar-mat" style="width:0%"></div></div>
      </div>
    </div>
    <div class="card">
      <div class="section-title">Completion by Day</div>
      <div id="weekChart"></div>
    </div>
  </div>

  <!-- ===== TESTS PAGE ===== -->
  <div class="page" id="page-tests">
    <div class="section-title">📝 Test Results Tracker</div>

    <!-- Analytics top -->
    <div class="card" id="testAnalytics" style="display:none;">
      <div class="section-title">Analytics <span id="testCount"></span></div>
      <div class="stat-grid" style="margin-bottom:14px;">
        <div class="stat-box"><div class="stat-num" id="t-best" style="color:var(--gold);">—</div><div class="stat-lbl">Best Score 🏆</div></div>
        <div class="stat-box"><div class="stat-num" id="t-latest">—</div><div class="stat-lbl">Latest Score</div></div>
        <div class="stat-box"><div class="stat-num" id="t-improve">—</div><div class="stat-lbl">Improvement</div></div>
        <div class="stat-box"><div class="stat-num" id="t-weak">—</div><div class="stat-lbl">Needs Work</div></div>
      </div>
      <div style="margin-bottom:8px;">
        <div style="font-size:0.72rem;color:var(--text3);margin-bottom:6px;">Subject Averages</div>
        <div style="display:flex;gap:8px;flex-wrap:wrap;">
          <span class="score-chip score-phy" id="avg-phy">Phy: —</span>
          <span class="score-chip score-che" id="avg-che">Che: —</span>
          <span class="score-chip score-mat" id="avg-mat">Mat: —</span>
        </div>
      </div>
      <div class="section-title" style="margin-top:12px;">Score Trend</div>
      <div id="scoreChart"></div>
    </div>

    <button class="btn btn-primary btn-full" onclick="openTestModal()" style="margin-bottom:14px;">+ Log New Test Result</button>
    <div id="testList"></div>
    <div id="noTests" style="text-align:center;color:var(--text3);padding:40px 0;font-size:0.85rem;">No tests logged yet. Add your first test! 📝</div>
  </div>

  <!-- ===== REVISION PAGE ===== -->
  <div class="page" id="page-revision">
    <div class="section-title">📗 11th Syllabus Revision Tracker</div>

    <!-- Revision settings -->
    <div class="card" id="revSettings">
      <div style="display:flex;gap:10px;flex-wrap:wrap;align-items:flex-end;">
        <div class="input-group" style="flex:1;min-width:120px;margin:0;">
          <label class="input-label">Revision Start Date</label>
          <input type="date" id="revStart" onchange="saveRevDates()">
        </div>
        <div class="input-group" style="flex:1;min-width:120px;margin:0;">
          <label class="input-label">Target End Date</label>
          <input type="date" id="revEnd" onchange="saveRevDates()">
        </div>
      </div>
    </div>

    <!-- Dashboard -->
    <div class="card" id="revDash">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:10px;">
        <div class="section-title" style="margin:0;">Overall Progress</div>
        <div style="font-family:'JetBrains Mono',monospace;font-size:0.8rem;color:var(--accent);" id="revPct">0%</div>
      </div>
      <div class="prog-wrap" style="margin-bottom:10px;"><div class="prog-fill prog-all" id="revBar" style="width:0%"></div></div>
      <div id="revStatusMsg" style="margin-bottom:12px;"></div>
      <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:12px;">
        <div class="stat-box" style="padding:10px;">
          <div style="font-size:0.65rem;color:var(--phy);font-weight:700;margin-bottom:4px;">⚛ PHYSICS</div>
          <div class="prog-wrap"><div class="prog-fill prog-phy" id="rev-phy-bar" style="width:0%"></div></div>
          <div style="font-size:0.7rem;color:var(--text2);margin-top:4px;" id="rev-phy-lbl">0/11</div>
        </div>
        <div class="stat-box" style="padding:10px;">
          <div style="font-size:0.65rem;color:var(--che);font-weight:700;margin-bottom:4px;">⚗ CHEM</div>
          <div class="prog-wrap"><div class="prog-fill prog-che" id="rev-che-bar" style="width:0%"></div></div>
          <div style="font-size:0.7rem;color:var(--text2);margin-top:4px;" id="rev-che-lbl">0/14</div>
        </div>
        <div class="stat-box" style="padding:10px;">
          <div style="font-size:0.65rem;color:var(--mat);font-weight:700;margin-bottom:4px;">∑ MATHS</div>
          <div class="prog-wrap"><div class="prog-fill prog-mat" id="rev-mat-bar" style="width:0%"></div></div>
          <div style="font-size:0.7rem;color:var(--text2);margin-top:4px;" id="rev-mat-lbl">0/16</div>
        </div>
      </div>
      <div style="display:flex;gap:10px;flex-wrap:wrap;">
        <div class="stat-box" style="flex:1;padding:10px;"><div style="font-size:1rem;font-weight:800;font-family:'Syne',sans-serif;" id="revHrsDone">0h</div><div class="stat-lbl">Hours Done</div></div>
        <div class="stat-box" style="flex:1;padding:10px;"><div style="font-size:1rem;font-weight:800;font-family:'Syne',sans-serif;" id="revHrsLeft">0h</div><div class="stat-lbl">Hours Left</div></div>
        <div class="stat-box" style="flex:1;padding:10px;"><div style="font-size:1rem;font-weight:800;font-family:'Syne',sans-serif;" id="revDaysLeft">—</div><div class="stat-lbl">Days Left</div></div>
      </div>
    </div>

    <!-- Suggested chapter -->
    <div class="card" id="suggestCard" style="border-color:rgba(124,111,255,0.3);display:none;">
      <div class="section-title">🎯 Today's Suggested Chapter</div>
      <div id="suggestContent"></div>
    </div>

    <!-- Filters -->
    <input type="text" class="search-input" placeholder="🔍 Search chapters..." oninput="renderRevision()" id="revSearch">
    <div class="filter-row" id="revFilters">
      <button class="filter-chip active" data-filter="all" onclick="setRevFilter(this,'all')">All</button>
      <button class="filter-chip" data-filter="phy" onclick="setRevFilter(this,'phy')">⚛ Physics</button>
      <button class="filter-chip" data-filter="che" onclick="setRevFilter(this,'che')">⚗ Chemistry</button>
      <button class="filter-chip" data-filter="mat" onclick="setRevFilter(this,'mat')">∑ Maths</button>
      <button class="filter-chip" data-filter="high" onclick="setRevFilter(this,'high')">🔴 High Priority</button>
      <button class="filter-chip" data-filter="needsrev" onclick="setRevFilter(this,'needsrev')">🔁 Needs Revision</button>
      <button class="filter-chip" data-filter="done" onclick="setRevFilter(this,'done')">✅ Done</button>
      <button class="filter-chip" data-filter="notstarted" onclick="setRevFilter(this,'notstarted')">⬜ Not Started</button>
    </div>
    <div id="revisionList"></div>
  </div>

  <!-- ===== DATES PAGE ===== -->
  <div class="page" id="page-dates">
    <div class="section-title">🗓️ Key Dates</div>
    <div class="card" id="keyDates"></div>
    <div class="section-title" style="margin-top:4px;">Daily Routine Reference</div>
    <div class="card">
      <div style="font-size:0.8rem;line-height:2;color:var(--text2);">
        <div>⏰ <strong>7:30 AM</strong> — Wake up</div>
        <div>☀️ <strong>8:00–8:30 AM</strong> — Breakfast</div>
        <div>📚 <strong>9:00 AM–1:00 PM</strong> — JEE Self Study Block 1</div>
        <div>🍽️ <strong>1:00–2:00 PM</strong> — Lunch + Rest</div>
        <div>📖 <strong>2:00–5:30 PM</strong> — JEE Self Study Block 2 / 11th Revision</div>
        <div>🚶 <strong>5:30–6:30 PM</strong> — Evening Walk + Personal Time</div>
        <div>🚿 <strong>6:30–7:00 PM</strong> — Shower / Wind-down</div>
        <div>🎓 <strong>7:00–10:30 PM</strong> — PW Live Coaching (Mon–Sat)</div>
        <div>📝 <strong>10:30 PM–12:30 AM</strong> — DPP + Revision</div>
        <div>🌙 <strong>1:00 AM</strong> — Sleep</div>
      </div>
    </div>
  </div>

  <!-- ===== GITHUB PAGE ===== -->
  <div class="page" id="page-github">
    <div class="section-title">🚀 Host on GitHub Pages</div>
    <div class="announce">Get this planner live at <strong>yourusername.github.io/jee-planner</strong> — free, forever, accessible from any device!</div>

    <div class="step-card">
      <div class="step-num">STEP 01</div>
      <h4>Create a GitHub account</h4>
      <p>Go to <strong>github.com</strong> → click "Sign Up" → use your email → verify. Done!</p>
    </div>
    <div class="step-card">
      <div class="step-num">STEP 02</div>
      <h4>Create a new repository</h4>
      <ul>
        <li>Click the <strong>+</strong> icon → "New repository"</li>
        <li>Name it: <code>jee-planner</code></li>
        <li>Set to <strong>Public</strong></li>
        <li>Check "Add a README file"</li>
        <li>Click "Create repository"</li>
      </ul>
    </div>
    <div class="step-card">
      <div class="step-num">STEP 03</div>
      <h4>Upload your index.html</h4>
      <ul>
        <li>In your new repo, click <strong>"Add file" → "Upload files"</strong></li>
        <li>Drag and drop <code>index.html</code> (this file!)</li>
        <li>Scroll down → Click <strong>"Commit changes"</strong></li>
      </ul>
    </div>
    <div class="step-card">
      <div class="step-num">STEP 04</div>
      <h4>Enable GitHub Pages</h4>
      <ul>
        <li>Go to repo <strong>Settings</strong> → scroll to <strong>Pages</strong></li>
        <li>Source: <strong>Deploy from a branch</strong></li>
        <li>Branch: <strong>main</strong>, folder: <strong>/ (root)</strong></li>
        <li>Click <strong>Save</strong></li>
      </ul>
    </div>
    <div class="step-card">
      <div class="step-num">STEP 05</div>
      <h4>Access from anywhere!</h4>
      <p>Wait 1–2 minutes, then visit: <code>https://yourusername.github.io/jee-planner</code> 🎉</p>
      <p style="margin-top:6px;">Bookmark it on your phone and laptop. All data saves locally on each device.</p>
    </div>
    <div class="step-card" style="border-left-color:var(--gold);">
      <div class="step-num" style="color:var(--gold);">TIP</div>
      <h4>Updating the planner later</h4>
      <p>Just re-upload <code>index.html</code> to your repo → commit → wait 1 min → live!</p>
    </div>
  </div>

</div><!-- end main -->

<!-- BOTTOM NAV -->
<nav class="tab-nav">
  <button class="tab-btn active" onclick="showPage('schedule',this)"><span class="ti">📅</span>Schedule</button>
  <button class="tab-btn" onclick="showPage('stats',this)"><span class="ti">📊</span>Stats</button>
  <button class="tab-btn" onclick="showPage('tests',this)"><span class="ti">📝</span>Tests</button>
  <button class="tab-btn" onclick="showPage('revision',this)"><span class="ti">📗</span>Revision</button>
  <button class="tab-btn" onclick="showPage('dates',this)"><span class="ti">🗓️</span>Dates</button>
  <button class="tab-btn" onclick="showPage('github',this)"><span class="ti">🚀</span>Deploy</button>
</nav>

<!-- ADD/EDIT BLOCK MODAL -->
<div class="modal-bg" id="blockModal">
  <div class="modal">
    <div class="modal-handle"></div>
    <h3 id="blockModalTitle">Add Block</h3>
    <div class="input-group">
      <label class="input-label">Title</label>
      <input type="text" id="bTitle" placeholder="e.g. Physics – Kinematics">
    </div>
    <div class="input-group">
      <label class="input-label">Type</label>
      <select id="bType">
        <option value="phy">Physics</option>
        <option value="che">Chemistry</option>
        <option value="mat">Maths</option>
        <option value="coaching">Coaching</option>
        <option value="break">Break / Meal</option>
        <option value="personal">Personal / Walk</option>
        <option value="sleep">Sleep</option>
      </select>
    </div>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;">
      <div class="input-group">
        <label class="input-label">Start Time</label>
        <input type="text" id="bStart" placeholder="9:00 AM">
      </div>
      <div class="input-group">
        <label class="input-label">End Time</label>
        <input type="text" id="bEnd" placeholder="11:00 AM">
      </div>
    </div>
    <div class="input-group">
      <label class="input-label">Details (optional)</label>
      <textarea id="bDetail" placeholder="e.g. Chapter: Laws of Motion, DPP after"></textarea>
    </div>
    <div style="display:flex;gap:8px;flex-wrap:wrap;">
      <button class="btn btn-primary" style="flex:1;" onclick="saveBlock()">Save</button>
      <button class="btn btn-danger" id="bDeleteBtn" onclick="deleteBlock()" style="display:none;">Delete</button>
      <button class="btn btn-ghost" onclick="closeModal('blockModal')">Cancel</button>
    </div>
  </div>
</div>

<!-- TEST MODAL -->
<div class="modal-bg" id="testModal">
  <div class="modal">
    <div class="modal-handle"></div>
    <h3 id="testModalTitle">Log Test Result</h3>
    <input type="hidden" id="testEditId">
    <div class="input-group">
      <label class="input-label">Test Name</label>
      <input type="text" id="tName" placeholder="e.g. PW Minor Test 3">
    </div>
    <div class="input-group">
      <label class="input-label">Test Type</label>
      <select id="tType">
        <option>JEE Mock</option>
        <option>Chapter Test</option>
        <option>Part Test</option>
        <option>DPP Test</option>
        <option>Full Syllabus Mock</option>
        <option>School Test</option>
      </select>
    </div>
    <div class="input-group">
      <label class="input-label">Date</label>
      <input type="date" id="tDate">
    </div>
    <div class="input-group">
      <label class="input-label">Physics Marks</label>
      <div class="marks-row">
        <input type="number" id="tPhyObt" placeholder="Obtained" min="0">
        <div class="marks-sep">/</div>
        <input type="number" id="tPhyTot" placeholder="Total" min="0">
      </div>
    </div>
    <div class="input-group">
      <label class="input-label">Chemistry Marks</label>
      <div class="marks-row">
        <input type="number" id="tCheObt" placeholder="Obtained" min="0">
        <div class="marks-sep">/</div>
        <input type="number" id="tCheTot" placeholder="Total" min="0">
      </div>
    </div>
    <div class="input-group">
      <label class="input-label">Maths Marks</label>
      <div class="marks-row">
        <input type="number" id="tMatObt" placeholder="Obtained" min="0">
        <div class="marks-sep">/</div>
        <input type="number" id="tMatTot" placeholder="Total" min="0">
      </div>
    </div>
    <div style="display:grid;grid-template-columns:1fr 1fr;gap:10px;">
      <div class="input-group">
        <label class="input-label">Percentile (optional)</label>
        <input type="number" id="tPercentile" placeholder="e.g. 85.5" min="0" max="100" step="0.01">
      </div>
      <div class="input-group">
        <label class="input-label">Rank Estimate (optional)</label>
        <input type="number" id="tRank" placeholder="e.g. 15000" min="0">
      </div>
    </div>
    <div class="input-group">
      <label class="input-label">Weak Topics Identified</label>
      <textarea id="tWeak" placeholder="e.g. Rotational motion, Integration by parts..."></textarea>
    </div>
    <div class="input-group">
      <label class="input-label">Action Plan / What to Revise</label>
      <textarea id="tAction" placeholder="e.g. Redo Chapter 5 questions, watch PW video on..."></textarea>
    </div>
    <div class="input-group">
      <label class="input-label">Self Rating</label>
      <div class="star-row" id="starRow">
        <span class="star" data-v="1">⭐</span>
        <span class="star" data-v="2">⭐</span>
        <span class="star" data-v="3">⭐</span>
        <span class="star" data-v="4">⭐</span>
        <span class="star" data-v="5">⭐</span>
      </div>
    </div>
    <div style="display:flex;gap:8px;flex-wrap:wrap;">
      <button class="btn btn-primary" style="flex:1;" onclick="saveTest()">Save Test</button>
      <button class="btn btn-danger" id="tDeleteBtn" onclick="deleteTest()" style="display:none;">Delete</button>
      <button class="btn btn-ghost" onclick="closeModal('testModal')">Cancel</button>
    </div>
  </div>
</div>

<!-- TEST VIEW MODAL -->
<div class="modal-bg" id="testViewModal">
  <div class="modal">
    <div class="modal-handle"></div>
    <div id="testViewContent"></div>
    <div style="display:flex;gap:8px;flex-wrap:wrap;margin-top:14px;">
      <button class="btn btn-ghost" style="flex:1;" onclick="editTestFromView()">✏️ Edit</button>
      <button class="btn btn-ghost" onclick="closeModal('testViewModal')">Close</button>
    </div>
  </div>
</div>

<script>
// ============================================================
// STATE
// ============================================================
let currentDay = 0;
let editingBlockDay = null;
let editingBlockIdx = null;
let testStarRating = 0;
let editingTestId = null;
let viewingTestId = null;
let revFilter = 'all';

// ============================================================
// SCHEDULE DATA
// ============================================================
const DAYS = ['Mon','Tue','Wed','Thu','Fri','Sat','Sun'];
const SCHEDULE_KEY = 'shrishti_schedule_v4';
const DONE_KEY = 'shrishti_done_v4';
const STREAK_KEY = 'shrishti_streak_v3';
const TEST_KEY = 'shrishti_tests_v3';
const REV_KEY = 'shrishti_rev_v3';
const REVDATES_KEY = 'shrishti_revdates_v3';
const LASTACTIVE_KEY = 'shrishti_lastactive_v3';

// ─── SUBJECT ROTATION PATTERNS ───
// Slot A (9:00–11:00 AM)  — rotates: Phy → Che → Mat → Phy → Che → Mat → (Sun free)
// Slot B (11:15 AM–1:15 PM) — rotates: Mat → Phy → Che → Mat → Phy → Che → (Sun free)
// Slot C (2:15–4:15 PM)  — 11th REVISION only, rotates: Phy Rev → Che Rev → Mat Rev → ...
// Rule: Slot A & B always cover 2 DIFFERENT subjects per day, all 3 across 3 days
// Slot C is dedicated 11th revision — also rotates so all 3 subjects get covered

// Day index: 0=Mon,1=Tue,2=Wed,3=Thu,4=Fri,5=Sat,6=Sun
const SLOT_A = [
  // subject, title, detail
  { t:'phy', name:'JEE Self Study — Physics', det:'12th Physics: Concepts + Numericals + PYQs. Mark doubts for coaching.' },
  { t:'che', name:'JEE Self Study — Chemistry', det:'12th Chemistry: Theory + Reactions + NCERT examples. Organic/Inorganic/Physical.' },
  { t:'mat', name:'JEE Self Study — Maths', det:'12th Maths: Weak subject — focus on problem solving. Min. 2 hrs daily.' },
  { t:'phy', name:'JEE Self Study — Physics', det:'12th Physics: Revision + unsolved examples + past PYQs.' },
  { t:'che', name:'JEE Self Study — Chemistry', det:'12th Chemistry: Practice reactions, name reactions, equations.' },
  { t:'mat', name:'JEE Self Study — Maths', det:'12th Maths: JEE Advanced level problems — push difficulty.' },
];
const SLOT_B = [
  { t:'mat', name:'JEE Self Study — Maths', det:'12th Maths: Problem sets, DPP-style practice. Weak subject — stay consistent.' },
  { t:'phy', name:'JEE Self Study — Physics', det:'12th Physics: Numericals + concept maps + HC Verma / DC Pandey.' },
  { t:'che', name:'JEE Self Study — Chemistry', det:'12th Chemistry: NCERT thorough read + formula drill.' },
  { t:'mat', name:'JEE Self Study — Maths', det:'12th Maths: Calculus, Algebra, Coordinate Geometry rotation.' },
  { t:'phy', name:'JEE Self Study — Physics', det:'12th Physics: Electricity, Magnetism, Optics — chapter rotation.' },
  { t:'che', name:'JEE Self Study — Chemistry', det:'12th Chemistry: Electrochemistry, Solutions, Biomolecules — chapter rotation.' },
];
const SLOT_C_REV = [
  { t:'phy', name:'11th Revision — Physics', det:'11th Physics chapter-wise: Kinematics / Laws of Motion / Work-Energy / Rotation (rotate chapters). Do PYQs after each.' },
  { t:'che', name:'11th Revision — Chemistry', det:'11th Chemistry chapter-wise: Mole Concept / Chemical Bonding / Equilibrium / Organic (rotate). Thorough NCERT read.' },
  { t:'mat', name:'11th Revision — Maths', det:'11th Maths chapter-wise: Trigonometry / Complex Numbers / Sequences / Conic Sections (rotate). Solve JEE PYQs.' },
  { t:'phy', name:'11th Revision — Physics', det:'11th Physics: Thermodynamics / SHM / Waves / Gravitation (rotate chapters). Mark tough topics.' },
  { t:'che', name:'11th Revision — Chemistry', det:'11th Chemistry: s-Block / p-Block / Hydrocarbons / Redox (rotate). Focus on named reactions.' },
  { t:'mat', name:'11th Revision — Maths', det:'11th Maths: Permutations / Binomial / Limits & Derivatives / Probability (rotate). Speed + accuracy.' },
];

function defaultBlocks(dayIdx) {
  const weekday = dayIdx < 6; // Mon–Sat have coaching; Sun is free

  if (dayIdx === 6) {
    // ── SUNDAY — Full JEE Prep, no coaching ──
    return [
      { title:'Wake Up + Morning Routine', type:'personal', start:'7:30 AM', end:'8:00 AM', detail:'Freshen up, hydrate, set intention for the day' },
      { title:'Breakfast', type:'break', start:'8:00 AM', end:'8:30 AM', detail:'Eat well — brain needs fuel!' },
      { title:'JEE Self Study — Physics', type:'phy', start:'9:00 AM', end:'11:00 AM', detail:'Weekly Physics deep dive: pick 1 tough chapter, solve 20+ problems.' },
      { title:'Short Break', type:'break', start:'11:00 AM', end:'11:15 AM', detail:'Stretch, water, breathe' },
      { title:'JEE Self Study — Chemistry', type:'che', start:'11:15 AM', end:'1:15 PM', detail:'Weekly Chemistry: reactions, named reactions, tricky NCERT questions.' },
      { title:'Lunch + Rest', type:'break', start:'1:15 PM', end:'2:15 PM', detail:'Full meal + 20 min rest — no phone!' },
      { title:'11th Revision — Maths', type:'mat', start:'2:15 PM', end:'4:15 PM', detail:'11th Maths weekly revision: pick 1–2 chapters, solve PYQs. Update Revision Tracker.' },
      { title:'JEE Self Study — Maths', type:'mat', start:'4:15 PM', end:'5:15 PM', detail:'Weekly Maths mock: 15 JEE-level Maths questions timed — simulate exam.' },
      { title:'Evening Walk + Personal Time', type:'personal', start:'5:30 PM', end:'6:30 PM', detail:'Unwind, no study. You deserve it!' },
      { title:'Shower + Wind-down', type:'personal', start:'6:30 PM', end:'7:00 PM', detail:'' },
      { title:'Dinner', type:'break', start:'7:00 PM', end:'7:45 PM', detail:'Dinner + family time' },
      { title:'Weekly Full Mock / Test Practice', type:'mat', start:'8:00 PM', end:'10:30 PM', detail:'Take a full JEE mock OR review the week\'s weak topics. Log result in Test Tracker.' },
      { title:'Weekly Review + Planning', type:'personal', start:'10:30 PM', end:'12:30 AM', detail:'Review mistakes, plan next week\'s focus areas, update streak' },
      { title:'Sleep', type:'sleep', start:'12:30 AM', end:'1:00 AM', detail:'Rest well — consistency is built on recovery.' },
    ];
  }

  // ── MON–SAT: 3-slot rotating structure ──
  const a = SLOT_A[dayIdx];   // Slot A subject
  const b = SLOT_B[dayIdx];   // Slot B subject (always different from A)
  const c = SLOT_C_REV[dayIdx]; // Slot C — 11th Revision subject

  // DPP after coaching should match today's coaching subject (coaching covers both Phy & Chem or Math cyclically)
  // We'll make DPP rotate to cover the 3rd subject not studied in self-study
  const dppSubjects = ['Phy','Che','Mat'];
  const usedToday = [a.t, b.t];
  const dppFocus = dppSubjects.find(s => !usedToday.includes({Phy:'phy',Che:'che',Mat:'mat'}[s]) ) || 'all 3';

  const base = [
    { title:'Wake Up + Morning Routine', type:'personal', start:'7:30 AM', end:'8:00 AM', detail:'Freshen up, hydrate, set daily intention' },
    { title:'Breakfast', type:'break', start:'8:00 AM', end:'8:30 AM', detail:'Eat well — brain fuel!' },
    // ── SLOT A: JEE Self Study Subject 1 ──
    { title: a.name, type: a.t, start:'9:00 AM', end:'11:00 AM', detail: a.det },
    { title:'Short Break', type:'break', start:'11:00 AM', end:'11:15 AM', detail:'Stretch, water, 5-min walk' },
    // ── SLOT B: JEE Self Study Subject 2 ──
    { title: b.name, type: b.t, start:'11:15 AM', end:'1:15 PM', detail: b.det },
    { title:'Lunch + Rest', type:'break', start:'1:15 PM', end:'2:15 PM', detail:'Full meal + 20 min rest. Recharge before afternoon.' },
    // ── SLOT C: 11th REVISION (dedicated — alternating subject) ──
    { title: c.name, type: c.t, start:'2:15 PM', end:'4:15 PM', detail: c.det + ' | Update your Revision Tracker after this slot!' },
    { title:'Short Break', type:'break', start:'4:15 PM', end:'4:30 PM', detail:'Snack + mental reset before evening' },
    { title:'Evening Walk + Personal Time', type:'personal', start:'5:30 PM', end:'6:30 PM', detail:'Disconnect fully — no phone, no books. Walk & reset.' },
    { title:'Shower + Wind-down', type:'personal', start:'6:30 PM', end:'7:00 PM', detail:'Freshen up before coaching' },
    // ── COACHING ──
    { title:'PW Live Coaching — Lecture 1', type:'coaching', start:'7:00 PM', end:'8:15 PM', detail:'Attend live — be present, take notes, star doubts immediately' },
    { title:'PW Live Coaching — Lecture 2', type:'coaching', start:'8:15 PM', end:'9:30 PM', detail:'Stay engaged till the end. Mark any formula to revise.' },
    { title:'Dinner', type:'break', start:'9:30 PM', end:'10:15 PM', detail:'Dinner + short rest' },
    // ── DPP: covers all 3 subjects across the week ──
    { title:`DPP — ${a.t==='phy'?'Physics':a.t==='che'?'Chemistry':'Maths'} + ${b.t==='phy'?'Physics':b.t==='che'?'Chemistry':'Maths'}`, type: a.t, start:'10:15 PM', end:'11:15 PM', detail:`0.5h ${a.t==='phy'?'Physics':a.t==='che'?'Chemistry':'Maths'} DPP + 0.5h ${b.t==='phy'?'Physics':b.t==='che'?'Chemistry':'Maths'} DPP from today's coaching. Attempt honestly — no peeking!` },
    { title:`DPP — ${c.t==='phy'?'Physics':c.t==='che'?'Chemistry':'Maths'} + Concept Notes`, type: c.t, start:'11:15 PM', end:'12:30 AM', detail:`0.5h ${c.t==='phy'?'Physics':c.t==='che'?'Chemistry':'Maths'} DPP + 30 min: write key formulas / concepts from today's 11th revision in your notes.` },
    { title:'Wind-down + Sleep', type:'sleep', start:'12:30 AM', end:'1:00 AM', detail:'Put phone away 30 min before sleep. No screens. Rest = performance.' },
  ];
  return base;
}

function loadSchedule() {
  let s = localStorage.getItem(SCHEDULE_KEY);
  if (!s) {
    let sch = {};
    for (let i=0;i<7;i++) sch[i] = defaultBlocks(i);
    localStorage.setItem(SCHEDULE_KEY, JSON.stringify(sch));
    return sch;
  }
  return JSON.parse(s);
}
function saveSchedule(sch) { localStorage.setItem(SCHEDULE_KEY, JSON.stringify(sch)); }

function loadDone() {
  let d = localStorage.getItem(DONE_KEY);
  return d ? JSON.parse(d) : {};
}
function saveDone(d) { localStorage.setItem(DONE_KEY, JSON.stringify(d)); }

// ============================================================
// STREAK
// ============================================================
function getStreak() {
  let s = localStorage.getItem(STREAK_KEY);
  return s ? JSON.parse(s) : { count:0, lastDate:null };
}
function updateStreak() {
  let s = getStreak();
  const today = todayStr();
  if (s.lastDate === today) return;
  const done = loadDone();
  const todayBlocks = (loadSchedule()[currentDay]||[]);
  const allDone = todayBlocks.length > 0 && todayBlocks.every((_,i) => done[`${currentDay}-${i}`]);
  if (allDone) {
    const yesterday = new Date(); yesterday.setDate(yesterday.getDate()-1);
    const yStr = yesterday.toISOString().slice(0,10);
    if (s.lastDate === yStr) s.count++;
    else if (s.lastDate !== today) s.count = 1;
    s.lastDate = today;
    localStorage.setItem(STREAK_KEY, JSON.stringify(s));
  }
  document.getElementById('streakNum').textContent = s.count;
  document.getElementById('streakBadge').title = `${s.count} day streak`;
}
function todayStr() { return new Date().toISOString().slice(0,10); }

// ============================================================
// RENDER SCHEDULE
// ============================================================
function renderDayTabs() {
  const tabs = document.getElementById('dayTabs');
  const todayDow = (new Date().getDay() + 6) % 7; // Mon=0
  tabs.innerHTML = DAYS.map((d,i) => `
    <div class="day-tab ${i===currentDay?'active':''}" onclick="switchDay(${i})">
      <div class="d-name">${d}</div>
      <div style="font-size:0.6rem;">${i===todayDow?'Today':''}</div>
    </div>
  `).join('');
}

function renderBlocks() {
  const sch = loadSchedule();
  const done = loadDone();
  const blocks = sch[currentDay]||[];
  const el = document.getElementById('scheduleBlocks');
  el.innerHTML = blocks.map((b,i)=>{
    const key = `${currentDay}-${i}`;
    const isDone = !!done[key];
    return `
    <div class="block ${b.type} ${isDone?'done':''}" onclick="openEditBlock(${i})">
      <div class="block-cb ${isDone?'checked':''}" onclick="toggleBlock(event,${i})">${isDone?'✓':''}</div>
      <div class="block-body">
        <div class="block-time">${b.start} – ${b.end}</div>
        <div class="block-title">${b.title}</div>
        ${b.detail?`<div class="block-sub">${b.detail}</div>`:''}
      </div>
      <div class="block-tag tag-${b.type}">${b.type==='phy'?'Physics':b.type==='che'?'Chem':b.type==='mat'?'Maths':b.type==='coaching'?'Coaching':b.type==='break'?'Break':b.type==='personal'?'Personal':'Sleep'}</div>
    </div>`;
  }).join('');
  updateProgress();
  updateStreak();
}

function updateProgress() {
  const sch = loadSchedule();
  const done = loadDone();
  const blocks = sch[currentDay]||[];
  const total = blocks.length;
  const doneCount = blocks.filter((_,i)=>done[`${currentDay}-${i}`]).length;
  const pct = total ? Math.round(doneCount/total*100) : 0;
  document.getElementById('progBar').style.width = pct+'%';
  document.getElementById('progPct').textContent = pct+'%';
  document.getElementById('progLbl').textContent = `${doneCount} of ${total} tasks done`;
}

function toggleBlock(e, idx) {
  e.stopPropagation();
  const done = loadDone();
  const key = `${currentDay}-${idx}`;
  done[key] = !done[key];
  saveDone(done);
  renderBlocks();
}

function switchDay(i) {
  currentDay = i;
  renderDayTabs();
  renderBlocks();
}

// ============================================================
// BLOCK MODAL
// ============================================================
function openAddBlock() {
  editingBlockIdx = null;
  document.getElementById('blockModalTitle').textContent = 'Add Block';
  document.getElementById('bTitle').value = '';
  document.getElementById('bType').value = 'phy';
  document.getElementById('bStart').value = '';
  document.getElementById('bEnd').value = '';
  document.getElementById('bDetail').value = '';
  document.getElementById('bDeleteBtn').style.display = 'none';
  document.getElementById('blockModal').classList.add('open');
}
function openEditBlock(idx) {
  const sch = loadSchedule();
  const b = sch[currentDay][idx];
  editingBlockIdx = idx;
  document.getElementById('blockModalTitle').textContent = 'Edit Block';
  document.getElementById('bTitle').value = b.title;
  document.getElementById('bType').value = b.type;
  document.getElementById('bStart').value = b.start;
  document.getElementById('bEnd').value = b.end;
  document.getElementById('bDetail').value = b.detail||'';
  document.getElementById('bDeleteBtn').style.display = 'inline-flex';
  document.getElementById('blockModal').classList.add('open');
}
function saveBlock() {
  const sch = loadSchedule();
  const b = {
    title: document.getElementById('bTitle').value||'Block',
    type: document.getElementById('bType').value,
    start: document.getElementById('bStart').value,
    end: document.getElementById('bEnd').value,
    detail: document.getElementById('bDetail').value,
  };
  if (editingBlockIdx !== null) sch[currentDay][editingBlockIdx] = b;
  else sch[currentDay].push(b);
  saveSchedule(sch);
  closeModal('blockModal');
  renderBlocks();
}
function deleteBlock() {
  if (!confirm('Delete this block?')) return;
  const sch = loadSchedule();
  sch[currentDay].splice(editingBlockIdx,1);
  saveSchedule(sch);
  closeModal('blockModal');
  renderBlocks();
}
function closeModal(id) { document.getElementById(id).classList.remove('open'); }

// ============================================================
// TESTS
// ============================================================
function loadTests() {
  let t = localStorage.getItem(TEST_KEY);
  return t ? JSON.parse(t) : [];
}
function saveTests(t) { localStorage.setItem(TEST_KEY, JSON.stringify(t)); }

function openTestModal(editId) {
  editingTestId = editId||null;
  const tests = loadTests();
  const t = editId ? tests.find(x=>x.id===editId) : null;
  document.getElementById('testModalTitle').textContent = t ? 'Edit Test' : 'Log Test Result';
  document.getElementById('testEditId').value = editId||'';
  document.getElementById('tName').value = t?.name||'';
  document.getElementById('tType').value = t?.type||'JEE Mock';
  document.getElementById('tDate').value = t?.date||todayStr();
  document.getElementById('tPhyObt').value = t?.phyObt??'';
  document.getElementById('tPhyTot').value = t?.phyTot??'';
  document.getElementById('tCheObt').value = t?.cheObt??'';
  document.getElementById('tCheTot').value = t?.cheTot??'';
  document.getElementById('tMatObt').value = t?.matObt??'';
  document.getElementById('tMatTot').value = t?.matTot??'';
  document.getElementById('tPercentile').value = t?.percentile??'';
  document.getElementById('tRank').value = t?.rank??'';
  document.getElementById('tWeak').value = t?.weak||'';
  document.getElementById('tAction').value = t?.action||'';
  testStarRating = t?.stars||0;
  renderStars();
  document.getElementById('tDeleteBtn').style.display = editId?'inline-flex':'none';
  closeModal('testViewModal');
  document.getElementById('testModal').classList.add('open');
}

function renderStars() {
  document.querySelectorAll('#starRow .star').forEach(s=>{
    s.classList.toggle('active', parseInt(s.dataset.v) <= testStarRating);
  });
}
document.querySelectorAll('#starRow .star').forEach(s=>{
  s.addEventListener('click',()=>{ testStarRating=parseInt(s.dataset.v); renderStars(); });
});

function saveTest() {
  const tests = loadTests();
  const phyObt = parseFloat(document.getElementById('tPhyObt').value)||0;
  const phyTot = parseFloat(document.getElementById('tPhyTot').value)||0;
  const cheObt = parseFloat(document.getElementById('tCheObt').value)||0;
  const cheTot = parseFloat(document.getElementById('tCheTot').value)||0;
  const matObt = parseFloat(document.getElementById('tMatObt').value)||0;
  const matTot = parseFloat(document.getElementById('tMatTot').value)||0;
  const t = {
    id: editingTestId || Date.now().toString(),
    name: document.getElementById('tName').value||'Test',
    type: document.getElementById('tType').value,
    date: document.getElementById('tDate').value,
    phyObt,phyTot,cheObt,cheTot,matObt,matTot,
    totalObt: phyObt+cheObt+matObt,
    totalTot: phyTot+cheTot+matTot,
    percentile: parseFloat(document.getElementById('tPercentile').value)||null,
    rank: parseInt(document.getElementById('tRank').value)||null,
    weak: document.getElementById('tWeak').value,
    action: document.getElementById('tAction').value,
    stars: testStarRating,
  };
  if (editingTestId) { const idx=tests.findIndex(x=>x.id===editingTestId); if(idx>-1) tests[idx]=t; }
  else tests.push(t);
  saveTests(tests);
  closeModal('testModal');
  renderTests();
}
function deleteTest() {
  if (!confirm('Delete this test?')) return;
  let tests = loadTests();
  tests = tests.filter(x=>x.id!==editingTestId);
  saveTests(tests);
  closeModal('testModal');
  renderTests();
}

function pct(obt,tot) { return tot?Math.round(obt/tot*100):0; }
function starsHTML(n) { return '⭐'.repeat(n)+'☆'.repeat(5-n); }

function renderTests() {
  const tests = loadTests().sort((a,b)=>b.date.localeCompare(a.date));
  const el = document.getElementById('testList');
  const noEl = document.getElementById('noTests');
  const anaEl = document.getElementById('testAnalytics');

  if (!tests.length) { el.innerHTML=''; noEl.style.display='block'; anaEl.style.display='none'; return; }
  noEl.style.display='none'; anaEl.style.display='block';

  el.innerHTML = tests.map(t=>`
    <div class="test-card" onclick="viewTest('${t.id}')">
      <div class="test-card-header">
        <div>
          <div class="test-card-title">${t.name}</div>
          <div class="test-card-meta">${t.date} · ${t.type}</div>
        </div>
        <div style="text-align:right;">
          <div style="font-family:'Syne',sans-serif;font-size:1.1rem;font-weight:800;color:var(--accent);">${t.totalObt}/${t.totalTot}</div>
          <div style="font-size:0.72rem;color:var(--text3);">${pct(t.totalObt,t.totalTot)}%</div>
          <div style="font-size:0.75rem;">${starsHTML(t.stars)}</div>
        </div>
      </div>
      <div class="test-card-scores">
        ${t.phyTot?`<span class="score-chip score-phy">⚛ ${pct(t.phyObt,t.phyTot)}%</span>`:''}
        ${t.cheTot?`<span class="score-chip score-che">⚗ ${pct(t.cheObt,t.cheTot)}%</span>`:''}
        ${t.matTot?`<span class="score-chip score-mat">∑ ${pct(t.matObt,t.matTot)}%</span>`:''}
      </div>
    </div>
  `).join('');

  // Analytics
  document.getElementById('testCount').textContent = `· ${tests.length} test${tests.length>1?'s':''}`;
  const sorted = [...tests].sort((a,b)=>a.date.localeCompare(b.date));
  const best = tests.reduce((a,b)=>pct(a.totalObt,a.totalTot)>=pct(b.totalObt,b.totalTot)?a:b);
  const latest = sorted[sorted.length-1];
  const first = sorted[0];
  const imp = pct(latest.totalObt,latest.totalTot) - pct(first.totalObt,first.totalTot);
  const phyAvg = avg(tests.map(t=>pct(t.phyObt,t.phyTot)).filter(x=>x>0));
  const cheAvg = avg(tests.map(t=>pct(t.cheObt,t.cheTot)).filter(x=>x>0));
  const matAvg = avg(tests.map(t=>pct(t.matObt,t.matTot)).filter(x=>x>0));
  const weakSub = [['Phy',phyAvg],['Che',cheAvg],['Mat',matAvg]].sort((a,b)=>a[1]-b[1])[0];

  document.getElementById('t-best').textContent = `${pct(best.totalObt,best.totalTot)}%`;
  document.getElementById('t-latest').textContent = `${pct(latest.totalObt,latest.totalTot)}%`;
  document.getElementById('t-improve').textContent = (imp>=0?'+':'')+imp+'%';
  document.getElementById('t-improve').style.color = imp>=0?'var(--che)':'var(--danger)';
  document.getElementById('t-weak').textContent = weakSub[0];
  document.getElementById('avg-phy').textContent = `⚛ ${phyAvg}%`;
  document.getElementById('avg-che').textContent = `⚗ ${cheAvg}%`;
  document.getElementById('avg-mat').textContent = `∑ ${matAvg}%`;

  renderScoreChart(sorted);
}
function avg(arr) { return arr.length?Math.round(arr.reduce((a,b)=>a+b,0)/arr.length):0; }

function renderScoreChart(sorted) {
  if (!sorted.length) return;
  const el = document.getElementById('scoreChart');
  const max = 100;
  const h = 100, pad = 30, barW = Math.min(40, Math.floor((300-pad*2)/sorted.length)-4);
  const w = Math.max(300, sorted.length*(barW+6)+pad*2);
  el.innerHTML = `<div class="chart-wrap"><svg viewBox="0 0 ${w} ${h+30}" height="${h+30}" style="width:100%;min-width:${w}px;">
    ${sorted.map((t,i)=>{
      const p = pct(t.totalObt,t.totalTot);
      const bh = Math.max(4, p/max*h);
      const x = pad + i*(barW+6);
      const y = h - bh;
      return `<rect x="${x}" y="${y}" width="${barW}" height="${bh}" rx="4" fill="url(#bg)" opacity="0.9"/>
        <text x="${x+barW/2}" y="${h+12}" text-anchor="middle" fill="#5a5a72" font-size="8" font-family="Space Grotesk">${t.date.slice(5)}</text>
        <text x="${x+barW/2}" y="${y-4}" text-anchor="middle" fill="#e8e8f0" font-size="9" font-weight="600">${p}%</text>`;
    }).join('')}
    <defs><linearGradient id="bg" x1="0" y1="0" x2="0" y2="1"><stop offset="0%" stop-color="#7c6fff"/><stop offset="100%" stop-color="#ff6fa8"/></linearGradient></defs>
  </svg></div>`;
}

function viewTest(id) {
  viewingTestId = id;
  const t = loadTests().find(x=>x.id===id);
  if(!t) return;
  document.getElementById('testViewContent').innerHTML = `
    <h3 style="margin-bottom:6px;">${t.name}</h3>
    <div style="font-size:0.75rem;color:var(--text3);margin-bottom:14px;">${t.date} · ${t.type} · ${starsHTML(t.stars)}</div>
    <div style="display:grid;grid-template-columns:repeat(3,1fr);gap:8px;margin-bottom:14px;">
      <div class="stat-box" style="padding:10px;"><div style="font-size:1rem;font-weight:800;font-family:'Syne',sans-serif;color:var(--phy);">${pct(t.phyObt,t.phyTot)}%</div><div class="stat-lbl">Physics<br>${t.phyObt}/${t.phyTot}</div></div>
      <div class="stat-box" style="padding:10px;"><div style="font-size:1rem;font-weight:800;font-family:'Syne',sans-serif;color:var(--che);">${pct(t.cheObt,t.cheTot)}%</div><div class="stat-lbl">Chemistry<br>${t.cheObt}/${t.cheTot}</div></div>
      <div class="stat-box" style="padding:10px;"><div style="font-size:1rem;font-weight:800;font-family:'Syne',sans-serif;color:var(--mat);">${pct(t.matObt,t.matTot)}%</div><div class="stat-lbl">Maths<br>${t.matObt}/${t.matTot}</div></div>
    </div>
    <div class="stat-box" style="margin-bottom:14px;padding:12px;text-align:center;"><span style="font-family:'Syne',sans-serif;font-size:1.4rem;font-weight:800;color:var(--accent);">${t.totalObt}/${t.totalTot}</span> <span style="color:var(--text3);font-size:0.8rem;">(${pct(t.totalObt,t.totalTot)}%)</span></div>
    ${t.percentile?`<div style="font-size:0.8rem;color:var(--text2);margin-bottom:6px;">📊 Percentile: <strong>${t.percentile}</strong></div>`:''}
    ${t.rank?`<div style="font-size:0.8rem;color:var(--text2);margin-bottom:10px;">🏆 Rank Estimate: <strong>${t.rank}</strong></div>`:''}
    ${t.weak?`<div style="margin-bottom:10px;"><div style="font-size:0.72rem;color:var(--text3);margin-bottom:4px;">⚠️ Weak Topics</div><div style="font-size:0.82rem;background:var(--bg3);padding:10px;border-radius:8px;">${t.weak}</div></div>`:''}
    ${t.action?`<div><div style="font-size:0.72rem;color:var(--text3);margin-bottom:4px;">📋 Action Plan</div><div style="font-size:0.82rem;background:var(--bg3);padding:10px;border-radius:8px;">${t.action}</div></div>`:''}
  `;
  document.getElementById('testViewModal').classList.add('open');
}
function editTestFromView() { closeModal('testViewModal'); openTestModal(viewingTestId); }

// ============================================================
// REVISION DATA
// ============================================================
const CHAPTERS = [
  // Physics
  {id:'p1',subj:'phy',name:'Physical World & Measurement',imp:'low',hrs:1.5},
  {id:'p2',subj:'phy',name:'Kinematics (1D & 2D)',imp:'high',hrs:3},
  {id:'p3',subj:'phy',name:'Laws of Motion',imp:'high',hrs:3},
  {id:'p4',subj:'phy',name:'Work, Energy & Power',imp:'high',hrs:2.5},
  {id:'p5',subj:'phy',name:'System of Particles & Rotational Motion',imp:'high',hrs:3},
  {id:'p6',subj:'phy',name:'Gravitation',imp:'high',hrs:2.5},
  {id:'p7',subj:'phy',name:'Properties of Solids & Liquids',imp:'med',hrs:2},
  {id:'p8',subj:'phy',name:'Thermodynamics',imp:'high',hrs:2.5},
  {id:'p9',subj:'phy',name:'Kinetic Theory of Gases',imp:'med',hrs:2},
  {id:'p10',subj:'phy',name:'Oscillations (SHM)',imp:'high',hrs:2.5},
  {id:'p11',subj:'phy',name:'Waves',imp:'high',hrs:3},
  // Chemistry
  {id:'c1',subj:'che',name:'Some Basic Concepts of Chemistry (Mole Concept)',imp:'high',hrs:3},
  {id:'c2',subj:'che',name:'Structure of Atom',imp:'high',hrs:2.5},
  {id:'c3',subj:'che',name:'Classification of Elements & Periodicity',imp:'med',hrs:2},
  {id:'c4',subj:'che',name:'Chemical Bonding & Molecular Structure',imp:'high',hrs:3},
  {id:'c5',subj:'che',name:'States of Matter (Gases & Liquids)',imp:'med',hrs:2},
  {id:'c6',subj:'che',name:'Thermodynamics (Chemical)',imp:'high',hrs:2.5},
  {id:'c7',subj:'che',name:'Equilibrium',imp:'high',hrs:3},
  {id:'c8',subj:'che',name:'Redox Reactions',imp:'med',hrs:1.5},
  {id:'c9',subj:'che',name:'Hydrogen',imp:'low',hrs:1},
  {id:'c10',subj:'che',name:'s-Block Elements',imp:'low',hrs:1},
  {id:'c11',subj:'che',name:'p-Block Elements (Group 13 & 14)',imp:'med',hrs:2},
  {id:'c12',subj:'che',name:'Organic Chemistry – Basic Principles',imp:'high',hrs:3},
  {id:'c13',subj:'che',name:'Hydrocarbons',imp:'high',hrs:2.5},
  {id:'c14',subj:'che',name:'Environmental Chemistry',imp:'low',hrs:1},
  // Maths
  {id:'m1',subj:'mat',name:'Sets',imp:'low',hrs:1},
  {id:'m2',subj:'mat',name:'Relations & Functions',imp:'med',hrs:1.5},
  {id:'m3',subj:'mat',name:'Trigonometric Functions',imp:'high',hrs:3},
  {id:'m4',subj:'mat',name:'Principle of Mathematical Induction',imp:'low',hrs:1},
  {id:'m5',subj:'mat',name:'Complex Numbers & Quadratic Equations',imp:'high',hrs:3},
  {id:'m6',subj:'mat',name:'Linear Inequalities',imp:'low',hrs:1},
  {id:'m7',subj:'mat',name:'Permutations & Combinations',imp:'high',hrs:2.5},
  {id:'m8',subj:'mat',name:'Binomial Theorem',imp:'high',hrs:2.5},
  {id:'m9',subj:'mat',name:'Sequences & Series',imp:'high',hrs:2.5},
  {id:'m10',subj:'mat',name:'Straight Lines',imp:'high',hrs:2.5},
  {id:'m11',subj:'mat',name:'Conic Sections',imp:'high',hrs:3},
  {id:'m12',subj:'mat',name:'Introduction to 3D Geometry',imp:'med',hrs:1.5},
  {id:'m13',subj:'mat',name:'Limits & Derivatives',imp:'high',hrs:3},
  {id:'m14',subj:'mat',name:'Mathematical Reasoning',imp:'low',hrs:1},
  {id:'m15',subj:'mat',name:'Statistics',imp:'med',hrs:1.5},
  {id:'m16',subj:'mat',name:'Probability',imp:'high',hrs:2.5},
];

const STATUS_LABELS = ['⬜ Not Started','🔄 In Progress','✅ Done','🔁 Needs Revision'];
const QUALITY_OPTS = ['😵 Struggled','😐 Okay','😊 Good','🔥 Excellent'];

function loadRevData() {
  let d = localStorage.getItem(REV_KEY);
  if (!d) return {};
  return JSON.parse(d);
}
function saveRevData(d) { localStorage.setItem(REV_KEY, JSON.stringify(d)); }
function loadRevDates() {
  let d = localStorage.getItem(REVDATES_KEY);
  return d ? JSON.parse(d) : { start:'', end:'' };
}
function saveRevDates() {
  const s = document.getElementById('revStart').value;
  const e = document.getElementById('revEnd').value;
  localStorage.setItem(REVDATES_KEY, JSON.stringify({start:s,end:e}));
  renderRevDash();
}

function setRevFilter(el,f) {
  revFilter = f;
  document.querySelectorAll('.filter-chip').forEach(c=>c.classList.remove('active'));
  el.classList.add('active');
  renderRevision();
}

function renderRevision() {
  renderRevDash();
  const data = loadRevData();
  const query = document.getElementById('revSearch').value.toLowerCase();
  let chapters = CHAPTERS.filter(ch=>{
    if (query && !ch.name.toLowerCase().includes(query)) return false;
    if (revFilter==='phy') return ch.subj==='phy';
    if (revFilter==='che') return ch.subj==='che';
    if (revFilter==='mat') return ch.subj==='mat';
    if (revFilter==='high') return ch.imp==='high';
    if (revFilter==='done') return (data[ch.id]?.status||0)===2;
    if (revFilter==='needsrev') return (data[ch.id]?.status||0)===3;
    if (revFilter==='notstarted') return (data[ch.id]?.status||0)===0;
    return true;
  });

  const el = document.getElementById('revisionList');
  el.innerHTML = chapters.map(ch=>{
    const d = data[ch.id]||{status:0,quality:-1,pyq:false,notes:'',dateCompleted:''};
    const subClass = {phy:'phy',che:'che',mat:'mat'}[ch.subj];
    const subLabel = {phy:'⚛ Physics',che:'⚗ Chem',mat:'∑ Maths'}[ch.subj];
    const impClass = {high:'imp-high',med:'imp-med',low:'imp-low'}[ch.imp];
    const impLabel = {high:'🔴 High',med:'🟡 Med',low:'🟢 Low'}[ch.imp];
    const showQuality = d.status === 2 || d.status === 3;
    return `
    <div class="rev-card" id="rc-${ch.id}">
      <div class="rev-card-header">
        <span class="subj-tag subj-${subClass}">${subLabel}</span>
        <span class="imp-tag ${impClass}">${impLabel}</span>
        <span class="rev-title">${ch.name}</span>
        <span style="font-size:0.68rem;color:var(--text3);white-space:nowrap;">${ch.hrs}h</span>
      </div>
      <div class="rev-controls">
        <button class="status-btn status-${d.status}" onclick="cycleStatus('${ch.id}')">${STATUS_LABELS[d.status]}</button>
        <label style="display:flex;align-items:center;gap:5px;font-size:0.72rem;color:var(--text2);cursor:pointer;">
          <input type="checkbox" class="pyq-cb" ${d.pyq?'checked':''} onchange="togglePYQ('${ch.id}',this)"> PYQ Done
        </label>
        ${d.dateCompleted?`<span style="font-size:0.65rem;color:var(--text3);font-family:'JetBrains Mono',monospace;">✅ ${d.dateCompleted}</span>`:''}
      </div>
      ${showQuality?`<div class="quality-row">
        ${QUALITY_OPTS.map((q,qi)=>`<button class="q-btn ${d.quality===qi?'active':''}" onclick="setQuality('${ch.id}',${qi})">${q}</button>`).join('')}
      </div>`:''}
      <textarea class="rev-notes" placeholder="Notes, weak points, formulas..." onchange="saveNotes('${ch.id}',this.value)">${d.notes||''}</textarea>
    </div>`;
  }).join('');

  // Suggest today's chapter
  const allData = loadRevData();
  const nextHigh = CHAPTERS.find(ch=>ch.imp==='high'&&(allData[ch.id]?.status||0)===0);
  const suggestEl = document.getElementById('suggestCard');
  if (nextHigh) {
    suggestEl.style.display='block';
    document.getElementById('suggestContent').innerHTML = `
      <div class="rev-card" style="margin:0;background:var(--bg3);">
        <div class="rev-card-header">
          <span class="subj-tag subj-${nextHigh.subj}">${{phy:'⚛ Physics',che:'⚗ Chem',mat:'∑ Maths'}[nextHigh.subj]}</span>
          <span class="imp-tag imp-high">🔴 High</span>
          <span class="rev-title">${nextHigh.name}</span>
          <span style="font-size:0.68rem;color:var(--text3);">${nextHigh.hrs}h</span>
        </div>
        <button class="btn btn-primary" onclick="startSuggest('${nextHigh.id}')" style="margin-top:8px;padding:8px 16px;font-size:0.8rem;">Start Today →</button>
      </div>`;
  } else { suggestEl.style.display='none'; }
}

function startSuggest(id) {
  const data = loadRevData();
  if (!data[id]) data[id] = {};
  data[id].status = 1;
  saveRevData(data);
  renderRevision();
}

function cycleStatus(id) {
  const data = loadRevData();
  if (!data[id]) data[id] = {status:0,quality:-1,pyq:false,notes:'',dateCompleted:''};
  data[id].status = (data[id].status+1)%4;
  if (data[id].status===2) data[id].dateCompleted = todayStr();
  else if (data[id].status!==3) data[id].dateCompleted='';
  saveRevData(data);
  renderRevision();
}
function togglePYQ(id,el) {
  const data = loadRevData();
  if (!data[id]) data[id]={status:0,quality:-1,pyq:false,notes:'',dateCompleted:''};
  data[id].pyq = el.checked;
  saveRevData(data);
  renderRevDash();
}
function setQuality(id,q) {
  const data = loadRevData();
  if (!data[id]) data[id]={status:0,quality:-1,pyq:false,notes:'',dateCompleted:''};
  data[id].quality = data[id].quality===q ? -1 : q;
  saveRevData(data);
  renderRevision();
}
function saveNotes(id,val) {
  const data = loadRevData();
  if (!data[id]) data[id]={status:0,quality:-1,pyq:false,notes:'',dateCompleted:''};
  data[id].notes = val;
  saveRevData(data);
}

function renderRevDash() {
  const data = loadRevData();
  const total = CHAPTERS.length;
  const done = CHAPTERS.filter(ch=>(data[ch.id]?.status||0)===2).length;
  const inprog = CHAPTERS.filter(ch=>(data[ch.id]?.status||0)===1).length;
  const pctDone = Math.round(done/total*100);
  document.getElementById('revBar').style.width = pctDone+'%';
  document.getElementById('revPct').textContent = pctDone+'%';

  const phyDone = CHAPTERS.filter(ch=>ch.subj==='phy'&&(data[ch.id]?.status||0)===2).length;
  const cheDone = CHAPTERS.filter(ch=>ch.subj==='che'&&(data[ch.id]?.status||0)===2).length;
  const matDone = CHAPTERS.filter(ch=>ch.subj==='mat'&&(data[ch.id]?.status||0)===2).length;
  document.getElementById('rev-phy-bar').style.width = Math.round(phyDone/11*100)+'%';
  document.getElementById('rev-che-bar').style.width = Math.round(cheDone/14*100)+'%';
  document.getElementById('rev-mat-bar').style.width = Math.round(matDone/16*100)+'%';
  document.getElementById('rev-phy-lbl').textContent = `${phyDone}/11`;
  document.getElementById('rev-che-lbl').textContent = `${cheDone}/14`;
  document.getElementById('rev-mat-lbl').textContent = `${matDone}/16`;

  const hrsDone = CHAPTERS.filter(ch=>(data[ch.id]?.status||0)===2).reduce((a,ch)=>a+ch.hrs,0);
  const hrsLeft = CHAPTERS.filter(ch=>(data[ch.id]?.status||0)===0).reduce((a,ch)=>a+ch.hrs,0);
  document.getElementById('revHrsDone').textContent = hrsDone+'h';
  document.getElementById('revHrsLeft').textContent = hrsLeft+'h';

  // Days left + pace warning
  const dates = loadRevDates();
  if (dates.end) {
    const endDate = new Date(dates.end);
    const now = new Date();
    const daysLeft = Math.max(0,Math.ceil((endDate-now)/86400000));
    document.getElementById('revDaysLeft').textContent = daysLeft;
    const remaining = total - done;
    const statusMsg = document.getElementById('revStatusMsg');
    if (daysLeft > 0) {
      const needed = remaining/daysLeft;
      if (done===total) {
        statusMsg.innerHTML = `<div class="ok-box">🎉 All chapters done! Amazing work, Shrishti!</div>`;
      } else if (needed <= 1) {
        statusMsg.innerHTML = `<div class="ok-box">🔥 You're ahead of schedule! ${remaining} chapters left in ${daysLeft} days.</div>`;
      } else {
        statusMsg.innerHTML = `<div class="warn-box">⚠️ You need to do ${needed.toFixed(1)} chapters/day to finish by ${dates.end}. ${remaining} left in ${daysLeft} days.</div>`;
      }
    } else {
      statusMsg.innerHTML = done<total ? `<div class="warn-box">⚠️ Target date passed! ${remaining} chapters remaining.</div>` : '';
    }
  } else {
    document.getElementById('revDaysLeft').textContent = '—';
  }

  const pyqDone = CHAPTERS.filter(ch=>data[ch.id]?.pyq).length;
}

// ============================================================
// KEY DATES
// ============================================================
function renderDates() {
  const dates = [
    { d:'Apr 2026', label:'Summer Holidays Begin', info:'2 months to maximise JEE prep!', emoji:'🌞', color:'var(--gold)' },
    { d:'Jun 2026', label:'School Reopens (est.)', info:'Back to regular schedule', emoji:'🏫', color:'var(--text3)' },
    { d:'Sep 2026', label:'11th Revision Target Done', info:'Complete all 40 chapters before this', emoji:'📗', color:'var(--che)' },
    { d:'Nov 2026', label:'JEE Mains Form Release', info:'Keep documents ready — Aadhaar, marksheets', emoji:'📋', color:'var(--accent)' },
    { d:'Jan 2027', label:'JEE Mains Session 1', info:'Target: 99+ percentile | ≥200 marks', emoji:'🎯', color:'var(--accent2)' },
    { d:'Feb 2027', label:'CGBSE Board Exams Begin', info:'Class 12 board exams — 75% attendance needed', emoji:'📝', color:'var(--phy)' },
    { d:'Mar 2027', label:'JEE Mains Session 2', info:'Second attempt — use better score', emoji:'🚀', color:'var(--accent)' },
    { d:'May 2027', label:'JEE Advanced', info:'Top 2.5 lakh from Mains qualify. Your ultimate goal! 🏆', emoji:'⭐', color:'var(--gold)' },
  ];
  const el = document.getElementById('keyDates');
  el.innerHTML = dates.map(d=>`
    <div class="date-item">
      <div class="date-badge" style="border-color:${d.color};">
        <div class="d-num" style="color:${d.color};">${d.emoji}</div>
        <div class="d-mon">${d.d}</div>
      </div>
      <div class="date-info">
        <h4>${d.label}</h4>
        <p>${d.info}</p>
      </div>
    </div>
  `).join('');
}

// ============================================================
// STATS PAGE
// ============================================================
function renderStats() {
  const done = loadDone();
  const sch = loadSchedule();
  let totalDone=0, phyH=0, cheH=0, matH=0;
  for (let day=0;day<7;day++) {
    const blocks = sch[day]||[];
    blocks.forEach((b,i)=>{
      if (done[`${day}-${i}`]) {
        totalDone++;
        // rough hours from type
        if (b.type==='phy') phyH+=1.5;
        if (b.type==='che') cheH+=1.5;
        if (b.type==='mat') matH+=1.5;
      }
    });
  }
  const streak = getStreak();
  const tests = loadTests();
  const revData = loadRevData();
  const revDone = CHAPTERS.filter(ch=>(revData[ch.id]?.status||0)===2).length;
  document.getElementById('s-total').textContent = totalDone;
  document.getElementById('s-streak').textContent = streak.count;
  document.getElementById('s-tests').textContent = tests.length;
  document.getElementById('s-rev').textContent = revDone;

  const mx = Math.max(phyH,cheH,matH,1);
  document.getElementById('hrs-phy').textContent = phyH.toFixed(1)+'h';
  document.getElementById('hrs-che').textContent = cheH.toFixed(1)+'h';
  document.getElementById('hrs-mat').textContent = matH.toFixed(1)+'h';
  document.getElementById('bar-phy').style.width = (phyH/mx*100)+'%';
  document.getElementById('bar-che').style.width = (cheH/mx*100)+'%';
  document.getElementById('bar-mat').style.width = (matH/mx*100)+'%';

  // Day completion chart
  const chartEl = document.getElementById('weekChart');
  const w=280,h=80,bw=28,gap=8,pad=16;
  chartEl.innerHTML = `<svg viewBox="0 0 ${w} ${h+24}" style="width:100%;">
    ${DAYS.map((d,i)=>{
      const blocks = sch[i]||[];
      const doneCount = blocks.filter((_,bi)=>done[`${i}-${bi}`]).length;
      const p = blocks.length ? doneCount/blocks.length : 0;
      const bh = Math.max(2, p*h);
      const x = pad + i*(bw+gap);
      const y = h - bh;
      return `<rect x="${x}" y="${y}" width="${bw}" height="${bh}" rx="5" fill="${p===1?'url(#cg)':p>0?'rgba(124,111,255,0.4)':'rgba(90,90,114,0.2)'}"/>
        <text x="${x+bw/2}" y="${h+14}" text-anchor="middle" fill="#5a5a72" font-size="9" font-family="Space Grotesk">${d}</text>
        ${p>0?`<text x="${x+bw/2}" y="${y-4}" text-anchor="middle" fill="#e8e8f0" font-size="8">${Math.round(p*100)}%</text>`:''}`;
    }).join('')}
    <defs><linearGradient id="cg" x1="0" y1="0" x2="0" y2="1"><stop offset="0%" stop-color="#7c6fff"/><stop offset="100%" stop-color="#ff6fa8"/></linearGradient></defs>
  </svg>`;
}

// ============================================================
// PAGE NAV
// ============================================================
function showPage(name, btn) {
  document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
  document.querySelectorAll('.tab-btn').forEach(b=>b.classList.remove('active'));
  document.getElementById('page-'+name).classList.add('active');
  btn.classList.add('active');
  if (name==='stats') renderStats();
  if (name==='tests') renderTests();
  if (name==='revision') renderRevision();
}

// ============================================================
// INIT
// ============================================================
function init() {
  // Set today's day
  const todayDow = (new Date().getDay()+6)%7;
  currentDay = todayDow;

  renderDayTabs();
  renderBlocks();
  renderDates();

  // Restore rev dates
  const rd = loadRevDates();
  if (rd.start) document.getElementById('revStart').value = rd.start;
  if (rd.end) document.getElementById('revEnd').value = rd.end;

  // Streak
  const streak = getStreak();
  document.getElementById('streakNum').textContent = streak.count;

  // Close modals on bg click
  document.querySelectorAll('.modal-bg').forEach(m=>{
    m.addEventListener('click',e=>{ if(e.target===m) m.classList.remove('open'); });
  });
}

init();
</script>
</body>
</html>
