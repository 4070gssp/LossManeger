<!DOCTYPE html>
<html lang="ja">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>廃棄ロス管理ツール</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;700&family=Inter:wght@400;500;600;700&family=JetBrains+Mono:wght@500;600;700&display=swap" rel="stylesheet">
<script src="https://cdn.jsdelivr.net/npm/html5-qrcode@2.3.8/html5-qrcode.min.js"></script>
<style>
  :root{
    --bg:#0A0F0D;
    --surface:#121A16;
    --surface-2:#182019;
    --border:#213028;
    --border-soft:#182420;
    --ink:#EAF2ED;
    --muted:#7C9088;
    --muted-dim:#546059;
    --scan:#FF3B30;
    --scan-dim:rgba(255,59,48,0.14);
    --data:#39FF88;
    --data-dim:rgba(57,255,136,0.12);
    --amber:#FFB020;
    --amber-dim:rgba(255,176,32,0.14);
    --white:#FFFFFF;
    --font-display:'Space Grotesk', 'Noto Sans JP', sans-serif;
    --font-body:'Inter', 'Noto Sans JP', sans-serif;
    --font-mono:'JetBrains Mono', monospace;
  }
  *{box-sizing:border-box;}
  html,body{margin:0;padding:0;}
  body{
    background:
      radial-gradient(circle at 1px 1px, rgba(57,255,136,0.05) 1px, transparent 0) 0 0/22px 22px,
      var(--bg);
    color:var(--ink);
    font-family:var(--font-body);
    -webkit-tap-highlight-color:transparent;
    min-height:100vh;
    padding-bottom:28px;
  }
  h1,h2,h3{font-family:var(--font-display);}
  button{font-family:inherit; cursor:pointer;}
  input,select,textarea{font-family:inherit;}

  /* ---- corner-bracket "viewfinder" frame, the app's signature motif ---- */
  .cf-wrap{position:relative;}
  .cf-wrap > .cf{position:absolute; width:14px; height:14px; pointer-events:none; z-index:2;}
  .cf-wrap > .cf-tl{top:-1px; left:-1px; border-top:2px solid var(--cf-color, var(--data)); border-left:2px solid var(--cf-color, var(--data));}
  .cf-wrap > .cf-tr{top:-1px; right:-1px; border-top:2px solid var(--cf-color, var(--data)); border-right:2px solid var(--cf-color, var(--data));}
  .cf-wrap > .cf-bl{bottom:-1px; left:-1px; border-bottom:2px solid var(--cf-color, var(--data)); border-left:2px solid var(--cf-color, var(--data));}
  .cf-wrap > .cf-br{bottom:-1px; right:-1px; border-bottom:2px solid var(--cf-color, var(--data)); border-right:2px solid var(--cf-color, var(--data));}
  .cf-scan{--cf-color:var(--scan);}

  /* ---- scanline sweep animation ---- */
  @keyframes sweep{
    0%{ transform:translateY(0); opacity:.15; }
    8%{ opacity:.9; }
    50%{ opacity:.55; }
    92%{ opacity:.9; }
    100%{ transform:translateY(var(--sweep-h,120px)); opacity:.15; }
  }
  .scanline{
    position:absolute; left:6%; right:6%; top:0; height:2px;
    background:var(--scan);
    box-shadow:0 0 8px 1px var(--scan), 0 0 18px 3px rgba(255,59,48,0.5);
    animation:sweep 2.6s ease-in-out infinite alternate;
    pointer-events:none; z-index:1;
  }

  /* ---- Header ---- */
  header{
    position:sticky; top:0; z-index:30;
    background:var(--surface);
    border-bottom:1px solid var(--border);
    padding:16px 16px 16px;
  }
  .header-row{display:flex; align-items:center; justify-content:space-between;}
  .brand{display:flex; flex-direction:column; gap:3px;}
  .brand .eyebrow{
    font-family:var(--font-mono); font-size:10.5px; letter-spacing:.22em; color:var(--data); font-weight:600;
  }
  .brand h1{font-size:19px; margin:0; font-weight:700; letter-spacing:.01em; color:var(--white);}
  .icon-btn{
    background:var(--surface-2);
    border:1px solid var(--border); color:var(--data); width:40px; height:40px; border-radius:8px;
    display:flex; align-items:center; justify-content:center;
    flex-shrink:0;
  }
  .icon-btn:active{background:var(--data-dim); border-color:var(--data);}
  .icon-btn svg{width:19px; height:19px;}

  .store-row{margin-top:14px;}
  .store-row label{
    font-family:var(--font-mono); font-size:10px; letter-spacing:.16em; color:var(--muted);
    display:block; margin-bottom:6px; text-transform:uppercase;
  }
  select#storeSelect{
    width:100%; appearance:none; -webkit-appearance:none;
    background:var(--surface-2) url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="%2339FF88"><path d="M5.25 7.5L10 12.25L14.75 7.5H5.25Z"/></svg>') no-repeat right 14px center;
    background-size:16px;
    color:var(--white);
    border:1px solid var(--border); border-radius:8px;
    padding:13px 40px 13px 14px;
    font-family:var(--font-mono);
    font-size:15px; font-weight:600;
  }

  /* ---- Stats bar ---- */
  .stats{ display:flex; gap:10px; padding:16px 16px 0; }
  .stat-card{
    flex:1; background:var(--surface); border-radius:10px; padding:13px 14px;
    border:1px solid var(--border); position:relative;
  }
  .stat-card .eyebrow{ font-family:var(--font-mono); font-size:9.5px; letter-spacing:.14em; color:var(--muted); text-transform:uppercase; }
  .stat-card .num{
    font-family:var(--font-mono); font-size:26px; font-weight:700; line-height:1.3; color:var(--data);
    text-shadow:0 0 12px rgba(57,255,136,0.35);
  }
  .stat-card .label{font-size:11px; color:var(--muted); margin-top:2px;}
  .stat-card.pending{ --cf-color:var(--amber); }
  .stat-card.pending .num{color:var(--amber); text-shadow:0 0 12px rgba(255,176,32,0.35);}
  .stat-card.pending button{
    margin-top:8px; font-family:var(--font-mono); font-size:10.5px; background:var(--amber-dim); color:var(--amber);
    border:1px solid var(--amber); padding:5px 9px; border-radius:6px; font-weight:600;
  }

  main{padding:16px;}

  /* ---- Scan launch button ---- */
  .scan-launch{
    width:100%; border:1px solid var(--scan); border-radius:14px;
    background:linear-gradient(180deg, #1A0F0E 0%, var(--surface) 70%);
    color:var(--white); padding:0; display:flex; flex-direction:column; align-items:center; justify-content:center; gap:10px;
    position:relative; overflow:hidden; height:168px;
  }
  .scan-launch:active{transform:scale(.99);}
  .scan-launch .icon-wrap{
    width:52px; height:52px; border-radius:50%; background:var(--scan-dim); border:1px solid var(--scan);
    display:flex; align-items:center; justify-content:center; z-index:2;
  }
  .scan-launch .icon-wrap svg{width:24px; height:24px; stroke:var(--scan);}
  .scan-launch .title{font-family:var(--font-display); font-size:18px; font-weight:700; z-index:2;}
  .scan-launch .sub{font-family:var(--font-mono); font-size:10.5px; color:var(--muted); z-index:2; letter-spacing:.03em;}

  section.log{margin-top:24px;}
  section.log h2{
    font-family:var(--font-mono); font-size:11px; letter-spacing:.16em; text-transform:uppercase;
    margin:0 0 10px; color:var(--muted); font-weight:600;
  }
  .log-empty{
    text-align:center; color:var(--muted-dim); font-size:12.5px; padding:30px 10px;
    background:var(--surface); border-radius:10px; border:1px dashed var(--border);
    font-family:var(--font-mono);
  }
  .log-item{
    background:var(--surface); border-radius:10px; padding:11px 14px; margin-bottom:8px;
    display:flex; align-items:center; gap:12px; border:1px solid var(--border);
  }
  .log-item .badge{
    background:var(--data-dim); color:var(--data); font-weight:700; font-size:10.5px; font-family:var(--font-mono);
    padding:4px 8px; border-radius:5px; flex-shrink:0;
  }
  .log-item .barcode{
    font-family:var(--font-mono); font-size:13px; flex:1; letter-spacing:.02em; color:var(--ink);
    overflow:hidden; text-overflow:ellipsis; white-space:nowrap;
  }
  .log-item .qty{font-family:var(--font-mono); font-weight:700; color:var(--amber); font-size:14px; flex-shrink:0;}
  .log-item .time{font-family:var(--font-mono); font-size:10px; color:var(--muted); flex-shrink:0; width:42px; text-align:right;}
  .log-item.is-pending{border-color:var(--amber);}
  .log-item.is-pending .time{color:var(--amber);}

  /* ---- Full screen scan overlay ---- */
  .overlay{
    position:fixed; inset:0; background:#050807; z-index:100;
    display:flex; flex-direction:column;
  }
  .overlay.hidden{display:none;}
  .overlay-top{
    display:flex; align-items:center; justify-content:space-between; padding:16px;
    color:var(--white); border-bottom:1px solid var(--border-soft);
  }
  .overlay-top h3{margin:0; font-size:14px; font-weight:600; font-family:var(--font-mono); letter-spacing:.06em; color:var(--data);}
  .overlay-top .close-btn{
    background:var(--surface-2); border:1px solid var(--border); color:var(--white); width:36px; height:36px;
    border-radius:8px; display:flex; align-items:center; justify-content:center;
  }
  .overlay-top .close-btn svg{width:16px; height:16px;}
  .reader-frame{ flex:1; width:100%; position:relative; margin:14px; border-radius:12px; overflow:hidden; }
  #reader{ width:100%; height:100%; }
  #reader video{object-fit:cover !important; width:100% !important; height:100% !important;}
  .reader-frame .scanline{ --sweep-h:100%; }
  .scan-hint{
    color:var(--muted); text-align:center; font-size:12px; padding:6px 16px 18px; font-family:var(--font-mono);
  }

  /* ---- Bottom sheet ---- */
  .sheet-backdrop{
    position:fixed; inset:0; background:rgba(5,8,7,0.7); z-index:150;
    display:flex; align-items:flex-end; justify-content:center;
  }
  .sheet-backdrop.hidden{display:none;}
  .sheet{
    background:var(--surface); width:100%; max-width:480px; border-radius:18px 18px 0 0;
    padding:20px 20px 26px; border-top:1px solid var(--border);
  }
  .sheet-handle{width:36px; height:4px; background:var(--border); border-radius:2px; margin:0 auto 18px;}
  .led-panel{
    background:#05100B; border-radius:10px; padding:16px 18px; margin-bottom:18px;
    position:relative; border:1px solid var(--border-soft);
  }
  .led-panel .led-label{
    font-family:var(--font-mono); color:var(--muted); font-size:10px; letter-spacing:.18em; margin-bottom:8px;
  }
  .led-panel .led-value{
    color:var(--data); font-family:var(--font-mono); font-size:22px; font-weight:700;
    letter-spacing:.04em; word-break:break-all; text-shadow:0 0 10px rgba(57,255,136,0.5);
  }
  .store-tag{
    display:inline-block; margin-top:10px; background:var(--data-dim); color:var(--data);
    font-family:var(--font-mono); font-size:10.5px; font-weight:700; padding:3px 9px; border-radius:5px;
  }
  .qty-row{display:flex; align-items:center; justify-content:center; gap:16px; margin-bottom:22px;}
  .qty-btn{
    width:52px; height:52px; border-radius:10px; border:1px solid var(--border); background:var(--surface-2);
    color:var(--data); font-size:24px; font-weight:700; display:flex; align-items:center; justify-content:center;
  }
  .qty-btn:active{background:var(--data-dim); border-color:var(--data);}
  #qtyInput{
    width:92px; text-align:center; font-family:var(--font-mono); font-size:30px; font-weight:700;
    border:1px solid var(--border); border-radius:10px; padding:8px 4px; color:var(--amber);
    background:var(--surface-2);
  }
  .sheet-actions{display:flex; gap:10px;}
  .btn{
    flex:1; border:none; border-radius:10px; padding:15px; font-weight:700; font-size:14.5px;
    font-family:var(--font-display);
  }
  .btn-primary{background:var(--scan); color:var(--white);}
  .btn-primary:active{background:#D9291F;}
  .btn-ghost{background:var(--surface-2); color:var(--muted); border:1px solid var(--border);}

  /* ---- Settings modal ---- */
  .modal-backdrop{
    position:fixed; inset:0; background:rgba(5,8,7,0.7); z-index:200;
    display:flex; align-items:center; justify-content:center; padding:16px;
  }
  .modal-backdrop.hidden{display:none;}
  .modal{
    background:var(--surface); width:100%; max-width:440px; border-radius:14px; padding:20px;
    max-height:88vh; overflow-y:auto; border:1px solid var(--border);
  }
  .modal h2{margin:0 0 4px; font-size:16px; color:var(--white); font-family:var(--font-display);}
  .modal .desc{font-size:12px; color:var(--muted); margin-bottom:16px; line-height:1.6;}
  .field{margin-bottom:16px;}
  .field label{
    font-family:var(--font-mono); font-size:10.5px; letter-spacing:.08em; text-transform:uppercase;
    font-weight:600; display:block; margin-bottom:6px; color:var(--muted);
  }
  .field input[type=text], .field input[type=url], .field textarea{
    width:100%; border:1px solid var(--border); border-radius:8px; padding:11px 12px; font-size:13.5px;
    background:var(--surface-2); color:var(--ink);
  }
  .field input:focus, .field textarea:focus{ outline:none; border-color:var(--data); box-shadow:0 0 0 3px var(--data-dim); }
  .field textarea{min-height:130px; resize:vertical; font-family:var(--font-mono); font-size:12.5px; line-height:1.7;}
  .field .hint{font-size:10.5px; color:var(--muted-dim); margin-top:5px;}
  .setup-steps{
    background:var(--surface-2); border-radius:10px; padding:12px 14px; margin-bottom:16px; border:1px solid var(--border);
  }
  .setup-steps ol{margin:0; padding-left:18px; font-size:12px; line-height:1.9; color:var(--muted);}
  .reveal-btn{
    width:100%; background:var(--surface-2); border:1px dashed var(--border); border-radius:8px;
    padding:10px; font-size:12px; font-weight:600; color:var(--data); margin-bottom:8px; font-family:var(--font-mono);
  }
  #gasCode{
    display:none; white-space:pre; overflow-x:auto; background:#05100B; color:var(--data);
    font-family:var(--font-mono); font-size:10.5px; line-height:1.6; border-radius:8px; padding:12px; margin-bottom:8px;
    border:1px solid var(--border-soft);
  }
  .copy-btn{
    width:100%; background:var(--surface-2); color:var(--white); border:1px solid var(--border); border-radius:8px; padding:10px;
    font-size:12px; font-weight:600; margin-bottom:16px; font-family:var(--font-mono);
  }
  .modal-close{
    width:100%; background:var(--data); color:#052015; border:none; border-radius:10px; padding:13px;
    font-weight:700; font-size:14px; font-family:var(--font-display);
  }

  /* ---- Toast ---- */
  #toast{
    position:fixed; left:50%; bottom:24px; transform:translateX(-50%) translateY(20px);
    background:var(--surface); color:var(--ink); padding:12px 18px; border-radius:10px; font-size:13px;
    opacity:0; pointer-events:none; transition:all .25s ease; z-index:300; font-weight:500;
    display:flex; align-items:center; gap:8px; max-width:88%; text-align:center;
    border:1px solid var(--data); font-family:var(--font-mono);
  }
  #toast.show{opacity:1; transform:translateX(-50%) translateY(0);}
  #toast.error{border-color:var(--scan); color:var(--scan);}
