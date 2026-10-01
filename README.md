
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1, maximum-scale=1, viewport-fit=cover, user-scalable=no">
  <meta name="theme-color" content="#1a365d">
  <meta name="color-scheme" content="light">
  <meta name="mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-capable" content="yes">
  <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
  <meta name="format-detection" content="telephone=no">
  <title>Dealer Incentive Schemes Portal</title>
  <style>
    :root {
      --primary: #1a365d; --primary-light: #2b6cb0; --accent: #ed8936;
      --success: #38a169; --danger: #e53e3e; --warning: #d69e2e;
      --bg: #f7fafc; --card: #ffffff; --border: #e2e8f0; --text: #2d3748; --muted: #718096;
      --gutter: clamp(0.75rem, 3vw, 1.5rem);
      color-scheme: light;
    }
    
    /* Robust Reset & Box-Sizing */
    *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
    
    html, body { 
      width: 100%; 
      max-width: 100%; 
      overflow-x: hidden; 
      -webkit-text-size-adjust: 100%; 
      text-size-adjust: 100%; 
    }

    body {
      font-family: system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
      background: var(--bg); color: var(--text);
      min-height: 100vh; min-height: 100dvh; line-height: 1.5;
      -webkit-tap-highlight-color: transparent;
      -webkit-font-smoothing: antialiased;
      overflow-wrap: break-word;
      word-wrap: break-word;
      touch-action: pan-y; /* Fixes mobile panning issues */
    }

    /* Header (respects notch / safe areas) */
    .header {
      background: linear-gradient(135deg, var(--primary), var(--primary-light));
      color: #fff;
      padding: 1rem var(--gutter);
      padding-top: calc(1rem + env(safe-area-inset-top, 0px));
      padding-left: calc(var(--gutter) + env(safe-area-inset-left, 0px));
      padding-right: calc(var(--gutter) + env(safe-area-inset-right, 0px));
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
      width: 100%;
    }
    
    .header-inner {
      max-width: 1200px; 
      margin: 0 auto;
      display: flex; 
      justify-content: space-between; 
      align-items: center; 
      flex-wrap: wrap; 
      gap: 0.75rem;
    }
    
    .header-text { flex: 1; min-width: 200px; }
    .header h1 { font-size: clamp(1.1rem, 4vw, 1.5rem); font-weight: 600; line-height: 1.25; word-break: break-word; }
    .header p { opacity: 0.9; font-size: clamp(0.8rem, 2.8vw, 0.95rem); margin-top: 0.2rem; }

    .container {
      width: 100%;
      max-width: 1200px; 
      margin: 0 auto;
      padding: 1.25rem var(--gutter);
      padding-left: calc(var(--gutter) + env(safe-area-inset-left, 0px));
      padding-right: calc(var(--gutter) + env(safe-area-inset-right, 0px));
      padding-bottom: calc(2rem + env(safe-area-inset-bottom, 0px));
    }

    /* Login */
    .login-card {
      background: var(--card); border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.08);
      padding: clamp(1.25rem, 5vw, 2rem);
      width: 100%; max-width: 420px; margin: clamp(1rem, 6vh, 3rem) auto;
    }
    .login-card h2 { text-align: center; margin-bottom: 1.25rem; color: var(--primary); font-size: 1.35rem; }
    .form-group { margin-bottom: 1.1rem; }
    .form-group label { display: block; font-weight: 600; font-size: 0.875rem; margin-bottom: 0.4rem; }
    .form-group input {
      width: 100%; min-height: 48px; padding: 0.7rem 1rem;
      border: 1.5px solid var(--border); border-radius: 8px;
      font-size: 16px; /* Prevents auto-zoom on iOS */
      font-family: inherit; background: #fff; color: var(--text);
      -webkit-appearance: none; appearance: none;
      transition: border-color 0.2s, box-shadow 0.2s;
    }
    .form-group input:focus {
      outline: none; border-color: var(--primary-light);
      box-shadow: 0 0 0 3px rgba(43,108,176,0.18);
    }
    .btn {
      display: inline-flex; align-items: center; justify-content: center;
      width: 100%; min-height: 48px; padding: 0.75rem 1rem;
      background: var(--primary); color: #fff; border: none; border-radius: 8px;
      font-size: 1rem; font-weight: 600; font-family: inherit; cursor: pointer;
      touch-action: manipulation; -webkit-appearance: none; appearance: none;
      transition: background 0.2s, transform 0.05s;
    }
    .btn:active { transform: scale(0.98); }
    .btn:focus-visible { outline: 3px solid rgba(237,137,54,0.7); outline-offset: 2px; }
    @media (hover: hover) { .btn:hover { background: var(--primary-light); } }
    
    .btn-logout {
      width: auto; min-height: 44px; padding: 0.5rem 1.1rem; font-size: 0.9rem;
      background: rgba(255,255,255,0.2); flex-shrink: 0;
    }
    @media (hover: hover) { .btn-logout:hover { background: rgba(255,255,255,0.32); } }
    
    .error-msg {
      background: #fed7d7; color: var(--danger); padding: 0.75rem; border-radius: 8px;
      margin-bottom: 1rem; font-size: 0.9rem; display: none;
    }

    /* Dashboard */
    #dashboard { display: none; width: 100%; }
    .dealer-info {
      background: var(--card); border-radius: 12px;
      padding: 1.1rem 1.25rem; margin-bottom: 1.25rem;
      box-shadow: 0 2px 8px rgba(0,0,0,0.06);
      display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 0.5rem;
      width: 100%;
    }
    .dealer-info h2 { font-size: clamp(1.1rem, 4vw, 1.4rem); color: var(--primary); word-break: break-word; }
    .dealer-info .code { color: var(--muted); font-size: 0.9rem; }

    /* Schemes Layout */
    #schemesContainer { 
      display: grid; 
      grid-template-columns: minmax(0, 1fr); 
      gap: 1.25rem; 
      align-items: start; 
      width: 100%;
    }
    @media (min-width: 900px) { #schemesContainer { grid-template-columns: repeat(2, minmax(0, 1fr)); } }

    .scheme {
      background: var(--card); border-radius: 12px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.06); overflow: hidden; 
      width: 100%; min-width: 0;
    }
    .scheme-header {
      background: linear-gradient(135deg, var(--primary), #2c5282); color: #fff;
      padding: 0.9rem 1.1rem; font-size: clamp(0.95rem, 3.4vw, 1.1rem); font-weight: 600;
      display: flex; justify-content: space-between; align-items: center; flex-wrap: wrap; gap: 0.4rem 0.75rem;
      word-break: break-word;
    }
    .scheme-header .badge {
      background: rgba(255,255,255,0.2); padding: 0.25rem 0.75rem;
      border-radius: 20px; font-size: 0.75rem; font-weight: 500; white-space: nowrap;
    }
    .scheme-body { padding: 1.1rem; width: 100%; }

    .metrics {
      display: grid; 
      grid-template-columns: repeat(auto-fit, minmax(130px, 1fr));
      gap: 0.75rem; 
      margin-bottom: 0.75rem;
      width: 100%;
    }
    
    .metric {
      background: #f8fafc; border: 1px solid var(--border); border-radius: 8px;
      padding: 0.75rem 0.5rem; text-align: center; min-width: 0;
      display: flex; flex-direction: column; justify-content: center;
      word-wrap: break-word;
    }
    .metric .label {
      font-size: 0.7rem; text-transform: uppercase; letter-spacing: 0.03em;
      color: var(--muted); margin-bottom: 0.3rem; font-weight: 600; line-height: 1.3;
      word-break: break-word; /* Crucial for mobile sizing */
    }
    .metric .value { font-size: clamp(1.05rem, 4vw, 1.3rem); font-weight: 700; color: var(--primary); word-break: break-word; }
    .metric .value.positive { color: var(--success); }
    .metric .value.negative { color: var(--danger); }
    .metric .value.neutral { color: var(--warning); }
    .metric .value.text { font-size: 1.05rem; }

    .section-title {
      font-size: 0.8rem; font-weight: 600; color: var(--muted);
      margin: 1rem 0 0.5rem; text-transform: uppercase; letter-spacing: 0.04em;
      word-break: break-word;
    }

    /* Scheme conditions */
    .conditions { background: #fffaf0; border-bottom: 1px solid #fbd38d; padding: 0.9rem 1.1rem; width: 100%; }
    .conditions .cond-title {
      font-size: 0.75rem; font-weight: 700; text-transform: uppercase;
      letter-spacing: 0.05em; color: #9c4221; margin-bottom: 0.5rem;
    }
    .conditions ul { list-style: none; }
    .conditions li {
      font-size: 0.875rem; line-height: 1.5; color: var(--text);
      padding: 0.4rem 0 0.4rem 1.1rem; position: relative; border-top: 1px dashed #fbd38d;
      word-break: break-word;
    }
    .conditions li:first-child { border-top: none; }
    .conditions li::before { content: '\25B8'; position: absolute; left: 0; color: var(--accent); }
    .conditions li b { color: #7b341e; }

    /* Mobile Responsive Overrides */
    @media (max-width: 480px) {
      html { font-size: 15px; }
      :root { --gutter: 0.6rem; }
      .container { padding-top: 0.75rem; }
      .header { padding-top: calc(0.6rem + env(safe-area-inset-top, 0px)); padding-bottom: 0.6rem; }
      .header h1 { font-size: 1.05rem; }
      .header p { display: none; }
      .btn-logout { min-height: 40px; padding: 0.35rem 0.8rem; font-size: 0.8rem; }
      .dealer-info { padding: 0.7rem 0.9rem; margin-bottom: 0.75rem; }
      .dealer-info h2 { font-size: 1.05rem; }
      .dealer-info .code { font-size: 0.8rem; }
      #schemesContainer { gap: 0.75rem; }
      .scheme-header { padding: 0.6rem 0.8rem; font-size: 0.95rem; }
      .conditions { padding: 0.6rem 0.8rem; }
      .conditions .cond-title { font-size: 0.68rem; margin-bottom: 0.3rem; }
      .conditions li { font-size: 0.76rem; line-height: 1.4; padding: 0.3rem 0 0.3rem 0.9rem; }
      .scheme-body { padding: 0.7rem 0.8rem; }
      
      /* Grid collapse for very small screens */
      .metrics { grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 0.5rem; margin-bottom: 0.4rem; }
      .metric { padding: 0.5rem 0.3rem; }
      .metric .label { font-size: 0.6rem; margin-bottom: 0.2rem; }
      .metric .value { font-size: 1rem; }
      .metric .value.text { font-size: 0.9rem; }
      .section-title { font-size: 0.68rem; margin: 0.7rem 0 0.4rem; }
    }
    
    /* Super narrow screens (e.g., Galaxy Fold front screen) */
    @media (max-width: 320px) {
      .metrics { grid-template-columns: minmax(0, 1fr); }
    }

    @media print {
      .header .btn-logout { display: none; }
      .scheme { box-shadow: none; border: 1px solid #ccc; break-inside: avoid; }
    }
  </style>
</head>
<body>
  <div class="header">
    <div class="header-inner">
      <div class="header-text">
        <h1>Dealer Incentive Schemes</h1>
        <p>View your scheme-wise achievements &amp; earnings</p>
      </div>
      <button id="logoutBtn" class="btn btn-logout" style="display:none;" onclick="logout()">Logout</button>
    </div>
  </div>

  <div class="container">
    <!-- Login -->
    <div id="loginSection">
      <div class="login-card">
        <h2>Dealer Login</h2>
        <div id="errorMsg" class="error-msg" role="alert"></div>
        <form id="loginForm" onsubmit="return handleLogin(event)">
          <div class="form-group">
            <label for="dealerCode">Dealer Code</label>
            <input type="text" id="dealerCode" placeholder="e.g. G1NA" required autocomplete="username"
                   autocapitalize="characters" autocorrect="off" spellcheck="false" enterkeyhint="next">
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input type="password" id="password" placeholder="Enter password" required autocomplete="current-password"
                   autocapitalize="none" autocorrect="off" spellcheck="false" enterkeyhint="go">
          </div>
          <button type="submit" class="btn">View Schemes</button>
        </form>
      </div>
    </div>

    <!-- Dashboard -->
    <div id="dashboard">
      <div class="dealer-info">
        <div>
          <h2 id="dealerName">—</h2>
          <div class="code">Code: <span id="dealerCodeDisplay">—</span></div>
        </div>
      </div>
      <div id="schemesContainer"></div>
    </div>
  </div>

  <script>
    // ========== DEALER DATA ==========
    const DEALERS = {
      "G1NA": {
        "code": "G1NA",
        "password": "G1NAAdinath",
        "name": "Adinath",
        "vahan": { "tgt": 145, "ach": 68, "pend": 12, "pipe": 80, "gap": 65, "cur": 204000, "pot": 435000 },
        "pp": { "base": 537, "req": 564, "ach": 66, "gap": 498, "pq1": 87, "pcur": 54, "pgr": -0.3793, "pot": 1269000, "cur": 148500 },
        "psl": { "grp": "B", "rank": "-", "sb": 383, "sa": 66, "sg": -0.8277, "pb": 322, "pr": 54, "pgr": -0.8323, "qb": 110, "qa": 66, "qg": -0.4 },
        "nac": { "base": 422, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 452, "gvq3": 19, "req": 24, "gv_ach": null, "gv_gap": 24, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "D7NA": {
        "code": "D7NA",
        "password": "D7NACity",
        "name": "City Cars",
        "vahan": { "tgt": 165, "ach": 70, "pend": 37, "pipe": 107, "gap": 58, "cur": 210000, "pot": 495000 },
        "pp": { "base": 715, "req": 751, "ach": 87, "gap": 664, "pq1": 109, "pcur": 68, "pgr": -0.3761, "pot": 1689750, "cur": 195750 },
        "psl": { "grp": "B", "rank": "-", "sb": 470, "sa": 87, "sg": -0.8149, "pb": 411, "pr": 68, "pgr": -0.8345, "qb": 134, "qa": 87, "qg": -0.3507 },
        "nac": { "base": 559, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 599, "gvq3": 26, "req": 33, "gv_ach": null, "gv_gap": 33, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "KMNA": {
        "code": "KMNA",
        "password": "KMNAInfinity",
        "name": "Infinity",
        "vahan": { "tgt": 35, "ach": 26, "pend": 8, "pipe": 34, "gap": 1, "cur": 78000, "pot": 105000 },
        "pp": { "base": 170, "req": 179, "ach": 31, "gap": 148, "pq1": 23, "pcur": 25, "pgr": 0.087, "pot": 402750, "cur": 69750 },
        "psl": { "grp": "D", "rank": "-", "sb": 131, "sa": 31, "sg": -0.7634, "pb": 108, "pr": 25, "pgr": -0.7685, "qb": 30, "qa": 31, "qg": 0.0333 },
        "nac": { "base": 133, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 143, "gvq3": 4, "req": 5, "gv_ach": null, "gv_gap": 5, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "03NB": {
        "code": "03NB",
        "password": "03NBJeewan",
        "name": "Jeewan",
        "vahan": { "tgt": 100, "ach": 47, "pend": 13, "pipe": 60, "gap": 40, "cur": 141000, "pot": 300000 },
        "pp": { "base": 768, "req": 806, "ach": 56, "gap": 750, "pq1": 56, "pcur": 33, "pgr": -0.4107, "pot": 1813500, "cur": 126000 },
        "psl": { "grp": "B", "rank": "-", "sb": 633, "sa": 56, "sg": -0.9115, "pb": 426, "pr": 33, "pgr": -0.9225, "qb": 94, "qa": 56, "qg": -0.4043 },
        "nac": { "base": 593, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 635, "gvq3": 20, "req": 25, "gv_ach": null, "gv_gap": 25, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "U5NA": {
        "code": "U5NA",
        "password": "U5NAKamthi",
        "name": "Kamthi Motors",
        "vahan": { "tgt": 105, "ach": 58, "pend": 17, "pipe": 75, "gap": 30, "cur": 174000, "pot": 315000 },
        "pp": { "base": 493, "req": 518, "ach": 69, "gap": 449, "pq1": 74, "pcur": 65, "pgr": -0.1216, "pot": 1165500, "cur": 155250 },
        "psl": { "grp": "C", "rank": "-", "sb": 347, "sa": 69, "sg": -0.8012, "pb": 338, "pr": 65, "pgr": -0.8077, "qb": 79, "qa": 69, "qg": -0.1266 },
        "nac": { "base": 376, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 403, "gvq3": 19, "req": 24, "gv_ach": null, "gv_gap": 24, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NE": {
        "code": "53NE",
        "password": "53NEKTL",
        "name": "KTL",
        "vahan": { "tgt": 175, "ach": 103, "pend": 38, "pipe": 141, "gap": 34, "cur": 309000, "pot": 525000 },
        "pp": { "base": 409, "req": 429, "ach": 125, "gap": 304, "pq1": 70, "pcur": 52, "pgr": -0.2571, "pot": 965250, "cur": 281250 },
        "psl": { "grp": "National A", "rank": "-", "sb": 199, "sa": 125, "sg": -0.3719, "pb": 117, "pr": 52, "pgr": -0.5556, "qb": 122, "qa": 125, "qg": 0.0246 },
        "nac": { "base": 405, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 434, "gvq3": 15, "req": 19, "gv_ach": null, "gv_gap": 19, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "30NB": {
        "code": "30NB",
        "password": "30NBNikunj",
        "name": "Nikunj",
        "vahan": { "tgt": 110, "ach": 45, "pend": 41, "pipe": 86, "gap": 24, "cur": 135000, "pot": 330000 },
        "pp": { "base": 360, "req": 378, "ach": 74, "gap": 304, "pq1": 38, "pcur": 32, "pgr": -0.1579, "pot": 850500, "cur": 166500 },
        "psl": { "grp": "B", "rank": "-", "sb": 272, "sa": 74, "sg": -0.7279, "pb": 168, "pr": 32, "pgr": -0.8095, "qb": 63, "qa": 74, "qg": 0.1746 },
        "nac": { "base": 284, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 304, "gvq3": 11, "req": 14, "gv_ach": null, "gv_gap": 14, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "AUNA": {
        "code": "AUNA",
        "password": "AUNANimar",
        "name": "Nimar Motors",
        "vahan": { "tgt": 80, "ach": 56, "pend": 19, "pipe": 75, "gap": 5, "cur": 168000, "pot": 240000 },
        "pp": { "base": 478, "req": 502, "ach": 75, "gap": 427, "pq1": 43, "pcur": 46, "pgr": 0.0698, "pot": 1129500, "cur": 168750 },
        "psl": { "grp": "B", "rank": "-", "sb": 336, "sa": 75, "sg": -0.7768, "pb": 250, "pr": 46, "pgr": -0.816, "qb": 59, "qa": 75, "qg": 0.2712 },
        "nac": { "base": 369, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 395, "gvq3": 22, "req": 28, "gv_ach": null, "gv_gap": 28, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NB": {
        "code": "53NB",
        "password": "53NBOcean",
        "name": "Ocean Group",
        "vahan": { "tgt": 305, "ach": 173, "pend": 78, "pipe": 251, "gap": 54, "cur": 519000, "pot": 915000 },
        "pp": { "base": 1489, "req": 1563, "ach": 229, "gap": 1334, "pq1": 125, "pcur": 110, "pgr": -0.12, "pot": 3516750, "cur": 515250 },
        "psl": { "grp": "A", "rank": "-", "sb": 985, "sa": 229, "sg": -0.7675, "pb": 631, "pr": 110, "pgr": -0.8257, "qb": 225, "qa": 229, "qg": 0.0178 },
        "nac": { "base": 1146, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 1227, "gvq3": 80, "req": 100, "gv_ach": null, "gv_gap": 100, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NA": {
        "code": "53NA",
        "password": "53NAPatel",
        "name": "Patel Group",
        "vahan": { "tgt": 215, "ach": 114, "pend": 61, "pipe": 175, "gap": 40, "cur": 342000, "pot": 645000 },
        "pp": { "base": 923, "req": 969, "ach": 162, "gap": 807, "pq1": 98, "pcur": 102, "pgr": 0.0408, "pot": 2180250, "cur": 364500 },
        "psl": { "grp": "A", "rank": "-", "sb": 649, "sa": 162, "sg": -0.7504, "pb": 480, "pr": 102, "pgr": -0.7875, "qb": 163, "qa": 162, "qg": -0.0061 },
        "nac": { "base": 680, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 728, "gvq3": 34, "req": 43, "gv_ach": null, "gv_gap": 43, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "30NA": {
        "code": "30NA",
        "password": "30NAPrem",
        "name": "Prem Group",
        "vahan": { "tgt": 195, "ach": 116, "pend": 26, "pipe": 142, "gap": 53, "cur": 348000, "pot": 585000 },
        "pp": { "base": 542, "req": 569, "ach": 132, "gap": 437, "pq1": 78, "pcur": 47, "pgr": -0.3974, "pot": 1280250, "cur": 297000 },
        "psl": { "grp": "National A", "rank": "-", "sb": 485, "sa": 132, "sg": -0.7278, "pb": 294, "pr": 47, "pgr": -0.8401, "qb": 148, "qa": 132, "qg": -0.1081 },
        "nac": { "base": 384, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 411, "gvq3": 15, "req": 19, "gv_ach": null, "gv_gap": 19, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "03NC": {
        "code": "03NC",
        "password": "03NCRajrup",
        "name": "Rajrup",
        "vahan": { "tgt": 185, "ach": 118, "pend": 17, "pipe": 135, "gap": 50, "cur": 354000, "pot": 555000 },
        "pp": { "base": 949, "req": 996, "ach": 115, "gap": 881, "pq1": 80, "pcur": 55, "pgr": -0.3125, "pot": 2241000, "cur": 258750 },
        "psl": { "grp": "B", "rank": "-", "sb": 653, "sa": 115, "sg": -0.8239, "pb": 493, "pr": 55, "pgr": -0.8884, "qb": 129, "qa": 115, "qg": -0.1085 },
        "nac": { "base": 719, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 770, "gvq3": 42, "req": 53, "gv_ach": null, "gv_gap": 53, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NC": {
        "code": "53NC",
        "password": "53NCRukmani",
        "name": "Rukmani",
        "vahan": { "tgt": 170, "ach": 104, "pend": 55, "pipe": 159, "gap": 11, "cur": 312000, "pot": 510000 },
        "pp": { "base": 851, "req": 894, "ach": 124, "gap": 770, "pq1": 55, "pcur": 62, "pgr": 0.1273, "pot": 2011500, "cur": 279000 },
        "psl": { "grp": "A", "rank": "-", "sb": 645, "sa": 124, "sg": -0.8078, "pb": 442, "pr": 62, "pgr": -0.8597, "qb": 103, "qa": 124, "qg": 0.2039 },
        "nac": { "base": 643, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 689, "gvq3": 46, "req": 58, "gv_ach": null, "gv_gap": 58, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "54ND": {
        "code": "54ND",
        "password": "54NBShubh",
        "name": "Shubh",
        "vahan": { "tgt": 125, "ach": 80, "pend": 16, "pipe": 96, "gap": 29, "cur": 240000, "pot": 375000 },
        "pp": { "base": 588, "req": 617, "ach": 89, "gap": 528, "pq1": 90, "pcur": 79, "pgr": -0.1222, "pot": 1388250, "cur": 200250 },
        "psl": { "grp": "B", "rank": "-", "sb": 391, "sa": 89, "sg": -0.7724, "pb": 367, "pr": 79, "pgr": -0.7847, "qb": 100, "qa": 89, "qg": -0.11 },
        "nac": { "base": 468, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 501, "gvq3": 27, "req": 34, "gv_ach": null, "gv_gap": 34, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "54NC": {
        "code": "54NC",
        "password": "54NCStandard",
        "name": "Standard Group",
        "vahan": { "tgt": 200, "ach": 120, "pend": 34, "pipe": 154, "gap": 46, "cur": 360000, "pot": 600000 },
        "pp": { "base": 852, "req": 895, "ach": 135, "gap": 760, "pq1": 157, "pcur": 106, "pgr": -0.3248, "pot": 2013750, "cur": 303750 },
        "psl": { "grp": "B", "rank": "-", "sb": 600, "sa": 135, "sg": -0.775, "pb": 551, "pr": 106, "pgr": -0.8076, "qb": 178, "qa": 135, "qg": -0.2416 },
        "nac": { "base": 694, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 743, "gvq3": 43, "req": 54, "gv_ach": null, "gv_gap": 54, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "3QNB": {
        "code": "3QNB",
        "password": "3QNAUnitara",
        "name": "Unitara",
        "vahan": { "tgt": 40, "ach": 40, "pend": 4, "pipe": 44, "gap": -4, "cur": 120000, "pot": 120000 },
        "pp": { "base": 193, "req": 203, "ach": 36, "gap": 167, "pq1": 16, "pcur": 23, "pgr": 0.4375, "pot": 456750, "cur": 81000 },
        "psl": { "grp": "C", "rank": "-", "sb": 137, "sa": 36, "sg": -0.7372, "pb": 77, "pr": 23, "pgr": -0.7013, "qb": 38, "qa": 36, "qg": -0.0526 },
        "nac": { "base": 152, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 163, "gvq3": 8, "req": 10, "gv_ach": null, "gv_gap": 10, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "3WNA": {
        "code": "3WNA",
        "password": "3WNAYug",
        "name": "Yug Cars",
        "vahan": { "tgt": 50, "ach": 30, "pend": 7, "pipe": 37, "gap": 13, "cur": 90000, "pot": 150000 },
        "pp": { "base": 275, "req": 289, "ach": 33, "gap": 256, "pq1": 13, "pcur": 10, "pgr": -0.2308, "pot": 650250, "cur": 74250 },
        "psl": { "grp": "C", "rank": "-", "sb": 213, "sa": 33, "sg": -0.8451, "pb": 119, "pr": 10, "pgr": -0.916, "qb": 35, "qa": 33, "qg": -0.0571 },
        "nac": { "base": 196, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 210, "gvq3": 12, "req": 15, "gv_ach": null, "gv_gap": 15, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      }
    };

    // ========== SCHEME CONDITIONS ==========
    const CONDITIONS = {
      "vahan": [
        { "label": "Super Qualifying Criteria", "text": "It is compulsory to achieve atleast 40% Retail & 40% Vahan Target* for SEP-26 by 15th September’26 to qualify for any Incentive" },
        { "label": null, "text": "It is compulsory to achieve atleast 100% Retail Target for Sep-26 to qualify for any Incentive. BI Net Retail will be considered to calculate Retail Target Achievement." },
        { "label": null, "text": "Permanent registration done for All Models of NEXA Channel would be considered for scheme calculation and payout" },
        { "label": null, "text": "Payout will be paid on Vahan registration issued against applicable models from 1-Sep-26 to 30-Sep-26 updated till 5th Oct’26" }
      ],
      "pp": [
        { "label": "Scheme Period", "text": "September'26 to December'26" },
        { "label": "Slabs", "text": "Slab 1 : >=0% to <3% : 700 || Slab 2 : >=3% to <5% : 1,000 || Slab 3 : >=5% : 1,500" },
        { "label": "Additional Earning Opportunity (September)", "text": "No retail de-growth of “All Models combined retail (Excluding CNG Variants)” in Sep’26 (ie. from 1st Sep’26 - 30th Sep’26) over Q1’26-27 monthly retail average of “All Models combined retail (Excluding CNG Variants)" },
        { "label": "Vahan / MI Condition", "text": "At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail" }
      ],
      "psl": [
        { "label": "Super Qualifying Condition", "text": "No net retail de-growth during Sep’26 to Nov'26 over Sep’25 to Nov'25." },
        { "label": "Vahan / MI Condition", "text": "At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 7th Jan'27 for scheme period's retail" },
        { "label": "Ranking Condition 1", "text": "Sept to Nov - All Models (excluding CNG variants) Net retail growth during Sep’26 to Nov'26 over Sep’25 to Nov'25 (Weightage - 30%)" },
        { "label": "Ranking Condition 2", "text": "September - Net Retail Growth (All Models) in Sep'26 over the Apr'26 to Jun'26 average monthly Net Retail" }
      ],
      "nac": [
        { "label": "Target Slabs", "text": "Sigma - 0%, Delta - 2%, Zeta - 4%, Alpha - 7%" },
        { "label": "Vahan / MI Condition", "text": "At least 95% of Non-cancelled DMS retail should have Vahan registration or Maruti Insurance. Retail Period: 1st Sep'26 to 31st Dec'26. Vahan/MI Period: 1st Sep'26 to 17th Jan'27 for scheme period's retail" },
        { "label": "Additional Earning Opportunity of 25% (October)", "text": "Atleast 25% retail growth in Grand Vitara & e VITARA (combined) in Oct'26 over Q3'25-26 monthly average retail." },
        { "label": null, "text": "Slab Growth shall be considered basis retail done in Q3’26-27 over Q3’25-26 (excluding Ignis)." }
      ]
    };

    // ========== HELPERS ==========
    function fmt(v, type) {
      if (v === null || v === undefined || v === '' || v === '-' || v === '#N/A' || v === '#DIV/0!' || v === '#NA') return '—';
      if (typeof v === 'number') {
        if (type === 'pct') return (v * 100).toFixed(1) + '%';
        if (type === 'cur') return '₹' + v.toLocaleString('en-IN');
        if (Number.isInteger(v)) return v.toLocaleString('en-IN');
        return v.toFixed(2);
      }
      return v;
    }
    
    function cls(v, type) {
      if (type === 'text') return 'text';
      if (type === 'pct' && typeof v === 'number') return v > 0 ? 'positive' : (v < 0 ? 'negative' : '');
      return '';
    }
    
    function metric(label, value, type) {
      return `<div class="metric"><div class="label">${label}</div><div class="value ${cls(value, type)}">${fmt(value, type)}</div></div>`;
    }
    
    function esc(s) { return String(s).replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;'); }
    
    function conditionsBox(key) {
      const items = CONDITIONS[key].map(c =>
        `<li>${c.label ? '<b>' + esc(c.label) + ':</b> ' : ''}${esc(c.text)}</li>`).join('');
      return `<div class="conditions"><div class="cond-title">Scheme Conditions</div><ul>${items}</ul></div>`;
    }

    // ========== LOGIN ==========
    function handleLogin(e) {
      e.preventDefault();
      const code = document.getElementById('dealerCode').value.trim().toUpperCase();
      const pwd = document.getElementById('password').value.trim();
      const err = document.getElementById('errorMsg');
      const dealer = DEALERS[code];
      if (!dealer || dealer.password !== pwd) {
        err.style.display = 'block';
        err.textContent = 'Invalid Dealer Code or Password. Please try again.';
        return false;
      }
      err.style.display = 'none';
      showDashboard(dealer);
      return false;
    }
    
    function logout() {
      document.getElementById('dashboard').style.display = 'none';
      document.getElementById('loginSection').style.display = 'block';
      document.getElementById('logoutBtn').style.display = 'none';
      document.getElementById('loginForm').reset();
    }
    
    function showDashboard(d) {
      document.getElementById('loginSection').style.display = 'none';
      document.getElementById('dashboard').style.display = 'block';
      document.getElementById('logoutBtn').style.display = 'inline-block';
      document.getElementById('dealerName').textContent = d.name;
      document.getElementById('dealerCodeDisplay').textContent = d.code;
      document.getElementById('schemesContainer').innerHTML = renderAllSchemes(d);
      window.scrollTo(0, 0);
    }

    // ========== RENDER SCHEMES ==========
    function renderAllSchemes(d) {
      return [renderVahan(d.vahan), renderPP(d.pp), renderPSL(d.psl), renderNAC(d.nac)].join('');
    }

    function renderVahan(v) {
      return `
      <div class="scheme">
        <div class="scheme-header">1. Vahan Retail Cashback – October</div>
        ${conditionsBox('vahan')}
        <div class="scheme-body">
          <div class="metrics">
            ${metric('Target', v.tgt)}
            ${metric('Achievement', v.ach)}
            ${metric('Pendency', v.pend)}
            ${metric('Total Pipeline', v.pipe)}
            ${metric('Gap', v.gap)}
            ${metric('Current Earnings', v.cur, 'cur')}
            ${metric('Earning Potential', v.pot, 'cur')}
          </div>
        </div>
      </div>`;
    }

    function renderPP(p) {
      return `
      <div class="scheme">
        <div class="scheme-header">2. Maruti Power Performer 2.0</div>
        ${conditionsBox('pp')}
        <div class="scheme-body">
          <div class="section-title">Scheme Achievement</div>
          <div class="metrics">
            ${metric('All Model Retail Base (Sep–Dec)', p.base)}
            ${metric('Retail Required (@5% Growth)', p.req)}
            ${metric('Retail Achievement', p.ach)}
            ${metric('Gap', p.gap)}
          </div>
          <div class="section-title">Additional Earning Opportunity</div>
          <div class="metrics">
            ${metric('Petrol Retail (Q1 Avg)', p.pq1)}
            ${metric('Current Petrol Retails', p.pcur)}
            ${metric('Growth', p.pgr, 'pct')}
          </div>
          <div class="section-title">Earnings</div>
          <div class="metrics">
            ${metric('Earning Potential', p.pot, 'cur')}
            ${metric('Current Earnings', p.cur, 'cur')}
          </div>
        </div>
      </div>`;
    }

    function renderPSL(s) {
      return `
      <div class="scheme">
        <div class="scheme-header">3. Maruti Suzuki Premier League <span class="badge">Group: ${esc(fmt(s.grp))}</span></div>
        ${conditionsBox('psl')}
        <div class="scheme-body">
          <div class="metrics">
            ${metric('Dealer Group', s.grp, 'text')}
            ${metric('HO Ranking', s.rank, 'text')}
          </div>
          <div class="section-title">Super Qualifying Criteria</div>
          <div class="metrics">
            ${metric('Retail Base Sep–Nov', s.sb)}
            ${metric('Retail Achi', s.sa)}
            ${metric('Growth %', s.sg, 'pct')}
          </div>
          <div class="section-title">Ranking Condition 1 : Sept to Nov</div>
          <div class="metrics">
            ${metric('Petrol Base', s.pb)}
            ${metric('Petrol Retail', s.pr)}
            ${metric('Growth %', s.pgr, 'pct')}
          </div>
          <div class="section-title">Ranking Condition 2 : October</div>
          <div class="metrics">
            ${metric('Q1 Retail Base', s.qb)}
            ${metric('Achi', s.qa)}
            ${metric('Growth', s.qg, 'pct')}
          </div>
        </div>
      </div>`;
    }

    function renderNAC(n) {
      return `
      <div class="scheme">
        <div class="scheme-header">4. NEXA Achiever's Club</div>
        ${conditionsBox('nac')}
        <div class="scheme-body">
          <div class="section-title">Slab Achievement</div>
          <div class="metrics">
            ${metric('Retail Base (Excl. Ignis)', n.base)}
            ${metric('Retail Achievement', n.ach)}
            ${metric('Gap Sigma (₹900/Car)', n.g_sigma)}
            ${metric('Gap Delta (₹1,100/Car)', n.g_delta)}
            ${metric('Gap Zeta (₹1,400/Car)', n.g_zeta)}
            ${metric('Gap Alpha (₹1,800/Car)', n.g_alpha)}
          </div>
          <div class="section-title">Additional Earning Opportunity – October</div>
          <div class="metrics">
            ${metric('Q3 GV & EV Avg Retail', n.gvq3)}
            ${metric('Required Retail', n.req)}
            ${metric('Achi', n.gv_ach)}
            ${metric('Gap', n.gv_gap)}
          </div>
          <div class="section-title">Wholesale Achievement</div>
          <div class="metrics">
            ${metric('Target – October', n.wtgt)}
            ${metric('Achi', n.wach)}
            ${metric('Achi %', n.wpct, 'pct')}
          </div>
          <div class="section-title">Payout</div>
          <div class="metrics">
            ${metric('Current Earnings', n.cur, 'cur')}
            ${metric('Earning Potential', n.pot, 'cur')}
          </div>
        </div>
      </div>`;
    }
  </script>
</body>
</html>
