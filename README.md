
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <title>Dealer Incentive Schemes Portal</title>
  <style>
    :root {
      --primary: #1a365d;
      --primary-light: #2b6cb0;
      --accent: #ed8936;
      --success: #38a169;
      --danger: #e53e3e;
      --warning: #d69e2e;
      --bg: #f7fafc;
      --card: #ffffff;
      --border: #e2e8f0;
      --text: #2d3748;
      --muted: #718096;
    }
    * { box-sizing: border-box; margin: 0; padding: 0; }
    body {
      font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
    }
    
    /* Header Structure */
    .header {
      background: linear-gradient(135deg, var(--primary), var(--primary-light));
      color: white;
      padding: 1.25rem 1.5rem;
      box-shadow: 0 2px 8px rgba(0,0,0,0.15);
      position: sticky;
      top: 0;
      z-index: 10;
    }
    .header-content {
      max-width: 960px;
      margin: 0 auto;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 1rem;
    }
    .header h1 { font-size: 1.4rem; font-weight: 600; line-height: 1.2; }
    .header p { opacity: 0.9; font-size: 0.9rem; margin-top: 0.35rem; }
    .container { max-width: 960px; margin: 0 auto; padding: 1.5rem 1rem; }
    
    /* Login */
    .login-card {
      background: var(--card);
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.08);
      padding: 2.5rem 2rem;
      max-width: 420px;
      margin: 3rem auto;
    }
    .login-card h2 {
      text-align: center;
      margin-bottom: 1.5rem;
      color: var(--primary);
      font-size: 1.5rem;
    }
    .form-group { margin-bottom: 1.25rem; }
    .form-group label {
      display: block;
      font-weight: 600;
      font-size: 0.875rem;
      margin-bottom: 0.5rem;
      color: var(--text);
    }
    .form-group input {
      width: 100%;
      padding: 0.85rem 1rem; /* Better touch targets */
      border: 1.5px solid var(--border);
      border-radius: 8px;
      font-size: 1rem;
      transition: border-color 0.2s;
      appearance: none; /* Removes default iOS styling */
    }
    .form-group input:focus {
      outline: none;
      border-color: var(--primary-light);
      box-shadow: 0 0 0 3px rgba(43,108,176,0.15);
    }
    .btn {
      display: inline-block;
      width: 100%;
      padding: 1rem; /* Improved touch target for mobile */
      background: var(--primary);
      color: white;
      border: none;
      border-radius: 8px;
      font-size: 1rem;
      font-weight: 600;
      cursor: pointer;
      transition: background 0.2s;
      text-align: center;
    }
    .btn:hover { background: var(--primary-light); }
    .btn-logout {
      width: auto;
      padding: 0.6rem 1.2rem;
      font-size: 0.9rem;
      background: rgba(255,255,255,0.2);
    }
    .btn-logout:hover { background: rgba(255,255,255,0.3); }
    .error-msg {
      background: #fed7d7;
      color: var(--danger);
      padding: 0.85rem;
      border-radius: 8px;
      margin-bottom: 1.2rem;
      font-size: 0.9rem;
      display: none;
      text-align: center;
    }
    
    /* Dashboard */
    #dashboard { display: none; }
    .dealer-info {
      background: var(--card);
      border-radius: 12px;
      padding: 1.25rem 1.5rem;
      margin-bottom: 1.5rem;
      box-shadow: 0 2px 8px rgba(0,0,0,0.06);
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 0.75rem;
    }
    .dealer-info h2 { font-size: 1.35rem; color: var(--primary); }
    .dealer-info .code { color: var(--muted); font-size: 0.95rem; margin-top: 0.2rem;}
    
    /* Scheme cards */
    .scheme {
      background: var(--card);
      border-radius: 12px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.06);
      margin-bottom: 1.5rem;
      overflow: hidden;
    }
    .scheme-header {
      background: linear-gradient(135deg, var(--primary), #2c5282);
      color: white;
      padding: 1rem 1.25rem;
      font-size: 1.05rem;
      font-weight: 600;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 0.75rem;
    }
    .scheme-header .badge {
      background: rgba(255,255,255,0.2);
      padding: 0.35rem 0.85rem;
      border-radius: 20px;
      font-size: 0.75rem;
      font-weight: 600;
      white-space: nowrap;
    }
    .scheme-body { padding: 1.25rem; }
    
    .metrics {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
      gap: 1rem;
      margin-bottom: 1rem;
    }
    .metric {
      background: #f8fafc;
      border: 1px solid var(--border);
      border-radius: 8px;
      padding: 1rem 0.85rem;
      text-align: center;
    }
    .metric .label {
      font-size: 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.03em;
      color: var(--muted);
      margin-bottom: 0.4rem;
      font-weight: 600;
    }
    .metric .value {
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--primary);
      word-break: break-word; /* Prevents overflow of large numbers */
    }
    .metric .value.positive { color: var(--success); }
    .metric .value.negative { color: var(--danger); }
    .metric .value.neutral { color: var(--warning); }
    
    .section-title {
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--muted);
      margin: 1.25rem 0 0.75rem;
      text-transform: uppercase;
      letter-spacing: 0.04em;
    }
    .status-yes { color: var(--success); font-weight: 700; }
    .status-no { color: var(--danger); font-weight: 700; }
    
    .note {
      font-size: 0.85rem;
      color: var(--muted);
      margin-top: 1rem;
      padding-top: 1rem;
      border-top: 1px dashed var(--border);
    }
    
    /* =============== MOBILE RESPONSIVE TWEAKS =============== */
    @media (max-width: 600px) {
      .header {
        padding: 1rem;
      }
      .header h1 {
        font-size: 1.2rem;
      }
      .container {
        padding: 1rem 0.5rem;
      }
      
      /* Login tweaks */
      .login-card {
        margin: 1rem auto;
        padding: 1.75rem 1.25rem;
      }
      
      /* Dashboard header tweaks */
      .dealer-info {
        flex-direction: column; 
        align-items: flex-start;
        padding: 1rem;
      }
      .header-content {
        flex-direction: column;
        align-items: flex-start;
      }
      .btn-logout {
        width: 100%; /* Make logout full width on mobile for easy tapping */
        text-align: center;
      }
      
      /* Scheme Cards Tweaks */
      .scheme-header {
        flex-direction: column;
        align-items: flex-start;
      }
      .scheme-body {
        padding: 1rem;
      }
      
      /* Metrics layout for mobile */
      .metrics { 
        grid-template-columns: repeat(2, 1fr); 
        gap: 0.75rem;
      }
      .metric {
        padding: 0.85rem 0.5rem;
      }
      .metric .value {
        font-size: 1.15rem;
      }
    }

    /* Very small screens (e.g. iPhone SE, older Androids) */
    @media (max-width: 380px) {
      .metrics {
        grid-template-columns: 1fr; /* Stack into a single column */
      }
    }
  </style>