</style>
</head>
<body>

<header>
  <div class="header-row">
    <div class="brand">
      <span class="eyebrow">WASTE SCAN TERMINAL</span>
      <h1>廃棄ロス管理ツール</h1>
    </div>
    <button class="icon-btn" id="openSettings" aria-label="設定">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="12" cy="12" r="3"/><path d="M19.4 15a1.65 1.65 0 0 0 .33 1.82l.06.06a2 2 0 1 1-2.83 2.83l-.06-.06a1.65 1.65 0 0 0-1.82-.33 1.65 1.65 0 0 0-1 1.51V21a2 2 0 0 1-4 0v-.09A1.65 1.65 0 0 0 9 19.4a1.65 1.65 0 0 0-1.82.33l-.06.06a2 2 0 1 1-2.83-2.83l.06-.06a1.65 1.65 0 0 0 .33-1.82 1.65 1.65 0 0 0-1.51-1H3a2 2 0 0 1 0-4h.09A1.65 1.65 0 0 0 4.6 9a1.65 1.65 0 0 0-.33-1.82l-.06-.06a2 2 0 1 1 2.83-2.83l.06.06a1.65 1.65 0 0 0 1.82.33H9a1.65 1.65 0 0 0 1-1.51V3a2 2 0 0 1 4 0v.09a1.65 1.65 0 0 0 1 1.51 1.65 1.65 0 0 0 1.82-.33l.06-.06a2 2 0 1 1 2.83 2.83l-.06.06a1.65 1.65 0 0 0-.33 1.82V9a1.65 1.65 0 0 0 1.51 1H21a2 2 0 0 1 0 4h-.09a1.65 1.65 0 0 0-1.51 1z"/></svg>
    </button>
  </div>
  <div class="store-row">
    <label>STORE / 店舗</label>
    <select id="storeSelect"></select>
  </div>
