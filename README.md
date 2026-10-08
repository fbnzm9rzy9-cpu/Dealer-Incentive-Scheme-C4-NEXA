
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, user-scalable=no, viewport-fit=cover">
<meta name="theme-color" content="#0b1635">
<meta name="color-scheme" content="light">
<meta name="format-detection" content="telephone=no">
<title>Dealer Incentive Schemes</title>
<style>
/* ===== RESET & BASE ===== */
*, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  min-width: 0;
}

html {
  width: 100%;
  max-width: 100vw;
  overflow-x: hidden;
  -webkit-text-size-adjust: 100%;
  font-size: 14.5px;
}

body {
  font-family: system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif;
  background: #f0f4f8;
  color: #1a202c;
  width: 100%;
  max-width: 100vw;
  min-height: 100dvh;
  overflow-x: hidden;
  overflow-wrap: anywhere;
  line-height: 1.4;
  -webkit-tap-highlight-color: transparent;
  touch-action: pan-y;
}

/* ===== CSS VARIABLES ===== */
:root {
  --p: #1a365d;
  --p2: #2b6cb0;
  --g: #2f855a;
  --o: #dd6b20;
  --r: #c53030;
  --bd: #e2e8f0;
  --mu: #718096;
  --safe-l: env(safe-area-inset-left, 0px);
  --safe-r: env(safe-area-inset-right, 0px);
  --safe-t: env(safe-area-inset-top, 0px);
  --safe-b: env(safe-area-inset-bottom, 0px);
}

/* ===== HEADER ===== */
.header {
  background: linear-gradient(135deg, #1a365d, #2b6cb0);
  color: #fff;
  padding: calc(0.55rem + var(--safe-t)) max(0.7rem, var(--safe-r)) 0.55rem max(0.7rem, var(--safe-l));
  position: sticky;
  top: 0;
  z-index: 100;
  width: 100%;
  max-width: 100vw;
  box-shadow: 0 2px 10px rgba(0,0,0,.18);
}

.header-in {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 0.5rem;
  width: 100%;
  max-width: 100%;
}

.header h1 {
  font-size: 1.05rem;
  font-weight: 700;
  line-height: 1.2;
}

.header p {
  font-size: 0.68rem;
  opacity: 0.85;
  margin-top: 0.05rem;
}

/* ===== CONTAINER ===== */
.container {
  width: 100%;
  max-width: 100%;
  padding: 0.7rem max(0.7rem, var(--safe-r)) calc(1.2rem + var(--safe-b)) max(0.7rem, var(--safe-l));
}

/* ===== LOGIN ===== */
#loginSection {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: calc(100dvh - 65px);
  width: 100%;
}

.login {
  background: #fff;
  border-radius: 14px;
  box-shadow: 0 6px 24px rgba(26,54,93,.12);
  padding: 1.35rem 1.1rem;
  width: 100%;
  max-width: 340px;
}

.login h2 {
  text-align: center;
  color: var(--p);
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 1.1rem;
}

.fg { margin-bottom: 0.9rem; }

.fg label {
  display: block;
  font-weight: 600;
  font-size: 0.78rem;
  margin-bottom: 0.3rem;
}

.fg input {
  width: 100%;
  min-height: 46px;
  padding: 0.65rem 0.85rem;
  border: 1.5px solid var(--bd);
  border-radius: 10px;
  font-size: 16px; /* critical – stops iOS zoom */
  font-family: inherit;
  background: #fff;
  -webkit-appearance: none;
  appearance: none;
}

.fg input:focus {
  outline: none;
  border-color: var(--p2);
  box-shadow: 0 0 0 3px rgba(43,108,176,.2);
}

.btn {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 100%;
  min-height: 46px;
  background: linear-gradient(135deg, var(--p), var(--p2));
  color: #fff;
  border: 0;
  border-radius: 10px;
  font: 600 0.95rem inherit;
  cursor: pointer;
  touch-action: manipulation;
}

.btn:active { transform: scale(0.98); }

.btn-out {
  width: auto;
  min-height: 34px;
  padding: 0.25rem 0.75rem;
  font-size: 0.75rem;
  background: rgba(255,255,255,.2);
  border-radius: 8px;
  flex-shrink: 0;
}

.err {
  background: #fed7d7;
  color: var(--r);
  padding: 0.6rem 0.8rem;
  border-radius: 9px;
  margin-bottom: 0.9rem;
  font-size: 0.82rem;
  text-align: center;
  display: none;
}

/* ===== DASHBOARD ===== */
#dashboard { display: none; width: 100%; max-width: 100%; }

.dealer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  gap: 0.4rem;
  background: #fff;
  border-radius: 12px;
  padding: 0.65rem 0.85rem;
  margin-bottom: 0.65rem;
  box-shadow: 0 2px 8px rgba(0,0,0,.05);
  width: 100%;
}

.dealer h2 {
  font-size: 1.1rem;
  color: var(--p);
  font-weight: 700;
}

.dealer .code {
  color: var(--mu);
  font-size: 0.75rem;
  white-space: nowrap;
}

.running {
  display: flex;
  align-items: center;
  gap: 0.4rem;
  margin: 0.8rem 0 0.3rem;
  width: 100%;
}

.running h3 {
  font-size: 1rem;
  color: var(--p);
  font-weight: 700;
}

.count {
  background: var(--p);
  color: #fff;
  border-radius: 999px;
  padding: 0.08rem 0.5rem;
  font-size: 0.72rem;
  font-weight: 700;
}

.link {
  margin-left: auto;
  background: none;
  border: 1.5px solid var(--p2);
  color: var(--p2);
  border-radius: 999px;
  padding: 0.25rem 0.7rem;
  font: 600 0.72rem inherit;
  cursor: pointer;
  min-height: 30px;
  flex-shrink: 0;
}

.hint {
  font-size: 0.7rem;
  color: var(--mu);
  margin-bottom: 0.55rem;
}

/* ===== SCHEMES ===== */
#schemes {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  width: 100%;
  max-width: 100%;
}

.scheme {
  background: #fff;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0,0,0,.06);
  overflow: hidden;
  width: 100%;
  max-width: 100%;
}

