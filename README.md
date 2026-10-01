
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dealer Incentive Schemes Portal</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #0f172a;
      --primary-light: #1e293b;
      --accent: #2563eb;
      --accent-hover: #1d4ed8;
      --success: #16a34a;
      --success-bg: #dcfce7;
      --danger: #dc2626;
      --danger-bg: #fee2e2;
      --warning: #d97706;
      --warning-bg: #fef3c7;
      --bg: #f8fafc;
      --card: #ffffff;
      --border: #e2e8f0;
      --text-main: #0f172a;
      --text-muted: #64748b;
      --radius-lg: 12px;
      --radius-md: 8px;
      --shadow-sm: 0 1px 3px rgba(0,0,0,0.1);
      --shadow-md: 0 4px 6px -1px rgba(0,0,0,0.1), 0 2px 4px -1px rgba(0,0,0,0.06);
      --shadow-lg: 0 10px 15px -3px rgba(0,0,0,0.1), 0 4px 6px -2px rgba(0,0,0,0.05);
    }

    * { box-sizing: border-box; margin: 0; padding: 0; }
    
    body {
      font-family: 'Inter', sans-serif;
      background: var(--bg);
      color: var(--text-main);
      min-height: 100vh;
      line-height: 1.6;
      -webkit-font-smoothing: antialiased;
    }

    /* Top Navigation */
    .header {
      background: var(--primary);
      color: white;
      padding: 1rem 2rem;
      position: sticky;
      top: 0;
      z-index: 100;
      box-shadow: var(--shadow-md);
    }
    
    .header-content {
      max-width: 1200px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .header-branding h1 {
      font-size: 1.25rem;
      font-weight: 600;
      letter-spacing: -0.025em;
    }

    .header-branding p {
      color: #94a3b8;
      font-size: 0.875rem;
      margin-top: 0.25rem;
    }

    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 2rem 1rem;
    }

    /* Buttons & Forms */
    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      padding: 0.75rem 1.5rem;
      background: var(--accent);
      color: white;
      border: none;
      border-radius: var(--radius-md);
      font-size: 0.95rem;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.2s ease;
      box-shadow: var(--shadow-sm);
    }

    .btn:hover {
      background: var(--accent-hover);
      transform: translateY(-1px);
    }

    .btn-logout {
      background: transparent;
      border: 1px solid #334155;
      padding: 0.5rem 1rem;
      font-size: 0.875rem;
    }

    .btn-logout:hover {
      background: #1e293b;
      border-color: #475569;
    }

    /* Login Section */
    .login-card {
      background: var(--card);
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-lg);
      padding: 2.5rem;
      max-width: 400px;
      margin: 4rem auto;
      border: 1px solid var(--border);
    }

    .login-card h2 {
      text-align: center;
      margin-bottom: 2rem;
      color: var(--text-main);
      font-size: 1.5rem;
      font-weight: 700;
    }

    .form-group { margin-bottom: 1.5rem; }
    
    .form-group label {
      display: block;
      font-weight: 500;
      font-size: 0.875rem;
      margin-bottom: 0.5rem;
      color: var(--text-main);
    }

    .form-group input {
      width: 100%;
      padding: 0.75rem 1rem;
      border: 1px solid #cbd5e1;
      border-radius: var(--radius-md);
      font-size: 1rem;
      font-family: inherit;
      transition: all 0.2s;
      background: #f8fafc;
    }

    .form-group input:focus {
      outline: none;
      border-color: var(--accent);
      background: #ffffff;
      box-shadow: 0 0 0 4px rgba(37, 99, 235, 0.1);
    }

    .btn-block { width: 100%; margin-top: 0.5rem; }

    .error-msg {
      background: var(--danger-bg);
      color: var(--danger);
      padding: 1rem;
      border-radius: var(--radius-md);
      margin-bottom: 1.5rem;
      font-size: 0.875rem;
      font-weight: 500;
      display: none;
      border: 1px solid #fecaca;
    }

    /* Dashboard Layout */
    #dashboard { display: none; }
    
    .dealer-banner {
      background: linear-gradient(135deg, #1e293b 0%, #0f172a 100%);
      border-radius: var(--radius-lg);
      padding: 2rem;
      margin-bottom: 2rem;
      color: white;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: var(--shadow-md);
    }

    .dealer-banner h2 { font-size: 1.75rem; font-weight: 700; }
    .dealer-banner .code { 
      color: #94a3b8; 
      font-size: 1rem; 
      margin-top: 0.25rem;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }
    
    .dealer-banner .badge {
      background: rgba(255, 255, 255, 0.1);
      padding: 0.25rem 0.75rem;
      border-radius: 9999px;
      font-size: 0.75rem;
      font-weight: 600;
      letter-spacing: 0.05em;
    }

    /* Scheme Cards */
    .schemes-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 2rem;
    }

    .scheme-card {
      background: var(--card);
      border-radius: var(--radius-lg);
      box-shadow: var(--shadow-md);
      border: 1px solid var(--border);
      overflow: hidden;
      transition: transform 0.2s ease, box-shadow 0.2s ease;
    }

    .scheme-card:hover {
      box-shadow: var(--shadow-lg);
    }

    .scheme-header {
      background: #f1f5f9;
      padding: 1.25rem 1.5rem;
      border-bottom: 1px solid var(--border);
      display: flex;
      justify-content: space-between;
      align-items: center;
    }

    .scheme-header h3 {
      font-size: 1.125rem;
      font-weight: 700;
      color: var(--primary);
      display: flex;
      align-items: center;
      gap: 0.75rem;
    }

    .scheme-header h3::before {
      content: '';
      display: block;
      width: 4px;
      height: 1.25rem;
      background: var(--accent);
      border-radius: 4px;
    }

    .scheme-body { padding: 1.5rem; }

    /* Collapsible Conditions */
    details.conditions {
      background: #fffbeb;
      border-bottom: 1px solid #fde68a;
      padding: 1rem 1.5rem;
    }
    
    details.conditions summary {
      font-size: 0.875rem;
      font-weight: 600;
      color: #b45309;
      cursor: pointer;
      list-style: none;
      display: flex;
      align-items: center;
      gap: 0.5rem;
    }

    details.conditions summary::before {
      content: 'ℹ️';
      font-size: 1rem;
    }

    details.conditions ul {
      margin-top: 1rem;
      list-style: none;
      padding-left: 0;
    }

    details.conditions li {
      font-size: 0.875rem;
      color: #78350f;
      padding: 0.5rem 0 0.5rem 1.5rem;
      position: relative;
      border-top: 1px dashed #fcd34d;
    }

    details.conditions li:first-child { border-top: none; }
    
    details.conditions li::before {
      content: '•';
      position: absolute;
      left: 0.5rem;
      color: #d97706;
      font-weight: bold;
    }

    /* Metrics Grid */
    .section-title {
      font-size: 0.75rem;
      font-weight: 700;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.05em;
      margin: 1.5rem 0 1rem;
      border-bottom: 1px solid var(--border);
      padding-bottom: 0.5rem;
    }
    
    .section-title:first-child { margin-top: 0; }

    .metrics-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
      gap: 1rem;
    }

    .metric-box {
      background: #f8fafc;
      border: 1px solid var(--border);
      border-radius: var(--radius-md);
      padding: 1.25rem 1rem;
      display: flex;
      flex-direction: column;
      justify-content: center;
      transition: background 0.2s;
    }

    .metric-box:hover {
      background: #f1f5f9;
      border-color: #cbd5e1;
    }

    .metric-label {
      font-size: 0.75rem;
      font-weight: 600;
      color: var(--text-muted);
      margin-bottom: 0.5rem;
      line-height: 1.2;
    }

    .metric-value {
      font-size: 1.5rem;
      font-weight: 700;
      color: var(--text-main);
      letter-spacing: -0.025em;
    }

    /* Status Colors */
    .metric-value.positive { color: var(--success); }
    .metric-value.negative { color: var(--danger); }
    .metric-value.neutral { color: var(--warning); }
    .metric-value.cur { color: var(--accent); }
    .metric-value.text { font-size: 1.25rem; }

    @media (max-width: 768px) {
      .metrics-grid { grid-template-columns: repeat(2, 1fr); }
      .dealer-banner { flex-direction: column; align-items: flex-start; gap: 1rem; }
    }
    
    @media (max-width: 480px) {
      .metrics-grid { grid-template-columns: 1fr; }
      .login-card { padding: 1.5rem; margin: 2rem 1rem; }
    }
  </style>