</header>

<main>
  <div class="stats">
    <div class="stat-card cf-wrap">
      <i class="cf cf-tl"></i><i class="cf cf-tr"></i><i class="cf cf-bl"></i><i class="cf cf-br"></i>
      <div class="eyebrow">TODAY</div>
      <div class="num" id="todayCount">0</div>
      <div class="label">本日の記録件数</div>
    </div>
    <div class="stat-card pending cf-wrap" id="pendingCard" style="display:none;">
      <i class="cf cf-tl"></i><i class="cf cf-tr"></i><i class="cf cf-bl"></i><i class="cf cf-br"></i>
      <div class="eyebrow">PENDING</div>
      <div class="num" id="pendingCount">0</div>
      <div class="label">未送信</div>
      <button id="retryBtn">再送信する</button>
    </div>
  </div>

  <div style="margin-top:18px;">
    <button class="scan-launch cf-wrap cf-scan" id="startScanBtn">
      <i class="cf cf-tl"></i><i class="cf cf-tr"></i><i class="cf cf-bl"></i><i class="cf cf-br"></i>
      <div class="scanline" style="--sweep-h:150px;"></div>
      <span class="icon-wrap">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M3 7V5a2 2 0 0 1 2-2h2"/><path d="M17 3h2a2 2 0 0 1 2 2v2"/><path d="M21 17v2a2 2 0 0 1-2 2h-2"/><path d="M7 21H5a2 2 0 0 1-2-2v-2"/><line x1="7" y1="12" x2="17" y2="12"/></svg>
      </span>
      <span class="title">スキャン開始</span>
      <span class="sub">TAP TO ACTIVATE CAMERA</span>
    </button>
  </div>

  <section class="log">
    <h2>RECENT LOGS / 最近の記録</h2>
    <div id="logList"><div class="log-empty">NO RECORDS YET — まだ記録がありません</div></div>
  </section>
