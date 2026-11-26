<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no" />
  <title>Zombie Tower 2.5D</title>
  <style>
    :root {
      --bg: #070b14;
      --panel: #111827;
      --panel-2: #1e293b;
      --border: #334155;
      --text: #f8fafc;
      --muted: #94a3b8;
      --accent: #38bdf8;
      --accent-2: #22c55e;
      --danger: #ef4444;
      --gold: #facc15;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
      -webkit-user-select: none;
      user-select: none;
      -webkit-tap-highlight-color: transparent;
    }

    html, body {
      width: 100%;
      height: 100%;
      background: var(--bg);
      color: var(--text);
      overflow: hidden;
      touch-action: none;
    }

    #gameRoot {
      position: relative;
      width: 100vw;
      height: 100vh;
      background: #05080f;
    }

    canvas#gameCanvas {
      width: 100%;
      height: 100%;
      display: block;
      cursor: crosshair;
    }

    /* Top HUD */
    .hud {
      position: fixed;
      top: 10px;
      left: 10px;
      right: 10px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 8px;
      pointer-events: none;
      z-index: 15;
      flex-wrap: wrap;
    }

    .hud-cluster {
      display: flex;
      align-items: center;
      gap: 8px;
      flex-wrap: wrap;
      pointer-events: auto;
    }

    .pill {
      background: rgba(15, 23, 42, 0.9);
      border: 1px solid var(--border);
      backdrop-filter: blur(8px);
      padding: 6px 11px;
      border-radius: 10px;
      font-size: 12.5px;
      font-weight: 700;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .pill-gold {
      border-color: rgba(250, 204, 21, 0.45);
      color: var(--gold);
    }

    .pill-floor {
      border-color: rgba(56, 189, 248, 0.45);
      color: var(--accent);
    }

    .meter {
      width: 84px;
      height: 8px;
      background: #020617;
      border-radius: 999px;
      overflow: hidden;
      border: 1px solid #1e293b;
    }

    .meter-fill { height: 100%; transition: width 0.14s ease; }
    .hp-bar { background: linear-gradient(90deg, #dc2626, #ef4444); }
    .ar-bar { background: linear-gradient(90deg, #0284c7, #38bdf8); }

    .btn {
      background: var(--panel-2);
      color: var(--text);
      border: 1px solid var(--border);
      padding: 8px 13px;
      border-radius: 10px;
      font-size: 12.5px;
      font-weight: 700;
      cursor: pointer;
      transition: transform 0.1s, filter 0.15s;
    }

    .btn:hover { filter: brightness(1.08); }
    .btn:active { transform: scale(0.95); }
    .btn:disabled { opacity: 0.45; cursor: not-allowed; }
    .btn-primary { background: linear-gradient(135deg, #0284c7, #38bdf8); color: #04101c; border-color: #7dd3fc; }
    .btn-success { background: linear-gradient(135deg, #16a34a, #22c55e); color: #05160b; border-color: #86efac; }
    .btn-gold { background: linear-gradient(135deg, #ca8a04, #facc15); color: #1c1402; border-color: #fde047; }
    .btn-danger { background: rgba(239, 68, 68, 0.18); border-color: #ef4444; color: #fca5a5; }

    /* Bottom Weapon Bar */
    .weapon-bar {
      position: fixed;
      bottom: 10px;
      left: 50%;
      transform: translateX(-50%);
      display: flex;
      gap: 6px;
      background: rgba(15, 23, 42, 0.92);
      border: 1px solid var(--border);
      padding: 6px;
      border-radius: 14px;
      z-index: 15;
      max-width: 96vw;
      overflow-x: auto;
    }

    .w-slot {
      min-width: 78px;
      padding: 6px 8px;
      border-radius: 9px;
      background: #090e1a;
      border: 1px solid #1e293b;
      color: var(--muted);
      font-size: 11px;
      font-weight: 700;
      cursor: pointer;
      text-align: center;
    }

    .w-slot.active {
      background: rgba(56, 189, 248, 0.18);
      border-color: var(--accent);
      color: var(--text);
    }

    .w-slot.locked { opacity: 0.35; cursor: not-allowed; }

    /* Touch Joysticks */
    .joy-zone {
      position: fixed;
      bottom: 66px;
      width: 124px;
      height: 124px;
      border-radius: 50%;
      background: rgba(15, 23, 42, 0.45);
      border: 2px solid rgba(148, 163, 184, 0.28);
      z-index: 14;
      display: none;
    }

    #leftJoy { left: 16px; }
    #rightJoy { right: 16px; border-color: rgba(239, 68, 68, 0.35); }

    .joy-knob {
      position: absolute;
      width: 48px;
      height: 48px;
      left: 50%;
      top: 50%;
      transform: translate(-50%, -50%);
      border-radius: 50%;
      background: rgba(56, 189, 248, 0.75);
      pointer-events: none;
    }

    #rightJoy .joy-knob { background: rgba(239, 68, 68, 0.75); }

    #touchReloadBtn {
      position: fixed;
      bottom: 202px;
      right: 20px;
      z-index: 15;
      display: none;
    }

    /* Fullscreen Main Menu */
    #mainMenu {
      position: fixed;
      inset: 0;
      width: 100vw;
      height: 100vh;
      background:
        radial-gradient(circle at 18% 20%, rgba(56, 189, 248, 0.14), transparent 42%),
        radial-gradient(circle at 82% 78%, rgba(34, 197, 94, 0.12), transparent 45%),
        linear-gradient(180deg, #070c18 0%, #04070e 100%);
      display: flex;
      flex-direction: column;
      justify-content: center;
      padding: clamp(16px, 3vw, 34px);
      overflow-y: auto;
      z-index: 30;
    }

    .full-menu-inner {
      width: 100%;
      max-width: 1120px;
      margin: auto;
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .menu-hero {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      flex-wrap: wrap;
      background: rgba(15, 23, 42, 0.72);
      border: 1px solid rgba(148, 163, 184, 0.2);
      backdrop-filter: blur(12px);
      border-radius: 20px;
      padding: clamp(16px, 2.5vw, 24px);
    }

    .title-grad {
      font-size: clamp(28px, 4.5vw, 44px);
      font-weight: 900;
      letter-spacing: 0.4px;
      background: linear-gradient(90deg, #38bdf8, #22c55e);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .sub { color: var(--muted); font-size: 13.5px; margin-top: 4px; }

    .menu-main-grid {
      display: grid;
      grid-template-columns: 1.25fr 0.95fr;
      gap: 18px;
    }

    .panel-box {
      background: rgba(15, 23, 42, 0.76);
      border: 1px solid rgba(148, 163, 184, 0.2);
      backdrop-filter: blur(12px);
      border-radius: 20px;
      padding: clamp(16px, 2.2vw, 22px);
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 14px;
    }

    /* Modals */
    .overlay {
      position: fixed;
      inset: 0;
      background: rgba(4, 7, 15, 0.88);
      backdrop-filter: blur(8px);
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 16px;
      z-index: 35;
    }

    .hidden { display: none !important; }

    .card {
      width: 100%;
      max-width: 820px;
      max-height: 92vh;
      overflow-y: auto;
      background: var(--panel);
      border: 1px solid var(--border);
      border-radius: 18px;
      padding: 20px;
      box-shadow: 0 24px 60px rgba(0, 0, 0, 0.65);
    }

    .card-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 12px;
      flex-wrap: wrap;
      padding-bottom: 14px;
      border-bottom: 1px solid #1e293b;
    }

    .stats-4 {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 10px;
    }

    .stat-card {
      background: rgba(9, 14, 26, 0.85);
      border: 1px solid #1e293b;
      border-radius: 12px;
      padding: 12px;
    }

    .stat-k { font-size: 11px; color: var(--muted); text-transform: uppercase; }
    .stat-v { font-size: 20px; font-weight: 800; margin-top: 3px; }

    .diff-3 {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .diff-box {
      background: rgba(9, 14, 26, 0.85);
      border: 2px solid #1e293b;
      border-radius: 12px;
      padding: 12px;
      cursor: pointer;
      transition: border-color 0.15s, background 0.15s;
    }

    .diff-box.active {
      border-color: var(--accent);
      background: rgba(56, 189, 248, 0.12);
    }

    .diff-box h4 { font-size: 14px; margin-bottom: 3px; }
    .diff-box p { font-size: 11.5px; color: var(--muted); }

    .code-box {
      display: flex;
      gap: 8px;
      background: rgba(9, 14, 26, 0.85);
      border: 1px solid #1e293b;
      border-radius: 12px;
      padding: 10px;
      align-items: center;
      flex-wrap: wrap;
    }

    .code-input {
      flex: 1;
      min-width: 170px;
      background: #0f172a;
      border: 1px solid #334155;
      color: var(--text);
      padding: 8px 12px;
      border-radius: 9px;
      font-size: 13px;
      outline: none;
      -webkit-user-select: text;
      user-select: text;
    }

    .code-input:focus { border-color: var(--accent); }

    .row-actions {
      display: flex;
      gap: 10px;
      flex-wrap: wrap;
    }

    .inv-layout {
      display: grid;
      grid-template-columns: 205px 1fr;
      gap: 14px;
      margin-top: 14px;
    }

    @media (max-width: 820px) {
      .menu-main-grid { grid-template-columns: 1fr; }
    }

    @media (max-width: 680px) {
      .inv-layout { grid-template-columns: 1fr; }
      .diff-3 { grid-template-columns: 1fr; }
    }

    .preview-card {
      background: #070c17;
      border: 1px solid #1e293b;
      border-radius: 12px;
      padding: 12px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
    }

    .section-lbl {
      font-size: 11.5px;
      font-weight: 800;
      color: var(--muted);
      letter-spacing: 0.4px;
      text-transform: uppercase;
    }

    .armor-slots {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 8px;
      margin-bottom: 10px;
    }

    .eq-box {
      background: #090e1a;
      border: 1px dashed #334155;
      border-radius: 10px;
      padding: 9px;
      min-height: 72px;
    }

    .eq-box.equipped {
      border-style: solid;
      border-color: var(--accent);
      background: rgba(56, 189, 248, 0.08);
    }

    .grid-items {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(175px, 1fr));
      gap: 8px;
    }

    .item-tile {
      background: #090e1a;
      border: 1px solid #1e293b;
      border-radius: 10px;
      padding: 10px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      gap: 8px;
    }

    .item-tile h5 { font-size: 12.5px; }
    .item-tile p { font-size: 11px; color: var(--muted); line-height: 1.35; }

    .swatch {
      width: 100%;
      height: 8px;
      border-radius: 999px;
      margin-bottom: 4px;
    }

    .toast {
      position: fixed;
      top: 58px;
      left: 50%;
      transform: translateX(-50%);
      background: rgba(15, 23, 42, 0.95);
      border: 1px solid var(--accent);
      color: var(--text);
      padding: 7px 15px;
      border-radius: 999px;
      font-size: 12.5px;
      font-weight: 700;
      z-index: 45;
      pointer-events: none;
    }
  </style>
</head>
<body>
  <div id="gameRoot">
    <canvas id="gameCanvas"></canvas>

    <!-- Game HUD -->
    <div id="gameHud" class="hud hidden">
      <div class="hud-cluster">
        <div class="pill">
          <span>❤️</span>
          <span id="hudHp">100/100</span>
          <div class="meter"><div id="hudHpBar" class="meter-fill hp-bar" style="width:100%"></div></div>
        </div>
        <div class="pill">
          <span>🛡️</span>
          <span id="hudArmor">0</span>
          <div class="meter"><div id="hudArmorBar" class="meter-fill ar-bar" style="width:0%"></div></div>
        </div>
        <div class="pill pill-floor">
          <span id="hudFloorRoom">Floor 1 • Room 1/5</span>
        </div>
        <div class="pill">
          <span id="hudZombies">Zombies: 0</span>
        </div>
        <div class="pill pill-gold">
          <span>🪙</span>
          <span id="hudCoins">0</span>
        </div>
      </div>

      <div class="hud-cluster">
        <button class="btn" id="btnHudInv">🎭 Skins & Bag</button>
        <button class="btn btn-gold" id="btnHudShop">🛒 Shop</button>
        <button class="btn" id="btnHudMenu">☰ Menu</button>
      </div>
    </div>

    <!-- Weapon Bar -->
    <div id="weaponBar" class="weapon-bar hidden"></div>

    <!-- Touch Joysticks -->
    <div id="leftJoy" class="joy-zone"><div class="joy-knob" id="leftKnob"></div></div>
    <div id="rightJoy" class="joy-zone"><div class="joy-knob" id="rightKnob"></div></div>
    <button class="btn" id="touchReloadBtn">🔄 Reload</button>

    <div id="toast" class="toast hidden"></div>

    <!-- MAIN MENU -->
    <div id="mainMenu">
      <div class="full-menu-inner">
        <div class="menu-hero">
          <div>
            <div class="title-grad">ZOMBIE TOWER 2.5D</div>
            <div class="sub">3 Floors • 5 Rooms Each • Escape by Helicopter</div>
          </div>
          <div class="pill pill-gold" style="font-size:15px;padding:10px 16px;">
            <span>🪙</span>
            <span>Coins: <strong id="menuCoins">0</strong></span>
          </div>
        </div>

        <div class="menu-main-grid">
          <div class="panel-box">
            <div>
              <div class="section-lbl" style="margin-bottom:10px;">MODE</div>
              <div class="diff-3">
                <div class="diff-box" data-diff="easy">
                  <h4>🟢 Easy</h4>
                  <p>Fewer zombies, low damage.</p>
                </div>
                <div class="diff-box active" data-diff="normal">
                  <h4>🟡 Normal</h4>
                  <p>Balanced rooms and damage.</p>
                </div>
                <div class="diff-box" data-diff="hard">
                  <h4>🔴 Hard</h4>
                  <p>More zombies, high damage.</p>
                </div>
              </div>
            </div>

            <div class="code-box">
              <span style="font-size:12.5px;font-weight:700;">🔑 Code:</span>
              <input type="text" id="menuCodeInput" class="code-input" placeholder="Enter code" autocomplete="off" />
              <button class="btn btn-primary" id="btnMenuCodeSubmit">Use</button>
            </div>

            <div class="row-actions">
              <button class="btn btn-success" id="btnStartRun" style="padding:13px 24px;font-size:15px;flex:1;">▶ Play</button>
              <button class="btn btn-primary" id="btnMenuInv" style="padding:13px 18px;">🎭 Skins & Bag</button>
              <button class="btn btn-gold" id="btnMenuShop" style="padding:13px 18px;">🛒 Shop</button>
              <button class="btn btn-danger" id="btnResetSave" style="padding:13px 14px;">🗑️ Reset</button>
            </div>
          </div>

          <div class="panel-box">
            <div class="section-lbl">SAVED STATS</div>
            <div class="stats-4">
              <div class="stat-card">
                <div class="stat-k">Coins</div>
                <div class="stat-v" style="color:var(--gold)" id="statCoins">0</div>
              </div>
              <div class="stat-card">
                <div class="stat-k">Best Score</div>
                <div class="stat-v" style="color:var(--accent)" id="statScore">0</div>
              </div>
              <div class="stat-card">
                <div class="stat-k">Escapes</div>
                <div class="stat-v" style="color:var(--accent-2)" id="statEscapes">0</div>
              </div>
              <div class="stat-card">
                <div class="stat-k">Kills</div>
                <div class="stat-v" id="statKills">0</div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- SKINS, ARMOR & BAG -->
    <div id="invModal" class="overlay hidden">
      <div class="card">
        <div class="card-header">
          <div>
            <h3>🎭 Skins & Bag</h3>
            <p class="sub">Pick your skin, gun skin, and armor.</p>
          </div>
          <button class="btn" id="btnCloseInv">✕ Close</button>
        </div>

        <div class="inv-layout">
          <div class="preview-card">
            <canvas id="previewCanvas" width="175" height="185"></canvas>
            <div style="font-size:12px;font-weight:700;color:var(--accent)" id="previewSkinName">Classic</div>
            <div style="font-size:11.5px;color:var(--muted);">
              Armor: <strong id="previewArmor" style="color:var(--text)">0</strong>
            </div>
          </div>

          <div>
            <div class="section-lbl" style="margin-bottom:6px;">SKINS</div>
            <div id="charSkinList" class="grid-items"></div>

            <div class="section-lbl" style="margin:12px 0 6px;">AK-47 SKINS</div>
            <div id="weaponSkinList" class="grid-items"></div>

            <div class="section-lbl" style="margin:12px 0 6px;">ARMOR SLOTS</div>
            <div class="armor-slots">
              <div class="eq-box" id="slotHead"></div>
              <div class="eq-box" id="slotChest"></div>
              <div class="eq-box" id="slotBoots"></div>
            </div>

            <div class="section-lbl" style="margin-bottom:6px;">ARMOR BAG</div>
            <div id="armorList" class="grid-items"></div>

            <div class="section-lbl" style="margin:12px 0 6px;">GUNS</div>
            <div id="weaponList" class="grid-items"></div>
          </div>
        </div>
      </div>
    </div>

    <!-- SHOP -->
    <div id="shopModal" class="overlay hidden">
      <div class="card">
        <div class="card-header">
          <div>
            <h3>🛒 Shop</h3>
            <p class="sub">Buy gun skins with coins.</p>
          </div>
          <div style="display:flex;align-items:center;gap:8px;">
            <div class="pill pill-gold">🪙 <span id="shopCoins">0</span></div>
            <button class="btn" id="btnCloseShop">✕ Close</button>
          </div>
        </div>

        <div class="code-box" style="margin:12px 0;">
          <span style="font-size:12.5px;font-weight:700;">🔑 Code:</span>
          <input type="text" id="shopCodeInput" class="code-input" placeholder="Enter code" autocomplete="off" />
          <button class="btn btn-gold" id="btnShopCodeSubmit">Use</button>
        </div>

        <div class="section-lbl" style="margin-bottom:6px;">AK-47 SKINS</div>
        <div id="shopItemsGrid" class="grid-items"></div>
      </div>
    </div>

    <!-- PAUSE / GAME OVER -->
    <div id="endModal" class="overlay hidden">
      <div class="card" style="max-width:440px;text-align:center;">
        <h2 id="endTitle" style="font-size:26px;margin-bottom:6px;">Game Over!</h2>
        <p id="endSub" class="sub" style="margin-bottom:14px;"></p>
        <div class="stats-4" style="text-align:left;margin-bottom:14px;">
          <div class="stat-card">
            <div class="stat-k">Score</div>
            <div class="stat-v" id="endScore">0</div>
          </div>
          <div class="stat-card">
            <div class="stat-k">Coins Earned</div>
            <div class="stat-v" style="color:var(--gold)" id="endCoins">+0</div>
          </div>
        </div>
        <div class="row-actions" style="justify-content:center;">
          <button class="btn btn-success" id="btnResume">▶ Resume</button>
          <button class="btn btn-primary" id="btnRestart">↻ Play Again</button>
          <button class="btn" id="btnToMenu">🏠 Menu</button>
        </div>
      </div>
    </div>
  </div>

  <script>
    const SAVE_KEY = "zombie_tower_25d_save_v2";
    const TOTAL_FLOORS = 3;
    const ROOMS_PER_FLOOR = 5;
    const ESCAPE_REWARD_COINS = 1000;

    const CHAR_SKINS = {
      default: {
        id: "default",
        name: "Classic",
        desc: "Standard soldier skin.",
        bodyColor: "#0369a1",
        headColor: "#e2cba8",
        accent: "#38bdf8",
        isRoboBunny: false
      },
      robo_bunny_blue: {
        id: "robo_bunny_blue",
        name: "Blue Robo Bunny",
        desc: "Blue robot bunny with ears and glow eyes.",
        bodyColor: "#0284c7",
        headColor: "#38bdf8",
        accent: "#7dd3fc",
        isRoboBunny: true
      }
    };

    const AK47_SKINS = {
      default: {
        id: "default",
        weaponId: "rifle",
        name: "Classic AK-47",
        desc: "Standard dark AK-47.",
        price: 0,
        bodyColor: "#0f172a",
        stripeColor: "#22c55e",
        bulletColor: "#22c55e"
      },
      ak_blue: {
        id: "ak_blue",
        weaponId: "rifle",
        name: "Blue AK-47",
        desc: "Blue skin and blue shots.",
        price: 50,
        bodyColor: "#1d4ed8",
        stripeColor: "#38bdf8",
        bulletColor: "#38bdf8"
      },
      ak_green: {
        id: "ak_green",
        weaponId: "rifle",
        name: "Green AK-47",
        desc: "Green skin and green shots.",
        price: 50,
        bodyColor: "#15803d",
        stripeColor: "#4ade80",
        bulletColor: "#4ade80"
      }
    };

    const WEAPON_DEFS = {
      pistol:  { id: "pistol",  name: "Pistol",  key: "1", dmg: 24, fireRate: 230, speed: 800, spread: 0.03, pellets: 1, mag: 15, reload: 850,  color: "#38bdf8" },
      axe:     { id: "axe",     name: "Axe",     key: "2", dmg: 55, fireRate: 400, speed: 0,   spread: 0,    pellets: 1, mag: 999, reload: 300, color: "#f59e0b", melee: true, range: 66 },
      shotgun: { id: "shotgun", name: "Shotgun", key: "3", dmg: 19, fireRate: 650, speed: 700, spread: 0.22, pellets: 6, mag: 6,  reload: 1300, color: "#fb923c" },
      rifle:   { id: "rifle",   name: "AK-47",   key: "4", dmg: 27, fireRate: 118, speed: 880, spread: 0.06, pellets: 1, mag: 30, reload: 1150, color: "#22c55e" },
      plasma:  { id: "plasma",  name: "Laser",   key: "5", dmg: 46, fireRate: 205, speed: 950, spread: 0.02, pellets: 1, mag: 20, reload: 1250, color: "#e879f9" }
    };

    const ARMOR_DEFS = {
      head_t1:  { id: "head_t1",  slot: "head",  name: "Cap Helmet",    armor: 12, color: "#64748b", accent: "#94a3b8" },
      head_t2:  { id: "head_t2",  slot: "head",  name: "Visor Helmet",  armor: 22, color: "#0284c7", accent: "#38bdf8" },
      head_t3:  { id: "head_t3",  slot: "head",  name: "Pro Helmet",    armor: 35, color: "#7c3aed", accent: "#e879f9" },
      chest_t1: { id: "chest_t1", slot: "chest", name: "Light Vest",    armor: 18, color: "#475569", accent: "#94a3b8" },
      chest_t2: { id: "chest_t2", slot: "chest", name: "Guard Vest",    armor: 32, color: "#1d4ed8", accent: "#60a5fa" },
      chest_t3: { id: "chest_t3", slot: "chest", name: "Heavy Vest",    armor: 50, color: "#b45309", accent: "#fbbf24" },
      boots_t1: { id: "boots_t1", slot: "boots", name: "Basic Boots",   armor: 8,  color: "#57534e", accent: "#a8a29e" },
      boots_t2: { id: "boots_t2", slot: "boots", name: "Fast Boots",    armor: 15, color: "#0f766e", accent: "#2dd4bf" },
      boots_t3: { id: "boots_t3", slot: "boots", name: "Power Boots",   armor: 24, color: "#be123c", accent: "#fb7185" }
    };

    const FLOOR_THEMES = [
      { name: "Floor 1", floor: "#141d2e", tile: "#1a253b", wall: "#334155", wallTop: "#475569" },
      { name: "Floor 2", floor: "#14231d", tile: "#1a2e26", wall: "#2f4f44", wallTop: "#416e5e" },
      { name: "Floor 3 (Roof)", floor: "#221a16", tile: "#2e231d", wall: "#523e32", wallTop: "#735847" }
    ];

    const DIFF_CFG = {
      easy:   { base: 4, perRoom: 1, dmgMult: 0.7 },
      normal: { base: 6, perRoom: 2, dmgMult: 1.0 },
      hard:   { base: 9, perRoom: 2, dmgMult: 1.35 }
    };

    function defaultSave() {
      return {
        coins: 0,
        highScore: 0,
        escapes: 0,
        totalKills: 0,
        difficulty: "normal",
        unlockedWeapons: ["pistol"],
        equippedWeapon: "pistol",
        ownedArmor: ["head_t1"],
        equippedArmor: { head: "head_t1", chest: null, boots: null },
        unlockedCharSkins: ["default"],
        equippedCharSkin: "default",
        unlockedAkSkins: ["default"],
        equippedAkSkin: "default",
        redeemedCodes: []
      };
    }

    function loadSave() {
      try {
        const raw = localStorage.getItem(SAVE_KEY);
        if (!raw) return defaultSave();
        const p = JSON.parse(raw);
        return {
          ...defaultSave(),
          ...p,
          equippedArmor: {
            head: p.equippedArmor?.head ?? null,
            chest: p.equippedArmor?.chest ?? null,
            boots: p.equippedArmor?.boots ?? null
          },
          unlockedCharSkins: Array.isArray(p.unlockedCharSkins) ? p.unlockedCharSkins : ["default"],
          unlockedAkSkins: Array.isArray(p.unlockedAkSkins) ? p.unlockedAkSkins : ["default"],
          redeemedCodes: Array.isArray(p.redeemedCodes) ? p.redeemedCodes : []
        };
      } catch {
        return defaultSave();
      }
    }

    let saveData = loadSave();

    function persistSave() {
      try { localStorage.setItem(SAVE_KEY, JSON.stringify(saveData)); } catch {}
      refreshStatsUI();
    }

    function addCoins(amount) {
      saveData.coins += amount;
      persistSave();
    }

    function handleCodeSubmit(inputId) {
      const inp = document.getElementById(inputId);
      const code = (inp.value || "").trim().toLowerCase();
      inp.value = "";
      if (!code) {
        showToast("Type a code.");
        return;
      }

      if (code === "eko123") {
        if (saveData.unlockedCharSkins.includes("robo_bunny_blue")) {
          saveData.equippedCharSkin = "robo_bunny_blue";
          persistSave();
          renderPreview();
          showToast("Blue Robo Bunny equipped!");
          return;
        }
        saveData.unlockedCharSkins.push("robo_bunny_blue");
        saveData.equippedCharSkin = "robo_bunny_blue";
        if (!saveData.redeemedCodes.includes("eko123")) saveData.redeemedCodes.push("eko123");
        persistSave();
        renderPreview();
        showToast("Unlocked Blue Robo Bunny!");
        return;
      }

      showToast("Wrong code.");
    }

    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");
    const previewCanvas = document.getElementById("previewCanvas");
    const pCtx = previewCanvas.getContext("2d");

    const WORLD_W = 1400;
    const WORLD_H = 960;

    let mode = "menu";
    let currentFloor = 1;
    let currentRoom = 1;
    let score = 0;
    let runCoins = 0;
    let lastTime = performance.now();
    let toastTimer = null;

    const heliScene = {
      active: false,
      timer: 0,
      x: WORLD_W - 150,
      y: WORLD_H / 2,
      rotorAngle: 0,
      liftY: 0,
      rewardGiven: false
    };

    const player = {
      x: 130,
      y: WORLD_H / 2,
      radius: 17,
      speed: 230,
      hp: 100,
      maxHp: 100,
      armor: 0,
      maxArmor: 100,
      angle: 0,
      walkPhase: 0,
      isMoving: false,
      lastShot: 0,
      reloadingUntil: 0,
      slashAnim: 0,
      ammo: { pistol: 15, axe: 999, shotgun: 6, rifle: 30, plasma: 20 },
      invuln: 0
    };

    let walls = [];
    let zombies = [];
    let bullets = [];
    let acidOrbs = [];
    let pickups = [];
    let particles = [];
    let exitZone = { x: WORLD_W - 96, y: WORLD_H / 2 - 68, w: 58, h: 136, open: false, isHelipad: false };

    const keys = {};
    const mouse = { x: 0, y: 0, down: false, active: false };
    const isTouch = ("ontouchstart" in window) || navigator.maxTouchPoints > 0;
    const joy = { leftId: null, leftDx: 0, leftDy: 0, rightId: null, rightDx: 0, rightDy: 0 };

    function showToast(msg) {
      const el = document.getElementById("toast");
      el.textContent = msg;
      el.classList.remove("hidden");
      clearTimeout(toastTimer);
      toastTimer = setTimeout(() => el.classList.add("hidden"), 2200);
    }

    function resize() {
      const dpr = Math.min(window.devicePixelRatio || 1, 2);
      canvas.width = Math.floor(window.innerWidth * dpr);
      canvas.height = Math.floor(window.innerHeight * dpr);
      ctx.setTransform(dpr, 0, 0, dpr, 0, 0);
    }
    window.addEventListener("resize", resize);
    resize();

    function getArmorTotal() {
      let total = 0;
      ["head", "chest", "boots"].forEach(s => {
        const id = saveData.equippedArmor[s];
        if (id && ARMOR_DEFS[id]) total += ARMOR_DEFS[id].armor;
      });
      return total;
    }

    function syncArmor() {
      const a = getArmorTotal();
      player.maxArmor = Math.max(20, a);
      player.armor = a;
    }

    function refreshStatsUI() {
      ["hudCoins", "menuCoins", "statCoins", "shopCoins"].forEach(id => {
        const el = document.getElementById(id);
        if (el) el.textContent = saveData.coins;
      });
      document.getElementById("statScore").textContent = saveData.highScore;
      document.getElementById("statEscapes").textContent = saveData.escapes;
      document.getElementById("statKills").textContent = saveData.totalKills;
    }

    function getActiveAkSkin() {
      return AK47_SKINS[saveData.equippedAkSkin] || AK47_SKINS.default;
    }

    function buildWeaponBar() {
      const bar = document.getElementById("weaponBar");
      bar.innerHTML = "";
      Object.values(WEAPON_DEFS).forEach(w => {
        const unlocked = saveData.unlockedWeapons.includes(w.id);
        const active = saveData.equippedWeapon === w.id;
        const btn = document.createElement("button");
        btn.className = `w-slot ${active ? "active" : ""} ${!unlocked ? "locked" : ""}`;
        const ammoStr = w.melee ? "∞" : `${player.ammo[w.id] ?? w.mag}/${w.mag}`;
        btn.innerHTML = `<div>[${w.key}] ${w.name}</div><div style="margin-top:2px;color:${unlocked ? "#f8fafc" : "#64748b"}">${unlocked ? ammoStr : "Locked"}</div>`;
        btn.onclick = () => {
          if (!unlocked) return showToast("Gun locked.");
          equipWeapon(w.id);
        };
        bar.appendChild(btn);
      });
    }

    function equipWeapon(id) {
      if (!saveData.unlockedWeapons.includes(id)) return;
      saveData.equippedWeapon = id;
      player.reloadingUntil = 0;
      persistSave();
      buildWeaponBar();
      showToast(`Equipped ${WEAPON_DEFS[id].name}`);
    }

    function getGlobalRoomNumber() {
      return (currentFloor - 1) * ROOMS_PER_FLOOR + currentRoom;
    }

    function loadRoom(floorNum, roomNum) {
      currentFloor = floorNum;
      currentRoom = roomNum;
      const gRoom = getGlobalRoomNumber();
      const isFinalRoom = (floorNum === TOTAL_FLOORS && roomNum === ROOMS_PER_FLOOR);

      walls = [
        { x: 320, y: 165, w: 120, h: 42 },
        { x: 320, y: 750, w: 120, h: 42 },
        { x: 640, y: 330, w: 52,  h: 140 },
        { x: 640, y: 550, w: 52,  h: 140 },
        { x: 960, y: 185, w: 125, h: 42 },
        { x: 960, y: 730, w: 125, h: 42 }
      ];

      if (roomNum % 2 === 0) {
        walls.push({ x: 485, y: 435, w: 85, h: 85 });
        walls.push({ x: 820, y: 435, w: 85, h: 85 });
      }

      zombies = [];
      bullets = [];
      acidOrbs = [];
      pickups = [];
      particles = [];

      player.x = 120;
      player.y = WORLD_H / 2;
      exitZone.open = false;
      exitZone.isHelipad = isFinalRoom;

      const cfg = DIFF_CFG[saveData.difficulty] || DIFF_CFG.normal;
      const zCount = cfg.base + (gRoom - 1) * cfg.perRoom + (isFinalRoom ? 4 : 0);

      for (let i = 0; i < zCount; i++) {
        spawnZombie(gRoom);
      }

      const unlockOrder = ["axe", "shotgun", "rifle", "plasma"];
      const candidateWeapon = unlockOrder[(gRoom - 1) % unlockOrder.length];
      if (!saveData.unlockedWeapons.includes(candidateWeapon)) {
        pickups.push({
          kind: "weapon",
          weaponId: candidateWeapon,
          x: 740 + (gRoom * 29) % 210,
          y: 230 + (gRoom * 73) % 440
        });
      }

      if (roomNum === 2 || roomNum === 4 || isFinalRoom) {
        const armorKeys = Object.keys(ARMOR_DEFS);
        pickups.push({
          kind: "armor",
          armorId: armorKeys[Math.floor(Math.random() * armorKeys.length)],
          x: 520 + Math.random() * 440,
          y: 180 + Math.random() * 580
        });
      }

      pickups.push({
        kind: "heal",
        x: 390 + Math.random() * 560,
        y: 220 + Math.random() * 500
      });

      const fTheme = FLOOR_THEMES[currentFloor - 1];
      showToast(`${fTheme.name} • Room ${currentRoom}/${ROOMS_PER_FLOOR}`);
    }

    function spawnZombie(gRoom) {
      const r = Math.random();
      let type = "walker";
      if (gRoom >= 8 && r > 0.8) type = "tank";
      else if (gRoom >= 4 && r > 0.6) type = "spitter";
      else if (r > 0.35) type = "runner";

      let pos = { x: WORLD_W - 220, y: WORLD_H / 2 };
      for (let attempt = 0; attempt < 25; attempt++) {
        const cx = 390 + Math.random() * (WORLD_W - 490);
        const cy = 90 + Math.random() * (WORLD_H - 180);
        if (Math.hypot(cx - player.x, cy - player.y) < 260) continue;
        const hitWall = walls.some(w => cx > w.x - 28 && cx < w.x + w.w + 28 && cy > w.y - 28 && cy < w.y + w.h + 28);
        if (!hitWall) { pos = { x: cx, y: cy }; break; }
      }

      const mult = 1 + (gRoom - 1) * 0.1;
      const stats = {
        walker:  { hp: 52 * mult,  speed: 84,  radius: 17, dmg: 12, score: 15, spitCd: 0 },
        runner:  { hp: 38 * mult,  speed: 150, radius: 15, dmg: 10, score: 20, spitCd: 0 },
        spitter: { hp: 62 * mult,  speed: 75,  radius: 18, dmg: 14, score: 25, spitCd: 2300 },
        tank:    { hp: 175 * mult, speed: 58,  radius: 26, dmg: 24, score: 50, spitCd: 0 }
      }[type];

      zombies.push({
        type, x: pos.x, y: pos.y,
        hp: stats.hp, maxHp: stats.hp,
        speed: stats.speed, radius: stats.radius,
        dmg: stats.dmg, score: stats.score,
        spitCd: stats.spitCd, spitTimer: Math.random() * 1200,
        angle: Math.PI, walkPhase: Math.random() * 6.28, hitFlash: 0
      });
    }

    function startNewGame() {
      score = 0;
      runCoins = 0;
      heliScene.active = false;
      heliScene.timer = 0;
      heliScene.liftY = 0;
      heliScene.rewardGiven = false;

      player.hp = player.maxHp;
      player.ammo = { pistol: 15, axe: 999, shotgun: 6, rifle: 30, plasma: 20 };
      syncArmor();
      buildWeaponBar();

      loadRoom(1, 1);

      mode = "playing";
      document.getElementById("mainMenu").classList.add("hidden");
      document.getElementById("endModal").classList.add("hidden");
      document.getElementById("gameHud").classList.remove("hidden");
      document.getElementById("weaponBar").classList.remove("hidden");

      if (isTouch) {
        document.getElementById("leftJoy").style.display = "block";
        document.getElementById("rightJoy").style.display = "block";
        document.getElementById("touchReloadBtn").style.display = "inline-block";
      }
    }

    function triggerHelicopterEscape() {
      mode = "escaping";
      heliScene.active = true;
      heliScene.timer = 0;
      heliScene.liftY = 0;
      showToast("Escaping by helicopter!");
    }

    function openEndScreen(title, subText, canResume) {
      mode = canResume ? "paused" : "ended";
      if (score > saveData.highScore) saveData.highScore = score;
      persistSave();

      document.getElementById("endTitle").textContent = title;
      document.getElementById("endSub").textContent = subText;
      document.getElementById("endScore").textContent = score;
      document.getElementById("endCoins").textContent = `+${runCoins} (Total: ${saveData.coins})`;
      document.getElementById("btnResume").classList.toggle("hidden", !canResume);
      document.getElementById("endModal").classList.remove("hidden");
    }

    function resolveWalls(ent) {
      const pad = 26;
      ent.x = Math.max(pad + ent.radius, Math.min(WORLD_W - pad - ent.radius, ent.x));
      ent.y = Math.max(pad + ent.radius, Math.min(WORLD_H - pad - ent.radius, ent.y));
      for (const w of walls) {
        const cx = Math.max(w.x, Math.min(ent.x, w.x + w.w));
        const cy = Math.max(w.y, Math.min(ent.y, w.y + w.h));
        const dx = ent.x - cx;
        const dy = ent.y - cy;
        const d2 = dx * dx + dy * dy;
        if (d2 < ent.radius * ent.radius) {
          const d = Math.sqrt(d2) || 0.001;
          const ov = ent.radius - d;
          ent.x += (dx / d) * ov;
          ent.y += (dy / d) * ov;
        }
      }
    }

    function hitWall(x, y) {
      if (x < 24 || x > WORLD_W - 24 || y < 24 || y > WORLD_H - 24) return true;
      return walls.some(w => x >= w.x && x <= w.x + w.w && y >= w.y && y <= w.y + w.h);
    }

    function spawnSparks(x, y, color, n = 6) {
      for (let i = 0; i < n; i++) {
        const a = Math.random() * Math.PI * 2;
        const spd = 45 + Math.random() * 135;
        particles.push({ x, y, vx: Math.cos(a) * spd, vy: Math.sin(a) * spd, life: 0.28, color, r: 2.5 });
      }
    }

    function reload() {
      const w = WEAPON_DEFS[saveData.equippedWeapon];
      if (!w || w.melee) return;
      const now = performance.now();
      if (player.reloadingUntil > now || player.ammo[w.id] === w.mag) return;
      player.reloadingUntil = now + w.reload;
      showToast("Reloading...");
    }

    function attack() {
      if (mode !== "playing") return;
      const now = performance.now();
      if (player.reloadingUntil > now) return;
      const w = WEAPON_DEFS[saveData.equippedWeapon];
      if (!w) return;
      if (!w.melee && player.ammo[w.id] <= 0) { reload(); return; }
      if (now - player.lastShot < w.fireRate) return;
      player.lastShot = now;

      if (w.melee) {
        player.slashAnim = 1;
        for (let i = zombies.length - 1; i >= 0; i--) {
          const z = zombies[i];
          const dx = z.x - player.x;
          const dy = z.y - player.y;
          if (Math.hypot(dx, dy) <= w.range + z.radius) {
            let diff = Math.abs(Math.atan2(dy, dx) - player.angle);
            if (diff > Math.PI) diff = Math.PI * 2 - diff;
            if (diff <= 0.95) killOrHurtZombie(i, w.dmg);
          }
        }
        return;
      }

      player.ammo[w.id]--;
      buildWeaponBar();
      if (player.ammo[w.id] === 0) reload();

      const akSkin = w.id === "rifle" ? getActiveAkSkin() : null;
      const projColor = akSkin ? akSkin.bulletColor : w.color;

      const mx = player.x + Math.cos(player.angle) * 24;
      const my = player.y + Math.sin(player.angle) * 24;
      for (let p = 0; p < w.pellets; p++) {
        const ang = player.angle + (Math.random() - 0.5) * w.spread;
        bullets.push({ x: mx, y: my, vx: Math.cos(ang) * w.speed, vy: Math.sin(ang) * w.speed, dmg: w.dmg, color: projColor, life: 1.1 });
      }
      spawnSparks(mx, my, projColor, 3);
    }

    function killOrHurtZombie(idx, dmg) {
      const z = zombies[idx];
      if (!z) return;
      z.hp -= dmg;
      z.hitFlash = 0.1;
      spawnSparks(z.x, z.y, "#ef4444", 4);

      if (z.hp <= 0) {
        addCoins(1);
        runCoins += 1;
        score += z.score;
        saveData.totalKills += 1;
        if (score > saveData.highScore) saveData.highScore = score;
        persistSave();

        if (z.type === "tank" && Math.random() < 0.5) {
          const keysA = Object.keys(ARMOR_DEFS);
          pickups.push({ kind: "armor", armorId: keysA[Math.floor(Math.random() * keysA.length)], x: z.x, y: z.y });
        } else if (Math.random() < 0.16) {
          pickups.push({ kind: "heal", x: z.x, y: z.y });
        }

        spawnSparks(z.x, z.y, "#22c55e", 10);
        zombies.splice(idx, 1);
      }
    }

    function hurtPlayer(dmg) {
      if (mode !== "playing" || player.invuln > 0) return;
      const cfg = DIFF_CFG[saveData.difficulty] || DIFF_CFG.normal;
      let finalDmg = Math.max(1, Math.round(dmg * cfg.dmgMult));

      if (player.armor > 0) {
        const abs = Math.min(player.armor, Math.ceil(finalDmg * 0.65));
        player.armor -= abs;
        finalDmg -= abs;
      }

      player.hp = Math.max(0, player.hp - finalDmg);
      player.invuln = 0.45;
      spawnSparks(player.x, player.y, "#38bdf8", 7);

      if (player.hp <= 0) {
        openEndScreen("Game Over!", "You were defeated.", false);
      }
    }

    function update(dt) {
      if (mode === "escaping") {
        heliScene.timer += dt;
        heliScene.rotorAngle += dt * 36;
        if (heliScene.timer > 0.7) {
          heliScene.liftY -= (heliScene.timer - 0.7) * 95;
          heliScene.x += dt * 165;
          heliScene.y -= dt * 75;
        }
        if (heliScene.timer >= 2.6 && !heliScene.rewardGiven) {
          heliScene.rewardGiven = true;
          addCoins(ESCAPE_REWARD_COINS);
          runCoins += ESCAPE_REWARD_COINS;
          score += 500;
          saveData.escapes += 1;
          if (score > saveData.highScore) saveData.highScore = score;
          persistSave();
          openEndScreen(
            "Game Over! You Escaped!",
            `You escaped by helicopter! Bonus: +${ESCAPE_REWARD_COINS} coins.`,
            false
          );
        }
        return;
      }

      if (mode !== "playing") return;

      heliScene.rotorAngle += dt * 14;
      const now = performance.now();
      if (player.reloadingUntil > 0 && now >= player.reloadingUntil) {
        const w = WEAPON_DEFS[saveData.equippedWeapon];
        if (w && !w.melee) player.ammo[w.id] = w.mag;
        player.reloadingUntil = 0;
        buildWeaponBar();
      }

      if (player.invuln > 0) player.invuln = Math.max(0, player.invuln - dt);
      if (player.slashAnim > 0) player.slashAnim = Math.max(0, player.slashAnim - dt * 5.5);

      let mx = joy.leftDx, my = joy.leftDy;
      if (keys["KeyW"] || keys["ArrowUp"]) my -= 1;
      if (keys["KeyS"] || keys["ArrowDown"]) my += 1;
      if (keys["KeyA"] || keys["ArrowLeft"]) mx -= 1;
      if (keys["KeyD"] || keys["ArrowRight"]) mx += 1;

      const mag = Math.hypot(mx, my);
      if (mag > 1) { mx /= mag; my /= mag; }
      player.isMoving = mag > 0.08;

      if (player.isMoving) {
        player.x += mx * player.speed * dt;
        player.y += my * player.speed * dt;
        player.walkPhase += dt * 11;
        resolveWalls(player);
      }

      const vw = window.innerWidth, vh = window.innerHeight;
      const camX = Math.max(0, Math.min(WORLD_W - vw, player.x - vw / 2));
      const camY = Math.max(0, Math.min(WORLD_H - vh, player.y - vh / 2));

      if (Math.hypot(joy.rightDx, joy.rightDy) > 0.18) {
        player.angle = Math.atan2(joy.rightDy, joy.rightDx);
        attack();
      } else if (mouse.active) {
        player.angle = Math.atan2((mouse.y + camY) - player.y, (mouse.x + camX) - player.x);
        if (mouse.down) attack();
      } else if (player.isMoving) {
        player.angle = Math.atan2(my, mx);
      }

      if (zombies.length === 0 && !exitZone.open) {
        exitZone.open = true;
        if (exitZone.isHelipad) {
          showToast("Go to the helicopter!");
        } else if (currentRoom === ROOMS_PER_FLOOR) {
          showToast("Go to the next floor!");
        } else {
          showToast("Go to the next room!");
        }
      }

      if (
        exitZone.open &&
        player.x + player.radius > exitZone.x &&
        player.x - player.radius < exitZone.x + exitZone.w &&
        player.y + player.radius > exitZone.y &&
        player.y - player.radius < exitZone.y + exitZone.h
      ) {
        if (exitZone.isHelipad) {
          triggerHelicopterEscape();
          return;
        }
        if (currentRoom < ROOMS_PER_FLOOR) {
          loadRoom(currentFloor, currentRoom + 1);
        } else {
          loadRoom(currentFloor + 1, 1);
        }
        return;
      }

      for (let i = bullets.length - 1; i >= 0; i--) {
        const b = bullets[i];
        b.x += b.vx * dt;
        b.y += b.vy * dt;
        b.life -= dt;
        if (b.life <= 0 || hitWall(b.x, b.y)) { bullets.splice(i, 1); continue; }

        let hit = false;
        for (let j = zombies.length - 1; j >= 0; j--) {
          const z = zombies[j];
          if (Math.hypot(b.x - z.x, b.y - z.y) <= z.radius + 4) {
            killOrHurtZombie(j, b.dmg);
            hit = true;
            break;
          }
        }
        if (hit) bullets.splice(i, 1);
      }

      for (let i = 0; i < zombies.length; i++) {
        const z = zombies[i];
        if (z.hitFlash > 0) z.hitFlash = Math.max(0, z.hitFlash - dt);
        const dx = player.x - z.x;
        const dy = player.y - z.y;
        const dist = Math.hypot(dx, dy) || 1;
        z.angle = Math.atan2(dy, dx);

        if (z.type === "spitter" && dist < 430 && dist > 110) {
          z.spitTimer -= dt * 1000;
          if (z.spitTimer <= 0) {
            z.spitTimer = z.spitCd;
            acidOrbs.push({
              x: z.x + Math.cos(z.angle) * (z.radius + 6),
              y: z.y + Math.sin(z.angle) * (z.radius + 6),
              vx: Math.cos(z.angle) * 280,
              vy: Math.sin(z.angle) * 280,
              dmg: z.dmg,
              life: 2.1
            });
          }
        } else {
          z.x += (dx / dist) * z.speed * dt;
          z.y += (dy / dist) * z.speed * dt;
        }

        z.walkPhase += dt * (z.speed * 0.11);
        resolveWalls(z);
        if (dist < z.radius + player.radius - 2) hurtPlayer(z.dmg);
      }

      for (let i = acidOrbs.length - 1; i >= 0; i--) {
        const o = acidOrbs[i];
        o.x += o.vx * dt;
        o.y += o.vy * dt;
        o.life -= dt;
        if (o.life <= 0 || hitWall(o.x, o.y)) { acidOrbs.splice(i, 1); continue; }
        if (Math.hypot(o.x - player.x, o.y - player.y) < player.radius + 7) {
          hurtPlayer(o.dmg);
          acidOrbs.splice(i, 1);
        }
      }

      for (let i = pickups.length - 1; i >= 0; i--) {
        const pk = pickups[i];
        if (Math.hypot(pk.x - player.x, pk.y - player.y) < player.radius + 20) {
          if (pk.kind === "heal") {
            player.hp = Math.min(player.maxHp, player.hp + 30);
            showToast("+30 HP");
          } else if (pk.kind === "weapon") {
            if (!saveData.unlockedWeapons.includes(pk.weaponId)) saveData.unlockedWeapons.push(pk.weaponId);
            equipWeapon(pk.weaponId);
          } else if (pk.kind === "armor") {
            const ad = ARMOR_DEFS[pk.armorId];
            if (!saveData.ownedArmor.includes(pk.armorId)) {
              saveData.ownedArmor.push(pk.armorId);
              showToast(`Got ${ad.name}`);
            } else {
              addCoins(2);
              runCoins += 2;
              showToast(`${ad.name} (+2 Coins)`);
            }
            saveData.equippedArmor[ad.slot] = pk.armorId;
            syncArmor();
            persistSave();
          }
          pickups.splice(i, 1);
        }
      }

      for (let i = particles.length - 1; i >= 0; i--) {
        const pt = particles[i];
        pt.x += pt.vx * dt;
        pt.y += pt.vy * dt;
        pt.life -= dt;
        if (pt.life <= 0) particles.splice(i, 1);
      }

      document.getElementById("hudHp").textContent = `${Math.ceil(player.hp)}/${player.maxHp}`;
      document.getElementById("hudHpBar").style.width = `${(player.hp / player.maxHp) * 100}%`;
      document.getElementById("hudArmor").textContent = `${Math.ceil(player.armor)}`;
      document.getElementById("hudArmorBar").style.width = `${player.maxArmor ? (player.armor / player.maxArmor) * 100 : 0}%`;
      document.getElementById("hudFloorRoom").textContent = `${FLOOR_THEMES[currentFloor - 1].name} • Room ${currentRoom}/${ROOMS_PER_FLOOR}`;
      document.getElementById("hudZombies").textContent = `Zombies: ${zombies.length}`;
    }

    function drawPlayer25D(tCtx, x, y, angle, walkPhase, moving, scale = 1, slash = 0) {
      tCtx.save();
      tCtx.translate(x, y);
      tCtx.scale(scale, scale);

      const skin = CHAR_SKINS[saveData.equippedCharSkin] || CHAR_SKINS.default;
      const head = ARMOR_DEFS[saveData.equippedArmor.head];
      const chest = ARMOR_DEFS[saveData.equippedArmor.chest];
      const boots = ARMOR_DEFS[saveData.equippedArmor.boots];

      tCtx.fillStyle = "rgba(0,0,0,0.42)";
      tCtx.beginPath();
      tCtx.ellipse(0, 14, 18, 9, 0, 0, Math.PI * 2);
      tCtx.fill();

      tCtx.rotate(angle);

      const stride = moving ? Math.sin(walkPhase) * 7 : 0;
      const defaultBoot = skin.isRoboBunny ? "#0369a1" : "#1e293b";
      tCtx.fillStyle = boots ? boots.color : defaultBoot;
      tCtx.fillRect(-5 + stride, -11, 11, 7);
      tCtx.fillRect(-5 - stride, 4, 11, 7);
      if (boots || skin.isRoboBunny) {
        tCtx.fillStyle = boots ? boots.accent : skin.accent;
        tCtx.fillRect(1 + stride, -11, 5, 7);
        tCtx.fillRect(1 - stride, 4, 5, 7);
      }

      tCtx.fillStyle = chest ? chest.color : skin.bodyColor;
      tCtx.beginPath();
      tCtx.roundRect(-11, -14, 22, 26, 6);
      tCtx.fill();

      if (chest) {
        tCtx.fillStyle = chest.accent;
        tCtx.fillRect(-7, -15, 14, 4);
        tCtx.fillRect(-7, 8, 14, 4);
      } else if (skin.isRoboBunny) {
        tCtx.strokeStyle = "#bae6fd";
        tCtx.lineWidth = 2;
        tCtx.strokeRect(-7, -10, 14, 18);
        tCtx.fillStyle = "#e0f2fe";
        tCtx.beginPath();
        tCtx.arc(1, -1, 4, 0, Math.PI * 2);
        tCtx.fill();
      }

      const w = WEAPON_DEFS[saveData.equippedWeapon] || WEAPON_DEFS.pistol;
      tCtx.fillStyle = skin.isRoboBunny ? "#7dd3fc" : "#e2cba8";
      tCtx.fillRect(2, -13, 12, 5);
      tCtx.fillRect(2, 8, 12, 5);

      if (w.melee) {
        tCtx.save();
        tCtx.rotate(slash > 0 ? Math.sin(slash * Math.PI) * 1.1 - 0.55 : 0);
        tCtx.fillStyle = w.color;
        tCtx.fillRect(12, 7, 16, 5);
        tCtx.restore();
      } else if (w.id === "rifle") {
        const akSkin = getActiveAkSkin();
        tCtx.fillStyle = akSkin.bodyColor;
        tCtx.fillRect(9, 4.5, 18, 6);
        tCtx.fillStyle = akSkin.stripeColor;
        tCtx.fillRect(13, 6, 13, 2.5);
      } else {
        tCtx.fillStyle = "#0f172a";
        tCtx.fillRect(10, 5, 15, 5);
        tCtx.fillStyle = w.color;
        tCtx.fillRect(21, 6, 4, 3);
      }

      tCtx.fillStyle = skin.headColor;
      tCtx.beginPath();
      tCtx.arc(0, -2, 10, 0, Math.PI * 2);
      tCtx.fill();

      if (skin.isRoboBunny) {
        tCtx.fillStyle = "#0284c7";
        tCtx.strokeStyle = "#bae6fd";
        tCtx.lineWidth = 1.5;

        tCtx.beginPath();
        tCtx.roundRect(-21, -9, 15, 5.5, 3);
        tCtx.fill();
        tCtx.stroke();
        tCtx.fillStyle = "#e0f2fe";
        tCtx.fillRect(-18, -7.2, 9, 2);

        tCtx.fillStyle = "#0284c7";
        tCtx.beginPath();
        tCtx.roundRect(-21, 0.5, 15, 5.5, 3);
        tCtx.fill();
        tCtx.stroke();
        tCtx.fillStyle = "#e0f2fe";
        tCtx.fillRect(-18, 2.2, 9, 2);

        tCtx.fillStyle = "#0f172a";
        tCtx.fillRect(3, -7, 6, 10);
        tCtx.fillStyle = "#38bdf8";
        tCtx.fillRect(5, -6, 3.5, 3);
        tCtx.fillRect(5, -1, 3.5, 3);
      }

      if (head) {
        tCtx.fillStyle = head.color;
        tCtx.globalAlpha = skin.isRoboBunny ? 0.72 : 1;
        tCtx.beginPath();
        tCtx.arc(-1, -3, 11, 0, Math.PI * 2);
        tCtx.fill();
        tCtx.fillStyle = head.accent;
        tCtx.fillRect(4, -8, 6, 10);
        tCtx.globalAlpha = 1;
      }

      tCtx.restore();
    }

    function drawZombie25D(z) {
      ctx.save();
      ctx.translate(z.x, z.y);

      ctx.fillStyle = "rgba(0,0,0,0.4)";
      ctx.beginPath();
      ctx.ellipse(0, z.radius * 0.75, z.radius, z.radius * 0.5, 0, 0, Math.PI * 2);
      ctx.fill();

      ctx.rotate(z.angle);
      const step = Math.sin(z.walkPhase) * (z.type === "runner" ? 8 : 5);
      const fl = z.hitFlash > 0;

      const pal = {
        walker:  { skin: "#4d7c0f", cloth: "#3f6212", arm: "#65a30d", eye: "#fde047" },
        runner:  { skin: "#991b1b", cloth: "#450a0a", arm: "#dc2626", eye: "#fef08a" },
        spitter: { skin: "#15803d", cloth: "#14532d", arm: "#4ade80", eye: "#a3e635" },
        tank:    { skin: "#334155", cloth: "#1e293b", arm: "#475569", eye: "#f87171" }
      }[z.type];

      ctx.fillStyle = fl ? "#fff" : pal.cloth;
      ctx.fillRect(-6 + step, -z.radius * 0.55, 10, 6);
      ctx.fillRect(-6 - step, z.radius * 0.2, 10, 6);

      ctx.beginPath();
      ctx.roundRect(-z.radius * 0.65, -z.radius * 0.75, z.radius * 1.3, z.radius * 1.5, 6);
      ctx.fill();

      if (z.type === "spitter") {
        ctx.fillStyle = fl ? "#fff" : "#84cc16";
        ctx.beginPath(); ctx.arc(-4, 0, 7, 0, Math.PI * 2); ctx.fill();
      }

      ctx.fillStyle = fl ? "#fff" : pal.arm;
      ctx.fillRect(2, -z.radius * 0.75, z.radius * 0.9, 5);
      ctx.fillRect(2, z.radius * 0.45, z.radius * 0.9, 5);

      ctx.fillStyle = fl ? "#fff" : pal.skin;
      ctx.beginPath(); ctx.arc(1, -2, z.radius * 0.56, 0, Math.PI * 2); ctx.fill();

      ctx.fillStyle = pal.eye;
      ctx.fillRect(z.radius * 0.25, -6, 3.5, 3);
      ctx.fillRect(z.radius * 0.25, 0, 3.5, 3);
      ctx.restore();

      if (z.hp < z.maxHp) {
        const bw = z.radius * 1.8;
        ctx.fillStyle = "rgba(0,0,0,0.65)";
        ctx.fillRect(z.x - bw / 2, z.y - z.radius - 13, bw, 5);
        ctx.fillStyle = "#ef4444";
        ctx.fillRect(z.x - bw / 2, z.y - z.radius - 13, bw * Math.max(0, z.hp / z.maxHp), 5);
      }
    }

    function drawHelicopter() {
      const hx = heliScene.x;
      const hy = heliScene.y + heliScene.liftY;
      ctx.save();
      ctx.translate(hx, hy);

      const shScale = Math.max(0.25, 1 + heliScene.liftY / 240);
      ctx.fillStyle = "rgba(0,0,0,0.42)";
      ctx.beginPath();
      ctx.ellipse(0, 36 - heliScene.liftY, 54 * shScale, 24 * shScale, 0, 0, Math.PI * 2);
      ctx.fill();

      ctx.fillStyle = "#1e293b";
      ctx.fillRect(36, -6, 48, 12);
      ctx.fillStyle = "#38bdf8";
      ctx.fillRect(76, -16, 9, 32);

      ctx.fillStyle = "#0f172a";
      ctx.strokeStyle = "#38bdf8";
      ctx.lineWidth = 2.5;
      ctx.beginPath();
      ctx.ellipse(0, 0, 42, 24, 0, 0, Math.PI * 2);
      ctx.fill();
      ctx.stroke();

      ctx.fillStyle = "#7dd3fc";
      ctx.beginPath();
      ctx.ellipse(-20, 0, 14, 15, 0, 0, Math.PI * 2);
      ctx.fill();

      ctx.save();
      ctx.rotate(heliScene.rotorAngle);
      ctx.strokeStyle = "rgba(248, 250, 252, 0.78)";
      ctx.lineWidth = 4;
      ctx.beginPath();
      ctx.moveTo(-64, 0); ctx.lineTo(64, 0);
      ctx.moveTo(0, -64); ctx.lineTo(0, 64);
      ctx.stroke();
      ctx.restore();

      ctx.restore();
    }

    function render() {
      const vw = window.innerWidth, vh = window.innerHeight;
      ctx.fillStyle = "#04070d";
      ctx.fillRect(0, 0, vw, vh);

      const theme = FLOOR_THEMES[(currentFloor - 1) % FLOOR_THEMES.length];
      const camX = Math.max(0, Math.min(WORLD_W - vw, player.x - vw / 2));
      const camY = Math.max(0, Math.min(WORLD_H - vh, player.y - vh / 2));

      ctx.save();
      ctx.translate(-camX, -camY);

      ctx.fillStyle = theme.floor;
      ctx.fillRect(0, 0, WORLD_W, WORLD_H);

      ctx.strokeStyle = theme.tile;
      for (let gx = 0; gx <= WORLD_W; gx += 60) {
        ctx.beginPath(); ctx.moveTo(gx, 0); ctx.lineTo(gx, WORLD_H); ctx.stroke();
      }
      for (let gy = 0; gy <= WORLD_H; gy += 60) {
        ctx.beginPath(); ctx.moveTo(0, gy); ctx.lineTo(WORLD_W, gy); ctx.stroke();
      }

      ctx.strokeStyle = theme.wallTop;
      ctx.lineWidth = 6;
      ctx.strokeRect(20, 20, WORLD_W - 40, WORLD_H - 40);

      const gateColor = exitZone.isHelipad ? "#38bdf8" : "#22c55e";
      ctx.fillStyle = exitZone.open ? (exitZone.isHelipad ? "rgba(56,189,248,0.22)" : "rgba(34,197,94,0.22)") : "rgba(100,116,139,0.15)";
      ctx.strokeStyle = exitZone.open ? gateColor : "#475569";
      ctx.lineWidth = 3;
      ctx.fillRect(exitZone.x, exitZone.y, exitZone.w, exitZone.h);
      ctx.strokeRect(exitZone.x, exitZone.y, exitZone.w, exitZone.h);

      ctx.fillStyle = exitZone.open ? "#f8fafc" : "#94a3b8";
      ctx.font = "bold 11px sans-serif";
      ctx.textAlign = "center";
      const label = !exitZone.open ? "LOCKED" : (exitZone.isHelipad ? "HELI" : (currentRoom === ROOMS_PER_FLOOR ? "NEXT FLOOR ▶" : "NEXT ROOM ▶"));
      ctx.fillText(label, exitZone.x + exitZone.w / 2, exitZone.y + exitZone.h / 2);

      for (const pk of pickups) {
        ctx.save();
        ctx.translate(pk.x, pk.y);
        if (pk.kind === "heal") {
          ctx.fillStyle = "#22c55e";
          ctx.fillRect(-3, -8, 6, 16); ctx.fillRect(-8, -3, 16, 6);
        } else if (pk.kind === "weapon") {
          const wd = WEAPON_DEFS[pk.weaponId];
          ctx.fillStyle = wd.color; ctx.fillRect(-10, -4, 20, 8);
          ctx.fillStyle = "#fff"; ctx.font = "bold 10px sans-serif"; ctx.fillText(wd.name, 0, -16);
        } else if (pk.kind === "armor") {
          const ad = ARMOR_DEFS[pk.armorId];
          ctx.fillStyle = ad.accent; ctx.beginPath(); ctx.arc(0, 0, 10, 0, Math.PI * 2); ctx.fill();
          ctx.fillStyle = "#fde047"; ctx.font = "bold 10px sans-serif"; ctx.fillText(ad.name, 0, -16);
        }
        ctx.restore();
      }

      for (const w of walls) {
        ctx.fillStyle = theme.wall;
        ctx.fillRect(w.x, w.y + w.h - 14, w.w, 20);
        ctx.fillStyle = theme.wallTop;
        ctx.fillRect(w.x, w.y - 14, w.w, w.h);
      }

      zombies.forEach(drawZombie25D);

      if (mode !== "menu" && mode !== "escaping") {
        drawPlayer25D(ctx, player.x, player.y, player.angle, player.walkPhase, player.isMoving, 1, player.slashAnim);
      }

      if (exitZone.isHelipad || heliScene.active) {
        drawHelicopter();
      }

      for (const b of bullets) {
        ctx.fillStyle = b.color;
        ctx.beginPath(); ctx.arc(b.x, b.y, 4, 0, Math.PI * 2); ctx.fill();
      }
      for (const o of acidOrbs) {
        ctx.fillStyle = "#a3e635";
        ctx.beginPath(); ctx.arc(o.x, o.y, 7, 0, Math.PI * 2); ctx.fill();
      }
      for (const pt of particles) {
        ctx.fillStyle = pt.color;
        ctx.globalAlpha = Math.max(0, pt.life * 3.2);
        ctx.beginPath(); ctx.arc(pt.x, pt.y, pt.r, 0, Math.PI * 2); ctx.fill();
        ctx.globalAlpha = 1;
      }

      ctx.restore();
    }

    function renderPreview() {
      pCtx.clearRect(0, 0, previewCanvas.width, previewCanvas.height);
      pCtx.fillStyle = "#0b1220";
      pCtx.fillRect(0, 0, previewCanvas.width, previewCanvas.height);
      drawPlayer25D(pCtx, previewCanvas.width / 2, previewCanvas.height / 2 + 12, -Math.PI / 2, 0.5, true, 2.05, 0);
      const activeSkin = CHAR_SKINS[saveData.equippedCharSkin] || CHAR_SKINS.default;
      document.getElementById("previewSkinName").textContent = activeSkin.name;
      document.getElementById("previewArmor").textContent = getArmorTotal();
    }

    function renderShop() {
      refreshStatsUI();
      const grid = document.getElementById("shopItemsGrid");
      grid.innerHTML = "";

      Object.values(AK47_SKINS).filter(s => s.price > 0).forEach(skin => {
        const owned = saveData.unlockedAkSkins.includes(skin.id);
        const equipped = saveData.equippedAkSkin === skin.id;

        const tile = document.createElement("div");
        tile.className = "item-tile";
        tile.innerHTML = `
          <div>
            <div class="swatch" style="background:linear-gradient(90deg, ${skin.bodyColor}, ${skin.stripeColor})"></div>
            <h5>${skin.name}</h5>
            <p>${skin.desc}</p>
          </div>
        `;

        const btn = document.createElement("button");
        if (owned) {
          btn.className = `btn ${equipped ? "btn-success" : "btn-primary"}`;
          btn.textContent = equipped ? "Equipped" : "Equip";
          btn.onclick = () => {
            saveData.equippedAkSkin = skin.id;
            persistSave();
            renderShop();
            showToast(`Equipped ${skin.name}`);
          };
        } else {
          btn.className = "btn btn-gold";
          btn.textContent = `🪙 Buy (${skin.price})`;
          btn.disabled = saveData.coins < skin.price;
          btn.onclick = () => {
            if (saveData.coins < skin.price) return showToast("Not enough coins.");
            saveData.coins -= skin.price;
            saveData.unlockedAkSkins.push(skin.id);
            saveData.equippedAkSkin = skin.id;
            persistSave();
            renderShop();
            showToast(`Bought ${skin.name}!`);
          };
        }

        tile.appendChild(btn);
        grid.appendChild(tile);
      });
    }

    function openInv() {
      renderPreview();

      const charList = document.getElementById("charSkinList");
      charList.innerHTML = "";
      Object.values(CHAR_SKINS).forEach(sk => {
        const unlocked = saveData.unlockedCharSkins.includes(sk.id);
        const equipped = saveData.equippedCharSkin === sk.id;
        const tile = document.createElement("div");
        tile.className = "item-tile";
        tile.innerHTML = `
          <div>
            <div class="swatch" style="background:linear-gradient(90deg, ${sk.bodyColor}, ${sk.accent})"></div>
            <h5>${sk.name}</h5>
            <p>${unlocked ? sk.desc : "Locked."}</p>
          </div>
        `;
        const btn = document.createElement("button");
        if (!unlocked) {
          btn.className = "btn";
          btn.disabled = true;
          btn.textContent = "🔒 Locked";
        } else {
          btn.className = `btn ${equipped ? "btn-success" : "btn-primary"}`;
          btn.textContent = equipped ? "Equipped" : "Equip";
          btn.onclick = () => {
            saveData.equippedCharSkin = sk.id;
            persistSave();
            openInv();
            showToast(`Skin: ${sk.name}`);
          };
        }
        tile.appendChild(btn);
        charList.appendChild(tile);
      });

      const wSkinList = document.getElementById("weaponSkinList");
      wSkinList.innerHTML = "";
      Object.values(AK47_SKINS).forEach(sk => {
        const unlocked = saveData.unlockedAkSkins.includes(sk.id);
        const equipped = saveData.equippedAkSkin === sk.id;
        const tile = document.createElement("div");
        tile.className = "item-tile";
        tile.innerHTML = `
          <div>
            <div class="swatch" style="background:linear-gradient(90deg, ${sk.bodyColor}, ${sk.stripeColor})"></div>
            <h5>${sk.name}</h5>
            <p>${unlocked ? sk.desc : `Shop: ${sk.price} Coins`}</p>
          </div>
        `;
        const btn = document.createElement("button");
        if (!unlocked) {
          btn.className = "btn";
          btn.disabled = true;
          btn.textContent = `🔒 ${sk.price} Coins`;
        } else {
          btn.className = `btn ${equipped ? "btn-success" : "btn-primary"}`;
          btn.textContent = equipped ? "Equipped" : "Equip";
          btn.onclick = () => {
            saveData.equippedAkSkin = sk.id;
            persistSave();
            openInv();
            showToast(`AK-47: ${sk.name}`);
          };
        }
        tile.appendChild(btn);
        wSkinList.appendChild(tile);
      });

      const labels = { head: "Head", chest: "Chest", boots: "Boots" };
      ["head", "chest", "boots"].forEach(slot => {
        const box = document.getElementById("slot" + slot[0].toUpperCase() + slot.slice(1));
        const eqId = saveData.equippedArmor[slot];
        if (eqId && ARMOR_DEFS[eqId]) {
          const item = ARMOR_DEFS[eqId];
          box.className = "eq-box equipped";
          box.innerHTML = `<div style="font-size:10.5px;color:#94a3b8">${labels[slot]}</div><div style="font-size:12px;font-weight:700">${item.name}</div><div style="font-size:11px;color:#38bdf8">+${item.armor} Armor</div>`;
        } else {
          box.className = "eq-box";
          box.innerHTML = `<div style="font-size:10.5px;color:#94a3b8">${labels[slot]}</div><div style="font-size:11.5px;color:#64748b">Empty</div>`;
        }
      });

      const aList = document.getElementById("armorList");
      aList.innerHTML = "";
      saveData.ownedArmor.forEach(aid => {
        const def = ARMOR_DEFS[aid];
        if (!def) return;
        const eq = saveData.equippedArmor[def.slot] === aid;
        const tile = document.createElement("div");
        tile.className = "item-tile";
        tile.innerHTML = `<div><h5>${def.name}</h5><p>${labels[def.slot]} • +${def.armor} Armor</p></div>`;
        const btn = document.createElement("button");
        btn.className = `btn ${eq ? "btn-success" : "btn-primary"}`;
        btn.textContent = eq ? "Equipped" : "Equip";
        btn.onclick = () => {
          saveData.equippedArmor[def.slot] = eq ? null : aid;
          syncArmor();
          persistSave();
          openInv();
        };
        tile.appendChild(btn);
        aList.appendChild(tile);
      });

      const wList = document.getElementById("weaponList");
      wList.innerHTML = "";
      saveData.unlockedWeapons.forEach(wid => {
        const def = WEAPON_DEFS[wid];
        if (!def) return;
        const eq = saveData.equippedWeapon === wid;
        const tile = document.createElement("div");
        tile.className = "item-tile";
        tile.innerHTML = `<div><h5>${def.name}</h5><p>Power: ${def.dmg}</p></div>`;
        const btn = document.createElement("button");
        btn.className = `btn ${eq ? "btn-success" : "btn-primary"}`;
        btn.textContent = eq ? "Equipped" : "Equip";
        btn.onclick = () => { equipWeapon(wid); openInv(); };
        tile.appendChild(btn);
        wList.appendChild(tile);
      });

      document.getElementById("invModal").classList.remove("hidden");
    }

    function loop(now) {
      const dt = Math.min(0.05, (now - lastTime) / 1000);
      lastTime = now;
      update(dt);
      render();
      requestAnimationFrame(loop);
    }

    window.addEventListener("keydown", e => {
      keys[e.code] = true;
      if (e.code === "KeyR") reload();
      if (e.code === "KeyE" && mode === "playing") openInv();
      if (e.code === "Escape") {
        if (!document.getElementById("invModal").classList.contains("hidden")) document.getElementById("invModal").classList.add("hidden");
        else if (!document.getElementById("shopModal").classList.contains("hidden")) document.getElementById("shopModal").classList.add("hidden");
        else if (mode === "playing") openEndScreen("Paused", "Game paused.", true);
      }
      const wKey = Object.values(WEAPON_DEFS).find(w => `Digit${w.key}` === e.code);
      if (wKey && saveData.unlockedWeapons.includes(wKey.id)) equipWeapon(wKey.id);
    });
    window.addEventListener("keyup", e => { keys[e.code] = false; });

    canvas.addEventListener("mousemove", e => { mouse.x = e.clientX; mouse.y = e.clientY; mouse.active = true; });
    canvas.addEventListener("mousedown", e => {
      if (e.button === 0) { mouse.x = e.clientX; mouse.y = e.clientY; mouse.down = true; mouse.active = true; attack(); }
    });
    window.addEventListener("mouseup", () => { mouse.down = false; });

    function bindJoy(zoneId, knobId, side) {
      const zone = document.getElementById(zoneId);
      const knob = document.getElementById(knobId);
      const maxR = 38;

      zone.addEventListener("touchstart", e => {
        e.preventDefault();
        const t = e.changedTouches[0];
        if (side === "left" && joy.leftId === null) joy.leftId = t.identifier;
        if (side === "right" && joy.rightId === null) joy.rightId = t.identifier;
      }, { passive: false });

      zone.addEventListener("touchmove", e => {
        e.preventDefault();
        const rect = zone.getBoundingClientRect();
        const cx = rect.left + rect.width / 2, cy = rect.top + rect.height / 2;
        for (const t of e.changedTouches) {
          const id = side === "left" ? joy.leftId : joy.rightId;
          if (t.identifier !== id) continue;
          let dx = t.clientX - cx, dy = t.clientY - cy;
          const d = Math.hypot(dx, dy);
          if (d > maxR) { dx = (dx / d) * maxR; dy = (dy / d) * maxR; }
          knob.style.transform = `translate(calc(-50% + ${dx}px), calc(-50% + ${dy}px))`;
          if (side === "left") { joy.leftDx = dx / maxR; joy.leftDy = dy / maxR; }
          else { joy.rightDx = dx / maxR; joy.rightDy = dy / maxR; }
        }
      }, { passive: false });

      const release = e => {
        for (const t of e.changedTouches) {
          if (side === "left" && t.identifier === joy.leftId) {
            joy.leftId = null; joy.leftDx = 0; joy.leftDy = 0;
            knob.style.transform = "translate(-50%, -50%)";
          }
          if (side === "right" && t.identifier === joy.rightId) {
            joy.rightId = null; joy.rightDx = 0; joy.rightDy = 0;
            knob.style.transform = "translate(-50%, -50%)";
          }
        }
      };
      zone.addEventListener("touchend", release);
      zone.addEventListener("touchcancel", release);
    }

    bindJoy("leftJoy", "leftKnob", "left");
    bindJoy("rightJoy", "rightKnob", "right");
    document.getElementById("touchReloadBtn").addEventListener("click", reload);

    document.querySelectorAll(".diff-box").forEach(box => {
      if (box.dataset.diff === saveData.difficulty) {
        document.querySelectorAll(".diff-box").forEach(b => b.classList.remove("active"));
        box.classList.add("active");
      }
      box.addEventListener("click", () => {
        document.querySelectorAll(".diff-box").forEach(b => b.classList.remove("active"));
        box.classList.add("active");
        saveData.difficulty = box.dataset.diff;
        persistSave();
      });
    });

    document.getElementById("btnMenuCodeSubmit").addEventListener("click", () => handleCodeSubmit("menuCodeInput"));
    document.getElementById("btnShopCodeSubmit").addEventListener("click", () => handleCodeSubmit("shopCodeInput"));

    document.getElementById("btnStartRun").addEventListener("click", startNewGame);
    document.getElementById("btnHudInv").addEventListener("click", openInv);
    document.getElementById("btnMenuInv").addEventListener("click", openInv);
    document.getElementById("btnCloseInv").addEventListener("click", () => document.getElementById("invModal").classList.add("hidden"));

    const openShopModal = () => {
      renderShop();
      document.getElementById("shopModal").classList.remove("hidden");
    };
    document.getElementById("btnHudShop").addEventListener("click", openShopModal);
    document.getElementById("btnMenuShop").addEventListener("click", openShopModal);
    document.getElementById("btnCloseShop").addEventListener("click", () => document.getElementById("shopModal").classList.add("hidden"));

    document.getElementById("btnHudMenu").addEventListener("click", () => {
      if (mode === "playing") openEndScreen("Paused", "Game paused.", true);
    });
    document.getElementById("btnResume").addEventListener("click", () => {
      document.getElementById("endModal").classList.add("hidden");
      mode = "playing";
    });
    document.getElementById("btnRestart").addEventListener("click", startNewGame);
    document.getElementById("btnToMenu").addEventListener("click", () => {
      mode = "menu";
      document.getElementById("endModal").classList.add("hidden");
      document.getElementById("gameHud").classList.add("hidden");
      document.getElementById("weaponBar").classList.add("hidden");
      document.getElementById("leftJoy").style.display = "none";
      document.getElementById("rightJoy").style.display = "none";
      document.getElementById("touchReloadBtn").style.display = "none";
      document.getElementById("mainMenu").classList.remove("hidden");
      refreshStatsUI();
    });

    document.getElementById("btnResetSave").addEventListener("click", () => {
      saveData = defaultSave();
      syncArmor();
      persistSave();
      showToast("Save reset.");
    });

    syncArmor();
    refreshStatsUI();
    requestAnimationFrame(loop);
  </script>
</body>
</html>
