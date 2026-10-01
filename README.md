
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
<meta name="theme-color" content="#0f172a">
<meta name="apple-mobile-web-app-capable" content="yes">
<title>Dealer Incentive App</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<style>
:root{--navy:#0f172a;--navy2:#1e293b;--accent:#3b82f6;--green:#15803d;--green-bg:#dcfce7;--green-bd:#86efac;--orange:#c2410c;--orange-bg:#ffedd5;--orange-bd:#fdba74;--red:#dc2626;--bg:#f1f5f9;--card:#fff;--bd:#e2e8f0;--muted:#64748b}
*{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
html,body{height:100%;overflow:hidden;background:#020617}
body{font-family:'Inter',system-ui,sans-serif;color:var(--navy);-webkit-font-smoothing:antialiased}
.app{position:relative;height:100%;max-width:430px;margin:0 auto;background:var(--bg);overflow:hidden;display:flex;flex-direction:column}
@media(min-width:500px){.app{height:min(100%,900px);margin-top:max(0px,calc((100% - 900px)/2));border-radius:28px}}
.screen{position:absolute;inset:0;display:none;flex-direction:column;padding-top:env(safe-area-inset-top);padding-bottom:env(safe-area-inset-bottom)}
.screen.on{display:flex}

/* Login */
#login{background:linear-gradient(160deg,#0f172a,#1e3a8a);justify-content:center;padding:1.5rem}
.logo{width:64px;height:64px;border-radius:18px;background:#fff;color:var(--navy);display:flex;align-items:center;justify-content:center;font-size:1.9rem;margin:0 auto 1rem;box-shadow:0 10px 25px rgba(0,0,0,.3)}
#login h1{color:#fff;text-align:center;font-size:1.4rem;font-weight:800}
#login p.s{color:#93c5fd;text-align:center;font-size:.85rem;margin-bottom:1.75rem}
.lc{background:#fff;border-radius:20px;padding:1.4rem;box-shadow:0 20px 40px rgba(0,0,0,.35)}
.lc label{display:block;font-size:.75rem;font-weight:600;margin-bottom:.35rem;color:var(--muted)}
.lc input{width:100%;padding:.8rem 1rem;border:1px solid #cbd5e1;border-radius:12px;font:1rem inherit;font-family:inherit;background:#f8fafc;margin-bottom:1rem}
.lc input:focus{outline:0;border-color:var(--accent);box-shadow:0 0 0 4px rgba(59,130,246,.15)}
.btn{width:100%;padding:.9rem;border:0;border-radius:12px;background:var(--accent);color:#fff;font:700 1rem inherit;font-family:inherit}
.btn:active{transform:scale(.98)}
.err{display:none;background:#fee2e2;color:var(--red);padding:.7rem;border-radius:10px;font-size:.8rem;font-weight:600;margin-bottom:1rem}

/* Top bar */
.top{background:var(--navy);color:#fff;padding:.8rem 1rem .9rem;display:flex;align-items:center;gap:.75rem;flex:none}
.av{width:40px;height:40px;border-radius:12px;background:var(--accent);display:flex;align-items:center;justify-content:center;font-weight:800;font-size:1.1rem;flex:none}
.top .who{flex:1;min-width:0}
.top h2{font-size:1.05rem;font-weight:700;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
.top small{color:#94a3b8;font-size:.72rem}
.ib{background:rgba(255,255,255,.1);border:0;color:#fff;width:38px;height:38px;border-radius:12px;font-size:1.05rem;flex:none}

/* Home */
.home{flex:1;display:flex;flex-direction:column;padding:.75rem;gap:.6rem;min-height:0}
.tots{display:grid;grid-template-columns:1fr 1fr;gap:.5rem;flex:none}
.tot{border-radius:14px;padding:.6rem .8rem;border:1px solid}
.tot span{display:block;font-size:.66rem;font-weight:700;text-transform:uppercase;letter-spacing:.03em}
.tot b{font-size:1.25rem;font-weight:800;letter-spacing:-.02em}
.tot.cur,.earn.cur{background:var(--orange-bg);border-color:var(--orange-bd);color:var(--orange)}
.tot.pot,.earn.pot{background:var(--green-bg);border-color:var(--green-bd);color:var(--green)}
.lbl{display:flex;justify-content:space-between;align-items:center;font-size:.8rem;font-weight:700;flex:none;padding:0 .15rem}
.lbl em{font-style:normal;background:var(--accent);color:#fff;border-radius:99px;font-size:.7rem;padding:.05rem .5rem;margin-left:.35rem}
.lbl small{font-weight:500;color:var(--muted);font-size:.7rem}
.tiles{flex:1;min-height:0;display:grid;grid-template-columns:1fr 1fr;grid-auto-rows:1fr;gap:.5rem}
.tile{background:var(--card);border:1px solid var(--bd);border-radius:16px;padding:.6rem .7rem;display:flex;flex-direction:column;justify-content:space-between;text-align:left;font-family:inherit;color:inherit;box-shadow:0 1px 3px rgba(0,0,0,.06);min-height:0;overflow:hidden}
.tile:active{background:#f8fafc;transform:scale(.98)}
.tile.w{grid-column:span 2}
.tt{display:flex;align-items:center;gap:.4rem}
.tn{flex:none;width:1.4rem;height:1.4rem;border-radius:50%;background:var(--navy);color:#fff;font-size:.7rem;font-weight:700;display:flex;align-items:center;justify-content:center}
.tt h3{font-size:.78rem;font-weight:700;line-height:1.15}
.ev{display:flex;justify-content:space-between;gap:.3rem;font-size:.66rem;font-weight:700}
.ev .c{color:var(--orange)}.ev .p{color:var(--green)}
.ev b{display:block;font-size:.85rem;font-weight:800}
.pb{height:5px;background:#e2e8f0;border-radius:5px;overflow:hidden}
.pb i{display:block;height:100%;background:var(--accent);border-radius:5px}.pb i.ok{background:var(--green)}
.pt{font-size:.62rem;color:var(--muted);font-weight:600;display:flex;justify-content:space-between}

/* Detail */
#detail{background:var(--bg);transform:translateX(100%);transition:transform .25s ease;display:flex}
#detail.on{transform:none}
.dh{background:var(--navy);color:#fff;padding:.7rem 1rem;display:flex;align-items:center;gap:.7rem;flex:none}
.dh h2{font-size:1rem;font-weight:700;line-height:1.2}
.dbody{flex:1;display:flex;flex-direction:column;min-height:0;padding:.75rem;gap:.6rem}
.earn-row{display:grid;grid-template-columns:1fr 1fr;gap:.5rem;flex:none}
.earn{border-radius:14px;padding:.6rem .8rem;border:1px solid}
.earn span{display:block;font-size:.66rem;font-weight:700;text-transform:uppercase}
.earn b{font-size:1.3rem;font-weight:800}
.seg{display:grid;grid-template-columns:1fr 1fr;background:#e2e8f0;border-radius:12px;padding:3px;flex:none}
.seg button{border:0;background:transparent;padding:.55rem;border-radius:10px;font:600 .85rem inherit;font-family:inherit;color:var(--muted)}
.seg button.on{background:#fff;color:var(--navy);box-shadow:0 1px 3px rgba(0,0,0,.15)}
.pane{flex:1;min-height:0;overflow-y:auto;-webkit-overflow-scrolling:touch}
.sec{font-size:.66rem;font-weight:700;color:var(--muted);text-transform:uppercase;letter-spacing:.05em;margin:.6rem 0 .35rem}
.sec:first-child{margin-top:0}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:.4rem}
.grid.two{grid-template-columns:repeat(2,1fr)}
.m{background:#fff;border:1px solid var(--bd);border-radius:12px;padding:.5rem .6rem}
.m .l{font-size:.62rem;font-weight:600;color:var(--muted);line-height:1.2;margin-bottom:.15rem}
.m .v{font-size:1.05rem;font-weight:800;word-break:break-word}
.m .v.pos{color:var(--green)}.m .v.neg{color:var(--red)}.m .v.txt{font-size:.95rem}
.m.key{background:#eff6ff;border-color:#bfdbfe}
.bar{margin:.1rem 0 .3rem}
.bar .t{display:flex;justify-content:space-between;font-size:.68rem;font-weight:700;color:var(--muted);margin-bottom:.2rem}
.bar .tr{height:8px;background:#e2e8f0;border-radius:8px;overflow:hidden}
.bar .f{height:100%;background:var(--accent);border-radius:8px}.bar .f.ok{background:var(--green)}
table.mt{width:100%;border-collapse:collapse;font-size:.78rem;background:#fff;border-radius:12px;overflow:hidden}
table.mt th{font-size:.62rem;text-transform:uppercase;color:var(--muted);text-align:right;padding:.4rem .5rem;background:#f8fafc}
table.mt td{padding:.5rem;text-align:right;border-top:1px solid var(--bd);font-weight:700}
table.mt th:first-child,table.mt td:first-child{text-align:left}
ul.cond{list-style:none}
ul.cond li{background:#fffbeb;border:1px solid #fde68a;border-radius:12px;padding:.6rem .75rem;margin-bottom:.4rem;font-size:.78rem;color:#78350f}
</style>
</head>
<body>
<div class="app">

<section id="login" class="screen on">
  <div class="logo">🚗</div>
  <h1>Dealer Incentive App</h1>
  <p class="s">Performance &amp; Earnings Dashboard</p>
  <form class="lc" onsubmit="return handleLogin(event)">
    <div id="errorMsg" class="err"></div>
    <label for="dealerCode">DEALER CODE</label>
    <input id="dealerCode" placeholder="Enter your Dealer Code" required autocomplete="username" autocapitalize="characters">
    <label for="password">PASSWORD</label>
    <input id="password" type="password" placeholder="Enter your password" required autocomplete="current-password">
    <button class="btn" type="submit">Sign In</button>
  </form>
</section>

<section id="home" class="screen">
  <div class="top"><div class="av" id="av">—</div>
    <div class="who"><h2 id="dealerName">—</h2><small>Dealer Code: <span id="dealerCodeDisplay">—</span></small></div>
    <button class="ib" onclick="logout()" aria-label="Sign out">⏻</button></div>
  <div class="home">
    <div class="tots" id="totals"></div>
    <div class="lbl"><span>Schemes Running<em id="cnt">0</em></span><small>Tap a scheme for details</small></div>
    <div class="tiles" id="tiles"></div>
  </div>
</section>

<section id="detail" class="screen">
  <div class="dh"><button class="ib" onclick="closeDetail()" aria-label="Back">←</button><h2 id="dTitle"></h2></div>
  <div class="dbody">
    <div class="earn-row" id="dEarn"></div>
    <div class="seg"><button id="tabW" class="on" onclick="tab('w')">Scheme Workings</button><button id="tabC" onclick="tab('c')">Conditions</button></div>
    <div class="pane" id="dPane"></div>
  </div>
</section>

</div>
<script>
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

// ========== HELPERS ==========
function fmt(v,type){
  if(v===null||v===undefined||v===''||v==='-') return '—';
  if(typeof v==='number'){
    if(type==='pct') return (v*100).toFixed(1)+'%';
    if(type==='cur') return '₹'+v.toLocaleString('en-IN');
    return Number.isInteger(v)?v.toLocaleString('en-IN'):v.toFixed(2);
  }
  return v;
}
const esc=s=>String(s).replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');
function m(label,v,type,key){
  let c='';
  if(type==='txt') c='txt';
  else if(type==='pct'&&typeof v==='number') c=v>0?'pos':(v<0?'neg':'');
  return `<div class="m${key?' key':''}"><div class="l">${label}</div><div class="v ${c}">${fmt(v,type)}</div></div>`;
}
const grid=(a,two)=>`<div class="grid${two?' two':''}">${a.join('')}</div>`;
const sec=(t,h)=>`<div class="sec">${t}</div>${h}`;
const pct=(a,t)=>(typeof a==='number'&&typeof t==='number'&&t>0)?Math.round(a/t*100):null;
function bar(label,a,t){
  const p=pct(a,t); if(p===null) return '';
  return `<div class="bar"><div class="t"><span>${label}</span><span>${p}%</span></div><div class="tr"><div class="f ${p>=100?'ok':''}" style="width:${Math.min(p,100)}%"></div></div></div>`;
}
const earn=(c,p)=>`<div class="earn cur"><span>Current Earnings</span><b>${fmt(c,'cur')}</b></div><div class="earn pot"><span>Earning Potential</span><b>${fmt(p,'cur')}</b></div>`;

// ========== SCHEME REGISTRY (workings first, conditions second) ==========
const SCHEMES=[
 {k:'vahan',short:'Vahan Retail Cashback',title:'Vahan Retail Cashback – October',
  prog:d=>[d.ach,d.tgt,'Achi vs Target'],
  work:v=>bar('Achievement vs Target',v.ach,v.tgt)+
    sec('Target vs Achievement',grid([m('Target',v.tgt),m('Achievement',v.ach,0,1),m('Gap',v.gap,0,1)]))+
    sec('Pipeline',grid([m('Pendency',v.pend),m('Total Pipeline',v.pipe)],1))},
 {k:'pp',short:'Power Performer 2.0',title:'Maruti Power Performer 2.0',
  prog:d=>[d.ach,d.req,'Achi vs Required'],
  work:p=>bar('Achievement vs Required',p.ach,p.req)+
    sec('Scheme Achievement (Sep–Dec)',grid([m('Retail Base',p.base),m('Required @5%',p.req),m('Achievement',p.ach,0,1),m('Gap',p.gap,0,1)],1))+
    sec('Additional Opportunity – September',grid([m('Petrol Q1 Avg',p.pq1),m('Current Petrol',p.pcur),m('Growth',p.pgr,'pct',1)]))},
 {k:'psl',short:'Premier League',title:'Maruti Suzuki Premier League',
  prog:null,
  work:s=>sec('Your Standing',grid([m('Dealer Group',s.grp,'txt'),m('HO Ranking',s.rank,'txt')],1))+
    sec('Super Qualifying (Sep–Nov)',grid([m('Retail Base',s.sb),m('Retail Achi',s.sa),m('Growth %',s.sg,'pct',1)]))+
    sec('Ranking 1 – Petrol (Sep–Nov)',grid([m('Petrol Base',s.pb),m('Petrol Retail',s.pr),m('Growth %',s.pgr,'pct',1)]))+
    sec('Ranking 2 – September',grid([m('Q1 Retail Base',s.qb),m('Achievement',s.qa),m('Growth %',s.qg,'pct',1)]))},
 {k:'nac',short:"NEXA Achiever's Club",title:"NEXA Achiever's Club",
  prog:n=>[n.wach,n.wtgt,'Wholesale Achi'],
  work:n=>sec('Slab Achievement',grid([m('Base (Excl. Ignis)',n.base),m('Retail Achi',n.ach,0,1)],1))+
    sec('Cars Needed per Slab',grid([m('Sigma ₹900',n.g_sigma),m('Delta ₹1,100',n.g_delta),m('Zeta ₹1,400',n.g_zeta),m('Alpha ₹1,800',n.g_alpha)],1))+
    sec('Additional – October (GV & e VITARA)',grid([m('Q3 GV & EV Avg',n.gvq3),m('Required',n.req),m('Achievement',n.gv_ach,0,1),m('Gap',n.gv_gap,0,1)],1))+
    sec('Wholesale – October',bar('Wholesale Achievement',n.wach,n.wtgt)+grid([m('Target',n.wtgt),m('Achi',n.wach),m('Achi %',n.wpct,'pct')]))},
 {k:'mega',short:'Mega Dealer Cashback',title:'Mega Dealer Retail Cashback – October',
  prog:g=>[g.ach,g.tgt,'Retail Achi'],
  work:g=>bar('All Model Retail Achievement',g.ach,g.tgt)+
    sec('Qualifying – All Model Retail',grid([m('Target',g.tgt),m('Achi Net BI',g.ach,0,1),m('Achi %',g.pct,'pct',1),m('DMS backed by MI',g.mi),m('MI Achi %',g.mipct,'pct'),m('Slab',g.slab,'txt')]))+
    sec('Model-wise Workings','<table class="mt"><tr><th>Model</th><th>Target</th><th>Achi</th><th>Payout</th></tr>'+
      [['GV Strong Hybrid',g.gv],['Invicto',g.inv],['XL6',g.xl6],['Jimny',g.jim]].map(([n,x])=>`<tr><td>${n}</td><td>${fmt(x.t)}</td><td>${fmt(x.a)}</td><td>${fmt(x.p,'cur')}</td></tr>`).join('')+'</table>')},
 {k:'gv',short:'GV Hybrid Super Cashback',title:'Grand Vitara Strong Hybrid Super Cashback',
  prog:g=>[g.ach,g.tgt,'Achi vs Target'],
  work:g=>bar('Achievement vs Target',g.ach,g.tgt)+sec('Target vs Achievement',grid([m('Target',g.tgt),m('Achievement',g.ach,0,1),m('Achi %',g.pct,'pct',1)]))},
 {k:'dtd',short:'Dealer Trade Discount',title:'Dealer Trade Discount Scheme – October',wide:1,
  prog:d=>[d.ach,d.tgt,'GV Retail Achi'],
  work:d=>bar('GV Retail Achievement',d.ach,d.tgt)+
    sec('GV Retail Target vs Achievement',grid([m('GV Retail Target',d.tgt),m('Achievement',d.ach,0,1),m('Achi %',d.pct,'pct',1)]))+
    sec('Wholesale GV Slabs',grid([m('Sigma',d.sigma),m('Delta',d.delta)],1))}
];
let CUR=null,CURS=null;

// ========== SCREENS ==========
const show=id=>document.querySelectorAll('.screen').forEach(s=>{if(s.id!=='detail')s.classList.toggle('on',s.id===id)});
function handleLogin(e){
  e.preventDefault();
  const code=dealerCode.value.trim().toUpperCase(),pwd=password.value.trim(),d=DEALERS[code];
  if(!d||d.password!==pwd){errorMsg.style.display='block';errorMsg.textContent='Invalid Dealer Code or Password. Please try again.';return false}
  errorMsg.style.display='none';CUR=d;render(d);show('home');return false;
}
function logout(){CUR=null;closeDetail();show('login');document.querySelector('.lc').reset();}
function render(d){
  dealerName.textContent=d.name;dealerCodeDisplay.textContent=d.code;av.textContent=d.name.charAt(0).toUpperCase();
  const S=k=>SCHEMES.reduce((a,s)=>a+(Number(d[s.k][k])||0),0);
  totals.innerHTML=`<div class="tot cur"><span>Total Earned</span><b>${fmt(S('cur'),'cur')}</b></div><div class="tot pot"><span>Total Potential</span><b>${fmt(S('pot'),'cur')}</b></div>`;
  cnt.textContent=SCHEMES.length;
  tiles.innerHTML=SCHEMES.map((s,i)=>{
    const x=d[s.k],pr=s.prog?s.prog(x):null,p=pr?pct(pr[0],pr[1]):null;
    const foot=s.prog?`<div><div class="pt"><span>${pr[2]}</span><span>${p===null?'—':p+'%'}</span></div><div class="pb"><i class="${p>=100?'ok':''}" style="width:${Math.min(p||0,100)}%"></i></div></div>`
      :`<div class="pt"><span>Group ${esc(x.grp)}</span><span>Rank ${esc(x.rank)}</span></div>`;
    return `<button class="tile${s.wide?' w':''}" onclick="openDetail(${i})">
      <div class="tt"><span class="tn">${i+1}</span><h3>${s.short}</h3></div>
      <div class="ev"><div class="c">Earned<b>${fmt(x.cur,'cur')}</b></div><div class="p" style="text-align:right">Potential<b>${fmt(x.pot,'cur')}</b></div></div>${foot}</button>`}).join('');
}
function openDetail(i){
  CURS=SCHEMES[i];const x=CUR[CURS.k];
  dTitle.textContent=`${i+1}. ${CURS.title}`;dEarn.innerHTML=earn(x.cur,x.pot);
  tab('w');detail.classList.add('on');
}
function closeDetail(){detail.classList.remove('on')}
function tab(t){
  tabW.classList.toggle('on',t==='w');tabC.classList.toggle('on',t==='c');
  dPane.scrollTop=0;
  dPane.innerHTML=t==='w'?CURS.work(CUR[CURS.k]):'<ul class="cond">'+CONDITIONS[CURS.k].map(c=>`<li>${c.l?'<strong>'+esc(c.l)+':</strong> ':''}${esc(c.t)}</li>`).join('')+'</ul>';
}
</script>
</body>
</html>