</main>

<!-- Camera overlay -->
<div class="overlay hidden" id="scanOverlay">
  <div class="overlay-top">
    <h3>◉ SCANNING...</h3>
    <button class="close-btn" id="closeScanBtn">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"/><line x1="6" y1="6" x2="18" y2="18"/></svg>
    </button>
  </div>
  <div class="reader-frame cf-wrap cf-scan">
    <i class="cf cf-tl"></i><i class="cf cf-tr"></i><i class="cf cf-bl"></i><i class="cf cf-br"></i>
    <div id="reader"></div>
    <div class="scanline"></div>
  </div>
  <div class="scan-hint">枠内にバーコードを合わせてください</div>
</div>

<!-- Result / quantity sheet -->
<div class="sheet-backdrop hidden" id="resultSheet">
  <div class="sheet">
    <div class="sheet-handle"></div>
    <div class="led-panel cf-wrap">
      <i class="cf cf-tl"></i><i class="cf cf-tr"></i><i class="cf cf-bl"></i><i class="cf cf-br"></i>
      <div class="led-label">SCANNED CODE</div>
      <div class="led-value" id="scannedBarcode">-</div>
      <span class="store-tag" id="sheetStoreTag">-</span>
    </div>
    <div class="qty-row">
      <button class="qty-btn" id="qtyMinus">−</button>
      <input type="number" id="qtyInput" value="1" min="1" inputmode="numeric">
      <button class="qty-btn" id="qtyPlus">＋</button>
    </div>
    <div class="sheet-actions">
      <button class="btn btn-ghost" id="rescanBtn">再スキャン</button>
      <button class="btn btn-primary" id="submitBtn">送信する</button>
    </div>
  </div>
