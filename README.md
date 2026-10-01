
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Dealer Incentive Schemes Portal</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
:root{--primary:#0f172a;--accent:#2563eb;--accent-h:#1d4ed8;--green:#15803d;--green-bg:#dcfce7;--green-bd:#86efac;--orange:#c2410c;--orange-bg:#ffedd5;--orange-bd:#fdba74;--danger:#dc2626;--danger-bg:#fee2e2;--bg:#f1f5f9;--card:#fff;--border:#e2e8f0;--text:#0f172a;--muted:#64748b;--r:12px;--r2:8px;--sh:0 4px 6px -1px rgba(0,0,0,.1),0 2px 4px -1px rgba(0,0,0,.06)}
*{box-sizing:border-box;margin:0;padding:0}
body{font-family:'Inter',system-ui,sans-serif;background:var(--bg);color:var(--text);min-height:100vh;line-height:1.5;-webkit-font-smoothing:antialiased}
.header{background:var(--primary);color:#fff;padding:1rem 2rem;position:sticky;top:0;z-index:100;box-shadow:var(--sh)}
.header-content{max-width:1000px;margin:0 auto;display:flex;justify-content:space-between;align-items:center;gap:1rem}
.header h1{font-size:1.2rem;font-weight:600}
.header p{color:#94a3b8;font-size:.8rem}
.container{max-width:1000px;margin:0 auto;padding:1.5rem 1rem}
.btn{display:inline-flex;align-items:center;justify-content:center;padding:.75rem 1.5rem;background:var(--accent);color:#fff;border:0;border-radius:var(--r2);font:600 .95rem inherit;font-family:inherit;cursor:pointer}
.btn:hover{background:var(--accent-h)}
.btn-logout{background:transparent;border:1px solid #475569;padding:.45rem .9rem;font-size:.8rem;white-space:nowrap}
.login-card{background:var(--card);border-radius:var(--r);box-shadow:var(--sh);padding:2.25rem;max-width:400px;margin:3rem auto;border:1px solid var(--border)}
.login-card h2{text-align:center;margin-bottom:1.5rem;font-size:1.4rem}
.fg{margin-bottom:1.25rem}.fg label{display:block;font-weight:500;font-size:.85rem;margin-bottom:.4rem}
.fg input{width:100%;padding:.75rem 1rem;border:1px solid #cbd5e1;border-radius:var(--r2);font:1rem inherit;font-family:inherit;background:#f8fafc}
.fg input:focus{outline:0;border-color:var(--accent);box-shadow:0 0 0 4px rgba(37,99,235,.1);background:#fff}
.btn-block{width:100%}
.error-msg{background:var(--danger-bg);color:var(--danger);padding:.9rem;border-radius:var(--r2);margin-bottom:1.25rem;font-size:.85rem;font-weight:500;display:none}
#dashboard{display:none}
.dealer-banner{background:linear-gradient(135deg,#1e293b,#0f172a);border-radius:var(--r);padding:1.5rem;margin-bottom:1.25rem;color:#fff;box-shadow:var(--sh)}
.dealer-banner h2{font-size:1.6rem;font-weight:700}
.dealer-banner .code{color:#94a3b8;font-size:.9rem;margin-top:.25rem;display:flex;align-items:center;gap:.5rem}
.badge{background:rgba(255,255,255,.12);padding:.2rem .7rem;border-radius:99px;font-size:.7rem;font-weight:600;letter-spacing:.05em}
.totals{display:grid;grid-template-columns:1fr 1fr;gap:.6rem;margin-top:1.1rem}
.tot{border-radius:var(--r2);padding:.7rem .9rem}
.tot span{display:block;font-size:.7rem;font-weight:600;opacity:.85}
.tot b{font-size:1.25rem}
.tot.cur{background:var(--orange-bg);color:var(--orange)}.tot.pot{background:var(--green-bg);color:var(--green)}
.running{display:flex;align-items:baseline;justify-content:space-between;margin:0 .25rem .75rem;flex-wrap:wrap;gap:.25rem}
.running h2{font-size:1.15rem;font-weight:700}
.running h2 em{font-style:normal;background:var(--accent);color:#fff;border-radius:99px;font-size:.8rem;padding:.1rem .6rem;margin-left:.4rem}
.running small{color:var(--muted);font-size:.8rem}
.schemes{display:grid;gap:.75rem}
details.scheme{background:var(--card);border:1px solid var(--border);border-radius:var(--r);box-shadow:var(--sh);overflow:hidden}
details.scheme>summary{list-style:none;cursor:pointer;padding:1rem 1.1rem;display:flex;align-items:center;gap:.75rem}
details.scheme>summary::-webkit-details-marker{display:none}
.num{flex:none;width:1.9rem;height:1.9rem;border-radius:50%;background:var(--primary);color:#fff;font-size:.85rem;font-weight:700;display:flex;align-items:center;justify-content:center}
.stitle{flex:1;min-width:0}
.stitle h3{font-size:1rem;font-weight:700;line-height:1.25}
.chips{display:flex;gap:.4rem;margin-top:.4rem;flex-wrap:wrap}
.chip{font-size:.72rem;font-weight:600;padding:.15rem .55rem;border-radius:99px}
.chip.cur{background:var(--orange-bg);color:var(--orange)}.chip.pot{background:var(--green-bg);color:var(--green)}
.chev{flex:none;width:.6rem;height:.6rem;border-right:2px solid var(--muted);border-bottom:2px solid var(--muted);transform:rotate(45deg);transition:transform .2s;margin-right:.3rem}
details[open]>summary .chev{transform:rotate(-135deg)}
details[open]>summary{border-bottom:1px solid var(--border);background:#f8fafc}
.body{padding:1.1rem}
.earn-row{display:grid;grid-template-columns:1fr 1fr;gap:.6rem;margin-bottom:.25rem}
.earn{border-radius:var(--r2);padding:.8rem .9rem;border:1px solid}
.earn span{display:block;font-size:.72rem;font-weight:600}
.earn b{font-size:1.4rem;letter-spacing:-.02em}
.earn.cur{background:var(--orange-bg);border-color:var(--orange-bd);color:var(--orange)}
.earn.pot{background:var(--green-bg);border-color:var(--green-bd);color:var(--green)}
.part{font-size:.7rem;font-weight:700;color:#fff;background:var(--accent);display:inline-block;padding:.15rem .6rem;border-radius:4px;letter-spacing:.06em;text-transform:uppercase;margin:1.25rem 0 .5rem}
.part.c{background:#b45309}
.sec{font-size:.72rem;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.05em;margin:1rem 0 .5rem;padding-bottom:.3rem;border-bottom:1px solid var(--border)}
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(150px,1fr));gap:.6rem}
.m{background:#f8fafc;border:1px solid var(--border);border-radius:var(--r2);padding:.7rem .8rem}
.m .l{font-size:.68rem;font-weight:600;color:var(--muted);line-height:1.25;margin-bottom:.25rem}
.m .v{font-size:1.2rem;font-weight:700;word-break:break-word}
.m .v.pos{color:var(--green)}.m .v.neg{color:var(--danger)}.m .v.txt{font-size:1.05rem}
.m.key{background:#eff6ff;border-color:#bfdbfe}
.bar{margin:.6rem 0 .2rem}
.bar .t{display:flex;justify-content:space-between;font-size:.72rem;font-weight:600;color:var(--muted);margin-bottom:.25rem}
.bar .tr{height:9px;background:#e2e8f0;border-radius:9px;overflow:hidden}
.bar .f{height:100%;background:var(--accent);border-radius:9px}
.bar .f.ok{background:var(--green)}
table.mt{width:100%;border-collapse:collapse;font-size:.85rem}
table.mt th{font-size:.68rem;text-transform:uppercase;color:var(--muted);text-align:right;padding:.4rem .5rem;border-bottom:1px solid var(--border)}
table.mt td{padding:.55rem .5rem;text-align:right;border-bottom:1px solid var(--border);font-weight:600}
table.mt th:first-child,table.mt td:first-child{text-align:left}
ul.cond{list-style:none;background:#fffbeb;border:1px solid #fde68a;border-radius:var(--r2);padding:.25rem .9rem}
ul.cond li{font-size:.82rem;color:#78350f;padding:.6rem 0;border-top:1px dashed #fcd34d}
ul.cond li:first-child{border-top:0}
@media(max-width:600px){
.header{padding:.7rem 1rem}.container{padding:1rem .5rem}
.dealer-banner{padding:1.1rem}.dealer-banner h2{font-size:1.35rem}
.grid{grid-template-columns:repeat(2,1fr);gap:.5rem}
.m{padding:.6rem .7rem}.m .v{font-size:1.05rem}.earn b{font-size:1.2rem}
.body{padding:.9rem}.login-card{padding:1.5rem;margin:2rem .5rem}}
</style>
</head>
<body>
<header class="header"><div class="header-content">
<div><h1>Dealer Incentive Schemes</h1><p>Performance &amp; Earnings Dashboard</p></div>
<button id="logoutBtn" class="btn btn-logout" style="display:none" onclick="logout()">Sign Out</button>
</div></header>

<main class="container">
<div id="loginSection"><div class="login-card">
<h2>Dealer Portal Access</h2>
<div id="errorMsg" class="error-msg"></div>
<form id="loginForm" onsubmit="return handleLogin(event)">
<div class="fg"><label for="dealerCode">Dealer Code</label><input type="text" id="dealerCode" placeholder="Enter your Dealer Code" required autocomplete="username"></div>
<div class="fg"><label for="password">Password</label><input type="password" id="password" placeholder="Enter your password" required autocomplete="current-password"></div>
<button type="submit" class="btn btn-block">Access Dashboard</button>
</form></div></div>

<div id="dashboard">
<div class="dealer-banner">
<h2 id="dealerName">—</h2>
<div class="code"><span class="badge">DEALER CODE</span><span id="dealerCodeDisplay">—</span></div>
<div class="totals" id="totals"></div>
</div>
<div class="running"><h2>Schemes Running<em id="schemeCount">0</em></h2><small>Tap a scheme to view details</small></div>
<div id="schemesContainer" class="schemes"></div>
</div>
</main>

<script>
// ========== DEALER DATA (generated from Book3.xlsx) ==========
const DEALERS = {"G1NA": {"code": "G1NA", "password": "G1NAAdinath", "name": "Adinath", "vahan": {"tgt": 145, "ach": 68, "pend": 12, "pipe": 80, "gap": 65, "cur": 204000, "pot": 435000}, "pp": {"base": 537, "req": 564, "ach": 66, "gap": 498, "pq1": 87, "pcur": 54, "pgr": -0.3793, "pot": 1269000, "cur": 148500}, "psl": {"grp": "B", "rank": "-", "sb": 383, "sa": 66, "sg": -0.8277, "pb": 322, "pr": 54, "pgr": -0.8323, "qb": 110, "qa": 66, "qg": -0.4}, "nac": {"base": 422, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 452, "gvq3": 19, "req": 24, "gv_ach": null, "gv_gap": 24, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0.0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0.0, "cur": 0, "pot": 40000}}, "D7NA": {"code": "D7NA", "password": "D7NACity", "name": "City Cars", "vahan": {"tgt": 165, "ach": 70, "pend": 37, "pipe": 107, "gap": 58, "cur": 210000, "pot": 495000}, "pp": {"base": 715, "req": 751, "ach": 87, "gap": 664, "pq1": 109, "pcur": 68, "pgr": -0.3761, "pot": 1689750, "cur": 195750}, "psl": {"grp": "B", "rank": "-", "sb": 470, "sa": 87, "sg": -0.8149, "pb": 411, "pr": 68, "pgr": -0.8345, "qb": 134, "qa": 87, "qg": -0.3507}, "nac": {"base": 559, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 599, "gvq3": 26, "req": 33, "gv_ach": null, "gv_gap": 33, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "KMNA": {"code": "KMNA", "password": "KMNAInfinity", "name": "Infinity", "vahan": {"tgt": 35, "ach": 26, "pend": 8, "pipe": 34, "gap": 1, "cur": 78000, "pot": 105000}, "pp": {"base": 170, "req": 179, "ach": 31, "gap": 148, "pq1": 23, "pcur": 25, "pgr": 0.087, "pot": 402750, "cur": 69750}, "psl": {"grp": "D", "rank": "-", "sb": 131, "sa": 31, "sg": -0.7634, "pb": 108, "pr": 25, "pgr": -0.7685, "qb": 30, "qa": 31, "qg": 0.0333}, "nac": {"base": 133, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 143, "gvq3": 4, "req": 5, "gv_ach": null, "gv_gap": 5, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "03NB": {"code": "03NB", "password": "03NBJeewan", "name": "Jeewan", "vahan": {"tgt": 100, "ach": 47, "pend": 13, "pipe": 60, "gap": 40, "cur": 141000, "pot": 300000}, "pp": {"base": 768, "req": 806, "ach": 56, "gap": 750, "pq1": 56, "pcur": 33, "pgr": -0.4107, "pot": 1813500, "cur": 126000}, "psl": {"grp": "B", "rank": "-", "sb": 633, "sa": 56, "sg": -0.9115, "pb": 426, "pr": 33, "pgr": -0.9225, "qb": 94, "qa": 56, "qg": -0.4043}, "nac": {"base": 593, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 635, "gvq3": 20, "req": 25, "gv_ach": null, "gv_gap": 25, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "U5NA": {"code": "U5NA", "password": "U5NAKamthi", "name": "Kamthi Motors", "vahan": {"tgt": 105, "ach": 58, "pend": 17, "pipe": 75, "gap": 30, "cur": 174000, "pot": 315000}, "pp": {"base": 493, "req": 518, "ach": 69, "gap": 449, "pq1": 74, "pcur": 65, "pgr": -0.1216, "pot": 1165500, "cur": 155250}, "psl": {"grp": "C", "rank": "-", "sb": 347, "sa": 69, "sg": -0.8012, "pb": 338, "pr": 65, "pgr": -0.8077, "qb": 79, "qa": 69, "qg": -0.1266}, "nac": {"base": 376, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 403, "gvq3": 19, "req": 24, "gv_ach": null, "gv_gap": 24, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "53NE": {"code": "53NE", "password": "53NEKTL", "name": "KTL", "vahan": {"tgt": 175, "ach": 103, "pend": 38, "pipe": 141, "gap": 34, "cur": 309000, "pot": 525000}, "pp": {"base": 409, "req": 429, "ach": 125, "gap": 304, "pq1": 70, "pcur": 52, "pgr": -0.2571, "pot": 965250, "cur": 281250}, "psl": {"grp": "National A", "rank": "-", "sb": 199, "sa": 125, "sg": -0.3719, "pb": 117, "pr": 52, "pgr": -0.5556, "qb": 122, "qa": 125, "qg": 0.0246}, "nac": {"base": 405, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 434, "gvq3": 15, "req": 19, "gv_ach": null, "gv_gap": 19, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "30NB": {"code": "30NB", "password": "30NBNikunj", "name": "Nikunj", "vahan": {"tgt": 110, "ach": 45, "pend": 41, "pipe": 86, "gap": 24, "cur": 135000, "pot": 330000}, "pp": {"base": 360, "req": 378, "ach": 74, "gap": 304, "pq1": 38, "pcur": 32, "pgr": -0.1579, "pot": 850500, "cur": 166500}, "psl": {"grp": "B", "rank": "-", "sb": 272, "sa": 74, "sg": -0.7279, "pb": 168, "pr": 32, "pgr": -0.8095, "qb": 63, "qa": 74, "qg": 0.1746}, "nac": {"base": 284, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 304, "gvq3": 11, "req": 14, "gv_ach": null, "gv_gap": 14, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "AUNA": {"code": "AUNA", "password": "AUNANimar", "name": "Nimar Motors", "vahan": {"tgt": 80, "ach": 56, "pend": 19, "pipe": 75, "gap": 5, "cur": 168000, "pot": 240000}, "pp": {"base": 478, "req": 502, "ach": 75, "gap": 427, "pq1": 43, "pcur": 46, "pgr": 0.0698, "pot": 1129500, "cur": 168750}, "psl": {"grp": "B", "rank": "-", "sb": 336, "sa": 75, "sg": -0.7768, "pb": 250, "pr": 46, "pgr": -0.816, "qb": 59, "qa": 75, "qg": 0.2712}, "nac": {"base": 369, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 395, "gvq3": 22, "req": 28, "gv_ach": null, "gv_gap": 28, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "53NB": {"code": "53NB", "password": "53NBOcean", "name": "Ocean Group", "vahan": {"tgt": 305, "ach": 173, "pend": 78, "pipe": 251, "gap": 54, "cur": 519000, "pot": 915000}, "pp": {"base": 1489, "req": 1563, "ach": 229, "gap": 1334, "pq1": 125, "pcur": 110, "pgr": -0.12, "pot": 3516750, "cur": 515250}, "psl": {"grp": "A", "rank": "-", "sb": 985, "sa": 229, "sg": -0.7675, "pb": 631, "pr": 110, "pgr": -0.8257, "qb": 225, "qa": 229, "qg": 0.0178}, "nac": {"base": 1146, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 1227, "gvq3": 80, "req": 100, "gv_ach": null, "gv_gap": 100, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "53NA": {"code": "53NA", "password": "53NAPatel", "name": "Patel Group", "vahan": {"tgt": 215, "ach": 114, "pend": 61, "pipe": 175, "gap": 40, "cur": 342000, "pot": 645000}, "pp": {"base": 923, "req": 969, "ach": 162, "gap": 807, "pq1": 98, "pcur": 102, "pgr": 0.0408, "pot": 2180250, "cur": 364500}, "psl": {"grp": "A", "rank": "-", "sb": 649, "sa": 162, "sg": -0.7504, "pb": 480, "pr": 102, "pgr": -0.7875, "qb": 163, "qa": 162, "qg": -0.0061}, "nac": {"base": 680, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 728, "gvq3": 34, "req": 43, "gv_ach": null, "gv_gap": 43, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "30NA": {"code": "30NA", "password": "30NAPrem", "name": "Prem Group", "vahan": {"tgt": 195, "ach": 116, "pend": 26, "pipe": 142, "gap": 53, "cur": 348000, "pot": 585000}, "pp": {"base": 542, "req": 569, "ach": 132, "gap": 437, "pq1": 78, "pcur": 47, "pgr": -0.3974, "pot": 1280250, "cur": 297000}, "psl": {"grp": "National A", "rank": "-", "sb": 485, "sa": 132, "sg": -0.7278, "pb": 294, "pr": 47, "pgr": -0.8401, "qb": 148, "qa": 132, "qg": -0.1081}, "nac": {"base": 384, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 411, "gvq3": 15, "req": 19, "gv_ach": null, "gv_gap": 19, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "03NC": {"code": "03NC", "password": "03NCRajrup", "name": "Rajrup", "vahan": {"tgt": 185, "ach": 118, "pend": 17, "pipe": 135, "gap": 50, "cur": 354000, "pot": 555000}, "pp": {"base": 949, "req": 996, "ach": 115, "gap": 881, "pq1": 80, "pcur": 55, "pgr": -0.3125, "pot": 2241000, "cur": 258750}, "psl": {"grp": "B", "rank": "-", "sb": 653, "sa": 115, "sg": -0.8239, "pb": 493, "pr": 55, "pgr": -0.8884, "qb": 129, "qa": 115, "qg": -0.1085}, "nac": {"base": 719, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 770, "gvq3": 42, "req": 53, "gv_ach": null, "gv_gap": 53, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "53NC": {"code": "53NC", "password": "53NCRukmani", "name": "Rukmani", "vahan": {"tgt": 170, "ach": 104, "pend": 55, "pipe": 159, "gap": 11, "cur": 312000, "pot": 510000}, "pp": {"base": 851, "req": 894, "ach": 124, "gap": 770, "pq1": 55, "pcur": 62, "pgr": 0.1273, "pot": 2011500, "cur": 279000}, "psl": {"grp": "A", "rank": "-", "sb": 645, "sa": 124, "sg": -0.8078, "pb": 442, "pr": 62, "pgr": -0.8597, "qb": 103, "qa": 124, "qg": 0.2039}, "nac": {"base": 643, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 689, "gvq3": 46, "req": 58, "gv_ach": null, "gv_gap": 58, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "54ND": {"code": "54ND", "password": "54NBShubh", "name": "Shubh", "vahan": {"tgt": 125, "ach": 80, "pend": 16, "pipe": 96, "gap": 29, "cur": 240000, "pot": 375000}, "pp": {"base": 588, "req": 617, "ach": 89, "gap": 528, "pq1": 90, "pcur": 79, "pgr": -0.1222, "pot": 1388250, "cur": 200250}, "psl": {"grp": "B", "rank": "-", "sb": 391, "sa": 89, "sg": -0.7724, "pb": 367, "pr": 79, "pgr": -0.7847, "qb": 100, "qa": 89, "qg": -0.11}, "nac": {"base": 468, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 501, "gvq3": 27, "req": 34, "gv_ach": null, "gv_gap": 34, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "54NC": {"code": "54NC", "password": "54NCStandard", "name": "Standard Group", "vahan": {"tgt": 200, "ach": 120, "pend": 34, "pipe": 154, "gap": 46, "cur": 360000, "pot": 600000}, "pp": {"base": 852, "req": 895, "ach": 135, "gap": 760, "pq1": 157, "pcur": 106, "pgr": -0.3248, "pot": 2013750, "cur": 303750}, "psl": {"grp": "B", "rank": "-", "sb": 600, "sa": 135, "sg": -0.775, "pb": 551, "pr": 106, "pgr": -0.8076, "qb": 178, "qa": 135, "qg": -0.2416}, "nac": {"base": 694, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 743, "gvq3": 43, "req": 54, "gv_ach": null, "gv_gap": 54, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "3QNB": {"code": "3QNB", "password": "3QNAUnitara", "name": "Unitara", "vahan": {"tgt": 40, "ach": 40, "pend": 4, "pipe": 44, "gap": -4, "cur": 120000, "pot": 120000}, "pp": {"base": 193, "req": 203, "ach": 36, "gap": 167, "pq1": 16, "pcur": 23, "pgr": 0.4375, "pot": 456750, "cur": 81000}, "psl": {"grp": "C", "rank": "-", "sb": 137, "sa": 36, "sg": -0.7372, "pb": 77, "pr": 23, "pgr": -0.7013, "qb": 38, "qa": 36, "qg": -0.0526}, "nac": {"base": 152, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 163, "gvq3": 8, "req": 10, "gv_ach": null, "gv_gap": 10, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}, "3WNA": {"code": "3WNA", "password": "3WNAYug", "name": "Yug Cars", "vahan": {"tgt": 50, "ach": 30, "pend": 7, "pipe": 37, "gap": 13, "cur": 90000, "pot": 150000}, "pp": {"base": 275, "req": 289, "ach": 33, "gap": 256, "pq1": 13, "pcur": 10, "pgr": -0.2308, "pot": 650250, "cur": 74250}, "psl": {"grp": "C", "rank": "-", "sb": 213, "sa": 33, "sg": -0.8451, "pb": 119, "pr": 10, "pgr": -0.916, "qb": 35, "qa": 33, "qg": -0.0571}, "nac": {"base": 196, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 210, "gvq3": 12, "req": 15, "gv_ach": null, "gv_gap": 15, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0}, "mega": {"tgt": null, "ach": null, "pct": null, "mi": null, "mipct": null, "slab": null, "gv": {"t": null, "a": null, "p": null}, "inv": {"t": null, "a": null, "p": null}, "xl6": {"t": null, "a": null, "p": null}, "jim": {"t": null, "a": null, "p": null}, "cur": null, "pot": 0}, "gv": {"tgt": 1, "ach": null, "pct": 0, "cur": 0, "pot": 50000}, "dtd": {"tgt": 1, "ach": null, "pct": 0, "sigma": null, "delta": 0, "cur": 0, "pot": 40000}}};

// ========== SCHEME CONDITIONS ==========
const CONDITIONS = {
  vahan: [
    {l:"Super Qualifying Criteria",t:"It is compulsory to achieve atleast 40% Retail & 40% Vahan Target* for SEP-26 by 15th September’26 to qualify for any Incentive"},
    {t:"It is compulsory to achieve atleast 100% Retail Target for Sep-26 to qualify for any Incentive. BI Net Retail will be considered to calculate Retail Target Achievement."},
    {t:"Permanent registration done for All Models of NEXA Channel would be considered for scheme calculation and payout"},
    {t:"Payout will be paid on Vahan registration issued against applicable models from 1-Sep-26 to 30-Sep-26 updated till 5th Oct’26"}
  ],
  pp: [
    {l:"Scheme Period",t:"September'26 to December'26"},
    {l:"Slabs",t:"Slab 1 : >=0% to <3% : 700 || Slab 2 : >=3% to <5% : 1,000 || Slab 3 : >=5% : 1,500"},
    {l:"Additional Earning Opportunity (September)",t:"No retail de-growth of “All Models combined retail (Excluding CNG Variants)” in Sep’26 (ie. from 1st Sep’26 - 30th Sep’26) over Q1’26-27 monthly retail average of “All Models combined retail (Excluding CNG Variants)"},
    {l:"Vahan / MI Condition",t:"At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail"}
  ],
  psl: [
    {l:"Super Qualifying Condition",t:"No net retail de-growth during Sep’26 to Nov'26 over Sep’25 to Nov'25."},
    {l:"Vahan / MI Condition",t:"At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 7th Jan'27 for scheme period's retail"},
    {l:"Ranking Condition 1",t:"Sept to Nov - All Models (excluding CNG variants) Net retail growth during Sep’26 to Nov'26 over Sep’25 to Nov'25 (Weightage - 30%)"},
    {l:"Ranking Condition 2",t:"September - Net Retail Growth (All Models) in Sep'26 over the Apr'26 to Jun'26 average monthly Net Retail"}
  ],
  nac: [
    {l:"Target Slabs",t:"Sigma - 0%, Delta - 2%, Zeta - 4%, Alpha - 7%"},
    {l:"Vahan / MI Condition",t:"At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail"},
    {l:"Additional Earning Opportunity of 25% (October)",t:"Atleast 25% retail growth in Grand Vitara & e VITARA (combined) in Oct'26 over Q3'25-26 monthly average retail."},
    {t:"Slab Growth shall be considered basis retail done in Q3’26-27 over Q3’25-26 (excluding Ignis)."}
  ],
  mega: [
    {l:"Super Qualifying Condition",t:"100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount."},
    {t:"Minimum 90% All Models NET BI Retail Target achievement between 1st Oct’26 – 31st Oct’26 (both days inclusive)."},
    {l:"Qualifying Condition",t:"Minimum 90% All Models Retail Target Achievement between 1st Oct’26 – 31st Oct’26 (both days inclusive)."}
  ],
  gv: [
    {t:"It is mandatory to achieve at least 100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount."}
  ],
  dtd: [
    {l:"Qualifying Condition",t:"97% Wholesale Target Achievement of GV (All Variants) at Parent level."},
    {l:"Super Qualifying Condition",t:"It is mandatory to achieve at least 100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount."},
    {t:"90% NET BI Retail Target Achievement of GV (All Variants) at Parent level."}
  ]
};

// ========== FORMAT HELPERS ==========
function fmt(v,type){
  if(v===null||v===undefined||v===''||v==='-') return '—';
  if(typeof v==='number'){
    if(type==='pct') return (v*100).toFixed(1)+'%';
    if(type==='cur') return '₹'+v.toLocaleString('en-IN');
    return Number.isInteger(v)?v.toLocaleString('en-IN'):v.toFixed(2);
  }
  return v;
}
function esc(s){return String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;')}
function m(label,v,type,key){
  let c='';
  if(type==='txt') c='txt';
  else if(type==='pct'&&typeof v==='number') c=v>0?'pos':(v<0?'neg':'');
  return `<div class="m${key?' key':''}"><div class="l">${label}</div><div class="v ${c}">${fmt(v,type)}</div></div>`;
}
const grid=(...x)=>`<div class="grid">${x.join('')}</div>`;
const sec=(t,h)=>`<div class="sec">${t}</div>${h}`;
function bar(label,ach,tgt){
  if(typeof ach!=='number'||typeof tgt!=='number'||tgt<=0) return '';
  const p=Math.round(ach/tgt*100);
  return `<div class="bar"><div class="t"><span>${label}</span><span>${p}%</span></div><div class="tr"><div class="f ${p>=100?'ok':''}" style="width:${Math.min(p,100)}%"></div></div></div>`;
}
function earn(c,p){
  return `<div class="earn-row">
    <div class="earn cur"><span>Current Earnings</span><b>${fmt(c,'cur')}</b></div>
    <div class="earn pot"><span>Earning Potential</span><b>${fmt(p,'cur')}</b></div></div>`;
}
function conditions(key){
  return `<div class="part c">Scheme Conditions</div><ul class="cond">`+
    CONDITIONS[key].map(c=>`<li>${c.l?'<strong>'+esc(c.l)+':</strong> ':''}${esc(c.t)}</li>`).join('')+`</ul>`;
}
function card(n,title,cur,pot,workings,key,open){
  return `<details class="scheme"${open?' open':''}>
    <summary><span class="num">${n}</span>
      <div class="stitle"><h3>${title}</h3>
        <div class="chips"><span class="chip cur">Earned ${fmt(cur,'cur')}</span><span class="chip pot">Potential ${fmt(pot,'cur')}</span></div></div>
      <span class="chev"></span></summary>
    <div class="body"><div class="part">Scheme Workings</div>${earn(cur,pot)}${workings}${conditions(key)}</div>
  </details>`;
}

// ========== SCHEME RENDERERS ==========
function rVahan(v){
  return card(1,'Vahan Retail Cashback – October',v.cur,v.pot,
    bar('Achievement vs Target',v.ach,v.tgt)+
    sec('Target vs Achievement',grid(m('Target',v.tgt),m('Achievement',v.ach,0,1),m('Gap to Target',v.gap,0,1)))+
    sec('Pipeline',grid(m('Pendency',v.pend),m('Total Pipeline',v.pipe))),'vahan');
}
function rPP(p){
  return card(2,'Maruti Power Performer 2.0',p.cur,p.pot,
    bar('Achievement vs Required',p.ach,p.req)+
    sec('Scheme Achievement (Sep–Dec)',grid(m('All Model Retail Base',p.base),m('Required (@5% Growth)',p.req),m('Achievement',p.ach,0,1),m('Gap',p.gap,0,1)))+
    sec('Additional Opportunity – September',grid(m('Petrol Retail (Q1 Avg)',p.pq1),m('Current Petrol Retail',p.pcur),m('Growth',p.pgr,'pct',1))),'pp');
}
function rPSL(s){
  return card(3,'Maruti Suzuki Premier League',s.cur,s.pot,
    sec('Your Standing',grid(m('Dealer Group',s.grp,'txt'),m('HO Ranking',s.rank,'txt')))+
    sec('Super Qualifying Criteria (Sep–Nov)',grid(m('Retail Base',s.sb),m('Retail Achievement',s.sa),m('Growth %',s.sg,'pct',1)))+
    sec('Ranking Condition 1 – Petrol (Sep–Nov)',grid(m('Petrol Base',s.pb),m('Petrol Retail',s.pr),m('Growth %',s.pgr,'pct',1)))+
    sec('Ranking Condition 2 – September',grid(m('Q1 Retail Base',s.qb),m('Achievement',s.qa),m('Growth %',s.qg,'pct',1))),'psl');
}
function rNAC(n){
  return card(4,"NEXA Achiever's Club",n.cur,n.pot,
    sec('Slab Achievement',grid(m('Retail Base (Excl. Ignis)',n.base),m('Retail Achievement',n.ach,0,1)))+
    sec('Gap to Each Slab (cars needed)',grid(m('Sigma (₹900/car)',n.g_sigma),m('Delta (₹1,100/car)',n.g_delta),m('Zeta (₹1,400/car)',n.g_zeta),m('Alpha (₹1,800/car)',n.g_alpha)))+
    sec('Additional Opportunity – October (GV & e VITARA)',grid(m('Q3 GV & EV Avg Retail',n.gvq3),m('Required Retail',n.req),m('Achievement',n.gv_ach,0,1),m('Gap',n.gv_gap,0,1)))+
    sec('Wholesale Achievement – October',bar('Wholesale Achievement',n.wach,n.wtgt)+grid(m('Target',n.wtgt),m('Achievement',n.wach),m('Achi %',n.wpct,'pct'))),'nac');
}
function rMega(g){
  const rows=[['Grand Vitara Strong Hybrid',g.gv],['Invicto',g.inv],['XL6',g.xl6],['Jimny',g.jim]]
    .map(([n,x])=>`<tr><td>${n}</td><td>${fmt(x.t)}</td><td>${fmt(x.a)}</td><td>${fmt(x.p,'cur')}</td></tr>`).join('');
  return card(5,'Mega Dealer Retail Cashback – October',g.cur,g.pot,
    bar('All Model Retail Achievement',g.ach,g.tgt)+
    sec('Qualifying Criteria – All Model Retail',grid(m('Target',g.tgt),m('Achi Net BI',g.ach,0,1),m('Achi %',g.pct,'pct',1),m('DMS backed by MI',g.mi),m('MI Achi %',g.mipct,'pct'),m('Slab',g.slab,'txt')))+
    sec('Model-wise Workings',`<table class="mt"><tr><th>Model</th><th>Target</th><th>Achi</th><th>Payout</th></tr>${rows}</table>`),'mega');
}
function rGV(g){
  return card(6,'Grand Vitara Strong Hybrid Super Cashback',g.cur,g.pot,
    bar('Achievement vs Target',g.ach,g.tgt)+
    sec('Target vs Achievement',grid(m('Target',g.tgt),m('Achievement',g.ach,0,1),m('Achi %',g.pct,'pct',1))),'gv');
}
function rDTD(d){
  return card(7,'Dealer Trade Discount Scheme – October',d.cur,d.pot,
    bar('GV Retail Achievement',d.ach,d.tgt)+
    sec('GV Retail Target vs Achievement',grid(m('GV Retail Target',d.tgt),m('Achievement',d.ach,0,1),m('Achi %',d.pct,'pct',1)))+
    sec('Wholesale GV Slabs',grid(m('Wholesale GV – Sigma',d.sigma),m('Wholesale GV – Delta',d.delta))),'dtd');
}

// ========== LOGIN & DASHBOARD ==========
function handleLogin(e){
  e.preventDefault();
  const code=document.getElementById('dealerCode').value.trim().toUpperCase();
  const pwd=document.getElementById('password').value.trim();
  const err=document.getElementById('errorMsg');
  const d=DEALERS[code];
  if(!d||d.password!==pwd){err.style.display='block';err.textContent='Invalid Dealer Code or Password. Please verify and try again.';return false}
  err.style.display='none';showDashboard(d);return false;
}
function logout(){
  document.getElementById('dashboard').style.display='none';
  document.getElementById('loginSection').style.display='block';
  document.getElementById('logoutBtn').style.display='none';
  document.getElementById('loginForm').reset();
}
function showDashboard(d){
  document.getElementById('loginSection').style.display='none';
  document.getElementById('dashboard').style.display='block';
  document.getElementById('logoutBtn').style.display='inline-flex';
  document.getElementById('dealerName').textContent=d.name;
  document.getElementById('dealerCodeDisplay').textContent=d.code;
  const parts=[rVahan(d.vahan),rPP(d.pp),rPSL(d.psl),rNAC(d.nac),rMega(d.mega),rGV(d.gv),rDTD(d.dtd)];
  document.getElementById('schemesContainer').innerHTML=parts.join('');
  document.getElementById('schemeCount').textContent=parts.length;
  const S=k=>['vahan','pp','psl','nac','mega','gv','dtd'].reduce((a,s)=>a+(Number(d[s][k])||0),0);
  document.getElementById('totals').innerHTML=
    `<div class="tot cur"><span>Total Current Earnings</span><b>${fmt(S('cur'),'cur')}</b></div>
     <div class="tot pot"><span>Total Earning Potential</span><b>${fmt(S('pot'),'cur')}</b></div>`;
  window.scrollTo({top:0,behavior:'smooth'});
}
</script>
</body>
</html>