</head>
<body>
  <div class="header">
    <div class="header-content">
      <div>
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
        <div id="errorMsg" class="error-msg"></div>
        <form id="loginForm" onsubmit="return handleLogin(event)">
          <div class="form-group">
            <label for="dealerCode">Dealer Code</label>
            <input type="text" id="dealerCode" placeholder="e.g. G1NA" required autocomplete="username">
          </div>
          <div class="form-group">
            <label for="password">Password</label>
            <input type="password" id="password" placeholder="Enter password" required autocomplete="current-password">
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
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 17, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 2, "retail_pct": 0},
    "elevate": {"base": 76, "bi_jul": 42, "bi_aug": 27, "bi_sep": 1, "bi_ach": 70, "gap_bi_0": 6, "gap_bi_02": 8, "gap_bi_04": 10, "gap_bi_06": 11, "gr_bi": -0.0789, "dms_jul": 38, "dms_aug": 31, "dms_sep": 0, "dms_ach": 69, "gap_dms_0": 7, "gap_dms_02": 9, "gap_dms_04": 11, "gap_dms_06": 12, "gr_dms": -0.0921, "retail_base_bi": 225, "jul_bi": 110, "aug_bi": 96, "sep_bi": 2, "total_bi": 208, "growth_bi": -0.0756, "jul_dms": 100, "aug_dms": 89, "sep_dms": 0, "total_dms": 189, "growth_dms": -0.16, "incremental": 0.0679, "earning": 0},
    "nac": {"ret_base": 235, "jul_ach": 100, "aug_ach": 90, "sep_ach": 0, "total_ach": 190, "gap_02": 92, "gap_022": 97, "gap_025": 104, "gap_028": 111, "gv_base_q1": 21, "gv_base_aug": 5, "jul_ret": 13, "aug_ret": 7, "sep_ret": 0, "q2_ach": 20, "gr": -0.0476, "earning": 441000},
    "michelin": {"avg_retail": 4079, "category": "Michelin Gold", "ytd_cy": 184, "ytd_ly": 132, "growth": 0.3939, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 81, "aug_vahan": 44, "sep_vahan": 84, "jun_vahan": 59, "lm_vahan_tgt": 105, "vahan_ach_jul": 112, "gap": -7}
  },
  "D7NA": {
    "code": "D7NA",
    "password": "D7NACity",
    "name": "City",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 24, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 1, "gap": -1, "earning_top": 1500, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 9, "retail_pct": 0},
    "elevate": {"base": 143, "bi_jul": 53, "bi_aug": 39, "bi_sep": 5, "bi_ach": 97, "gap_bi_0": 46, "gap_bi_02": 49, "gap_bi_04": 52, "gap_bi_06": 55, "gr_bi": -0.3217, "dms_jul": 31, "dms_aug": 29, "dms_sep": 0, "dms_ach": 60, "gap_dms_0": 83, "gap_dms_02": 86, "gap_dms_04": 89, "gap_dms_06": 92, "gr_dms": -0.5804, "retail_base_bi": 300, "jul_bi": 127, "aug_bi": 98, "sep_bi": 9, "total_bi": 234, "growth_bi": -0.22, "jul_dms": 89, "aug_dms": 84, "sep_dms": 0, "total_dms": 173, "growth_dms": -0.4233, "incremental": -0.1571, "earning": 0},
    "nac": {"ret_base": 309, "jul_ach": 89, "aug_ach": 84, "sep_ach": 0, "total_ach": 173, "gap_02": 198, "gap_022": 204, "gap_025": 214, "gap_028": 223, "gv_base_q1": 28, "gv_base_aug": 9, "jul_ret": 19, "aug_ret": 6, "sep_ret": 1, "q2_ach": 26, "gr": -0.0714, "earning": 495000},
    "michelin": {"avg_retail": 4551, "category": "Michelin Gold", "ytd_cy": 174, "ytd_ly": 186, "growth": -0.0645, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 88, "aug_vahan": 81, "sep_vahan": 106, "jun_vahan": 84, "lm_vahan_tgt": null, "vahan_ach_jul": 89, "gap": null}
  },
  "KMNA": {
    "code": "KMNA",
    "password": "KMNAInfinity",
    "name": "Infinity",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 7, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 2, "retail_pct": 0},
    "elevate": {"base": 32, "bi_jul": 15, "bi_aug": 6, "bi_sep": 1, "bi_ach": 22, "gap_bi_0": 10, "gap_bi_02": 11, "gap_bi_04": 12, "gap_bi_06": 12, "gr_bi": -0.3125, "dms_jul": 9, "dms_aug": 5, "dms_sep": 0, "dms_ach": 14, "gap_dms_0": 18, "gap_dms_02": 19, "gap_dms_04": 20, "gap_dms_06": 20, "gr_dms": -0.5625, "retail_base_bi": 74, "jul_bi": 30, "aug_bi": 20, "sep_bi": 2, "total_bi": 52, "growth_bi": -0.2973, "jul_dms": 25, "aug_dms": 20, "sep_dms": 0, "total_dms": 45, "growth_dms": -0.3919, "incremental": -0.1706, "earning": 0},
    "nac": {"ret_base": 75, "jul_ach": 25, "aug_ach": 20, "sep_ach": 0, "total_ach": 45, "gap_02": 45, "gap_022": 47, "gap_025": 49, "gap_028": 51, "gv_base_q1": 7, "gv_base_aug": 1, "jul_ret": 1, "aug_ret": 1, "sep_ret": 0, "q2_ach": 2, "gr": -0.7143, "earning": 108000},
    "michelin": {"avg_retail": 1162, "category": "Michelin Gold", "ytd_cy": 27, "ytd_ly": 41, "growth": -0.3415, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 9, "aug_vahan": 27, "sep_vahan": 31, "jun_vahan": 19, "lm_vahan_tgt": 24, "vahan_ach_jul": 22, "gap": 2}
  },
  "03NB": {
    "code": "03NB",
    "password": "03NBJeewan",
    "name": "Jeewan",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 14, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 1, "payout_base": 20000, "payout_top": 30000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 1, "gap": -1, "earning_top": 1500, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 6, "retail_pct": 0},
    "elevate": {"base": 142, "bi_jul": 19, "bi_aug": 23, "bi_sep": 2, "bi_ach": 44, "gap_bi_0": 98, "gap_bi_02": 101, "gap_bi_04": 104, "gap_bi_06": 107, "gr_bi": -0.6901, "dms_jul": 25, "dms_aug": 13, "dms_sep": 0, "dms_ach": 38, "gap_dms_0": 104, "gap_dms_02": 107, "gap_dms_04": 110, "gap_dms_06": 113, "gr_dms": -0.7324, "retail_base_bi": 323, "jul_bi": 80, "aug_bi": 55, "sep_bi": 4, "total_bi": 139, "growth_bi": -0.5697, "jul_dms": 77, "aug_dms": 44, "sep_dms": 0, "total_dms": 121, "growth_dms": -0.6254, "incremental": -0.107, "earning": 0},
    "nac": {"ret_base": 339, "jul_ach": 81, "aug_ach": 45, "sep_ach": 0, "total_ach": 126, "gap_02": 281, "gap_022": 288, "gap_025": 298, "gap_028": 308, "gv_base_q1": 49, "gv_base_aug": 11, "jul_ret": 10, "aug_ret": 6, "sep_ret": 1, "q2_ach": 17, "gr": -0.6531, "earning": 270000},
    "michelin": {"avg_retail": 4115, "category": "Michelin Gold", "ytd_cy": 120, "ytd_ly": 197, "growth": -0.3909, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 79, "aug_vahan": 103, "sep_vahan": 132, "jun_vahan": 77, "lm_vahan_tgt": 76, "vahan_ach_jul": 76, "gap": 0}
  },
  "U5NA": {
    "code": "U5NA",
    "password": "U5NAKamthi",
    "name": "Kamthi",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 19, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 4, "retail_pct": 0},
    "elevate": {"base": 68, "bi_jul": 16, "bi_aug": 16, "bi_sep": 1, "bi_ach": 33, "gap_bi_0": 35, "gap_bi_02": 37, "gap_bi_04": 38, "gap_bi_06": 40, "gr_bi": -0.5147, "dms_jul": 19, "dms_aug": 16, "dms_sep": 0, "dms_ach": 35, "gap_dms_0": 33, "gap_dms_02": 35, "gap_dms_04": 36, "gap_dms_06": 38, "gr_dms": -0.4853, "retail_base_bi": 240, "jul_bi": 80, "aug_bi": 70, "sep_bi": 4, "total_bi": 154, "growth_bi": -0.3583, "jul_dms": 77, "aug_dms": 63, "sep_dms": 0, "total_dms": 140, "growth_dms": -0.4167, "incremental": -0.0686, "earning": 0},
    "nac": {"ret_base": 246, "jul_ach": 78, "aug_ach": 63, "sep_ach": 0, "total_ach": 141, "gap_02": 155, "gap_022": 160, "gap_025": 167, "gap_028": 174, "gv_base_q1": 26, "gv_base_aug": 15, "jul_ret": 14, "aug_ret": 0, "sep_ret": 0, "q2_ach": 14, "gr": -0.4615, "earning": 291600},
    "michelin": {"avg_retail": 3185, "category": "Michelin Gold", "ytd_cy": 148, "ytd_ly": 141, "growth": 0.0496, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 63, "aug_vahan": 71, "sep_vahan": 82, "jun_vahan": 60, "lm_vahan_tgt": null, "vahan_ach_jul": 83, "gap": null}
  },
  "53NE": {
    "code": "53NE",
    "password": "53NEKTL",
    "name": "KTL",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 40, "all_model_ws_pct": 0, "gv_sigma_ws": 5, "gv_delta_ws": 11, "payout_base": 345000, "payout_top": 530000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 4, "gap": -4, "earning_top": 6000, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 10, "retail_pct": 0},
    "elevate": {"base": 0, "bi_jul": 53, "bi_aug": 48, "bi_sep": 6, "bi_ach": 107, "gap_bi_0": -107, "gap_bi_02": -107, "gap_bi_04": -107, "gap_bi_06": -107, "gr_bi": 0, "dms_jul": 56, "dms_aug": 40, "dms_sep": 0, "dms_ach": 96, "gap_dms_0": -96, "gap_dms_02": -96, "gap_dms_04": -96, "gap_dms_06": -96, "gr_dms": 0, "retail_base_bi": 0, "jul_bi": 144, "aug_bi": 136, "sep_bi": 10, "total_bi": 290, "growth_bi": null, "jul_dms": 144, "aug_dms": 128, "sep_dms": 0, "total_dms": 272, "growth_dms": 0, "incremental": 0, "earning": 0},
    "nac": {"ret_base": 0, "jul_ach": 145, "aug_ach": 128, "sep_ach": 0, "total_ach": 273, "gap_02": -273, "gap_022": -273, "gap_025": -273, "gap_028": -273, "gv_base_q1": 0, "gv_base_aug": 0, "jul_ret": 26, "aug_ret": 24, "sep_ret": 1, "q2_ach": 51, "gr": null, "earning": 639000},
    "michelin": {"avg_retail": 4372, "category": "Michelin Gold", "ytd_cy": 292, "ytd_ly": 0, "growth": 0, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 0, "aug_vahan": 0, "sep_vahan": 0, "jun_vahan": 0, "lm_vahan_tgt": 128, "vahan_ach_jul": 149, "gap": -21}
  },
  "30NB": {
    "code": "30NB",
    "password": "30NBNikunj",
    "name": "Nikunj",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 17, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 1, "payout_base": 20000, "payout_top": 30000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 2, "gap": -2, "earning_top": 3000, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 3, "retail_pct": 0},
    "elevate": {"base": 61, "bi_jul": 23, "bi_aug": 35, "bi_sep": 2, "bi_ach": 60, "gap_bi_0": 1, "gap_bi_02": 3, "gap_bi_04": 4, "gap_bi_06": 5, "gr_bi": -0.0164, "dms_jul": 20, "dms_aug": 30, "dms_sep": 0, "dms_ach": 50, "gap_dms_0": 11, "gap_dms_02": 13, "gap_dms_04": 14, "gap_dms_06": 15, "gr_dms": -0.1803, "retail_base_bi": 173, "jul_bi": 75, "aug_bi": 59, "sep_bi": 3, "total_bi": 137, "growth_bi": -0.2081, "jul_dms": 51, "aug_dms": 75, "sep_dms": 0, "total_dms": 126, "growth_dms": -0.2717, "incremental": 0.0913, "earning": 0},
    "nac": {"ret_base": 178, "jul_ach": 51, "aug_ach": 77, "sep_ach": 0, "total_ach": 128, "gap_02": 86, "gap_022": 90, "gap_025": 95, "gap_028": 100, "gv_base_q1": 28, "gv_base_aug": 4, "jul_ret": 4, "aug_ret": 6, "sep_ret": 1, "q2_ach": 11, "gr": -0.6071, "earning": 284400},
    "michelin": {"avg_retail": 5015, "category": "Michelin Gold", "ytd_cy": 136, "ytd_ly": 122, "growth": 0.1148, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 56, "aug_vahan": 58, "sep_vahan": 64, "jun_vahan": 49, "lm_vahan_tgt": 71, "vahan_ach_jul": 69, "gap": 2}
  },
  "AUNA": {
    "code": "AUNA",
    "password": "AUNANimar",
    "name": "Nimar",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 7, "all_model_ws_pct": 0, "gv_sigma_ws": 2, "gv_delta_ws": 1, "payout_base": 70000, "payout_top": 110000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 6, "retail_pct": 0},
    "elevate": {"base": 70, "bi_jul": 19, "bi_aug": 17, "bi_sep": 3, "bi_ach": 39, "gap_bi_0": 31, "gap_bi_02": 33, "gap_bi_04": 34, "gap_bi_06": 36, "gr_bi": -0.4429, "dms_jul": 20, "dms_aug": 14, "dms_sep": 0, "dms_ach": 34, "gap_dms_0": 36, "gap_dms_02": 38, "gap_dms_04": 39, "gap_dms_06": 41, "gr_dms": -0.5143, "retail_base_bi": 203, "jul_bi": 50, "aug_bi": 71, "sep_bi": 6, "total_bi": 127, "growth_bi": -0.3744, "jul_dms": 67, "aug_dms": 48, "sep_dms": 0, "total_dms": 115, "growth_dms": -0.4335, "incremental": -0.0808, "earning": 0},
    "nac": {"ret_base": 214, "jul_ach": 68, "aug_ach": 49, "sep_ach": 0, "total_ach": 117, "gap_02": 140, "gap_022": 145, "gap_025": 151, "gap_028": 157, "gv_base_q1": 33, "gv_base_aug": 7, "jul_ret": 12, "aug_ret": 11, "sep_ret": 0, "q2_ach": 23, "gr": -0.303, "earning": 246600},
    "michelin": {"avg_retail": 3998, "category": "Michelin Gold", "ytd_cy": 123, "ytd_ly": 122, "growth": 0.0082, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 65, "aug_vahan": 46, "sep_vahan": 93, "jun_vahan": 53, "lm_vahan_tgt": null, "vahan_ach_jul": 72, "gap": null}
  },
  "53NB": {
    "code": "53NB",
    "password": "53NBOcean",
    "name": "Ocean",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 34, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 1, "payout_base": 20000, "payout_top": 30000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 1, "gap_bi": 0, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 9, "gap": -9, "earning_top": 13500, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 17, "retail_pct": 0},
    "elevate": {"base": 340, "bi_jul": 91, "bi_aug": 80, "bi_sep": 11, "bi_ach": 182, "gap_bi_0": 158, "gap_bi_02": 165, "gap_bi_04": 172, "gap_bi_06": 179, "gr_bi": -0.4647, "dms_jul": 89, "dms_aug": 84, "dms_sep": 0, "dms_ach": 173, "gap_dms_0": 167, "gap_dms_02": 174, "gap_dms_04": 181, "gap_dms_06": 188, "gr_dms": -0.4912, "retail_base_bi": 719, "jul_bi": 224, "aug_bi": 199, "sep_bi": 17, "total_bi": 440, "growth_bi": -0.388, "jul_dms": 216, "aug_dms": 195, "sep_dms": 0, "total_dms": 411, "growth_dms": -0.4284, "incremental": -0.0628, "earning": 0},
    "nac": {"ret_base": 744, "jul_ach": 219, "aug_ach": 199, "sep_ach": 0, "total_ach": 418, "gap_02": 475, "gap_022": 490, "gap_025": 512, "gap_028": 535, "gv_base_q1": 99, "gv_base_aug": 43, "jul_ret": 53, "aug_ret": 41, "sep_ret": 1, "q2_ach": 95, "gr": -0.0404, "earning": 894600},
    "michelin": {"avg_retail": 7408, "category": "Michelin Platinum", "ytd_cy": 416, "ytd_ly": 491, "growth": -0.1527, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 228, "aug_vahan": 237, "sep_vahan": 255, "jun_vahan": 171, "lm_vahan_tgt": null, "vahan_ach_jul": 211, "gap": null}
  },
  "53NA": {
    "code": "53NA",
    "password": "53NAPatel",
    "name": "Patel",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 32, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 7, "retail_pct": 0},
    "elevate": {"base": 226, "bi_jul": 61, "bi_aug": 73, "bi_sep": 4, "bi_ach": 138, "gap_bi_0": 88, "gap_bi_02": 93, "gap_bi_04": 98, "gap_bi_06": 102, "gr_bi": -0.3894, "dms_jul": 62, "dms_aug": 62, "dms_sep": 0, "dms_ach": 124, "gap_dms_0": 102, "gap_dms_02": 107, "gap_dms_04": 112, "gap_dms_06": 116, "gr_dms": -0.4513, "retail_base_bi": 507, "jul_bi": 169, "aug_bi": 151, "sep_bi": 7, "total_bi": 327, "growth_bi": -0.355, "jul_dms": 163, "aug_dms": 132, "sep_dms": 0, "total_dms": 295, "growth_dms": -0.4181, "incremental": -0.0332, "earning": 0},
    "nac": {"ret_base": 526, "jul_ach": 165, "aug_ach": 132, "sep_ach": 0, "total_ach": 297, "gap_02": 335, "gap_022": 345, "gap_025": 361, "gap_028": 377, "gv_base_q1": 39, "gv_base_aug": 11, "jul_ret": 26, "aug_ret": 8, "sep_ret": 1, "q2_ach": 35, "gr": -0.1026, "earning": 693000},
    "michelin": {"avg_retail": 8333, "category": "Michelin Platinum", "ytd_cy": 280, "ytd_ly": 321, "growth": -0.1277, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 138, "aug_vahan": 156, "sep_vahan": 212, "jun_vahan": 106, "lm_vahan_tgt": null, "vahan_ach_jul": 163, "gap": null}
  },
  "30NA": {
    "code": "30NA",
    "password": "30NAPrem",
    "name": "Prem",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 38, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 4, "gap": -4, "earning_top": 6000, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 19, "retail_pct": 0},
    "elevate": {"base": 153, "bi_jul": 78, "bi_aug": 54, "bi_sep": 7, "bi_ach": 139, "gap_bi_0": 14, "gap_bi_02": 18, "gap_bi_04": 21, "gap_bi_06": 24, "gr_bi": -0.0915, "dms_jul": 75, "dms_aug": 48, "dms_sep": 0, "dms_ach": 123, "gap_dms_0": 30, "gap_dms_02": 34, "gap_dms_04": 37, "gap_dms_06": 40, "gr_dms": -0.1961, "retail_base_bi": 373, "jul_bi": 162, "aug_bi": 135, "sep_bi": 19, "total_bi": 316, "growth_bi": -0.1528, "jul_dms": 151, "aug_dms": 114, "sep_dms": 0, "total_dms": 265, "growth_dms": -0.2895, "incremental": 0.0935, "earning": 0},
    "nac": {"ret_base": 381, "jul_ach": 151, "aug_ach": 115, "sep_ach": 0, "total_ach": 266, "gap_02": 192, "gap_022": 199, "gap_025": 211, "gap_028": 222, "gv_base_q1": 34, "gv_base_aug": 14, "jul_ret": 20, "aug_ret": 19, "sep_ret": 0, "q2_ach": 39, "gr": 0.1471, "earning": 671400},
    "michelin": {"avg_retail": 8043, "category": "Michelin Platinum", "ytd_cy": 272, "ytd_ly": 235, "growth": 0.1574, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 108, "aug_vahan": 118, "sep_vahan": 135, "jun_vahan": 97, "lm_vahan_tgt": null, "vahan_ach_jul": 148, "gap": null}
  },
  "03NC": {
    "code": "03NC",
    "password": "03NCRajrup",
    "name": "Rajrup",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 26, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 6, "payout_base": 120000, "payout_top": 180000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 12, "gap": -12, "earning_top": 18000, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 3, "retail_pct": 0},
    "elevate": {"base": 153, "bi_jul": 37, "bi_aug": 54, "bi_sep": 2, "bi_ach": 93, "gap_bi_0": 60, "gap_bi_02": 64, "gap_bi_04": 67, "gap_bi_06": 70, "gr_bi": -0.3922, "dms_jul": 48, "dms_aug": 47, "dms_sep": 0, "dms_ach": 95, "gap_dms_0": 58, "gap_dms_02": 62, "gap_dms_04": 65, "gap_dms_06": 68, "gr_dms": -0.3791, "retail_base_bi": 406, "jul_bi": 98, "aug_bi": 124, "sep_bi": 3, "total_bi": 225, "growth_bi": -0.4458, "jul_dms": 107, "aug_dms": 114, "sep_dms": 0, "total_dms": 221, "growth_dms": -0.4557, "incremental": 0.0766, "earning": 0},
    "nac": {"ret_base": 434, "jul_ach": 108, "aug_ach": 115, "sep_ach": 0, "total_ach": 223, "gap_02": 298, "gap_022": 307, "gap_025": 320, "gap_028": 333, "gv_base_q1": 56, "gv_base_aug": 15, "jul_ret": 22, "aug_ret": 17, "sep_ret": 0, "q2_ach": 39, "gr": -0.3036, "earning": 489600},
    "michelin": {"avg_retail": 5184, "category": "Michelin Gold", "ytd_cy": 251, "ytd_ly": 223, "growth": 0.1256, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 99, "aug_vahan": 110, "sep_vahan": 155, "jun_vahan": 76, "lm_vahan_tgt": 119, "vahan_ach_jul": 126, "gap": -7}
  },
  "53ND": {
    "code": "53ND",
    "password": "53NDRana",
    "name": "Rana",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 0, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 0, "retail_pct": 0},
    "elevate": {"base": 81, "bi_jul": 0, "bi_aug": 0, "bi_sep": 0, "bi_ach": 0, "gap_bi_0": 81, "gap_bi_02": 83, "gap_bi_04": 85, "gap_bi_06": 86, "gr_bi": -1, "dms_jul": 0, "dms_aug": 0, "dms_sep": 0, "dms_ach": 0, "gap_dms_0": 81, "gap_dms_02": 83, "gap_dms_04": 85, "gap_dms_06": 86, "gr_dms": -1, "retail_base_bi": 170, "jul_bi": 0, "aug_bi": 0, "sep_bi": 0, "total_bi": 0, "growth_bi": -1, "jul_dms": 0, "aug_dms": 0, "sep_dms": 0, "total_dms": 0, "growth_dms": -1, "incremental": 0, "earning": 0},
    "nac": {"ret_base": 175, "jul_ach": 0, "aug_ach": 0, "sep_ach": 0, "total_ach": 0, "gap_02": 210, "gap_022": 214, "gap_025": 219, "gap_028": 224, "gv_base_q1": 16, "gv_base_aug": 2, "jul_ret": 0, "aug_ret": 0, "sep_ret": 0, "q2_ach": 0, "gr": -1, "earning": 0},
    "michelin": {"avg_retail": 1322, "category": "Michelin Gold", "ytd_cy": 0, "ytd_ly": 99, "growth": -1, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 58, "aug_vahan": 38, "sep_vahan": 68, "jun_vahan": 49, "lm_vahan_tgt": null, "vahan_ach_jul": 0, "gap": null}
  },
  "53NC": {
    "code": "53NC",
    "password": "53NCRukmani",
    "name": "Rukmani",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 19, "all_model_ws_pct": 0, "gv_sigma_ws": 3, "gv_delta_ws": 2, "payout_base": 115000, "payout_top": 180000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 5, "gap": -5, "earning_top": 7500, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 4, "retail_pct": 0},
    "elevate": {"base": 118, "bi_jul": 34, "bi_aug": 32, "bi_sep": 2, "bi_ach": 68, "gap_bi_0": 50, "gap_bi_02": 53, "gap_bi_04": 55, "gap_bi_06": 58, "gr_bi": -0.4237, "dms_jul": 46, "dms_aug": 35, "dms_sep": 0, "dms_ach": 81, "gap_dms_0": 37, "gap_dms_02": 40, "gap_dms_04": 42, "gap_dms_06": 45, "gr_dms": -0.3136, "retail_base_bi": 456, "jul_bi": 85, "aug_bi": 97, "sep_bi": 4, "total_bi": 186, "growth_bi": -0.5921, "jul_dms": 144, "aug_dms": 119, "sep_dms": 0, "total_dms": 263, "growth_dms": -0.4232, "incremental": 0.1097, "earning": 0},
    "nac": {"ret_base": 468, "jul_ach": 147, "aug_ach": 121, "sep_ach": 0, "total_ach": 268, "gap_02": 294, "gap_022": 303, "gap_025": 317, "gap_028": 332, "gv_base_q1": 98, "gv_base_aug": 44, "jul_ret": 16, "aug_ret": 19, "sep_ret": 1, "q2_ach": 36, "gr": -0.6327, "earning": 446400},
    "michelin": {"avg_retail": 6206, "category": "Michelin Platinum", "ytd_cy": 223, "ytd_ly": 303, "growth": -0.264, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 127, "aug_vahan": 149, "sep_vahan": 149, "jun_vahan": 95, "lm_vahan_tgt": 143, "vahan_ach_jul": 120, "gap": 23}
  },
  "54NB": {
    "code": "54NB",
    "password": "54NBShubh",
    "name": "Shubh",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 1, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 17, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 1, "gap_bi_09": -1, "gap_bi_095": 1, "gap_bi_1": -1, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 1, "gap": -1, "earning_top": 1500, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 2, "retail_pct": 0},
    "elevate": {"base": 108, "bi_jul": 29, "bi_aug": 32, "bi_sep": 1, "bi_ach": 62, "gap_bi_0": 46, "gap_bi_02": 49, "gap_bi_04": 51, "gap_bi_06": 53, "gr_bi": -0.4259, "dms_jul": 35, "dms_aug": 25, "dms_sep": 0, "dms_ach": 60, "gap_dms_0": 48, "gap_dms_02": 51, "gap_dms_04": 53, "gap_dms_06": 55, "gr_dms": -0.4444, "retail_base_bi": 256, "jul_bi": 76, "aug_bi": 96, "sep_bi": 2, "total_bi": 174, "growth_bi": -0.3203, "jul_dms": 98, "aug_dms": 78, "sep_dms": 0, "total_dms": 176, "growth_dms": -0.3125, "incremental": -0.1319, "earning": 0},
    "nac": {"ret_base": 262, "jul_ach": 98, "aug_ach": 78, "sep_ach": 0, "total_ach": 176, "gap_02": 139, "gap_022": 144, "gap_025": 152, "gap_028": 160, "gv_base_q1": 52, "gv_base_aug": 16, "jul_ret": 11, "aug_ret": 15, "sep_ret": 1, "q2_ach": 27, "gr": -0.4808, "earning": 394200},
    "michelin": {"avg_retail": 4759, "category": "Michelin Gold", "ytd_cy": 176, "ytd_ly": 169, "growth": 0.0414, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 96, "aug_vahan": 65, "sep_vahan": 89, "jun_vahan": 76, "lm_vahan_tgt": 86, "vahan_ach_jul": 98, "gap": -12}
  },
  "54NC": {
    "code": "54NC",
    "password": "54NCStandard",
    "name": "Standard",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 25, "all_model_ws_pct": 0, "gv_sigma_ws": 5, "gv_delta_ws": 0, "payout_base": 125000, "payout_top": 200000},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 3, "gap": -3, "earning_top": 4500, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 6, "retail_pct": 0},
    "elevate": {"base": 152, "bi_jul": 57, "bi_aug": 47, "bi_sep": 4, "bi_ach": 108, "gap_bi_0": 44, "gap_bi_02": 48, "gap_bi_04": 51, "gap_bi_06": 54, "gr_bi": -0.2895, "dms_jul": 43, "dms_aug": 39, "dms_sep": 0, "dms_ach": 82, "gap_dms_0": 70, "gap_dms_02": 74, "gap_dms_04": 77, "gap_dms_06": 80, "gr_dms": -0.4605, "retail_base_bi": 354, "jul_bi": 162, "aug_bi": 129, "sep_bi": 6, "total_bi": 297, "growth_bi": -0.161, "jul_dms": 131, "aug_dms": 107, "sep_dms": 0, "total_dms": 238, "growth_dms": -0.3277, "incremental": -0.1328, "earning": 0},
    "nac": {"ret_base": 378, "jul_ach": 131, "aug_ach": 108, "sep_ach": 0, "total_ach": 239, "gap_02": 215, "gap_022": 223, "gap_025": 234, "gap_028": 245, "gv_base_q1": 66, "gv_base_aug": 13, "jul_ret": 22, "aug_ret": 24, "sep_ret": 0, "q2_ach": 46, "gr": -0.303, "earning": 610200},
    "michelin": {"avg_retail": 5343, "category": "Michelin Gold", "ytd_cy": 267, "ytd_ly": 274, "growth": -0.0255, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 144, "aug_vahan": 125, "sep_vahan": 117, "jun_vahan": 102, "lm_vahan_tgt": null, "vahan_ach_jul": 155, "gap": null}
  },
  "3QNA": {
    "code": "3QNA",
    "password": "3QNAUnitara",
    "name": "Unitara",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 7, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 1, "retail_pct": 0},
    "elevate": {"base": 21, "bi_jul": 13, "bi_aug": 11, "bi_sep": 1, "bi_ach": 25, "gap_bi_0": -4, "gap_bi_02": -4, "gap_bi_04": -4, "gap_bi_06": -3, "gr_bi": 0.1905, "dms_jul": 14, "dms_aug": 9, "dms_sep": 0, "dms_ach": 23, "gap_dms_0": -2, "gap_dms_02": -2, "gap_dms_04": -2, "gap_dms_06": -1, "gr_dms": 0.0952, "retail_base_bi": 97, "jul_bi": 45, "aug_bi": 30, "sep_bi": 1, "total_bi": 76, "growth_bi": -0.2165, "jul_dms": 34, "aug_dms": 25, "sep_dms": 0, "total_dms": 59, "growth_dms": -0.3918, "incremental": 0.487, "earning": 0},
    "nac": {"ret_base": 99, "jul_ach": 34, "aug_ach": 25, "sep_ach": 0, "total_ach": 59, "gap_02": 60, "gap_022": 62, "gap_025": 65, "gap_028": 68, "gv_base_q1": 8, "gv_base_aug": 3, "jul_ret": 6, "aug_ret": 4, "sep_ret": 0, "q2_ach": 10, "gr": 0.25, "earning": 136800},
    "michelin": {"avg_retail": 2874, "category": "Michelin Gold", "ytd_cy": 65, "ytd_ly": 77, "growth": -0.1558, "ro_vahan_grw": 0.0072, "qualification": "NO", "jul_vahan": 29, "aug_vahan": 27, "sep_vahan": 32, "jun_vahan": 31, "lm_vahan_tgt": 43, "vahan_ach_jul": 37, "gap": 6}
  },
  "3WNA": {
    "code": "3WNA",
    "password": "3WNAYug",
    "name": "Yug",
    "wtd": {"gv_retail_target": null, "gv_retail_ach": 0, "gv_retail_pct": 0, "all_model_ws_target": null, "all_model_ws_ach": 4, "all_model_ws_pct": 0, "gv_sigma_ws": 0, "gv_delta_ws": 0, "payout_base": 0, "payout_top": 0},
    "hybrid": {"ret_tgt": 1, "ach_net_bi": 0, "gap_bi": 1, "ach_dms": 0, "gap_dms": 1, "earning": 0, "ws_ach_pct": 0},
    "mega": {"ret_tgt": null, "ach_net_bi": 0, "gap_bi_09": 0, "gap_bi_095": 0, "gap_bi_1": 0, "ach_dms": 0, "gap_dms_09": 0, "gap_dms_095": 0, "gap_dms_1": 0, "strong_hybrid": 0, "invicto": 0, "xl6": 0, "jimny": 0, "earning": 0},
    "vahan": {"tgt": null, "ach": 0, "gap": 0, "earning_top": 0, "vahan_ach_40": 0, "retail_tgt": null, "retail_ach": 1, "retail_pct": 0},
    "elevate": {"base": 53, "bi_jul": 17, "bi_aug": 12, "bi_sep": 1, "bi_ach": 30, "gap_bi_0": 23, "gap_bi_02": 25, "gap_bi_04": 26, "gap_bi_06": 27, "gr_bi": -0.434, "dms_jul": 19, "dms_aug": 13, "dms_sep": 0, "dms_ach": 32, "gap_dms_0": 21, "gap_dms_02": 23, "gap_dms_04": 24, "gap_dms_06": 25, "gr_dms": -0.3962, "retail_base_bi": 140, "jul_bi": 34, "aug_bi": 30, "sep_bi": 1, "total_bi": 65, "growth_bi": -0.5357, "jul_dms": 40, "aug_dms": 29, "sep_dms": 0, "total_dms": 69, "growth_dms": -0.5071, "incremental": 0.1109, "earning": 0},
    "nac": {"ret_base": 143, "jul_ach": 41, "aug_ach": 29, "sep_ach": 0, "total_ach": 70, "gap_02": 102, "gap_022": 105, "gap_025": 109, "gap_028": 114, "gv_base_q1": 8, "gv_base_aug": 1, "jul_ret": 6, "aug_ret": 0, "sep_ret": 0, "q2_ach": 6, "gr": -0.25, "earning": 126000},
    "michelin": {"avg_retail": 2821, "category": "Michelin Gold", "ytd_cy": 72, "ytd_ly": 70, "growth": 0.0286, "ro_vahan_grw": 0.0072, "qualification": "YES", "jul_vahan": 35, "aug_vahan": 31, "sep_vahan": 68, "jun_vahan": 30, "lm_vahan_tgt": null, "vahan_ach_jul": 43, "gap": null}
  }
};

    // ========== HELPERS ==========
    function fmt(v, isPct = false, isCurrency = false) {
      if (v === null || v === undefined || v === '' || v === '#N/A' || v === '#DIV/0!' || v === '#NA') return '—';
      if (typeof v === 'number') {
        if (isPct) return (v * 100).toFixed(1) + '%';
        if (isCurrency) return '₹' + v.toLocaleString('en-IN');
        if (Number.isInteger(v)) return v.toLocaleString('en-IN');
        return v.toFixed(2);
      }
      return v;
    }
    function cls(v) {
      if (v === null || v === undefined) return '';
      if (typeof v === 'number') {
        if (v > 0) return 'positive';
        if (v < 0) return 'negative';
      }
      return '';
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
      window.scrollTo(0,0);
    }

    function showDashboard(d) {
      document.getElementById('loginSection').style.display = 'none';
      document.getElementById('dashboard').style.display = 'block';
      document.getElementById('logoutBtn').style.display = 'inline-block';
      document.getElementById('dealerName').textContent = d.name;
      document.getElementById('dealerCodeDisplay').textContent = d.code;
      document.getElementById('schemesContainer').innerHTML = renderAllSchemes(d);
    }

    // ========== RENDER SCHEMES ==========
    function renderAllSchemes(d) {
      return [
        renderWTD(d.wtd),
        renderHybrid(d.hybrid),
        renderMega(d.mega),
        renderVahan(d.vahan),
        renderElevate(d.elevate),
        renderNAC(d.nac),
        renderMichelin(d.michelin)
      ].join('');
    }

    function metric(label, value, isPct, isCur) {
      return `<div class="metric"><div class="label">${label}</div><div class="value ${cls(value)}">${fmt(value, isPct, isCur)}</div></div>`;
    }

    function renderWTD(w) {
      return `
      <div class="scheme">
        <div class="scheme-header">1. Wholesale Trade Discount</div>
        <div class="scheme-body">
          <div class="section-title">GV Retail</div>
          <div class="metrics">
            ${metric('Target', w.gv_retail_target)}
            ${metric('Net BI Ach', w.gv_retail_ach)}
            ${metric('Ach %', w.gv_retail_pct, true)}
          </div>
          <div class="section-title">All Model Wholesale</div>
          <div class="metrics">
            ${metric('Target', w.all_model_ws_target)}
            ${metric('Achievement', w.all_model_ws_ach)}
            ${metric('Ach %', w.all_model_ws_pct, true)}
          </div>
          <div class="section-title">GV Sigma / Delta Wholesale &amp; Payout</div>
          <div class="metrics">
            ${metric('GV Sigma WS', w.gv_sigma_ws)}
            ${metric('GV Delta WS', w.gv_delta_ws)}
            ${metric('Base Slab Payout', w.payout_base, false, true)}
            ${metric('Top Slab Payout', w.payout_top, false, true)}
          </div>
        </div>
      </div>`;
    }

    function renderHybrid(h) {
      return `
      <div class="scheme">
        <div class="scheme-header">2. GV Strong Hybrid Super Cashback (Retail)</div>
        <div class="scheme-body">
          <div class="metrics">
            ${metric('Retail Target', h.ret_tgt)}
            ${metric('Ach (Net BI)', h.ach_net_bi)}
            ${metric('Gap BI', h.gap_bi)}
            ${metric('Ach (DMS)', h.ach_dms)}
            ${metric('Gap DMS', h.gap_dms)}
            ${metric('Earning', h.earning, false, true)}
            ${metric('WS Ach %', h.ws_ach_pct, true)}
          </div>
          <div class="note">Qualifying condition: 95% GV Wholesale Target Achievement. Payout on Strong Hybrid retails based on achievement slabs.</div>
        </div>
      </div>`;
    }

    function renderMega(m) {
      return `
      <div class="scheme">
        <div class="scheme-header">3. MEGA DEALER RETAIL INCENTIVE SCHEME</div>
        <div class="scheme-body">
          <div class="section-title">All Model Retail</div>
          <div class="metrics">
            ${metric('Retail Target', m.ret_tgt)}
            ${metric('Ach Net BI', m.ach_net_bi)}
            ${metric('Gap @90%', m.gap_bi_09)}
            ${metric('Gap @95%', m.gap_bi_095)}
            ${metric('Gap @100%', m.gap_bi_1)}
          </div>
          <div class="section-title">DMS Backed by MI</div>
          <div class="metrics">
            ${metric('Ach DMS', m.ach_dms)}
            ${metric('Gap @90%', m.gap_dms_09)}
            ${metric('Gap @95%', m.gap_dms_095)}
            ${metric('Gap @100%', m.gap_dms_1)}
          </div>
          <div class="section-title">Model-wise &amp; Earning</div>
          <div class="metrics">
            ${metric('Strong Hybrid', m.strong_hybrid)}
            ${metric('Invicto', m.invicto)}
            ${metric('XL6', m.xl6)}
            ${metric('Jimny', m.jimny)}
            ${metric('Earning', m.earning, false, true)}
          </div>
        </div>
      </div>`;
    }

    function renderVahan(v) {
      return `
      <div class="scheme">
        <div class="scheme-header">4. Sept Vahan Cashback</div>
        <div class="scheme-body">
          <div class="metrics">
            ${metric('Target', v.tgt)}
            ${metric('Achievement', v.ach)}
            ${metric('Gap', v.gap)}
            ${metric('Earning (Top Slab)', v.earning_top, false, true)}
            ${metric('Vahan Ach (Min 40%)', v.vahan_ach_40)}
            ${metric('Retail Target', v.retail_tgt)}
            ${metric('Retail Ach', v.retail_ach)}
            ${metric('Retail Ach %', v.retail_pct, true)}
          </div>
        </div>
      </div>`;
    }

    function renderElevate(e) {
      return `
      <div class="scheme">
        <div class="scheme-header">5. Elevate Scheme (Jul – Sep)</div>
        <div class="scheme-body">
          <div class="section-title">Higher Variant – BI Retail</div>
          <div class="metrics">
            ${metric('Base (Jul-Sep)', e.base)}
            ${metric('Jul', e.bi_jul)}
            ${metric('Aug', e.bi_aug)}
            ${metric('Sep', e.bi_sep)}
            ${metric('Total Ach', e.bi_ach)}
            ${metric('Growth %', e.gr_bi, true)}
          </div>
          <div class="section-title">Higher Variant – DMS Backed by MI</div>
          <div class="metrics">
            ${metric('Jul', e.dms_jul)}
            ${metric('Aug', e.dms_aug)}
            ${metric('Sep', e.dms_sep)}
            ${metric('Total Ach', e.dms_ach)}
            ${metric('Growth %', e.gr_dms, true)}
          </div>
          <div class="section-title">Retail Growth (BI / DMS)</div>
          <div class="metrics">
            ${metric('BI Total (Jul+Aug+Sep)', e.total_bi)}
            ${metric('BI Growth', e.growth_bi, true)}
            ${metric('DMS Total', e.total_dms)}
            ${metric('DMS Growth', e.growth_dms, true)}
            ${metric('Incremental Growth', e.incremental, true)}
            ${metric('Earning', e.earning, false, true)}
          </div>
          <div class="note">Payout on Incremental Higher Variant Retails (GV, Baleno, Fronx, XL6, e Vitara). Slabs: ≥2%–&lt;4% ₹10,000 | ≥4%–&lt;6% ₹15,000 | ≥6% ₹20,000.</div>
        </div>
      </div>`;
    }

    function renderNAC(n) {
      return `
      <div class="scheme">
        <div class="scheme-header">6. Q2 NAC (Retail)</div>
        <div class="scheme-body">
          <div class="metrics">
            ${metric('Ret Base (Q2 DMS)', n.ret_base)}
            ${metric('Jul Ach', n.jul_ach)}
            ${metric('Aug Ach', n.aug_ach)}
            ${metric('Sep Ach', n.sep_ach)}
            ${metric('Total Ach Q1', n.total_ach)}
          </div>
          <div class="section-title">Growth Gaps (DMS)</div>
          <div class="metrics">
            ${metric('Gap @20%', n.gap_02)}
            ${metric('Gap @22%', n.gap_022)}
            ${metric('Gap @25%', n.gap_025)}
            ${metric('Gap @28%', n.gap_028)}
          </div>
          <div class="section-title">GV Retail Growth Qualifying</div>
          <div class="metrics">
            ${metric('GV Base Q1', n.gv_base_q1)}
            ${metric('Q2 Ach', n.q2_ach)}
            ${metric('Growth', n.gr, true)}
            ${metric('Earning NAC', n.earning, false, true)}
          </div>
        </div>
      </div>`;
    }

    function renderMichelin(m) {
      const qualClass = (m.qualification === 'YES') ? 'status-yes' : 'status-no';
      return `
      <div class="scheme">
        <div class="scheme-header">
          7. Michelin Dealers
          <span class="badge">${m.category || '—'}</span>
        </div>
        <div class="scheme-body">
          <div class="metrics">
            ${metric('Avg Retail (Arena+Nexa)', m.avg_retail)}
            ${metric('YTD CY', m.ytd_cy)}
            ${metric('YTD LY', m.ytd_ly)}
            ${metric('Growth %', m.growth, true)}
            ${metric('RO Vahan Grw', m.ro_vahan_grw, true)}
          </div>
          <div class="section-title">Qualification Status: <span class="${qualClass}">${m.qualification || '—'}</span></div>
          <div class="metrics">
            ${metric('Jul Vahan', m.jul_vahan)}
            ${metric('Aug Vahan', m.aug_vahan)}
            ${metric('Sep Vahan', m.sep_vahan)}
            ${metric('Jun Vahan (Base)', m.jun_vahan)}
            ${metric('LM Vahan Tgt', m.lm_vahan_tgt)}
            ${metric('Vahan Ach Jul', m.vahan_ach_jul)}
            ${metric('Gap', m.gap)}
          </div>
        </div>
      </div>`;
    }
  </script>
</body>
</html>