</div>

<!-- Settings modal -->
<div class="modal-backdrop hidden" id="settingsModal">
  <div class="modal">
    <h2>設定 / SETTINGS</h2>
    <div class="desc">スプレッドシート送信先と店舗リストを設定します。管理者がコードに送信先URLを埋め込み済みの場合、この画面での設定は不要です(この端末だけ別の送信先に切り替えたい場合のみ使用してください)。</div>
    <div class="field" style="margin-bottom:10px;">
      <label style="margin-bottom:2px;">現在の送信先</label>
      <div id="gasSourceStatus" style="font-size:12px; color:var(--muted); font-family:var(--font-mono);"></div>
    </div>

    <div class="setup-steps">
      <ol>
        <li>Googleスプレッドシートを新規作成</li>
        <li>「拡張機能」→「Apps Script」を開き、下のコードを貼り付け</li>
        <li>「デプロイ」→「新しいデプロイ」→種類「ウェブアプリ」、実行ユーザー「自分」、アクセスできるユーザー「全員」で公開</li>
        <li>発行された /exec のURLを下の欄に貼り付けて保存</li>
      </ol>
    </div>

    <button class="reveal-btn" id="revealGas">&gt; Apps Script コードを見る / コピー</button>
    <pre id="gasCode"></pre>
    <button class="copy-btn" id="copyGas">コードをコピー</button>

    <div class="field">
      <label>スプレッドシート送信先URL(GAS /exec URL)</label>
      <input type="url" id="gasUrlInput" placeholder="https://script.google.com/macros/s/.../exec">
      <div class="hint">この端末だけの設定として保存されます(コードの既定値より優先)</div>
    </div>
    <button class="reveal-btn" id="resetGasUrl" style="margin-bottom:16px;">この端末の個別設定を解除して既定値に戻す</button>

    <div class="field">
      <label>店舗リスト(1行に1店舗)</label>
      <textarea id="storeListInput"></textarea>
      <div class="hint">ここを編集すると店舗プルダウンに反映されます</div>
    </div>

    <button class="modal-close" id="saveSettings">保存して閉じる</button>
  </div>
