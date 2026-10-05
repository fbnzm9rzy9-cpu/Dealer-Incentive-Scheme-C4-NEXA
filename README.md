
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<meta name="theme-color" content="#1a365d">
<meta name="color-scheme" content="light">
<meta name="format-detection" content="telephone=no">
<title>Dealer Incentive Schemes Portal</title>
<style>
:root{--p:#1a365d;--p2:#2b6cb0;--bg:#f4f7fa;--bd:#e2e8f0;--tx:#2d3748;--mu:#718096;--g:#2f855a;--o:#dd6b20;--gut:clamp(.6rem,3vw,1.5rem);color-scheme:light}
*{box-sizing:border-box;margin:0;padding:0}
html{max-width:100%;overflow-x:hidden;-webkit-text-size-adjust:100%}
body{font-family:system-ui,-apple-system,'Segoe UI',Roboto,Arial,sans-serif;background:var(--bg);color:var(--tx);min-height:100vh;min-height:100dvh;line-height:1.45;width:100%;max-width:100%;overflow-x:hidden;overflow-wrap:break-word;touch-action:pan-y pinch-zoom;overscroll-behavior-x:none;-webkit-tap-highlight-color:transparent}
.header{background:linear-gradient(135deg,var(--p),var(--p2));color:#fff;padding:.8rem calc(var(--gut) + env(safe-area-inset-right,0px)) .8rem calc(var(--gut) + env(safe-area-inset-left,0px));padding-top:calc(.8rem + env(safe-area-inset-top,0px))}
.header-in{max-width:900px;margin:0 auto;display:flex;justify-content:space-between;align-items:center;gap:.6rem}
.header h1{font-size:clamp(1.05rem,4vw,1.4rem)}.header p{font-size:.85rem;opacity:.9}
.container{max-width:900px;margin:0 auto;padding:1rem calc(var(--gut) + env(safe-area-inset-right,0px)) calc(2rem + env(safe-area-inset-bottom,0px)) calc(var(--gut) + env(safe-area-inset-left,0px))}
.login{background:#fff;border-radius:12px;box-shadow:0 4px 20px rgba(0,0,0,.08);padding:clamp(1.25rem,5vw,2rem);max-width:420px;margin:clamp(1rem,6vh,3rem) auto}
.login h2{text-align:center;color:var(--p);margin-bottom:1.1rem;font-size:1.3rem}
.fg{margin-bottom:1rem}.fg label{display:block;font-weight:600;font-size:.85rem;margin-bottom:.35rem}
.fg input{width:100%;min-height:48px;padding:.7rem 1rem;border:1.5px solid var(--bd);border-radius:8px;font-size:16px;font-family:inherit;-webkit-appearance:none;appearance:none}
.fg input:focus{outline:none;border-color:var(--p2);box-shadow:0 0 0 3px rgba(43,108,176,.18)}
.btn{display:inline-flex;align-items:center;justify-content:center;width:100%;min-height:48px;background:var(--p);color:#fff;border:0;border-radius:8px;font:600 1rem inherit;font-family:inherit;cursor:pointer;touch-action:manipulation}
.btn-out{width:auto;min-height:40px;padding:.35rem .9rem;font-size:.85rem;background:rgba(255,255,255,.2);flex-shrink:0}
.err{background:#fed7d7;color:#c53030;padding:.7rem;border-radius:8px;margin-bottom:1rem;font-size:.9rem;display:none}
#dashboard{display:none}
.dealer{background:#fff;border-radius:12px;padding:.8rem 1rem;margin-bottom:1rem;box-shadow:0 2px 8px rgba(0,0,0,.06)}
.dealer h2{font-size:clamp(1.05rem,4vw,1.35rem);color:var(--p)}.dealer .code{color:var(--mu);font-size:.85rem}
.running{display:flex;align-items:center;gap:.5rem;margin:1.1rem 0 .2rem}
.running h3{font-size:1.2rem;color:var(--p)}
.count{background:var(--p);color:#fff;border-radius:20px;padding:.05rem .6rem;font-size:.8rem;font-weight:700}
.link{margin-left:auto;background:none;border:1.5px solid var(--p2);color:var(--p2);border-radius:20px;padding:.3rem .8rem;font:600 .78rem inherit;font-family:inherit;cursor:pointer;min-height:34px}
.hint{font-size:.8rem;color:var(--mu);margin-bottom:.7rem}
#schemes{display:grid;grid-template-columns:minmax(0,1fr);gap:.7rem}
.scheme{background:#fff;border-radius:12px;box-shadow:0 2px 10px rgba(0,0,0,.07);overflow:hidden;min-width:0}
.scheme>summary{list-style:none;cursor:pointer;background:linear-gradient(135deg,var(--p),#2c5282);color:#fff;padding:.7rem .9rem;touch-action:manipulation}
.scheme>summary::-webkit-details-marker{display:none}
.s-top{display:flex;align-items:center;gap:.6rem}
.s-num{background:rgba(255,255,255,.2);border-radius:50%;width:1.7rem;height:1.7rem;display:flex;align-items:center;justify-content:center;font-weight:700;font-size:.85rem;flex-shrink:0}
.s-title{font-weight:600;font-size:clamp(.92rem,3.5vw,1.05rem);flex:1;min-width:0}
.chev:after{content:'';display:block;width:.5rem;height:.5rem;border:solid #fff;border-width:0 2px 2px 0;transform:rotate(45deg);margin:0 .3rem .25rem;transition:transform .2s}
.scheme[open] .chev:after{transform:rotate(-135deg);margin-bottom:0;margin-top:.25rem}
.chips{display:flex;gap:.45rem;margin-top:.55rem;flex-wrap:wrap}
.chip{flex:1 1 0;min-width:0;border-radius:8px;padding:.3rem .6rem;display:flex;flex-direction:column;line-height:1.2}
.chip i{font-style:normal;font-size:.62rem;text-transform:uppercase;letter-spacing:.04em;opacity:.95}.chip b{font-size:.95rem}
.chip.cur,.tile.cur{background:linear-gradient(135deg,#f6993f,var(--o));color:#fff}
.chip.pot,.tile.pot{background:linear-gradient(135deg,#48bb78,var(--g));color:#fff}
.chip.nt{background:rgba(255,255,255,.2);color:#fff}
.s-body{padding:.8rem .9rem}
.sec{margin-bottom:.9rem}
.sec-t{font-size:.72rem;font-weight:700;text-transform:uppercase;letter-spacing:.05em;color:var(--p2);border-left:3px solid var(--p2);padding-left:.5rem;margin-bottom:.45rem}
.metrics{display:grid;grid-template-columns:repeat(auto-fill,minmax(140px,1fr));gap:.5rem}
.metric{background:#f8fafc;border:1px solid var(--bd);border-radius:8px;padding:.5rem .35rem;text-align:center;min-width:0}
.metric .l{font-size:.62rem;text-transform:uppercase;letter-spacing:.03em;color:var(--mu);font-weight:600;line-height:1.25;margin-bottom:.2rem}
.metric .v{font-size:1.05rem;font-weight:700;color:var(--p)}
.v.pos{color:#2f855a}.v.neg{color:#c53030}.v.txt{font-size:.95rem}
.earn{display:grid;grid-template-columns:1fr 1fr;gap:.5rem;margin-bottom:.9rem}
.tile{border-radius:10px;padding:.7rem .4rem;text-align:center;min-width:0}
.tile .l{font-size:.68rem;text-transform:uppercase;letter-spacing:.04em;font-weight:600;opacity:.95}
.tile .v{font-size:1.25rem;font-weight:800;margin-top:.15rem}
.bar{margin-bottom:.9rem}.bar-l{display:flex;justify-content:space-between;gap:.5rem;font-size:.75rem;color:var(--mu);margin-bottom:.3rem}.bar-l b{color:var(--p)}
.bar-t{height:10px;background:var(--bd);border-radius:6px;overflow:hidden}.bar-f{height:100%;background:var(--p2);border-radius:6px}.bar-f.ok{background:#38a169}
.tbl{width:100%;border-collapse:collapse;table-layout:fixed;font-size:.8rem;margin-top:.5rem}
.tbl th{background:#edf2f7;color:var(--mu);font-size:.65rem;text-transform:uppercase;padding:.4rem .2rem}
.tbl td{padding:.45rem .2rem;border-bottom:1px solid var(--bd);text-align:center}.tbl td:first-child,.tbl th:first-child{text-align:left;padding-left:.4rem}
.cond{background:#fffaf0;border:1px solid #fbd38d;border-radius:10px;padding:.65rem .8rem}
.cond-t{font-size:.7rem;font-weight:700;text-transform:uppercase;letter-spacing:.05em;color:#9c4221;margin-bottom:.3rem}
.cond ul{list-style:none}.cond li{font-size:.78rem;line-height:1.45;padding:.3rem 0 .3rem .9rem;position:relative;border-top:1px dashed #fbd38d}
.cond li:nth-child(2){border-top:0}.cond li:before{content:'\25B8';position:absolute;left:0;color:#ed8936}.cond li b{color:#7b341e}
.cond li.h{font-weight:700;color:#7b341e;padding-left:0;margin-top:.15rem}.cond li.h:before{content:none}
@media(min-width:600px){.metrics{grid-template-columns:repeat(auto-fill,minmax(160px,1fr))}.cond li{font-size:.85rem}}
@media(max-width:480px){html{font-size:15px}.metrics{grid-template-columns:repeat(2,minmax(0,1fr))}.header p{display:none}}
@media(max-width:340px){html{font-size:14px}}
</style>
</head>
<body>
<div class="header"><div class="header-in">
  <div><h1>Dealer Incentive Schemes</h1><p>View your scheme-wise achievements &amp; earnings</p></div>
  <button id="logoutBtn" class="btn btn-out" style="display:none" onclick="logout()">Logout</button>
</div></div>
<div class="container">
  <div id="loginSection"><div class="login">
    <h2>Dealer Login</h2>
    <div id="errorMsg" class="err" role="alert"></div>
    <form id="loginForm" onsubmit="return handleLogin(event)">
      <div class="fg"><label for="dealerCode">Dealer Code</label>
        <input type="text" id="dealerCode" placeholder="e.g. G1NA" required autocomplete="username" autocapitalize="characters" autocorrect="off" spellcheck="false" enterkeyhint="next"></div>
      <div class="fg"><label for="password">Password</label>
        <input type="password" id="password" placeholder="Enter password" required autocomplete="current-password" autocapitalize="none" autocorrect="off" spellcheck="false" enterkeyhint="go"></div>
      <button type="submit" class="btn">View Schemes</button>
    </form>
  </div></div>
  <div id="dashboard">
    <div class="dealer"><h2 id="dealerName">—</h2><div class="code">Code: <span id="dealerCodeDisplay">—</span></div></div>
    <div class="running"><h3>Schemes Running</h3><span class="count">7</span><button id="toggleBtn" class="link" onclick="toggleAll()">Expand all</button></div>
    <div class="hint">Tap a scheme to open its workings and conditions.</div>
    <div id="schemes"></div>
  </div>
</div>
<script>
const DEALERS = {"G1NA":{"code":"G1NA","password":"G1NAAdinath","name":"Adinath","vahan":{"tgt":145,"ach":68,"pend":12,"pipe":80,"gap":65,"cur":204000,"pot":435000},"pp":{"base":537,"req":564,"ach":66,"gap":498,"pq1":87,"pcur":54,"pgr":-0.3793,"pot":1269000,"cur":148500},"psl":{"grp":"B","rank":"-","sb":383,"sa":66,"sg":-0.8277,"pb":322,"pr":54,"pgr":-0.8323,"qb":110,"qa":66,"qg":-0.4},"nac":{"base":422,"ach":null,"g1":422,"g2":431,"g3":439,"g4":452,"gvq3":19,"req":24,"gach":null,"ggap":24,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"D7NA":{"code":"D7NA","password":"D7NACity","name":"City Cars","vahan":{"tgt":165,"ach":70,"pend":37,"pipe":107,"gap":58,"cur":210000,"pot":495000},"pp":{"base":715,"req":751,"ach":87,"gap":664,"pq1":109,"pcur":68,"pgr":-0.3761,"pot":1689750,"cur":195750},"psl":{"grp":"B","rank":"-","sb":470,"sa":87,"sg":-0.8149,"pb":411,"pr":68,"pgr":-0.8345,"qb":134,"qa":87,"qg":-0.3507},"nac":{"base":559,"ach":null,"g1":422,"g2":431,"g3":439,"g4":599,"gvq3":26,"req":33,"gach":null,"ggap":33,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"KMNA":{"code":"KMNA","password":"KMNAInfinity","name":"Infinity","vahan":{"tgt":35,"ach":26,"pend":8,"pipe":34,"gap":1,"cur":78000,"pot":105000},"pp":{"base":170,"req":179,"ach":31,"gap":148,"pq1":23,"pcur":25,"pgr":0.087,"pot":402750,"cur":69750},"psl":{"grp":"D","rank":"-","sb":131,"sa":31,"sg":-0.7634,"pb":108,"pr":25,"pgr":-0.7685,"qb":30,"qa":31,"qg":0.0333},"nac":{"base":133,"ach":null,"g1":422,"g2":431,"g3":439,"g4":143,"gvq3":4,"req":5,"gach":null,"ggap":5,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"03NB":{"code":"03NB","password":"03NBJeewan","name":"Jeewan","vahan":{"tgt":100,"ach":47,"pend":13,"pipe":60,"gap":40,"cur":141000,"pot":300000},"pp":{"base":768,"req":806,"ach":56,"gap":750,"pq1":56,"pcur":33,"pgr":-0.4107,"pot":1813500,"cur":126000},"psl":{"grp":"B","rank":"-","sb":633,"sa":56,"sg":-0.9115,"pb":426,"pr":33,"pgr":-0.9225,"qb":94,"qa":56,"qg":-0.4043},"nac":{"base":593,"ach":null,"g1":422,"g2":431,"g3":439,"g4":635,"gvq3":20,"req":25,"gach":null,"ggap":25,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"U5NA":{"code":"U5NA","password":"U5NAKamthi","name":"Kamthi Motors","vahan":{"tgt":105,"ach":58,"pend":17,"pipe":75,"gap":30,"cur":174000,"pot":315000},"pp":{"base":493,"req":518,"ach":69,"gap":449,"pq1":74,"pcur":65,"pgr":-0.1216,"pot":1165500,"cur":155250},"psl":{"grp":"C","rank":"-","sb":347,"sa":69,"sg":-0.8012,"pb":338,"pr":65,"pgr":-0.8077,"qb":79,"qa":69,"qg":-0.1266},"nac":{"base":376,"ach":null,"g1":422,"g2":431,"g3":439,"g4":403,"gvq3":19,"req":24,"gach":null,"ggap":24,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NE":{"code":"53NE","password":"53NEKTL","name":"KTL","vahan":{"tgt":175,"ach":103,"pend":38,"pipe":141,"gap":34,"cur":309000,"pot":525000},"pp":{"base":409,"req":429,"ach":125,"gap":304,"pq1":70,"pcur":52,"pgr":-0.2571,"pot":965250,"cur":281250},"psl":{"grp":"National A","rank":"-","sb":199,"sa":125,"sg":-0.3719,"pb":117,"pr":52,"pgr":-0.5556,"qb":122,"qa":125,"qg":0.0246},"nac":{"base":405,"ach":null,"g1":422,"g2":431,"g3":439,"g4":434,"gvq3":15,"req":19,"gach":null,"ggap":19,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"30NB":{"code":"30NB","password":"30NBNikunj","name":"Nikunj","vahan":{"tgt":110,"ach":45,"pend":41,"pipe":86,"gap":24,"cur":135000,"pot":330000},"pp":{"base":360,"req":378,"ach":74,"gap":304,"pq1":38,"pcur":32,"pgr":-0.1579,"pot":850500,"cur":166500},"psl":{"grp":"B","rank":"-","sb":272,"sa":74,"sg":-0.7279,"pb":168,"pr":32,"pgr":-0.8095,"qb":63,"qa":74,"qg":0.1746},"nac":{"base":284,"ach":null,"g1":422,"g2":431,"g3":439,"g4":304,"gvq3":11,"req":14,"gach":null,"ggap":14,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"AUNA":{"code":"AUNA","password":"AUNANimar","name":"Nimar Motors","vahan":{"tgt":80,"ach":56,"pend":19,"pipe":75,"gap":5,"cur":168000,"pot":240000},"pp":{"base":478,"req":502,"ach":75,"gap":427,"pq1":43,"pcur":46,"pgr":0.0698,"pot":1129500,"cur":168750},"psl":{"grp":"B","rank":"-","sb":336,"sa":75,"sg":-0.7768,"pb":250,"pr":46,"pgr":-0.816,"qb":59,"qa":75,"qg":0.2712},"nac":{"base":369,"ach":null,"g1":422,"g2":431,"g3":439,"g4":395,"gvq3":22,"req":28,"gach":null,"ggap":28,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NB":{"code":"53NB","password":"53NBOcean","name":"Ocean Group","vahan":{"tgt":305,"ach":173,"pend":78,"pipe":251,"gap":54,"cur":519000,"pot":915000},"pp":{"base":1489,"req":1563,"ach":229,"gap":1334,"pq1":125,"pcur":110,"pgr":-0.12,"pot":3516750,"cur":515250},"psl":{"grp":"A","rank":"-","sb":985,"sa":229,"sg":-0.7675,"pb":631,"pr":110,"pgr":-0.8257,"qb":225,"qa":229,"qg":0.0178},"nac":{"base":1146,"ach":null,"g1":422,"g2":431,"g3":439,"g4":1227,"gvq3":80,"req":100,"gach":null,"ggap":100,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NA":{"code":"53NA","password":"53NAPatel","name":"Patel Group","vahan":{"tgt":215,"ach":114,"pend":61,"pipe":175,"gap":40,"cur":342000,"pot":645000},"pp":{"base":923,"req":969,"ach":162,"gap":807,"pq1":98,"pcur":102,"pgr":0.0408,"pot":2180250,"cur":364500},"psl":{"grp":"A","rank":"-","sb":649,"sa":162,"sg":-0.7504,"pb":480,"pr":102,"pgr":-0.7875,"qb":163,"qa":162,"qg":-0.0061},"nac":{"base":680,"ach":null,"g1":422,"g2":431,"g3":439,"g4":728,"gvq3":34,"req":43,"gach":null,"ggap":43,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"30NA":{"code":"30NA","password":"30NAPrem","name":"Prem Group","vahan":{"tgt":195,"ach":116,"pend":26,"pipe":142,"gap":53,"cur":348000,"pot":585000},"pp":{"base":542,"req":569,"ach":132,"gap":437,"pq1":78,"pcur":47,"pgr":-0.3974,"pot":1280250,"cur":297000},"psl":{"grp":"National A","rank":"-","sb":485,"sa":132,"sg":-0.7278,"pb":294,"pr":47,"pgr":-0.8401,"qb":148,"qa":132,"qg":-0.1081},"nac":{"base":384,"ach":null,"g1":422,"g2":431,"g3":439,"g4":411,"gvq3":15,"req":19,"gach":null,"ggap":19,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"03NC":{"code":"03NC","password":"03NCRajrup","name":"Rajrup","vahan":{"tgt":185,"ach":118,"pend":17,"pipe":135,"gap":50,"cur":354000,"pot":555000},"pp":{"base":949,"req":996,"ach":115,"gap":881,"pq1":80,"pcur":55,"pgr":-0.3125,"pot":2241000,"cur":258750},"psl":{"grp":"B","rank":"-","sb":653,"sa":115,"sg":-0.8239,"pb":493,"pr":55,"pgr":-0.8884,"qb":129,"qa":115,"qg":-0.1085},"nac":{"base":719,"ach":null,"g1":422,"g2":431,"g3":439,"g4":770,"gvq3":42,"req":53,"gach":null,"ggap":53,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NC":{"code":"53NC","password":"53NCRukmani","name":"Rukmani","vahan":{"tgt":170,"ach":104,"pend":55,"pipe":159,"gap":11,"cur":312000,"pot":510000},"pp":{"base":851,"req":894,"ach":124,"gap":770,"pq1":55,"pcur":62,"pgr":0.1273,"pot":2011500,"cur":279000},"psl":{"grp":"A","rank":"-","sb":645,"sa":124,"sg":-0.8078,"pb":442,"pr":62,"pgr":-0.8597,"qb":103,"qa":124,"qg":0.2039},"nac":{"base":643,"ach":null,"g1":422,"g2":431,"g3":439,"g4":689,"gvq3":46,"req":58,"gach":null,"ggap":58,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"54ND":{"code":"54ND","password":"54NBShubh","name":"Shubh","vahan":{"tgt":125,"ach":80,"pend":16,"pipe":96,"gap":29,"cur":240000,"pot":375000},"pp":{"base":588,"req":617,"ach":89,"gap":528,"pq1":90,"pcur":79,"pgr":-0.1222,"pot":1388250,"cur":200250},"psl":{"grp":"B","rank":"-","sb":391,"sa":89,"sg":-0.7724,"pb":367,"pr":79,"pgr":-0.7847,"qb":100,"qa":89,"qg":-0.11},"nac":{"base":468,"ach":null,"g1":422,"g2":431,"g3":439,"g4":501,"gvq3":27,"req":34,"gach":null,"ggap":34,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"54NC":{"code":"54NC","password":"54NCStandard","name":"Standard Group","vahan":{"tgt":200,"ach":120,"pend":34,"pipe":154,"gap":46,"cur":360000,"pot":600000},"pp":{"base":852,"req":895,"ach":135,"gap":760,"pq1":157,"pcur":106,"pgr":-0.3248,"pot":2013750,"cur":303750},"psl":{"grp":"B","rank":"-","sb":600,"sa":135,"sg":-0.775,"pb":551,"pr":106,"pgr":-0.8076,"qb":178,"qa":135,"qg":-0.2416},"nac":{"base":694,"ach":null,"g1":422,"g2":431,"g3":439,"g4":743,"gvq3":43,"req":54,"gach":null,"ggap":54,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"3QNB":{"code":"3QNB","password":"3QNAUnitara","name":"Unitara","vahan":{"tgt":40,"ach":40,"pend":4,"pipe":44,"gap":-4,"cur":120000,"pot":120000},"pp":{"base":193,"req":203,"ach":36,"gap":167,"pq1":16,"pcur":23,"pgr":0.4375,"pot":456750,"cur":81000},"psl":{"grp":"C","rank":"-","sb":137,"sa":36,"sg":-0.7372,"pb":77,"pr":23,"pgr":-0.7013,"qb":38,"qa":36,"qg":-0.0526},"nac":{"base":152,"ach":null,"g1":422,"g2":431,"g3":439,"g4":163,"gvq3":8,"req":10,"gach":null,"ggap":10,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"3WNA":{"code":"3WNA","password":"3WNAYug","name":"Yug Cars","vahan":{"tgt":50,"ach":30,"pend":7,"pipe":37,"gap":13,"cur":90000,"pot":150000},"pp":{"base":275,"req":289,"ach":33,"gap":256,"pq1":13,"pcur":10,"pgr":-0.2308,"pot":650250,"cur":74250},"psl":{"grp":"C","rank":"-","sb":213,"sa":33,"sg":-0.8451,"pb":119,"pr":10,"pgr":-0.916,"qb":35,"qa":33,"qg":-0.0571},"nac":{"base":196,"ach":null,"g1":422,"g2":431,"g3":439,"g4":210,"gvq3":12,"req":15,"gach":null,"ggap":15,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}}};

const CONDITIONS = {"vahan": [{"l": "Super Qualifying Criteria", "t": "It is compulsory to achieve atleast 40% Retail & 40% Vahan Target* for SEP-26 by 15th September’26 to qualify for any Incentive"}, {"l": null, "t": "It is compulsory to achieve atleast 100% Retail Target for Sep-26 to qualify for any Incentive. BI Net Retail will be considered to calculate Retail Target Achievement."}, {"l": null, "t": "Permanent registration done for All Models of NEXA Channel would be considered for scheme calculation and payout"}, {"l": null, "t": "Payout will be paid on Vahan registration issued against applicable models from 1-Sep-26 to 30-Sep-26 updated till 5th Oct’26"}], "pp": [{"l": "Scheme Period", "t": "September'26 to December'26"}, {"l": "Slabs", "t": "Slab 1 : >=0% to <3% : 700 | Slab 2 : >=3% to <5% : 1,000 | Slab 3 : >=5% : 1,500"}, {"l": "Additional Earning Opportunity (September)", "t": "No retail de-growth of “All Models combined retail (Excluding CNG Variants)” in Sep’26 (ie. from 1st Sep’26 - 30th Sep’26) over Q1’26-27 monthly retail average of “All Models combined retail (Excluding CNG Variants)"}, {"l": "Vahan / MI Condition", "t": "At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail"}], "psl": [{"l": "Super Qualifying Condition", "t": "No net retail de-growth during Sep’26 to Nov'26 over Sep’25 to Nov'25."}, {"l": "Vahan / MI Condition", "t": "At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 7th Jan'27 for scheme period's retail"}, {"l": "Ranking Condition 1", "t": "Sept to Nov - All Models (excluding CNG variants) Net retail growth during Sep’26 to Nov'26 over Sep’25 to Nov'25 (Weightage - 30%)"}, {"l": "Ranking Condition 2", "t": "September - Net Retail Growth (All Models) in Sep'26 over the Apr'26 to Jun'26 average monthly Net Retail"}], "nac": [{"l": "Target Slabs", "t": "Sigma - 0%, Delta - 2%, Zeta - 4%, Alpha - 7%"}, {"l": "Vahan / MI Condition", "t": "At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail"}, {"l": "Additional Earning Opportunity of 25% (October)", "t": "Atleast 25% retail growth in Grand Vitara & e VITARA (combined) in Oct'26 over Q3'25-26 monthly average retail."}, {"l": null, "t": "Slab Growth shall be considered basis retail done in Q3’26-27 over Q3’25-26 (excluding Ignis)."}], "mega": [{"h": "Super Qualifying Condition"}, {"t": "100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount"}, {"t": "Minimum 90% All Models NET BI Retail Target achievement between 1st Oct’26 – 31st Oct’26 (both days inclusive)"}, {"l": "Qualifying Condition", "t": "Minimum 90% All Models Retail Target Achievement of between 1st Oct’26 – 31st Oct’26 (both days inclusive)"}], "gvsc": [{"l": null, "t": "It is mandatory to achieve at least 100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount."}], "tdd": [{"l": "Qualifying Condition", "t": "97% Wholesale Target Achievement of GV (All Variants) at Parent level"}, {"h": "Super Qualifying Condition"}, {"t": "It is mandatory to achieve at least 100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount"}, {"t": "90% NET BI Retail Target Achievement of GV (All Variants) at Parent level"}]};
const BAD = [null, undefined, '', '-', '#N/A', '#DIV/0!', '#NA'];
function fmt(v, t) {
  if (BAD.includes(v)) return '—';
  if (typeof v === 'number') {
    if (t === 'pct') return (v * 100).toFixed(1) + '%';
    if (t === 'cur') return '₹' + v.toLocaleString('en-IN');
    return Number.isInteger(v) ? v.toLocaleString('en-IN') : v.toFixed(2);
  }
  return v;
}
const esc = s => String(s).replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;');
function m(label, v, t) {
  const c = t === 'txt' ? 'txt' : (t === 'pct' && typeof v === 'number' ? (v > 0 ? 'pos' : v < 0 ? 'neg' : '') : '');
  return `<div class="metric"><div class="l">${label}</div><div class="v ${c}">${fmt(v, t)}</div></div>`;
}
const sec = (t, inner) => `<div class="sec"><div class="sec-t">${t}</div>${inner}</div>`;
const grid = a => `<div class="metrics">${a.join('')}</div>`;
function bar(a, t, lab) {
  if (typeof a !== 'number' || typeof t !== 'number' || t <= 0) return '';
  const p = Math.round(a / t * 100), w = Math.min(100, Math.max(0, p));
  return `<div class="bar"><div class="bar-l"><span>${lab}</span><b>${a.toLocaleString('en-IN')} / ${t.toLocaleString('en-IN')} (${p}%)</b></div><div class="bar-t"><div class="bar-f ${p >= 100 ? 'ok' : ''}" style="width:${w}%"></div></div></div>`;
}
function table(head, rows) {
  return `<table class="tbl"><tr>${head.map(h => `<th>${h}</th>`).join('')}</tr>${rows.map(r => `<tr>${r.map(c => `<td>${c}</td>`).join('')}</tr>`).join('')}</table>`;
}
const chips = (c, p) => `<div class="chips"><div class="chip cur"><i>Current Earnings</i><b>${fmt(c, 'cur')}</b></div><div class="chip pot"><i>Earning Potential</i><b>${fmt(p, 'cur')}</b></div></div>`;
const earn = (c, p) => sec('Earnings', `<div class="earn"><div class="tile cur"><div class="l">Current Earnings</div><div class="v">${fmt(c, 'cur')}</div></div><div class="tile pot"><div class="l">Earning Potential</div><div class="v">${fmt(p, 'cur')}</div></div></div>`);
function conds(key) {
  const li = CONDITIONS[key].map(c => c.h ? `<li class="h">${esc(c.h)}</li>` : `<li>${c.l ? '<b>' + esc(c.l) + ':</b> ' : ''}${esc(c.t)}</li>`).join('');
  return `<div class="cond"><div class="cond-t">Scheme Conditions</div><ul>${li}</ul></div>`;
}
function card(n, key, title, head, work) {
  return `<details class="scheme"><summary><div class="s-top"><span class="s-num">${n}</span><span class="s-title">${title}</span><span class="chev"></span></div>${head}</summary><div class="s-body">${work}${conds(key)}</div></details>`;
}

function renderAll(d) {
  const v = d.vahan, p = d.pp, s = d.psl, n = d.nac, g = d.mega, h = d.gvsc, t = d.tdd;
  const nt = (l, x) => `<div class="chip nt"><i>${l}</i><b>${fmt(x)}</b></div>`;
  return [
    card(1, 'vahan', 'Vahan Retail Cashback – October', chips(v.cur, v.pot),
      bar(v.ach, v.tgt, 'Achievement vs Target') +
      sec('Retail Position', grid([m('Target', v.tgt), m('Achievement', v.ach), m('Pendency', v.pend), m('Total Pipeline', v.pipe), m('Gap', v.gap)])) +
      earn(v.cur, v.pot)),
    card(2, 'pp', 'Maruti Power Performer 2.0', chips(p.cur, p.pot),
      bar(p.ach, p.req, 'Retail Achievement vs Required') +
      sec('Scheme Achievement', grid([m('All Model Retail Base (Sep–Dec)', p.base), m('Retail Required (@5% Growth)', p.req), m('Retail Achievement', p.ach), m('Gap', p.gap)])) +
      sec('Additional Earning Opportunity', grid([m('Petrol Retail (Q1 Avg)', p.pq1), m('Current Petrol Retails', p.pcur), m('Growth', p.pgr, 'pct')])) +
      earn(p.cur, p.pot)),
    card(3, 'psl', 'Maruti Suzuki Premier League', `<div class="chips">${nt('Dealer Group', s.grp)}${nt('HO Ranking', s.rank)}</div>`,
      sec('Super Qualifying Criteria', grid([m('Retail Base Sep–Nov', s.sb), m('Retail Achi', s.sa), m('Growth %', s.sg, 'pct')])) +
      sec('Ranking Condition 1 : Sept to Nov', grid([m('Petrol Base', s.pb), m('Petrol Retail', s.pr), m('Growth %', s.pgr, 'pct')])) +
      sec('Ranking Condition 2 : Sept', grid([m('Q1 Retail Base', s.qb), m('Achi', s.qa), m('Growth', s.qg, 'pct')]))),
    card(4, 'nac', "NEXA Achiever's Club", chips(n.cur, n.pot),
      sec('Slab Achievement', grid([m('Retail Base (Excl. Ignis)', n.base), m('Retail Achievement', n.ach)]) +
        table(['Slab', 'Per Car', 'Gap'], [['Sigma', '₹900', fmt(n.g1)], ['Delta', '₹1,100', fmt(n.g2)], ['Zeta', '₹1,400', fmt(n.g3)], ['Alpha', '₹1,800', fmt(n.g4)]])) +
      sec('Additional Earning Opportunity – October', grid([m('Q3 GV & EV Avg Retail', n.gvq3), m('Required Retail', n.req), m('Achi', n.gach), m('Gap', n.ggap)])) +
      bar(n.wach, n.wtgt, 'Wholesale Achi vs Target') +
      sec('Wholesale Achievement', grid([m('Target – October', n.wtgt), m('Achi', n.wach), m('Achi %', n.wpct, 'pct')])) +
      earn(n.cur, n.pot)),
    card(5, 'mega', 'Mega Dealer Retail Cashback – October', chips(g.cur, g.pot),
      sec('Qualifying Criteria – All Model Retail', grid([m('Target', g.tgt), m('Achi Net BI', g.ach), m('Achi %', g.achp, 'pct'), m('DMS backed by MI', g.dms), m('Achi % (MI)', g.dmsp, 'pct'), m('Slab', g.slab, 'txt')])) +
      sec('Model-wise Performance', table(['Model', 'Target', 'Achi', 'Payout'], [
        ['Grand Vitara Strong Hybrid', fmt(g.gt), fmt(g.ga), fmt(g.gp, 'cur')], ['Invicto', fmt(g.it), fmt(g.ia), fmt(g.ip, 'cur')],
        ['XL6', fmt(g.xt), fmt(g.xa), fmt(g.xp, 'cur')], ['Jimny', fmt(g.jt), fmt(g.ja), fmt(g.jp, 'cur')]])) +
      earn(g.cur, g.pot)),
    card(6, 'gvsc', 'Grand Vitara Strong Hybrid Super Cashback', chips(h.cur, h.pot),
      bar(h.ach, h.tgt, 'Achievement vs Target') +
      sec('Achievement', grid([m('Target', h.tgt), m('Achievement', h.ach), m('Achi %', h.pct, 'pct')])) +
      earn(h.cur, h.pot)),
    card(7, 'tdd', 'Dealer Trade Discount Scheme – October', chips(t.cur, t.pot),
      bar(t.ach, t.tgt, 'GV Retail Achievement vs Target') +
      sec('GV Retail', grid([m('GV Retail Target', t.tgt), m('Achievement', t.ach), m('Achi %', t.pct, 'pct')])) +
      sec('GV Wholesale', grid([m('Wholesale GV Sigma', t.sig), m('Wholesale GV Delta', t.dlt)])) +
      earn(t.cur, t.pot))
  ].join('');
}
function toggleAll() {
  const ds = [...document.querySelectorAll('details.scheme')], open = ds.some(x => !x.open);
  ds.forEach(x => x.open = open);
  document.getElementById('toggleBtn').textContent = open ? 'Collapse all' : 'Expand all';
}
function handleLogin(e) {
  e.preventDefault();
  const code = document.getElementById('dealerCode').value.trim().toUpperCase();
  const pwd = document.getElementById('password').value.trim();
  const err = document.getElementById('errorMsg'), d = DEALERS[code];
  if (!d || d.password !== pwd) { err.style.display = 'block'; err.textContent = 'Invalid Dealer Code or Password. Please try again.'; return false; }
  err.style.display = 'none';
  document.getElementById('loginSection').style.display = 'none';
  document.getElementById('dashboard').style.display = 'block';
  document.getElementById('logoutBtn').style.display = 'inline-flex';
  document.getElementById('dealerName').textContent = d.name;
  document.getElementById('dealerCodeDisplay').textContent = d.code;
  document.getElementById('schemes').innerHTML = renderAll(d);
  document.getElementById('toggleBtn').textContent = 'Expand all';
  window.scrollTo(0, 0);
  return false;
}
function logout() {
  document.getElementById('dashboard').style.display = 'none';
  document.getElementById('loginSection').style.display = 'block';
  document.getElementById('logoutBtn').style.display = 'none';
  document.getElementById('loginForm').reset();
}
</script>
</body>
</html>