</head>
<body>

  <!-- Header -->
  <header class="header">
    <div class="header-content">
      <div class="header-branding">
        <h1>Dealer Incentive Schemes</h1>
        <p>Performance & Earnings Dashboard</p>
      </div>
      <button id="logoutBtn" class="btn btn-logout" style="display:none;" onclick="logout()">
        Sign Out
      </button>
    </div>
  </header>

  <main class="container">
    
    <!-- Login Section -->
    <div id="loginSection">
      <div class="login-card">
        <h2>Dealer Portal Access</h2>
        <div id="errorMsg" class="error-msg"></div>
        <form id="loginForm" onsubmit="return handleLogin(event)">
          <div class="form-group">
            <label for="dealerCode">Dealer Code</label>
            <input type="text" id="dealerCode" placeholder="Enter your Dealer Code" required autocomplete="username">
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input type="password" id="password" placeholder="Enter your password" required autocomplete="current-password">
          </div>
          <button type="submit" class="btn btn-block">Access Dashboard</button>
        </form>
      </div>
    </div>

    <!-- Dashboard Section -->
    <div id="dashboard">
      <div class="dealer-banner">
        <div>
          <h2 id="dealerName">—</h2>
          <div class="code">
            <span class="badge">DEALER CODE</span>
            <span id="dealerCodeDisplay">—</span>
          </div>
        </div>
      </div>
      
      <!-- Schemes Container -->
      <div id="schemesContainer" class="schemes-grid"></div>
    </div>

  </main>

  <script>
    // ========== DEALER DATA ==========
    const DEALERS = {
      "G1NA": {
        "code": "G1NA", "password": "G1NAAdinath", "name": "Adinath",
        "vahan": { "tgt": 145, "ach": 68, "pend": 12, "pipe": 80, "gap": 65, "cur": 204000, "pot": 435000 },
        "pp": { "base": 537, "req": 564, "ach": 66, "gap": 498, "pq1": 87, "pcur": 54, "pgr": -0.3793, "pot": 1269000, "cur": 148500 },
        "psl": { "grp": "B", "rank": "-", "sb": 383, "sa": 66, "sg": -0.8277, "pb": 322, "pr": 54, "pgr": -0.8323, "qb": 110, "qa": 66, "qg": -0.4 },
        "nac": { "base": 422, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 452, "gvq3": 19, "req": 24, "gv_ach": null, "gv_gap": 24, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "D7NA": {
        "code": "D7NA", "password": "D7NACity", "name": "City Cars",
        "vahan": { "tgt": 165, "ach": 70, "pend": 37, "pipe": 107, "gap": 58, "cur": 210000, "pot": 495000 },
        "pp": { "base": 715, "req": 751, "ach": 87, "gap": 664, "pq1": 109, "pcur": 68, "pgr": -0.3761, "pot": 1689750, "cur": 195750 },
        "psl": { "grp": "B", "rank": "-", "sb": 470, "sa": 87, "sg": -0.8149, "pb": 411, "pr": 68, "pgr": -0.8345, "qb": 134, "qa": 87, "qg": -0.3507 },
        "nac": { "base": 559, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 599, "gvq3": 26, "req": 33, "gv_ach": null, "gv_gap": 33, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "KMNA": {
        "code": "KMNA", "password": "KMNAInfinity", "name": "Infinity",
        "vahan": { "tgt": 35, "ach": 26, "pend": 8, "pipe": 34, "gap": 1, "cur": 78000, "pot": 105000 },
        "pp": { "base": 170, "req": 179, "ach": 31, "gap": 148, "pq1": 23, "pcur": 25, "pgr": 0.087, "pot": 402750, "cur": 69750 },
        "psl": { "grp": "D", "rank": "-", "sb": 131, "sa": 31, "sg": -0.7634, "pb": 108, "pr": 25, "pgr": -0.7685, "qb": 30, "qa": 31, "qg": 0.0333 },
        "nac": { "base": 133, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 143, "gvq3": 4, "req": 5, "gv_ach": null, "gv_gap": 5, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "03NB": {
        "code": "03NB", "password": "03NBJeewan", "name": "Jeewan",
        "vahan": { "tgt": 100, "ach": 47, "pend": 13, "pipe": 60, "gap": 40, "cur": 141000, "pot": 300000 },
        "pp": { "base": 768, "req": 806, "ach": 56, "gap": 750, "pq1": 56, "pcur": 33, "pgr": -0.4107, "pot": 1813500, "cur": 126000 },
        "psl": { "grp": "B", "rank": "-", "sb": 633, "sa": 56, "sg": -0.9115, "pb": 426, "pr": 33, "pgr": -0.9225, "qb": 94, "qa": 56, "qg": -0.4043 },
        "nac": { "base": 593, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 635, "gvq3": 20, "req": 25, "gv_ach": null, "gv_gap": 25, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "U5NA": {
        "code": "U5NA", "password": "U5NAKamthi", "name": "Kamthi Motors",
        "vahan": { "tgt": 105, "ach": 58, "pend": 17, "pipe": 75, "gap": 30, "cur": 174000, "pot": 315000 },
        "pp": { "base": 493, "req": 518, "ach": 69, "gap": 449, "pq1": 74, "pcur": 65, "pgr": -0.1216, "pot": 1165500, "cur": 155250 },
        "psl": { "grp": "C", "rank": "-", "sb": 347, "sa": 69, "sg": -0.8012, "pb": 338, "pr": 65, "pgr": -0.8077, "qb": 79, "qa": 69, "qg": -0.1266 },
        "nac": { "base": 376, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 403, "gvq3": 19, "req": 24, "gv_ach": null, "gv_gap": 24, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NE": {
        "code": "53NE", "password": "53NEKTL", "name": "KTL",
        "vahan": { "tgt": 175, "ach": 103, "pend": 38, "pipe": 141, "gap": 34, "cur": 309000, "pot": 525000 },
        "pp": { "base": 409, "req": 429, "ach": 125, "gap": 304, "pq1": 70, "pcur": 52, "pgr": -0.2571, "pot": 965250, "cur": 281250 },
        "psl": { "grp": "National A", "rank": "-", "sb": 199, "sa": 125, "sg": -0.3719, "pb": 117, "pr": 52, "pgr": -0.5556, "qb": 122, "qa": 125, "qg": 0.0246 },
        "nac": { "base": 405, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 434, "gvq3": 15, "req": 19, "gv_ach": null, "gv_gap": 19, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "30NB": {
        "code": "30NB", "password": "30NBNikunj", "name": "Nikunj",
        "vahan": { "tgt": 110, "ach": 45, "pend": 41, "pipe": 86, "gap": 24, "cur": 135000, "pot": 330000 },
        "pp": { "base": 360, "req": 378, "ach": 74, "gap": 304, "pq1": 38, "pcur": 32, "pgr": -0.1579, "pot": 850500, "cur": 166500 },
        "psl": { "grp": "B", "rank": "-", "sb": 272, "sa": 74, "sg": -0.7279, "pb": 168, "pr": 32, "pgr": -0.8095, "qb": 63, "qa": 74, "qg": 0.1746 },
        "nac": { "base": 284, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 304, "gvq3": 11, "req": 14, "gv_ach": null, "gv_gap": 14, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "AUNA": {
        "code": "AUNA", "password": "AUNANimar", "name": "Nimar Motors",
        "vahan": { "tgt": 80, "ach": 56, "pend": 19, "pipe": 75, "gap": 5, "cur": 168000, "pot": 240000 },
        "pp": { "base": 478, "req": 502, "ach": 75, "gap": 427, "pq1": 43, "pcur": 46, "pgr": 0.0698, "pot": 1129500, "cur": 168750 },
        "psl": { "grp": "B", "rank": "-", "sb": 336, "sa": 75, "sg": -0.7768, "pb": 250, "pr": 46, "pgr": -0.816, "qb": 59, "qa": 75, "qg": 0.2712 },
        "nac": { "base": 369, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 395, "gvq3": 22, "req": 28, "gv_ach": null, "gv_gap": 28, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NB": {
        "code": "53NB", "password": "53NBOcean", "name": "Ocean Group",
        "vahan": { "tgt": 305, "ach": 173, "pend": 78, "pipe": 251, "gap": 54, "cur": 519000, "pot": 915000 },
        "pp": { "base": 1489, "req": 1563, "ach": 229, "gap": 1334, "pq1": 125, "pcur": 110, "pgr": -0.12, "pot": 3516750, "cur": 515250 },
        "psl": { "grp": "A", "rank": "-", "sb": 985, "sa": 229, "sg": -0.7675, "pb": 631, "pr": 110, "pgr": -0.8257, "qb": 225, "qa": 229, "qg": 0.0178 },
        "nac": { "base": 1146, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 1227, "gvq3": 80, "req": 100, "gv_ach": null, "gv_gap": 100, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NA": {
        "code": "53NA", "password": "53NAPatel", "name": "Patel Group",
        "vahan": { "tgt": 215, "ach": 114, "pend": 61, "pipe": 175, "gap": 40, "cur": 342000, "pot": 645000 },
        "pp": { "base": 923, "req": 969, "ach": 162, "gap": 807, "pq1": 98, "pcur": 102, "pgr": 0.0408, "pot": 2180250, "cur": 364500 },
        "psl": { "grp": "A", "rank": "-", "sb": 649, "sa": 162, "sg": -0.7504, "pb": 480, "pr": 102, "pgr": -0.7875, "qb": 163, "qa": 162, "qg": -0.0061 },
        "nac": { "base": 680, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 728, "gvq3": 34, "req": 43, "gv_ach": null, "gv_gap": 43, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "30NA": {
        "code": "30NA", "password": "30NAPrem", "name": "Prem Group",
        "vahan": { "tgt": 195, "ach": 116, "pend": 26, "pipe": 142, "gap": 53, "cur": 348000, "pot": 585000 },
        "pp": { "base": 542, "req": 569, "ach": 132, "gap": 437, "pq1": 78, "pcur": 47, "pgr": -0.3974, "pot": 1280250, "cur": 297000 },
        "psl": { "grp": "National A", "rank": "-", "sb": 485, "sa": 132, "sg": -0.7278, "pb": 294, "pr": 47, "pgr": -0.8401, "qb": 148, "qa": 132, "qg": -0.1081 },
        "nac": { "base": 384, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 411, "gvq3": 15, "req": 19, "gv_ach": null, "gv_gap": 19, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "03NC": {
        "code": "03NC", "password": "03NCRajrup", "name": "Rajrup",
        "vahan": { "tgt": 185, "ach": 118, "pend": 17, "pipe": 135, "gap": 50, "cur": 354000, "pot": 555000 },
        "pp": { "base": 949, "req": 996, "ach": 115, "gap": 881, "pq1": 80, "pcur": 55, "pgr": -0.3125, "pot": 2241000, "cur": 258750 },
        "psl": { "grp": "B", "rank": "-", "sb": 653, "sa": 115, "sg": -0.8239, "pb": 493, "pr": 55, "pgr": -0.8884, "qb": 129, "qa": 115, "qg": -0.1085 },
        "nac": { "base": 719, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 770, "gvq3": 42, "req": 53, "gv_ach": null, "gv_gap": 53, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "53NC": {
        "code": "53NC", "password": "53NCRukmani", "name": "Rukmani",
        "vahan": { "tgt": 170, "ach": 104, "pend": 55, "pipe": 159, "gap": 11, "cur": 312000, "pot": 510000 },
        "pp": { "base": 851, "req": 894, "ach": 124, "gap": 770, "pq1": 55, "pcur": 62, "pgr": 0.1273, "pot": 2011500, "cur": 279000 },
        "psl": { "grp": "A", "rank": "-", "sb": 645, "sa": 124, "sg": -0.8078, "pb": 442, "pr": 62, "pgr": -0.8597, "qb": 103, "qa": 124, "qg": 0.2039 },
        "nac": { "base": 643, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 689, "gvq3": 46, "req": 58, "gv_ach": null, "gv_gap": 58, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "54ND": {
        "code": "54ND", "password": "54NBShubh", "name": "Shubh",
        "vahan": { "tgt": 125, "ach": 80, "pend": 16, "pipe": 96, "gap": 29, "cur": 240000, "pot": 375000 },
        "pp": { "base": 588, "req": 617, "ach": 89, "gap": 528, "pq1": 90, "pcur": 79, "pgr": -0.1222, "pot": 1388250, "cur": 200250 },
        "psl": { "grp": "B", "rank": "-", "sb": 391, "sa": 89, "sg": -0.7724, "pb": 367, "pr": 79, "pgr": -0.7847, "qb": 100, "qa": 89, "qg": -0.11 },
        "nac": { "base": 468, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 501, "gvq3": 27, "req": 34, "gv_ach": null, "gv_gap": 34, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "54NC": {
        "code": "54NC", "password": "54NCStandard", "name": "Standard Group",
        "vahan": { "tgt": 200, "ach": 120, "pend": 34, "pipe": 154, "gap": 46, "cur": 360000, "pot": 600000 },
        "pp": { "base": 852, "req": 895, "ach": 135, "gap": 760, "pq1": 157, "pcur": 106, "pgr": -0.3248, "pot": 2013750, "cur": 303750 },
        "psl": { "grp": "B", "rank": "-", "sb": 600, "sa": 135, "sg": -0.775, "pb": 551, "pr": 106, "pgr": -0.8076, "qb": 178, "qa": 135, "qg": -0.2416 },
        "nac": { "base": 694, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 743, "gvq3": 43, "req": 54, "gv_ach": null, "gv_gap": 54, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "3QNB": {
        "code": "3QNB", "password": "3QNAUnitara", "name": "Unitara",
        "vahan": { "tgt": 40, "ach": 40, "pend": 4, "pipe": 44, "gap": -4, "cur": 120000, "pot": 120000 },
        "pp": { "base": 193, "req": 203, "ach": 36, "gap": 167, "pq1": 16, "pcur": 23, "pgr": 0.4375, "pot": 456750, "cur": 81000 },
        "psl": { "grp": "C", "rank": "-", "sb": 137, "sa": 36, "sg": -0.7372, "pb": 77, "pr": 23, "pgr": -0.7013, "qb": 38, "qa": 36, "qg": -0.0526 },
        "nac": { "base": 152, "ach": null, "g_sigma": 422, "g_delta": 431, "g_zeta": 439, "g_alpha": 163, "gvq3": 8, "req": 10, "gv_ach": null, "gv_gap": 10, "wtgt": null, "wach": null, "wpct": null, "cur": 0, "pot": 0 }
      },
      "3WNA": {
        "code": "3WNA", "password": "3WNAYug", "name": "Yug Cars",
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

    // ========== FORMATTING UTILS ==========
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
      if (type === 'cur') return 'cur';
      if (type === 'pct' && typeof v === 'number') return v > 0 ? 'positive' : (v < 0 ? 'negative' : '');
      return '';
    }

    function metric(label, value, type) {
      return `
        <div class="metric-box">
          <div class="metric-label">${label}</div>
          <div class="metric-value ${cls(value, type)}">${fmt(value, type)}</div>
        </div>
      `;
    }

    function esc(s) { 
      return String(s).replace(/&/g, '&amp;').replace(/</g, '&lt;').replace(/>/g, '&gt;'); 
    }

    function conditionsBox(key) {
      const items = CONDITIONS[key].map(c =>
        `<li>${c.label ? '<strong>' + esc(c.label) + ':</strong> ' : ''}${esc(c.text)}</li>`).join('');
      return `
        <details class="conditions">
          <summary>View Scheme Conditions</summary>
          <ul>${items}</ul>
        </details>
      `;
    }

    // ========== LOGIN & DASHBOARD LOGIC ==========
    function handleLogin(e) {
      e.preventDefault();
      const code = document.getElementById('dealerCode').value.trim().toUpperCase();
      const pwd = document.getElementById('password').value.trim();
      const err = document.getElementById('errorMsg');
      const dealer = DEALERS[code];
      
      if (!dealer || dealer.password !== pwd) {
        err.style.display = 'block';
        err.textContent = 'Invalid Dealer Code or Password. Please verify and try again.';
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
      document.getElementById('logoutBtn').style.display = 'inline-flex';
      
      document.getElementById('dealerName').textContent = d.name;
      document.getElementById('dealerCodeDisplay').textContent = d.code;
      document.getElementById('schemesContainer').innerHTML = renderAllSchemes(d);
      
      window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // ========== RENDER SCHEMES HTML ==========
    function renderAllSchemes(d) {
      return [
        renderVahan(d.vahan), 
        renderPP(d.pp), 
        renderPSL(d.psl), 
        renderNAC(d.nac)
      ].join('');
    }

    function renderVahan(v) {
      return `
      <div class="scheme-card">
        <div class="scheme-header">
          <h3>1. Vahan Retail Cashback – October</h3>
        </div>
        ${conditionsBox('vahan')}
        <div class="scheme-body">
          <div class="metrics-grid">
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
      <div class="scheme-card">
        <div class="scheme-header">
          <h3>2. Maruti Power Performer 2.0</h3>
        </div>
        ${conditionsBox('pp')}
        <div class="scheme-body">
          <div class="section-title">Scheme Achievement</div>
          <div class="metrics-grid">
            ${metric('Base (Sep–Dec)', p.base)}
            ${metric('Required (@5% Gr)', p.req)}
            ${metric('Achievement', p.ach)}
            ${metric('Gap', p.gap)}
          </div>
          
          <div class="section-title">Additional Earning Opportunity</div>
          <div class="metrics-grid">
            ${metric('Petrol Retail (Q1 Avg)', p.pq1)}
            ${metric('Current Petrol Retails', p.pcur)}
            ${metric('Growth', p.pgr, 'pct')}
          </div>
          
          <div class="section-title">Earnings Breakdown</div>
          <div class="metrics-grid">
            ${metric('Current Earnings', p.cur, 'cur')}
            ${metric('Earning Potential', p.pot, 'cur')}
          </div>
        </div>
      </div>`;
    }

    function renderPSL(s) {
      return `
      <div class="scheme-card">
        <div class="scheme-header">
          <h3>3. Maruti Suzuki Premier League</h3>
        </div>
        ${conditionsBox('psl')}
        <div class="scheme-body">
          <div class="metrics-grid" style="margin-bottom: 1.5rem;">
            ${metric('Dealer Group', s.grp, 'text')}
            ${metric('HO Ranking', s.rank, 'text')}
          </div>
          
          <div class="section-title">Super Qualifying Criteria</div>
          <div class="metrics-grid">
            ${metric('Retail Base (Sep–Nov)', s.sb)}
            ${metric('Retail Achi', s.sa)}
            ${metric('Growth %', s.sg, 'pct')}
          </div>
          
          <div class="section-title">Ranking Condition 1: Sept to Nov</div>
          <div class="metrics-grid">
            ${metric('Petrol Base', s.pb)}
            ${metric('Petrol Retail', s.pr)}
            ${metric('Growth %', s.pgr, 'pct')}
          </div>
          
          <div class="section-title">Ranking Condition 2: October</div>
          <div class="metrics-grid">
            ${metric('Q1 Retail Base', s.qb)}
            ${metric('Achievement', s.qa)}
            ${metric('Growth %', s.qg, 'pct')}
          </div>
        </div>
      </div>`;
    }

    function renderNAC(n) {
      return `
      <div class="scheme-card">
        <div class="scheme-header">
          <h3>4. NEXA Achiever's Club</h3>
        </div>
        ${conditionsBox('nac')}
        <div class="scheme-body">
          <div class="section-title">Slab Achievement</div>
          <div class="metrics-grid">
            ${metric('Base (Excl. Ignis)', n.base)}
            ${metric('Achievement', n.ach)}
            ${metric('Gap Sigma (₹900)', n.g_sigma)}
            ${metric('Gap Delta (₹1.1k)', n.g_delta)}
            ${metric('Gap Zeta (₹1.4k)', n.g_zeta)}
            ${metric('Gap Alpha (₹1.8k)', n.g_alpha)}
          </div>
          
          <div class="section-title">Additional Opportunity – October</div>
          <div class="metrics-grid">
            ${metric('Q3 GV & EV Avg', n.gvq3)}
            ${metric('Required Retail', n.req)}
            ${metric('Achievement', n.gv_ach)}
            ${metric('Gap', n.gv_gap)}
          </div>
          
          <div class="section-title">Wholesale Achievement & Payout</div>
          <div class="metrics-grid">
            ${metric('Target – Oct', n.wtgt)}
            ${metric('Achievement', n.wach)}
            ${metric('Current Earnings', n.cur, 'cur')}
            ${metric('Earning Potential', n.pot, 'cur')}
          </div>
        </div>
      </div>`;
    }
  </script>
</body>
</html>