</div>

<div id="toast"></div>

<script>
/* ============================================================
   ここに送信先のスプレッドシート(GAS /exec URL)を直接貼り付けてください。
   これを設定してGitHubに公開すれば、スタッフ側は⚙設定なしで
   開いた瞬間からそのスプレッドシートに送信されます。
   (空のままでも動作しますが、各端末で⚙から個別設定が必要になります)
   例: const DEFAULT_GAS_URL = "https://script.google.com/macros/s/AKfycbw6qmiINDfNgvB3UTn8n_GMxJ5a31iJx4BDhQ04DGirqjkacm5DPTy3z9wQJxru4Jyzqw/exec";
============================================================ */
const DEFAULT_GAS_URL = "https://script.google.com/macros/s/AKfycbxhlKQvXg4f_tPx-k8Uk2eWAw3XJ7J_3QFl0nj0TrOz76vlUeiL5FbTFX438P0xWZSzgQ/exec";

const DEFAULT_STORES = "ABCDEFGHIJKLMNOPQRSTUVW".split('').map(c => c + '店');
const LS_KEYS = { gasUrl:'haiki_gas_url', stores:'haiki_stores', selectedStore:'haiki_selected_store', logs:'haiki_logs', queue:'haiki_queue' };

const GAS_CODE = `function doPost(e) {
  var sheetName = '廃棄記録';
  var ss = SpreadsheetApp.getActiveSpreadsheet();
  var sheet = ss.getSheetByName(sheetName);
  if (!sheet) {
    sheet = ss.insertSheet(sheetName);
    sheet.appendRow(['日時', '店舗', 'バーコード', '数量']);
  }
  var data = JSON.parse(e.postData.contents);
  sheet.appendRow([data.timestamp, data.store, data.barcode, data.quantity]);
  return ContentService.createTextOutput(JSON.stringify({ result: 'success' }))
    .setMimeType(ContentService.MimeType.JSON);
}`;

let stores = JSON.parse(localStorage.getItem(LS_KEYS.stores) || 'null') || DEFAULT_STORES;
// 端末ごとに⚙で個別設定されていればそれを優先、なければコードに埋め込んだ既定URLを使う
let gasUrl = localStorage.getItem(LS_KEYS.gasUrl) || DEFAULT_GAS_URL;
let logs = JSON.parse(localStorage.getItem(LS_KEYS.logs) || '[]');       // today's on-device receipt list
let queue = JSON.parse(localStorage.getItem(LS_KEYS.queue) || '[]');     // failed/offline submissions pending retry
let html5QrCode = null;
let currentBarcode = null;