.scheme > summary {
  list-style: none;
  cursor: pointer;
  background: linear-gradient(135deg, #1a365d, #2c5282);
  color: #fff;
  padding: 0.5rem 0.65rem;
  touch-action: manipulation;
  width: 100%;
}

.scheme > summary::-webkit-details-marker { display: none; }

.s-top {
  display: flex;
  align-items: center;
  gap: 0.45rem;
  width: 100%;
}

.s-num {
  background: rgba(255,255,255,.22);
  border-radius: 50%;
  width: 1.5rem;
  height: 1.5rem;
  display: flex;
  align-items: center;
  justify-content: center;
  font-weight: 700;
  font-size: 0.75rem;
  flex-shrink: 0;
}

.s-title {
  font-weight: 600;
  font-size: 0.88rem;
  flex: 1;
  line-height: 1.25;
  min-width: 0;
}

.chev::after {
  content: "";
  display: block;
  width: 0.4rem;
  height: 0.4rem;
  border: solid #fff;
  border-width: 0 2px 2px 0;
  transform: rotate(45deg);
  margin: 0 0.2rem 0.15rem;
  transition: transform .2s;
  flex-shrink: 0;
}

.scheme[open] .chev::after {
  transform: rotate(-135deg);
  margin-bottom: 0;
  margin-top: 0.15rem;
}

/* Chips – critical for mobile fit */
.chips {
  display: flex;
  flex-wrap: wrap;
  gap: 0.3rem;
  margin-top: 0.35rem;
  width: 100%;
}

.chip {
  flex: 1 1 auto;
  min-width: 0;
  border-radius: 7px;
  padding: 0.28rem 0.4rem;
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 0.25rem;
  line-height: 1.15;
}

.chip i {
  font-style: normal;
  font-size: 0.55rem;
  text-transform: uppercase;
  letter-spacing: 0.02em;
  opacity: 0.95;
  white-space: nowrap;
}

.chip b {
  font-size: 0.78rem;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.chip.cur, .tile.cur {
  background: linear-gradient(135deg, #f6ad55, var(--o));
  color: #fff;
}

.chip.pot, .tile.pot {
  background: linear-gradient(135deg, #48bb78, var(--g));
  color: #fff;
}

.chip.nt {
  background: rgba(255,255,255,.18);
  color: #fff;
}

/* Body content */
.s-body {
  padding: 0.75rem 0.8rem;
  width: 100%;
}

.sec { margin-bottom: 0.8rem; }

.sec-t {
  font-size: 0.65rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: var(--p2);
  border-left: 3px solid var(--p2);
  padding-left: 0.4rem;
  margin-bottom: 0.35rem;
}

.metrics {
  display: grid;
  grid-template-columns: repeat(2, minmax(0, 1fr));
  gap: 0.35rem;
  width: 100%;
}

.metric {
  background: #f7fafc;
  border: 1px solid var(--bd);
  border-radius: 8px;
  padding: 0.4rem 0.25rem;
  text-align: center;
  min-width: 0;
}

.metric .l {
  font-size: 0.58rem;
  text-transform: uppercase;
  letter-spacing: 0.02em;
  color: var(--mu);
  font-weight: 600;
  line-height: 1.15;
  margin-bottom: 0.12rem;
}

.metric .v {
  font-size: 0.9rem;
  font-weight: 700;
  color: var(--p);
}

.v.pos { color: var(--g); }
.v.neg { color: var(--r); }
.v.txt { font-size: 0.82rem; }

.earn {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.35rem;
  margin-bottom: 0.8rem;
  width: 100%;
}

.tile {
  border-radius: 9px;
  padding: 0.55rem 0.3rem;
  text-align: center;
  min-width: 0;
}

.tile .l {
  font-size: 0.58rem;
  text-transform: uppercase;
  letter-spacing: 0.03em;
  font-weight: 600;
  opacity: 0.95;
}

.tile .v {
  font-size: 1.05rem;
  font-weight: 800;
  margin-top: 0.08rem;
}

.bar { margin-bottom: 0.8rem; width: 100%; }

.bar-l {
  display: flex;
  justify-content: space-between;
  gap: 0.3rem;
  font-size: 0.68rem;
  color: var(--mu);
  margin-bottom: 0.2rem;
}

.bar-l b { color: var(--p); }

.bar-t {
  height: 7px;
  background: var(--bd);
  border-radius: 5px;
  overflow: hidden;
}

.bar-f {
  height: 100%;
  background: var(--p2);
  border-radius: 5px;
}

.bar-f.ok { background: #38a169; }

.tbl {
  width: 100%;
  border-collapse: collapse;
  table-layout: fixed;
  font-size: 0.72rem;
  margin-top: 0.35rem;
}

.tbl th {
  background: #edf2f7;
  color: var(--mu);
  font-size: 0.58rem;
  text-transform: uppercase;
  padding: 0.3rem 0.12rem;
}

.tbl td, .tbl th { overflow-wrap: anywhere; }

.tbl td {
  padding: 0.3rem 0.12rem;
  border-bottom: 1px solid var(--bd);
  text-align: center;
}

.tbl td:first-child,
.tbl th:first-child {
  text-align: left;
  padding-left: 0.3rem;
}

.cond {
  background: #fffaf0;
  border: 1px solid #fbd38d;
  border-radius: 9px;
  padding: 0.55rem 0.7rem;
  width: 100%;
}

.cond-t {
  font-size: 0.62rem;
  font-weight: 700;
  text-transform: uppercase;
  letter-spacing: 0.04em;
  color: #9c4221;
  margin-bottom: 0.25rem;
}

.cond ul { list-style: none; }

.cond li {
  font-size: 0.72rem;
  line-height: 1.35;
  padding: 0.25rem 0 0.25rem 0.8rem;
  position: relative;
  border-top: 1px dashed #fbd38d;
}

.cond li:first-child { border-top: 0; }

.cond li::before {
  content: "▸";
  position: absolute;
  left: 0;
  color: #ed8936;
}

.cond li b { color: #7b341e; }

.cond li.h {
  font-weight: 700;
  color: #7b341e;
  padding-left: 0;
  margin-top: 0.12rem;
}

.cond li.h::before { content: none; }

/* Larger phones / tablets */
@media (min-width: 400px) {
  html { font-size: 15px; }
  .login { max-width: 360px; }
  .metrics { grid-template-columns: repeat(auto-fill, minmax(130px, 1fr)); }
}

@media (min-width: 600px) {
  html { font-size: 16px; }
  .header h1 { font-size: 1.25rem; }
  .metrics { grid-template-columns: repeat(auto-fill, minmax(150px, 1fr)); }
  .cond li { font-size: 0.8rem; }
}

/* ===== MODERN UI REFRESH ===== */
:root{
  --p:#0b1635;
  --p2:#1769e0;
  --p3:#4f46e5;
  --g:#0f9f6e;
  --o:#f59e0b;
  --r:#dc3545;
  --bd:#dfe6f1;
  --mu:#667085;
  --ink:#111827;
  --surface:#ffffff;
  --bg:#f4f7fc;
}

html{background:var(--bg)}
body{
  background:
    radial-gradient(circle at 8% 0%, rgba(79,70,229,.14), transparent 30rem),
    radial-gradient(circle at 95% 15%, rgba(23,105,224,.12), transparent 26rem),
    linear-gradient(180deg,#eef3fb 0%,#f7f9fc 45%,#f3f6fb 100%);
  color:var(--ink);
}

/* The oversized title/header has been removed. */
.header{display:none!important}

.container{
  max-width:1100px;
  margin:0 auto;
  padding:clamp(1rem,3vw,2rem) max(1rem,var(--safe-r)) calc(2rem + var(--safe-b)) max(1rem,var(--safe-l));
}

/* Login */
#loginSection{
  min-height:calc(100dvh - 3rem);
  position:relative;
}
#loginSection::before{
  content:"";
  position:absolute;
  width:18rem;height:18rem;
  border-radius:50%;
  background:linear-gradient(135deg,rgba(79,70,229,.16),rgba(23,105,224,.04));
  top:8%;left:-8rem;
  filter:blur(2px);
}
.login{
  position:relative;
  max-width:410px;
  padding:2rem 1.6rem 1.6rem;
  border:1px solid rgba(255,255,255,.9);
  border-radius:24px;
  background:rgba(255,255,255,.92);
  box-shadow:0 22px 60px rgba(16,35,75,.13),0 3px 12px rgba(16,35,75,.06);
  backdrop-filter:blur(16px);
  overflow:hidden;
}
.login::before{
  content:"";
  position:absolute;
  inset:0 0 auto;
  height:5px;
  background:linear-gradient(90deg,#1769e0,#4f46e5,#12b981);
}
.login-mark{
  width:58px;height:58px;
  display:grid;place-items:center;
  margin:0 auto .85rem;
  border-radius:18px;
  color:#fff;
  font-size:1rem;font-weight:900;
  letter-spacing:.06em;
  background:linear-gradient(135deg,#0b1635,#1769e0 60%,#4f46e5);
  box-shadow:0 10px 25px rgba(23,105,224,.28);
}
.login h2{
  color:#0b1635;
  font-size:1.45rem;
  text-align:center;
  margin-bottom:.25rem;
}
.login-sub{
  color:var(--mu);
  font-size:.78rem;
  text-align:center;
  margin-bottom:1.35rem;
}
.fg label{color:#344054;font-size:.75rem}
.fg input{
  border:1px solid #d7deea;
  background:#f9fbfe;
  border-radius:12px;
  transition:.2s ease;
}
.fg input:hover{border-color:#b8c5d8}
.fg input:focus{
  border-color:#1769e0;
  background:#fff;
  box-shadow:0 0 0 4px rgba(23,105,224,.11);
}
.btn{
  background:linear-gradient(135deg,#0b1635 0%,#1769e0 58%,#4f46e5 100%);
  border-radius:12px;
  box-shadow:0 8px 20px rgba(23,105,224,.22);
  transition:transform .18s ease,box-shadow .18s ease;
}
.btn:hover{box-shadow:0 12px 26px rgba(23,105,224,.28);transform:translateY(-1px)}
.btn:active{transform:translateY(0) scale(.99)}

/* Dashboard identity */
#dashboard{animation:fadeUp .45s ease both}
.dealer{
  position:relative;
  margin-bottom:1rem;
  padding:1rem 1.05rem;
  border:1px solid rgba(255,255,255,.85);
  border-radius:18px;
  background:linear-gradient(135deg,#0b1635 0%,#172b5d 62%,#243e83 100%);
  color:#fff;
  box-shadow:0 14px 35px rgba(11,22,53,.18);
  overflow:hidden;
}
.dealer::after{
  content:"";
  position:absolute;
  width:180px;height:180px;
  border-radius:50%;
  right:-70px;top:-95px;
  background:rgba(255,255,255,.08);
}
.dealer-main{position:relative;z-index:1}
.dealer h2{color:#fff;font-size:1.35rem;letter-spacing:-.02em}
.dealer-kicker{
  display:block;
  font-size:.58rem;
  letter-spacing:.12em;
  font-weight:800;
  color:#a9c7ff;
  margin-bottom:.2rem;
}
.dealer-actions{position:relative;z-index:2;display:flex;align-items:center;gap:.45rem;flex-shrink:0}
.dealer .code{
  position:relative;z-index:1;
  color:#d5e2fb;
  background:rgba(255,255,255,.09);
  border:1px solid rgba(255,255,255,.12);
  border-radius:999px;
  padding:.28rem .65rem;
}

/* Section toolbar */
.running{
  margin:1rem 0 .25rem;
  padding:.1rem .05rem;
}
.running h3{font-size:1.05rem;color:#0b1635}
.count{
  background:linear-gradient(135deg,#1769e0,#4f46e5);
  box-shadow:0 4px 12px rgba(23,105,224,.2);
}
.link{
  border-color:#c9d5e8;
  color:#1769e0;
  background:#fff;
  box-shadow:0 3px 10px rgba(16,35,75,.05);
  transition:.18s ease;
}
.link:hover{background:#eef5ff;border-color:#9db9e6}
.hint{color:#7b8798;margin-bottom:.8rem}

/* Scheme cards */
#schemes{gap:.8rem}
.scheme{
  border:1px solid #e3e8f0;
  border-radius:17px;
  box-shadow:0 5px 18px rgba(16,35,75,.055);
  transition:transform .2s ease,box-shadow .2s ease,border-color .2s ease;
}
.scheme:hover{
  transform:translateY(-2px);
  box-shadow:0 12px 30px rgba(16,35,75,.10);
  border-color:#d2dceb;
}
.scheme > summary{
  padding:.7rem .8rem;
  background:linear-gradient(135deg,#0b1635,#173b79 62%,#1769e0);
}
.scheme:nth-child(2) > summary{background:linear-gradient(135deg,#10233f,#155e75 62%,#0f9f9a)}
.scheme:nth-child(3) > summary{background:linear-gradient(135deg,#24134f,#4f2f9e 62%,#7c3aed)}
.scheme:nth-child(4) > summary{background:linear-gradient(135deg,#173b32,#087f5b 62%,#12b981)}
.scheme:nth-child(5) > summary{background:linear-gradient(135deg,#4a2405,#a75d08 62%,#f59e0b)}
.scheme:nth-child(6) > summary{background:linear-gradient(135deg,#102e50,#2563a9 62%,#38bdf8)}
.scheme:nth-child(7) > summary{background:linear-gradient(135deg,#3a1731,#8b2f61 62%,#e11d75)}
.s-num{
  background:rgba(255,255,255,.15);
  border:1px solid rgba(255,255,255,.16);
}
.s-title{font-weight:700}
.s-body{
  padding:.95rem;
  background:linear-gradient(180deg,#fff 0%,#fbfcfe 100%);
}
.sec-t{
  color:#2457a6;
  border-left-color:#1769e0;
}
.metric{
  background:#f8fafd;
  border-color:#e4e9f1;
  padding:.52rem .3rem;
  transition:.18s ease;
}
.metric:hover{background:#f1f6ff;border-color:#cddcf2}
.metric .v{color:#102a56}
.bar-t{background:#e7edf5;height:8px}
.bar-f{
  background:linear-gradient(90deg,#1769e0,#4f46e5);
  box-shadow:0 0 8px rgba(23,105,224,.2);
  transition:width .7s cubic-bezier(.2,.8,.2,1);
}
.bar-f.ok{background:linear-gradient(90deg,#0f9f6e,#20c997)}
.chip.cur,.tile.cur{
  background:linear-gradient(135deg,#f59e0b,#ea7b09);
  box-shadow:0 5px 14px rgba(245,158,11,.16);
}
.chip.pot,.tile.pot{
  background:linear-gradient(135deg,#0f9f6e,#087f5b);
  box-shadow:0 5px 14px rgba(15,159,110,.15);
}
.chip.nt{background:#eef3fa;color:#17365f}
.earn{gap:.55rem}
.tile{padding:.7rem .35rem;border-radius:12px}
.tile .v{font-size:1.12rem}
.tbl th{background:#eef3f9;color:#526173}
.tbl td{border-bottom-color:#e6ebf2}
.cond{
  background:linear-gradient(135deg,#fffaf0,#fffdf8);
  border-color:#f5d48a;
  box-shadow:0 4px 12px rgba(154,103,20,.05);
}
.cond-t{color:#a15c12}
.cond li{border-top-color:#f3dfb1}
.cond li::before{color:#e69a22}
.cond li b,.cond li.h{color:#814d13}


/* Dashboard data summary */
.dashboard-summary{
  display:grid;
  grid-template-columns:repeat(3,minmax(0,1fr));
  gap:.65rem;
  margin:.8rem 0 1rem;
}
.sum-card{
  position:relative;
  overflow:hidden;
  border-radius:16px;
  padding:.8rem .85rem;
  color:#fff;
  box-shadow:0 9px 22px rgba(16,35,75,.09);
}
.sum-card::after{
  content:"";
  position:absolute;
  width:90px;height:90px;border-radius:50%;
  right:-35px;top:-45px;background:rgba(255,255,255,.10);
}
.sum-card.blue{background:linear-gradient(135deg,#0b1635,#1769e0)}
.sum-card.green{background:linear-gradient(135deg,#07553e,#0f9f6e)}
.sum-card.purple{background:linear-gradient(135deg,#2c1a63,#7c3aed)}
.sum-label{font-size:.58rem;text-transform:uppercase;letter-spacing:.07em;font-weight:700;opacity:.8}
.sum-value{font-size:1.18rem;font-weight:850;margin-top:.12rem;position:relative;z-index:1}
.sum-note{font-size:.61rem;opacity:.78;margin-top:.1rem;position:relative;z-index:1}
@media(max-width:520px){
  .dashboard-summary{grid-template-columns:1fr 1fr}
  .sum-card:last-child{grid-column:1/-1}
}


/* Requested portal refinements */
.dealer-disclaimer{
  max-width:720px;margin-top:.35rem;color:#d7e4fb;font-size:.66rem;line-height:1.45;
  font-style:italic;position:relative;z-index:1;
}
.dealer-actions{margin-left:auto}
.scheme > summary{position:relative}
.qual-badge{
  margin-left:auto;flex:0 0 auto;padding:.26rem .58rem;border-radius:999px;
  font-size:.62rem;font-weight:800;letter-spacing:.02em;
  border:1px solid rgba(255,255,255,.22);background:rgba(255,255,255,.13);color:#fff;
}
.qual-yes{background:rgba(16,185,129,.20);border-color:rgba(110,231,183,.45);color:#d9fff1}
.qual-no{background:rgba(239,68,68,.16);border-color:rgba(252,165,165,.38);color:#ffe1e1}
.cond,.cond li,.cond-t{font-style:italic}
.gap,.gap-value,.is-gap,.num-gap{color:#d97706!important;font-weight:800!important}
/* Vahan Retail Cashback – Excel layout */
.vahan-layout{display:flex;flex-direction:column;gap:.35rem;width:100%}
.vahan-layout .vahan-row{width:100%}
.vahan-layout .vahan-row .metrics{width:100%}
.vahan-layout .vahan-row:not(.three) .metrics{grid-template-columns:minmax(0,1fr)}
.vahan-layout .vahan-row.three .metrics{grid-template-columns:repeat(3,minmax(0,1fr))}

.negative,.is-negative,.num-negative{color:#dc2626!important;font-weight:800!important}
@media(max-width:520px){
  .dealer-disclaimer{font-size:.59rem}.qual-badge{font-size:.56rem;padding:.23rem .45rem}
}

/* Gentle motion */
@keyframes fadeUp{
  from{opacity:0;transform:translateY(10px)}
  to{opacity:1;transform:translateY(0)}
}
@keyframes shimmer{
  from{background-position:0 0}
  to{background-position:200% 0}
}
.scheme[open] > summary{
  animation:none!important;
  background-size:100% 100%;
}
@media (prefers-reduced-motion:reduce){
  *,*::before,*::after{animation:none!important;transition:none!important}
}
@media (min-width:700px){
  .container{padding-top:2.2rem}
  #schemes{gap:1rem}
  .scheme > summary{padding:.8rem 1rem}
  .s-body{padding:1.15rem}
}
@media (max-width:520px){
  .container{padding-left:.75rem;padding-right:.75rem}
  .login{padding:1.8rem 1.15rem 1.35rem;border-radius:20px}
  .dealer{padding:.85rem}
  .dealer .code{font-size:.68rem}
  .s-title{font-size:.84rem}
}

</style>
</head>
<body>
<div class="container">
  <div id="loginSection">
    <div class="login">
      <div class="login-mark"><span>NEXA</span></div>
      <h2>Dealer Incentive Portal</h2>
      
      <div id="errorMsg" class="err" role="alert"></div>
      <form id="loginForm" onsubmit="return handleLogin(event)">
        <div class="fg">
          <label for="dealerCode">Dealer Code</label>
          <input type="text" id="dealerCode" placeholder="e.g. G1NA" required
                 autocomplete="username" autocapitalize="characters"
                 autocorrect="off" spellcheck="false" enterkeyhint="next">
        </div>
        <div class="fg">
          <label for="password">Password</label>
          <input type="password" id="password" placeholder="Enter password" required
                 autocomplete="current-password" autocapitalize="none"
                 autocorrect="off" spellcheck="false" enterkeyhint="go">
        </div>
        <button type="submit" class="btn">View Schemes</button>
      </form>
    </div>
  </div>

  <div id="dashboard">
    <div class="dealer">
      <div class="dealer-main">
        <span class="dealer-kicker">NEXA • C4 INCENTIVE</span>
        <h2 id="dealerName">—</h2>
        <div class="dealer-disclaimer">All Scheme achievement and payout status are tentative. For more information kindly contact regional office team.</div>
      </div>
      <div class="dealer-actions"><div class="code">Code: <span id="dealerCodeDisplay">—</span></div><button id="logoutBtn" class="btn-out" onclick="logout()" style="display:none">Logout</button></div>
    </div>
    <div class="running">
      <h3>Schemes Running</h3>
      <span class="count">7</span>
      <button id="toggleBtn" class="link" onclick="toggleAll()">Expand all</button>
    </div>
    
    <div id="dashboardSummary" class="dashboard-summary"></div>
    <div id="schemes"></div>
  </div>
</div>

<script>
const DEALERS = {"G1NA":{"code":"G1NA","password":"G1NAAdinath","name":"Adinath","vahan":{"tgt":145,"ach":68,"pend":12,"pipe":80,"gap":65,"cur":204000,"pot":435000},"pp":{"base":537,"req":564,"ach":66,"gap":498,"pq1":87,"pcur":54,"pgr":-0.3793,"pot":1269000,"cur":148500},"psl":{"grp":"B","rank":"-","sb":383,"sa":66,"sg":-0.8277,"pb":322,"pr":54,"pgr":-0.8323,"qb":110,"qa":66,"qg":-0.4},"nac":{"base":422,"ach":null,"g1":422,"g2":431,"g3":439,"g4":452,"gvq3":19,"req":24,"gach":null,"ggap":24,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"D7NA":{"code":"D7NA","password":"D7NACity","name":"City Cars","vahan":{"tgt":165,"ach":70,"pend":37,"pipe":107,"gap":58,"cur":210000,"pot":495000},"pp":{"base":715,"req":751,"ach":87,"gap":664,"pq1":109,"pcur":68,"pgr":-0.3761,"pot":1689750,"cur":195750},"psl":{"grp":"B","rank":"-","sb":470,"sa":87,"sg":-0.8149,"pb":411,"pr":68,"pgr":-0.8345,"qb":134,"qa":87,"qg":-0.3507},"nac":{"base":559,"ach":null,"g1":559,"g2":571,"g3":582,"g4":599,"gvq3":26,"req":33,"gach":null,"ggap":33,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"KMNA":{"code":"KMNA","password":"KMNAInfinity","name":"Infinity","vahan":{"tgt":35,"ach":26,"pend":8,"pipe":34,"gap":1,"cur":78000,"pot":105000},"pp":{"base":170,"req":179,"ach":31,"gap":148,"pq1":23,"pcur":25,"pgr":0.087,"pot":402750,"cur":69750},"psl":{"grp":"D","rank":"-","sb":131,"sa":31,"sg":-0.7634,"pb":108,"pr":25,"pgr":-0.7685,"qb":30,"qa":31,"qg":0.0333},"nac":{"base":133,"ach":null,"g1":133,"g2":136,"g3":139,"g4":143,"gvq3":4,"req":5,"gach":null,"ggap":5,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"03NB":{"code":"03NB","password":"03NBJeewan","name":"Jeewan","vahan":{"tgt":100,"ach":47,"pend":13,"pipe":60,"gap":40,"cur":141000,"pot":300000},"pp":{"base":768,"req":806,"ach":56,"gap":750,"pq1":56,"pcur":33,"pgr":-0.4107,"pot":1813500,"cur":126000},"psl":{"grp":"B","rank":"-","sb":633,"sa":56,"sg":-0.9115,"pb":426,"pr":33,"pgr":-0.9225,"qb":94,"qa":56,"qg":-0.4043},"nac":{"base":593,"ach":null,"g1":593,"g2":605,"g3":617,"g4":635,"gvq3":20,"req":25,"gach":null,"ggap":25,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"U5NA":{"code":"U5NA","password":"U5NAKamthi","name":"Kamthi Motors","vahan":{"tgt":105,"ach":58,"pend":17,"pipe":75,"gap":30,"cur":174000,"pot":315000},"pp":{"base":493,"req":518,"ach":69,"gap":449,"pq1":74,"pcur":65,"pgr":-0.1216,"pot":1165500,"cur":155250},"psl":{"grp":"C","rank":"-","sb":347,"sa":69,"sg":-0.8012,"pb":338,"pr":65,"pgr":-0.8077,"qb":79,"qa":69,"qg":-0.1266},"nac":{"base":376,"ach":null,"g1":376,"g2":384,"g3":392,"g4":403,"gvq3":19,"req":24,"gach":null,"ggap":24,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NE":{"code":"53NE","password":"53NEKTL","name":"KTL","vahan":{"tgt":175,"ach":103,"pend":38,"pipe":141,"gap":34,"cur":309000,"pot":525000},"pp":{"base":409,"req":429,"ach":125,"gap":304,"pq1":70,"pcur":52,"pgr":-0.2571,"pot":965250,"cur":281250},"psl":{"grp":"National A","rank":"-","sb":199,"sa":125,"sg":-0.3719,"pb":117,"pr":52,"pgr":-0.5556,"qb":122,"qa":125,"qg":0.0246},"nac":{"base":405,"ach":null,"g1":405,"g2":414,"g3":422,"g4":434,"gvq3":15,"req":19,"gach":null,"ggap":19,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"30NB":{"code":"30NB","password":"30NBNikunj","name":"Nikunj","vahan":{"tgt":110,"ach":45,"pend":41,"pipe":86,"gap":24,"cur":135000,"pot":330000},"pp":{"base":360,"req":378,"ach":74,"gap":304,"pq1":38,"pcur":32,"pgr":-0.1579,"pot":850500,"cur":166500},"psl":{"grp":"B","rank":"-","sb":272,"sa":74,"sg":-0.7279,"pb":168,"pr":32,"pgr":-0.8095,"qb":63,"qa":74,"qg":0.1746},"nac":{"base":284,"ach":null,"g1":284,"g2":290,"g3":296,"g4":304,"gvq3":11,"req":14,"gach":null,"ggap":14,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"AUNA":{"code":"AUNA","password":"AUNANimar","name":"Nimar Motors","vahan":{"tgt":80,"ach":56,"pend":19,"pipe":75,"gap":5,"cur":168000,"pot":240000},"pp":{"base":478,"req":502,"ach":75,"gap":427,"pq1":43,"pcur":46,"pgr":0.0698,"pot":1129500,"cur":168750},"psl":{"grp":"B","rank":"-","sb":336,"sa":75,"sg":-0.7768,"pb":250,"pr":46,"pgr":-0.816,"qb":59,"qa":75,"qg":0.2712},"nac":{"base":369,"ach":null,"g1":369,"g2":377,"g3":384,"g4":395,"gvq3":22,"req":28,"gach":null,"ggap":28,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NB":{"code":"53NB","password":"53NBOcean","name":"Ocean Group","vahan":{"tgt":305,"ach":173,"pend":78,"pipe":251,"gap":54,"cur":519000,"pot":915000},"pp":{"base":1489,"req":1563,"ach":229,"gap":1334,"pq1":125,"pcur":110,"pgr":-0.12,"pot":3516750,"cur":515250},"psl":{"grp":"A","rank":"-","sb":985,"sa":229,"sg":-0.7675,"pb":631,"pr":110,"pgr":-0.8257,"qb":225,"qa":229,"qg":0.0178},"nac":{"base":1146,"ach":null,"g1":1146,"g2":1169,"g3":1192,"g4":1227,"gvq3":80,"req":100,"gach":null,"ggap":100,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NA":{"code":"53NA","password":"53NAPatel","name":"Patel Group","vahan":{"tgt":215,"ach":114,"pend":61,"pipe":175,"gap":40,"cur":342000,"pot":645000},"pp":{"base":923,"req":969,"ach":162,"gap":807,"pq1":98,"pcur":102,"pgr":0.0408,"pot":2180250,"cur":364500},"psl":{"grp":"A","rank":"-","sb":649,"sa":162,"sg":-0.7504,"pb":480,"pr":102,"pgr":-0.7875,"qb":163,"qa":162,"qg":-0.0061},"nac":{"base":680,"ach":null,"g1":680,"g2":694,"g3":708,"g4":728,"gvq3":34,"req":43,"gach":null,"ggap":43,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"30NA":{"code":"30NA","password":"30NAPrem","name":"Prem Group","vahan":{"tgt":195,"ach":116,"pend":26,"pipe":142,"gap":53,"cur":348000,"pot":585000},"pp":{"base":542,"req":569,"ach":132,"gap":437,"pq1":78,"pcur":47,"pgr":-0.3974,"pot":1280250,"cur":297000},"psl":{"grp":"National A","rank":"-","sb":485,"sa":132,"sg":-0.7278,"pb":294,"pr":47,"pgr":-0.8401,"qb":148,"qa":132,"qg":-0.1081},"nac":{"base":384,"ach":null,"g1":384,"g2":392,"g3":400,"g4":411,"gvq3":15,"req":19,"gach":null,"ggap":19,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"03NC":{"code":"03NC","password":"03NCRajrup","name":"Rajrup","vahan":{"tgt":185,"ach":118,"pend":17,"pipe":135,"gap":50,"cur":354000,"pot":555000},"pp":{"base":949,"req":996,"ach":115,"gap":881,"pq1":80,"pcur":55,"pgr":-0.3125,"pot":2241000,"cur":258750},"psl":{"grp":"B","rank":"-","sb":653,"sa":115,"sg":-0.8239,"pb":493,"pr":55,"pgr":-0.8884,"qb":129,"qa":115,"qg":-0.1085},"nac":{"base":719,"ach":null,"g1":719,"g2":734,"g3":748,"g4":770,"gvq3":42,"req":53,"gach":null,"ggap":53,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"53NC":{"code":"53NC","password":"53NCRukmani","name":"Rukmani","vahan":{"tgt":170,"ach":104,"pend":55,"pipe":159,"gap":11,"cur":312000,"pot":510000},"pp":{"base":851,"req":894,"ach":124,"gap":770,"pq1":55,"pcur":62,"pgr":0.1273,"pot":2011500,"cur":279000},"psl":{"grp":"A","rank":"-","sb":645,"sa":124,"sg":-0.8078,"pb":442,"pr":62,"pgr":-0.8597,"qb":103,"qa":124,"qg":0.2039},"nac":{"base":643,"ach":null,"g1":643,"g2":656,"g3":669,"g4":689,"gvq3":46,"req":58,"gach":null,"ggap":58,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"54ND":{"code":"54ND","password":"54NBShubh","name":"Shubh","vahan":{"tgt":125,"ach":80,"pend":16,"pipe":96,"gap":29,"cur":240000,"pot":375000},"pp":{"base":588,"req":617,"ach":89,"gap":528,"pq1":90,"pcur":79,"pgr":-0.1222,"pot":1388250,"cur":200250},"psl":{"grp":"B","rank":"-","sb":391,"sa":89,"sg":-0.7724,"pb":367,"pr":79,"pgr":-0.7847,"qb":100,"qa":89,"qg":-0.11},"nac":{"base":468,"ach":null,"g1":468,"g2":478,"g3":487,"g4":501,"gvq3":27,"req":34,"gach":null,"ggap":34,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"54NC":{"code":"54NC","password":"54NCStandard","name":"Standard Group","vahan":{"tgt":200,"ach":120,"pend":34,"pipe":154,"gap":46,"cur":360000,"pot":600000},"pp":{"base":852,"req":895,"ach":135,"gap":760,"pq1":157,"pcur":106,"pgr":-0.3248,"pot":2013750,"cur":303750},"psl":{"grp":"B","rank":"-","sb":600,"sa":135,"sg":-0.775,"pb":551,"pr":106,"pgr":-0.8076,"qb":178,"qa":135,"qg":-0.2416},"nac":{"base":694,"ach":null,"g1":694,"g2":708,"g3":722,"g4":743,"gvq3":43,"req":54,"gach":null,"ggap":54,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"3QNB":{"code":"3QNB","password":"3QNAUnitara","name":"Unitara","vahan":{"tgt":40,"ach":40,"pend":4,"pipe":44,"gap":-4,"cur":120000,"pot":120000},"pp":{"base":193,"req":203,"ach":36,"gap":167,"pq1":16,"pcur":23,"pgr":0.4375,"pot":456750,"cur":81000},"psl":{"grp":"C","rank":"-","sb":137,"sa":36,"sg":-0.7372,"pb":77,"pr":23,"pgr":-0.7013,"qb":38,"qa":36,"qg":-0.0526},"nac":{"base":152,"ach":null,"g1":152,"g2":156,"g3":159,"g4":163,"gvq3":8,"req":10,"gach":null,"ggap":10,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}},"3WNA":{"code":"3WNA","password":"3WNAYug","name":"Yug Cars","vahan":{"tgt":50,"ach":30,"pend":7,"pipe":37,"gap":13,"cur":90000,"pot":150000},"pp":{"base":275,"req":289,"ach":33,"gap":256,"pq1":13,"pcur":10,"pgr":-0.2308,"pot":650250,"cur":74250},"psl":{"grp":"C","rank":"-","sb":213,"sa":33,"sg":-0.8451,"pb":119,"pr":10,"pgr":-0.916,"qb":35,"qa":33,"qg":-0.0571},"nac":{"base":196,"ach":null,"g1":196,"g2":200,"g3":204,"g4":210,"gvq3":12,"req":15,"gach":null,"ggap":15,"wtgt":null,"wach":null,"wpct":null,"cur":0,"pot":0},"mega":{"tgt":null,"ach":null,"achp":"#DIV/0!","dms":null,"dmsp":"#DIV/0!","slab":"#DIV/0!","gt":null,"ga":null,"gp":"#DIV/0!","it":null,"ia":null,"ip":"#DIV/0!","xt":null,"xa":null,"xp":"#DIV/0!","jt":null,"ja":null,"jp":"#DIV/0!","cur":"#DIV/0!","pot":0},"gvsc":{"tgt":1,"ach":null,"pct":0,"cur":0,"pot":50000},"tdd":{"tgt":1,"ach":null,"pct":0,"sig":null,"dlt":0,"cur":0,"pot":40000}}};


/* ===== Source of truth: All Scheme Portal Data.xlsx ===== */
const EXCEL_ROWS = [["G1NA","Adinath",220,0,3,3,217,0,0,"Not-Qualified",537,564,69,495,87,54,-0.3793103448275862,1269000,155250,"Not-Qualified","B","-",383,69,-0.8198433420365535,322,57,-0.8229813664596273,110,66,-0.4,"Not-Qualified",422,3,419,428,436,449,19,24,0,24,63,25,0.3968253968253968,56250,141750,"Not-Qualified",170,0,0,3,0.01764705882352941,"No Slab",1,0,0,1,0,0,14,0,0,1,0,0,0,215000,"Not-Qualified",1,0,0,"0",50000,"Not-Qualified",20,0,0,1,0,17,2,0.11764705882352941,40000,680000,"Not-Qualified"],["D7NA","City",300,0,3,3,297,0,0,"Not-Qualified",715,751,88,663,109,68,-0.37614678899082565,1689750,198000,"Not-Qualified","B","-",470,88,-0.8127659574468085,411,69,-0.8321167883211679,134,87,-0.35074626865671643,"Not-Qualified",559,1,558,570,581,598,26,33,1,32,101,36,0.3564356435643564,81000,227250,"Not-Qualified",250,0,0,1,0.004,"No Slab",1,0,0,2,0,0,24,0,0,1,0,0,0,345000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",35,0,0,2,0,28,7,0.25,0,1120000,"Not-Qualified"],["KMNA","Infinity",75,0,1,1,74,0,0,"Not-Qualified",170,179,32,147,23,26,0.13043478260869557,402750,72000,"Not-Qualified","D","-",131,32,-0.7557251908396947,108,26,-0.7592592592592593,30,32,0.06666666666666665,"Not-Qualified",133,0,133,136,139,143,4,5,0,5,29,16,0.5517241379310345,36000,65250,"Not-Qualified",65,3,0.046153846153846156,0,0,"No Slab",1,0,0,1,0,0,1,0,0,1,0,0,0,117500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",4,0,0,0,0,3,2,0.6666666666666666,0,120000,"Not-Qualified"],["03NB","Jeewan",175,0,0,0,175,0,0,"Not-Qualified",768,806,56,750,56,33,-0.4107142857142857,1813500,126000,"Not-Qualified","B","-",633,56,-0.9115323854660348,426,33,-0.9225352112676056,94,56,-0.4042553191489362,"Not-Qualified",593,0,593,605,617,635,20,25,0,25,45,6,0.13333333333333333,13500,101250,"Not-Qualified",105,0,0,0,0,"No Slab",1,0,0,2,0,0,4,0,0,1,0,0,0,195000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",9,0,0,0,0,12,0,0,0,480000,"Not-Qualified"],["U5NA","Kamthi",190,0,4,4,186,0,0,"Not-Qualified",493,518,69,449,74,65,-0.1216216216216216,1165500,155250,"Not-Qualified","C","-",347,69,-0.8011527377521614,338,65,-0.8076923076923077,79,69,-0.12658227848101267,"Not-Qualified",376,0,376,384,392,403,19,24,0,24,72,26,0.3611111111111111,58500,162000,"Not-Qualified",155,0,0,0,0,"No Slab",1,0,0,1,0,0,4,0,0,1,0,0,0,140000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",15,0,0,0,0,18,1,0.05555555555555555,0,720000,"Not-Qualified"],["53NE","KTL",295,0,2,2,293,0,0,"Not-Qualified",409,429,125,304,70,52,-0.2571428571428571,965250,281250,"Not-Qualified","National A","-",199,125,-0.371859296482412,117,52,-0.5555555555555556,122,125,0.024590163934426146,"Not-Qualified",405,0,405,414,422,434,15,19,0,19,113,47,0.415929203539823,105750,254250,"Not-Qualified",300,2,0.006666666666666667,0,0,"No Slab",1,0,0,1,0,0,15,0,0,1,0,0,0,222500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",58,0,0,1,2,70,18,0.2571428571428571,0,2800000,"Not-Qualified"],["30NB","Nikunj",150,0,1,1,149,0,0,"Not-Qualified",360,378,74,304,38,32,-0.1578947368421053,850500,166500,"Not-Qualified","B","-",272,74,-0.7279411764705883,168,32,-0.8095238095238095,63,74,0.17460317460317465,"Not-Qualified",284,0,284,290,296,304,11,14,0,14,45,16,0.35555555555555557,36000,101250,"Not-Qualified",125,1,0.008,0,0,"No Slab",1,0,0,1,0,0,4,0,0,1,0,0,0,140000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",16,0,0,0,0,14,3,0.21428571428571427,0,560000,"Not-Qualified"],["AUNA","Nimar",175,0,1,1,174,0,0,"Not-Qualified",478,502,75,427,43,46,0.06976744186046502,1129500,168750,"Not-Qualified","B","-",336,75,-0.7767857142857143,250,46,-0.8160000000000001,59,75,0.27118644067796605,"Not-Qualified",369,0,369,377,384,395,22,28,0,28,65,8,0.12307692307692308,18000,146250,"Not-Qualified",150,0,0,0,0,"No Slab",1,0,0,1,0,0,6,0,0,1,0,0,0,155000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",20,0,0,0,0,18,0,0,0,720000,"Not-Qualified"],["53NB","Ocean",540,0,6,6,534,0,0,"Not-Qualified",1489,1563,231,1332,125,110,-0.12,3516750,519750,"Not-Qualified","A","-",985,231,-0.7654822335025381,631,111,-0.8240887480190174,225,230,0.022222222222222143,"Not-Qualified",1146,1,1145,1168,1191,1226,80,100,1,99,216,79,0.36574074074074076,177750,486000,"Not-Qualified",540,0,0,1,0.001851851851851852,"No Slab",1,0,0,2,0,0,23,1,0,1,0,0,0,337500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",98,0,0,0,0,88,18,0.20454545454545456,0,3520000,"Not-Qualified"],["53NA","Patel",350,0,3,3,347,0,0,"Not-Qualified",923,969,161,808,98,101,0.030612244897959107,2180250,362250,"Not-Qualified","A","-",649,161,-0.7519260400616332,480,101,-0.7895833333333333,163,161,-0.012269938650306789,"Not-Qualified",680,0,680,694,708,728,34,43,0,43,126,57,0.4523809523809524,128250,283500,"Not-Qualified",325,3,0.009230769230769232,0,0,"No Slab",1,0,0,2,0,0,14,0,0,1,0,0,0,270000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",46,0,0,1,0,45,5,0.1111111111111111,0,1800000,"Not-Qualified"],["30NA","Prem",300,0,2,2,298,0,0,"Not-Qualified",542,569,132,437,78,47,-0.39743589743589747,1280250,297000,"Not-Qualified","National A","-",485,132,-0.7278350515463918,294,47,-0.8401360544217686,148,132,-0.10810810810810811,"Not-Qualified",384,0,384,392,400,411,15,19,1,18,104,42,0.40384615384615385,94500,234000,"Not-Qualified",300,3,0.01,0,0,"No Slab",1,0,0,2,0,0,14,0,0,1,0,0,0,270000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",42,0,0,0,0,25,3,0.12,0,1000000,"Not-Qualified"],["03NC","Rajrup",315,0,5,5,310,0,0,"Not-Qualified",949,996,116,880,80,56,-0.3,2241000,261000,"Not-Qualified","B","-",653,116,-0.8223583460949464,493,56,-0.8864097363083164,129,115,-0.10852713178294571,"Not-Qualified",719,1,718,733,747,769,42,53,1,52,113,67,0.5929203539823009,150750,254250,"Not-Qualified",300,21,0.07,1,0.0033333333333333335,"No Slab",1,0,0,2,0,0,17,0,0,1,0,0,0,292500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",37,0,0,0,0,34,0,0,0,1360000,"Not-Qualified"],["53NC","Rukmani",275,0,1,1,274,0,0,"Not-Qualified",851,894,124,770,55,62,0.1272727272727272,2011500,279000,"Not-Qualified","A","-",645,124,-0.8077519379844962,442,62,-0.8597285067873304,103,124,0.20388349514563098,"Not-Qualified",643,0,643,656,669,689,46,58,0,58,95,37,0.3894736842105263,83250,213750,"Not-Qualified",275,0,0,0,0,"No Slab",1,0,0,2,0,0,13,0,0,1,0,0,0,262500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",60,0,0,0,0,50,0,0,0,2000000,"Not-Qualified"],["54ND","Shubh",220,0,2,2,218,0,0,"Not-Qualified",588,617,89,528,90,79,-0.12222222222222223,1388250,200250,"Not-Qualified","B","-",391,89,-0.7723785166240409,367,79,-0.784741144414169,100,89,-0.10999999999999999,"Not-Qualified",468,0,468,478,487,501,27,34,0,34,72,31,0.4305555555555556,69750,162000,"Not-Qualified",190,1,0.005263157894736842,0,0,"No Slab",1,0,0,1,0,0,13,0,0,1,0,0,0,207500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",37,0,0,5,0,40,9,0.225,0,1600000,"Not-Qualified"],["54NC","Standard",300,0,5,5,295,0,0,"Not-Qualified",852,895,137,758,157,106,-0.32484076433121023,2013750,308250,"Not-Qualified","B","-",600,137,-0.7716666666666667,551,108,-0.8039927404718693,178,135,-0.2415730337078652,"Not-Qualified",694,2,692,706,720,741,43,54,0,54,90,50,0.5555555555555556,112500,202500,"Not-Qualified",275,3,0.01090909090909091,2,0.007272727272727273,"No Slab",1,0,0,2,0,0,27,1,0,1,0,0,0,367500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",66,0,0,5,1,51,13,0.2549019607843137,0,2040000,"Not-Qualified"],["3QNB","Unitara",80,0,1,1,79,0,0,"Not-Qualified",193,203,36,167,16,23,0.4375,456750,81000,"Not-Qualified","C","-",137,36,-0.7372262773722628,77,23,-0.7012987012987013,38,36,-0.052631578947368474,"Not-Qualified",152,0,152,156,159,163,8,10,0,10,25,3,0.12,6750,56250,"Not-Qualified",55,0,0,0,0,"No Slab",1,0,0,1,0,0,4,0,0,1,0,0,0,140000,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",5,0,0,0,0,6,2,0.3333333333333333,0,240000,"Not-Qualified"],["3WNA","Yug",80,0,0,0,80,0,0,"Not-Qualified",275,289,34,255,13,11,-0.15384615384615385,650250,76500,"Not-Qualified","C","-",213,34,-0.8403755868544601,119,11,-0.907563025210084,35,34,-0.02857142857142858,"Not-Qualified",196,0,196,200,204,210,12,15,0,15,24,18,0.75,40500,54000,"Not-Qualified",65,0,0,0,0,"No Slab",1,0,0,1,0,0,3,0,0,1,0,0,0,132500,"Not-Qualified",1,0,0,0,50000,"Not-Qualified",7,0,0,0,0,6,0,0,0,240000,"Not-Qualified"]];
const excelRow = a => ({
  code:a[0],name:a[1],
  vahan:{tgt:a[2],ach:a[3],pend:a[4],pipe:a[5],gap:a[6],cur:a[7],pot:a[8],qual:a[9]},
  pp:{base:a[10],req:a[11],ach:a[12],gap:a[13],pq1:a[14],pcur:a[15],pgr:a[16],pot:a[17],cur:a[18],qual:a[19]},
  psl:{grp:a[20],rank:a[21],sb:a[22],sa:a[23],sg:a[24],pb:a[25],pr:a[26],pgr:a[27],qb:a[28],qa:a[29],qg:a[30],qual:a[31]},
  nac:{base:a[32],ach:a[33],g1:a[34],g2:a[35],g3:a[36],g4:a[37],gvq3:a[38],req:a[39],gach:a[40],ggap:a[41],wtgt:a[42],wach:a[43],wpct:a[44],cur:a[45],pot:a[46],qual:a[47]},
  mega:{tgt:a[48],ach:a[49],achp:a[50],dms:a[51],dmsp:a[52],slab:a[53],gt:a[54],ga:a[55],gp:a[56],it:a[57],ia:a[58],ip:a[59],xt:a[60],xa:a[61],xp:a[62],jt:a[63],ja:a[64],jp:a[65],cur:a[66],pot:a[67],qual:a[68]},
  gvsc:{tgt:a[69],ach:a[70],pct:a[71],cur:a[72],pot:a[73],qual:a[74]},
  tdd:{tgt:a[75],ach:a[76],pct:a[77],sig:a[78],dlt:a[79],wsTgt:a[80],wsAch:a[81],wsAchi2:a[82],cur:a[83],pot:a[84],qual:a[85]}
});
EXCEL_ROWS.forEach(a => {
  const x=excelRow(a);
  if (DEALERS[a[0]]) {
    const password=DEALERS[a[0]].password;
    DEALERS[a[0]]={...DEALERS[a[0]],...x,password};
  }
});


const CONDITIONS = {"vahan":[{"l":null,"t":"To be announced"}],"pp":[{"l":"Scheme Period","t":"September'26 to December'26"},{"l":"Slabs","t":"Slab 1 : >=0% to <3% : 700 || Slab 2 : >=3% to <5% : 1,000 || Slab 3 : >=5% : 1,500"},{"l":"Additional Earning Opportunity (September)","t":"No retail de-growth of “All Models combined retail (Excluding CNG Variants)” in Sep’26 (ie. from 1st Sep’26 - 30th Sep’26) over Q1’26-27 monthly retail average of “All Models combined retail (Excluding CNG Variants)"},{"l":"Vahan / MI Condition","t":"At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail"}],"psl":[{"l":"Super Qualifying Condition","t":"No net retail de-growth during Sep’26 to Nov'26 over Sep’25 to Nov'25."},{"l":"Vahan / MI Condition","t":"At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail"},{"l":"Ranking Condition 1","t":"Sept to Nov - All Models (excluding CNG variants) Net retail growth during Sep’26 to Nov'26 over Sep’25 to Nov'25 (Weightage - 30%)"},{"l":"Ranking Condition 2","t":"September - Net Retail Growth (All Models) in Sep'26 over the Apr'26 to Jun'26 average monthly Net Retail"}],"nac":[{"l":"Target Slabs","t":"Sigma - 0%, Delta - 2%, Zeta - 4%, Alpha - 7%"},{"l":"Vahan / MI Condition","t":"At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail"},{"l":"Additional Earning Opportunity of 25% (October)","t":"Atleast 25% retail growth in Grand Vitara & e VITARA (combined) in Oct'26 over Q3'25-26 monthly average retail."},{"l":null,"t":"Slab Growth shall be considered basis retail done in Q3’26-27 over Q3’25-26 (excluding Ignis)."}],"mega":[{"h":"Super Qualifying Condition","t":"100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount"},{"h":null,"t":"Minimum 90% All Models NET BI Retail Target achievement between 1st Oct’26 – 31st Oct’26 (both days inclusive)"},{"l":"Qualifying Condition","t":"Minimum 90% All Models Retail Target Achievement of between 1st Oct’26 – 31st Oct’26 (both days inclusive)"}],"gvsc":[{"l":null,"t":"It is mandatory to achieve at least 100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount."}],"tdd":[{"l":"Qualifying Condition","t":"97% Wholesale Target Achievement of GV (All Variants) at Parent level"},{"h":"Super Qualifying Condition","t":"It is mandatory to achieve at least 100% Vahan Target in OCT’26 at Region Parent Level to qualify for 100% per car incentive as per qualified slab, else payout shall be 50% of the qualified slab amount"},{"h":null,"t":"90% NET BI Retail Target Achievement of GV (All Variants) at Parent level"}]}

const BAD = [null, undefined, '', '-', '#N/A', '#DIV/0!', '#NA'];

function fmt(v, t) {
  if (BAD.includes(v)) return '—';
  if (typeof v === 'number') {
    let out;
    if (t === 'pct') out = (v * 100).toFixed(1) + '%';
    else if (t === 'cur') out = '₹' + v.toLocaleString('en-IN');
    else out = Number.isInteger(v) ? v.toLocaleString('en-IN') : v.toFixed(2);
    return v < 0 ? '<span class="num-negative">' + out + '</span>' : out;
  }
  return v;
}

const esc = s => String(s).replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;');

function m(label, v, t) {
  let c = t === 'txt' ? 'txt' : (t === 'pct' && typeof v === 'number' ? (v > 0 ? 'pos' : v < 0 ? 'neg' : '') : '');
  if (label.toLowerCase().includes('gap')) c += ' gap-value';
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

const chips = (c, p) => `<div class="chips"><div class="chip cur"><i>Current</i><b>${fmt(c, 'cur')}</b></div><div class="chip pot"><i>Potential</i><b>${fmt(p, 'cur')}</b></div></div>`;
const earn = (c, p) => sec('Earnings', `<div class="earn"><div class="tile cur"><div class="l">Current Earnings</div><div class="v">${fmt(c, 'cur')}</div></div><div class="tile pot"><div class="l">Earning Potential</div><div class="v">${fmt(p, 'cur')}</div></div></div>`);

function conds(key) {
  const li = CONDITIONS[key].map(c => c.h ? `<li class="h">${esc(c.h)}</li>` : `<li>${c.l ? '<b>' + esc(c.l) + ':</b> ' : ''}${esc(c.t)}</li>`).join('');
  return `<div class="cond"><div class="cond-t">Scheme Conditions</div><ul>${li}</ul></div>`;
}

function card(n, key, title, head, work, status) {
  const qualified = String(status || '').toLowerCase() === 'qualified';
  const statusText = qualified ? 'Qualified' : 'Not Qualified';
  return `<details class="scheme"><summary><div class="s-top"><span class="s-num">${n}</span><span class="s-title">${title}</span><span class="qual-badge ${qualified ? 'qual-yes' : 'qual-no'}">${statusText}</span><span class="chev"></span></div>${head}</summary><div class="s-body">${work}${conds(key)}</div></details>`;
}

function renderAll(d) {
  const v = d.vahan, p = d.pp, s = d.psl, n = d.nac, g = d.mega, h = d.gvsc, t = d.tdd;
  const nt = (l, x) => `<div class="chip nt"><i>${l}</i><b>${fmt(x)}</b></div>`;
  return [
    card(1, 'vahan', 'Vahan Retail Cashback – October', chips(v.cur, v.pot),
      sec('Retail Position',
        '<div class="vahan-layout">' +
          '<div class="vahan-row">' + grid([m('Target', v.tgt)]) + '</div>' +
          '<div class="vahan-row three">' + grid([m('Achievement', v.ach), m('Pendency', v.pend), m('Pipeline', v.pipe)]) + '</div>' +
          '<div class="vahan-row">' + grid([m('Gap', v.gap)]) + '</div>' +
        '</div>'
      ) + earn(v.cur, v.pot), v.qual),
    card(2, 'pp', 'Maruti Power Performer 2.0', chips(p.cur, p.pot),
      bar(p.ach, p.req, 'Retail Achievement vs Required') +
      sec('Scheme Achievement', grid([m('All Model Retail Base (Sep–Dec)', p.base), m('Retail Required (@5% Growth)', p.req), m('Retail Achievement', p.ach), m('Gap', p.gap)])) +
      sec('Additional Earning Opportunity', grid([m('Petrol Retail (Q1 Avg)', p.pq1), m('Current Petrol Retails', p.pcur), m('Growth', p.pgr, 'pct')])) +
      earn(p.cur, p.pot), p.qual),
    card(3, 'psl', 'Maruti Suzuki Premier League', `<div class="chips">${nt('Dealer Group', s.grp)}${nt('HO Ranking', s.rank)}</div>`,
      sec('Super Qualifying Criteria', grid([m('Retail Base Sep–Nov', s.sb), m('Retail Achi', s.sa), m('Growth %', s.sg, 'pct')])) +
      sec('Ranking Condition 1 : Sept to Nov', grid([m('Petrol Base', s.pb), m('Petrol Retail', s.pr), m('Growth %', s.pgr, 'pct')])) +
      sec('Ranking Condition 2 : Sept', grid([m('Q1 Retail Base', s.qb), m('Achi', s.qa), m('Growth', s.qg, 'pct')])), s.qual),
    card(4, 'nac', "NEXA Achiever's Club", chips(n.cur, n.pot),
      sec('Slab Achievement', grid([m('Retail Base (Excl. Ignis)', n.base), m('Retail Achievement', n.ach)]) +
        table(['Slab', 'Per Car', 'Gap'], [['Sigma', '₹900', '<span class="gap-value">' + fmt(n.g1) + '</span>'], ['Delta', '₹1,100', '<span class="gap-value">' + fmt(n.g2) + '</span>'], ['Zeta', '₹1,400', '<span class="gap-value">' + fmt(n.g3) + '</span>'], ['Alpha', '₹1,800', '<span class="gap-value">' + fmt(n.g4) + '</span>']])) +
      sec('Additional Earning Opportunity – October', grid([m('Q3 GV & EV Avg Retail', n.gvq3), m('Required Retail', n.req), m('Achi', n.gach), m('Gap', n.ggap)])) +
      bar(n.wach, n.wtgt, 'Wholesale Achi vs Target') +
      sec('Wholesale Achievement', grid([m('Target – October', n.wtgt), m('Achi', n.wach), m('Achi %', n.wpct, 'pct')])) +
      earn(n.cur, n.pot), n.qual),
    card(5, 'mega', 'Mega Dealer Retail Cashback – October', chips(g.cur, g.pot),
      sec('Qualifying Criteria – All Model Retail', grid([m('Target', g.tgt), m('Achi Net BI', g.ach), m('Achi %', g.achp, 'pct'), m('DMS backed by MI', g.dms), m('Achi % (MI)', g.dmsp, 'pct'), m('Slab', g.slab, 'txt')])) +
      sec('Model-wise Performance', table(['Model', 'Target', 'Achi', 'Payout'], [
        ['Grand Vitara Strong Hybrid', fmt(g.gt), fmt(g.ga), fmt(g.gp, 'cur')], ['Invicto', fmt(g.it), fmt(g.ia), fmt(g.ip, 'cur')],
        ['XL6', fmt(g.xt), fmt(g.xa), fmt(g.xp, 'cur')], ['Jimny', fmt(g.jt), fmt(g.ja), fmt(g.jp, 'cur')]])) +
      earn(g.cur, g.pot), g.qual),
    card(6, 'gvsc', 'Grand Vitara Strong Hybrid Super Cashback', chips(h.cur, h.pot),
      bar(h.ach, h.tgt, 'Achievement vs Target') +
      sec('Achievement', grid([m('Target', h.tgt), m('Achievement', h.ach), m('Achi %', h.pct, 'pct')])) +
      earn(h.cur, h.pot), h.qual),
    card(7, 'tdd', 'Dealer Trade Discount Scheme – October', chips(t.cur, t.pot),
      bar(t.ach, t.tgt, 'GV Retail Achievement vs Target') +
      sec('GV Retail', grid([m('GV Retail Target', t.tgt), m('Achievement', t.ach), m('Achi %', t.pct, 'pct')])) +
      sec('GV Wholesale', grid([m('Wholesale Target', t.wsTgt), m('Wholesale Achievement', t.wsAch), m('Wholesale Achi %', t.wsAchi2, 'pct')])) +
      sec('WS Payout', grid([m('GV Sigma', t.sig), m('GV Delta', t.dlt)])) +
      earn(t.cur, t.pot), t.qual)
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

  if (!d || d.password !== pwd) {
    err.style.display = 'block';
    err.textContent = 'Invalid Dealer Code or Password. Please try again.';
    return false;
  }

  err.style.display = 'none';
  document.getElementById('loginSection').style.display = 'none';
  document.getElementById('dashboard').style.display = 'block';
  document.getElementById('logoutBtn').style.display = 'inline-flex';
  document.getElementById('dealerName').textContent = d.name;
  document.getElementById('dealerCodeDisplay').textContent = d.code;

  try {
    const all = [d.vahan, d.pp, d.psl, d.nac, d.mega, d.gvsc, d.tdd];
    const current = all.reduce((sum, x) => sum + (typeof x.cur === 'number' ? x.cur : 0), 0);
    const potential = all.reduce((sum, x) => sum + (typeof x.pot === 'number' ? x.pot : 0), 0);
    const ach = d.vahan && typeof d.vahan.tgt === 'number' && d.vahan.tgt > 0
      ? d.vahan.ach / d.vahan.tgt : 0;

    document.getElementById('dashboardSummary').innerHTML =
      '<div class="sum-card blue"><div class="sum-label">Current Earnings</div><div class="sum-value">' + fmt(current,'cur') + '</div></div>' +
      '<div class="sum-card green"><div class="sum-label">Earning Potential</div><div class="sum-value">' + fmt(potential,'cur') + '</div></div>' +
      '<div class="sum-card purple"><div class="sum-label">Vahan Achievement</div><div class="sum-value">' + fmt(ach,'pct') + '</div><div class="sum-note">' + fmt(d.vahan.ach) + ' / ' + fmt(d.vahan.tgt) + '</div></div>';

    document.getElementById('schemes').innerHTML = renderAll(d);
    document.querySelectorAll('#schemes .scheme').forEach(s => { s.open = false; });
    document.getElementById('toggleBtn').textContent = 'Expand all';
    window.scrollTo(0, 0);
  } catch (renderError) {
    console.error('Dashboard render error:', renderError);
    document.getElementById('schemes').innerHTML =
      '<div class="cond"><div class="cond-t">Dashboard data could not be rendered</div><ul><li>Please refresh the page and try again.</li></ul></div>';
  }

  return false;
}

function logout() {
  document.getElementById('dashboard').style.display = 'none';
  document.getElementById('dashboardSummary').innerHTML = '';
  document.getElementById('schemes').innerHTML = '';
  document.getElementById('loginSection').style.display = 'flex';
  document.getElementById('logoutBtn').style.display = 'none';
  document.getElementById('loginForm').reset();
}
</script>
</body>
</html>