const $ = id => document.getElementById(id);

function todayStr(){ return new Date().toISOString().slice(0,10); }

function saveStores(){ localStorage.setItem(LS_KEYS.stores, JSON.stringify(stores)); }
function saveLogs(){ localStorage.setItem(LS_KEYS.logs, JSON.stringify(logs)); }
function saveQueue(){ localStorage.setItem(LS_KEYS.queue, JSON.stringify(queue)); }

function renderStoreSelect(){
  const sel = $('storeSelect');
  const prev = localStorage.getItem(LS_KEYS.selectedStore);
  sel.innerHTML = stores.map(s => `<option value="${s}">${s}</option>`).join('');
  if (prev && stores.includes(prev)) sel.value = prev;
  sel.onchange = () => localStorage.setItem(LS_KEYS.selectedStore, sel.value);
}

function renderStats(){
  const todays = logs.filter(l => l.timestamp.slice(0,10) === todayStr());
  $('todayCount').textContent = todays.length;
  $('pendingCount').textContent = queue.length;
  $('pendingCard').style.display = queue.length > 0 ? 'block' : 'none';
}

function renderLog(){
  const list = $('logList');
  if (logs.length === 0){
    list.innerHTML = '<div class="log-empty">まだ記録がありません</div>';
    return;
  }
  const items = logs.slice(0, 30).map(l => {
    const t = new Date(l.timestamp);
    const hh = String(t.getHours()).padStart(2,'0');
    const mm = String(t.getMinutes()).padStart(2,'0');
    const pendingClass = l.pending ? ' is-pending' : '';
    const timeLabel = l.pending ? '未送信' : `${hh}:${mm}`;
    return `<div class="log-item${pendingClass}">
      <span class="badge">${l.store}</span>
      <span class="barcode">${l.barcode}</span>
      <span class="qty">×${l.quantity}</span>
      <span class="time">${timeLabel}</span>
    </div>`;
  }).join('');
  list.innerHTML = items;
}

function renderAll(){ renderStoreSelect(); renderStats(); renderLog(); }

function showToast(msg, isError=false){
  const t = $('toast');
  t.textContent = msg;
  t.classList.toggle('error', isError);
  t.classList.add('show');
  clearTimeout(showToast._timer);
  showToast._timer = setTimeout(() => t.classList.remove('show'), 2200);
}

/* ---- Scanning ---- */
function openScanOverlay(){
  $('scanOverlay').classList.remove('hidden');
  html5QrCode = new Html5Qrcode('reader');
  const config = {
    fps: 12,
    qrbox: { width: 280, height: 140 },
    formatsToSupport: [
      Html5QrcodeSupportedFormats.EAN_13,
      Html5QrcodeSupportedFormats.EAN_8,
      Html5QrcodeSupportedFormats.UPC_A,
      Html5QrcodeSupportedFormats.UPC_E,
      Html5QrcodeSupportedFormats.CODE_128,
      Html5QrcodeSupportedFormats.CODE_39,
      Html5QrcodeSupportedFormats.QR_CODE
    ]
  };
  html5QrCode.start({ facingMode: 'environment' }, config, onScanSuccess).catch(err => {
    showToast('カメラを起動できませんでした。権限を確認してください', true);
    closeScanOverlay();
  });
}

function closeScanOverlay(){
  if (html5QrCode){
    html5QrCode.stop().then(() => html5QrCode.clear()).catch(()=>{});
  }
  $('scanOverlay').classList.add('hidden');
}

function onScanSuccess(decodedText){
  if (navigator.vibrate) navigator.vibrate(80);
  currentBarcode = decodedText;
  if (html5QrCode){
    html5QrCode.stop().then(() => html5QrCode.clear()).catch(()=>{});
  }
  $('scanOverlay').classList.add('hidden');
  $('scannedBarcode').textContent = currentBarcode;
  $('sheetStoreTag').textContent = $('storeSelect').value;
  $('qtyInput').value = 1;
  $('resultSheet').classList.remove('hidden');
}

/* ---- Quantity controls ---- */
$('qtyMinus').onclick = () => {
  const v = Math.max(1, (parseInt($('qtyInput').value)||1) - 1);
  $('qtyInput').value = v;
};
$('qtyPlus').onclick = () => {
  const v = (parseInt($('qtyInput').value)||1) + 1;
  $('qtyInput').value = v;
};

/* ---- Submission ---- */
function submitEntry(entry){
  if (!gasUrl){
    entry.pending = true;
    queue.push(entry);
    logs.unshift(entry);
    saveQueue(); saveLogs(); renderAll();
    showToast('送信先が未設定です。設定から登録してください', true);
    return;
  }
  fetch(gasUrl, {
    method:'POST',
    mode:'no-cors',
    headers:{ 'Content-Type':'text/plain' },
    body: JSON.stringify(entry)
  }).then(() => {
    entry.pending = false;
    logs.unshift(entry);
    saveLogs(); renderAll();
    showToast('送信しました ✓');
  }).catch(() => {
    entry.pending = true;
    queue.push(entry);
    logs.unshift(entry);
    saveQueue(); saveLogs(); renderAll();
    showToast('通信に失敗しました。後で再送信できます', true);
  });
}

function retryQueue(){
  if (queue.length === 0) return;
  if (!gasUrl){ showToast('送信先が未設定です', true); return; }
  const pending = [...queue];
  queue = [];
  saveQueue();
  let ok = 0;
  Promise.all(pending.map(entry =>
    fetch(gasUrl, { method:'POST', mode:'no-cors', headers:{'Content-Type':'text/plain'}, body: JSON.stringify(entry) })
      .then(() => {
        ok++;
        const idx = logs.findIndex(l => l === entry || (l.timestamp === entry.timestamp && l.barcode === entry.barcode));
        if (idx > -1) logs[idx].pending = false;
      })
      .catch(() => { queue.push(entry); })
  )).then(() => {
    saveQueue(); saveLogs(); renderAll();
    showToast(ok > 0 ? `${ok}件を再送信しました` : '再送信に失敗しました', ok === 0);
  });
}

$('submitBtn').onclick = () => {
  const store = $('storeSelect').value;
  const quantity = Math.max(1, parseInt($('qtyInput').value) || 1);
  const entry = { store, barcode: currentBarcode, quantity, timestamp: new Date().toISOString(), pending:false };
  $('resultSheet').classList.add('hidden');
  submitEntry(entry);
};

$('rescanBtn').onclick = () => {
  $('resultSheet').classList.add('hidden');
  openScanOverlay();
};

$('startScanBtn').onclick = openScanOverlay;
$('closeScanBtn').onclick = closeScanOverlay;
$('retryBtn').onclick = retryQueue;

/* ---- Settings modal ---- */
function renderGasSourceStatus(){
  const deviceOverride = localStorage.getItem(LS_KEYS.gasUrl);
  const el = $('gasSourceStatus');
  if (deviceOverride){
    el.innerHTML = '🔧 この端末専用の設定を使用中<br>' + deviceOverride;
  } else if (DEFAULT_GAS_URL){
    el.innerHTML = '✅ コードに埋め込まれた既定の送信先を使用中<br>' + DEFAULT_GAS_URL;
  } else {
    el.innerHTML = '⚠ 未設定です。送信先URLを入力してください';
  }
}

$('openSettings').onclick = () => {
  $('gasUrlInput').value = localStorage.getItem(LS_KEYS.gasUrl) || '';
  $('storeListInput').value = stores.join('\n');
  renderGasSourceStatus();
  $('settingsModal').classList.remove('hidden');
};
$('resetGasUrl').onclick = () => {
  localStorage.removeItem(LS_KEYS.gasUrl);
  gasUrl = DEFAULT_GAS_URL;
  $('gasUrlInput').value = '';
  renderGasSourceStatus();
  showToast('既定の送信先に戻しました');
};
$('saveSettings').onclick = () => {
  gasUrl = $('gasUrlInput').value.trim();
  localStorage.setItem(LS_KEYS.gasUrl, gasUrl);
  const list = $('storeListInput').value.split('\n').map(s => s.trim()).filter(Boolean);
  if (list.length > 0){ stores = list; saveStores(); }
  $('settingsModal').classList.add('hidden');
  renderAll();
  showToast('設定を保存しました');
};
$('revealGas').onclick = () => {
  const el = $('gasCode');
  el.style.display = el.style.display === 'none' ? 'block' : 'none';
};
$('copyGas').onclick = () => {
  navigator.clipboard.writeText(GAS_CODE).then(() => showToast('コピーしました'));
};
$('gasCode').textContent = GAS_CODE;

/* ---- Init ---- */
renderAll();
</script>
</body>
</html>
