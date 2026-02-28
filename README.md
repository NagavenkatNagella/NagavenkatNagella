<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Nagella Nagavenkat – Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&family=Syne:wght@400;600;700;800&display=swap" rel="stylesheet">
<style>
  :root {
    --sky: #0ea5e9;
    --sky-dim: #0284c7;
    --sky-glow: rgba(14,165,233,0.25);
    --bg: #030712;
    --bg2: #0c1220;
    --border: rgba(14,165,233,0.18);
    --text: #e2e8f0;
    --muted: #64748b;
    --mono: 'Space Mono', monospace;
    --sans: 'Syne', sans-serif;
  }

  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  html { scroll-behavior: smooth; }

  body {
    font-family: var(--sans);
    background: var(--bg);
    color: var(--text);
    min-height: 100vh;
    overflow-x: hidden;
  }

  /* ── CANVAS BG ── */
  #bg-canvas {
    position: fixed;
    inset: 0;
    z-index: 0;
    pointer-events: none;
    opacity: .45;
  }

  /* ── WRAPPER ── */
  .wrap {
    position: relative;
    z-index: 1;
    max-width: 860px;
    margin: 0 auto;
    padding: 60px 24px 100px;
  }

  /* ── HERO ── */
  .hero {
    text-align: center;
    padding-bottom: 56px;
    border-bottom: 1px solid var(--border);
    animation: fadeUp .9s ease both;
  }

  .avatar-ring {
    display: inline-block;
    width: 96px; height: 96px;
    border-radius: 50%;
    border: 2px solid var(--sky);
    box-shadow: 0 0 28px var(--sky-glow), 0 0 60px rgba(14,165,233,.1);
    margin-bottom: 20px;
    animation: pulse 3s ease-in-out infinite;
    position: relative;
    overflow: hidden;
    background: var(--bg2);
  }

  .avatar-ring span {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%; height: 100%;
    font-size: 2.4rem;
  }

  @keyframes pulse {
    0%,100% { box-shadow: 0 0 28px var(--sky-glow), 0 0 60px rgba(14,165,233,.1); }
    50%      { box-shadow: 0 0 42px rgba(14,165,233,.5), 0 0 90px rgba(14,165,233,.2); }
  }

  h1.name {
    font-family: var(--sans);
    font-weight: 800;
    font-size: clamp(2rem, 6vw, 3.2rem);
    letter-spacing: -.03em;
    line-height: 1;
    background: linear-gradient(90deg, #fff 30%, var(--sky));
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    margin-bottom: 10px;
    animation: fadeUp .9s .1s ease both;
  }

  .tagline {
    font-family: var(--mono);
    font-size: .78rem;
    color: var(--sky);
    letter-spacing: .14em;
    text-transform: uppercase;
    margin-bottom: 24px;
    animation: fadeUp .9s .2s ease both;
  }

  .contacts {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
    margin-bottom: 28px;
    animation: fadeUp .9s .3s ease both;
  }

  .contacts a {
    font-family: var(--mono);
    font-size: .72rem;
    color: var(--muted);
    text-decoration: none;
    border: 1px solid var(--border);
    padding: 5px 14px;
    border-radius: 20px;
    transition: color .2s, border-color .2s, box-shadow .2s;
  }

  .contacts a:hover {
    color: var(--sky);
    border-color: var(--sky);
    box-shadow: 0 0 12px var(--sky-glow);
  }

  .btn-row {
    display: flex;
    flex-wrap: wrap;
    gap: 12px;
    justify-content: center;
    animation: fadeUp .9s .4s ease both;
  }

  .btn {
    font-family: var(--mono);
    font-size: .75rem;
    letter-spacing: .08em;
    color: #000;
    background: var(--sky);
    border: none;
    padding: 9px 22px;
    border-radius: 4px;
    text-decoration: none;
    font-weight: 700;
    text-transform: uppercase;
    transition: background .2s, transform .15s, box-shadow .2s;
    cursor: pointer;
  }

  .btn:hover {
    background: #38bdf8;
    transform: translateY(-2px);
    box-shadow: 0 8px 24px rgba(14,165,233,.35);
  }

  .btn.ghost {
    background: transparent;
    color: var(--sky);
    border: 1px solid var(--sky);
  }

  .btn.ghost:hover {
    background: var(--sky-glow);
  }

  /* ── SECTION ── */
  section {
    margin-top: 60px;
    opacity: 0;
    transform: translateY(28px);
    transition: opacity .7s ease, transform .7s ease;
  }

  section.visible {
    opacity: 1;
    transform: none;
  }

  .sec-label {
    font-family: var(--mono);
    font-size: .65rem;
    letter-spacing: .2em;
    text-transform: uppercase;
    color: var(--sky);
    margin-bottom: 4px;
    display: flex;
    align-items: center;
    gap: 8px;
  }

  .sec-label::after {
    content: '';
    flex: 1;
    height: 1px;
    background: var(--border);
  }

  .sec-title {
    font-size: clamp(1.3rem, 4vw, 1.8rem);
    font-weight: 800;
    letter-spacing: -.02em;
    color: #fff;
    margin-bottom: 28px;
  }

  /* ── OBJECTIVE ── */
  .objective-box {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-left: 3px solid var(--sky);
    border-radius: 8px;
    padding: 24px 28px;
    font-size: .92rem;
    line-height: 1.75;
    color: #94a3b8;
  }

  /* ── SKILLS GRID ── */
  .pills {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .pill {
    font-family: var(--mono);
    font-size: .72rem;
    letter-spacing: .06em;
    color: var(--sky);
    background: rgba(14,165,233,.08);
    border: 1px solid rgba(14,165,233,.22);
    border-radius: 4px;
    padding: 6px 14px;
    transition: background .2s, box-shadow .2s, transform .15s;
    cursor: default;
  }

  .pill:hover {
    background: rgba(14,165,233,.18);
    box-shadow: 0 0 12px var(--sky-glow);
    transform: translateY(-2px);
  }

  /* ── CARDS ── */
  .cards {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(260px, 1fr));
    gap: 16px;
  }

  .card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px;
    transition: border-color .25s, box-shadow .25s, transform .2s;
    position: relative;
    overflow: hidden;
  }

  .card::before {
    content: '';
    position: absolute;
    top: 0; left: 0;
    width: 100%; height: 2px;
    background: linear-gradient(90deg, var(--sky), transparent);
    opacity: 0;
    transition: opacity .25s;
  }

  .card:hover {
    border-color: rgba(14,165,233,.4);
    box-shadow: 0 8px 32px rgba(14,165,233,.12);
    transform: translateY(-3px);
  }

  .card:hover::before { opacity: 1; }

  .card-icon { font-size: 1.4rem; margin-bottom: 10px; }
  .card-title {
    font-size: .95rem;
    font-weight: 700;
    color: #e2e8f0;
    margin-bottom: 6px;
  }

  .card-desc {
    font-size: .8rem;
    color: var(--muted);
    line-height: 1.6;
  }

  .card-tag {
    display: inline-block;
    font-family: var(--mono);
    font-size: .6rem;
    letter-spacing: .06em;
    color: var(--sky);
    background: rgba(14,165,233,.1);
    border: 1px solid rgba(14,165,233,.2);
    border-radius: 3px;
    padding: 2px 8px;
    margin-top: 10px;
  }

  /* ── EDUCATION ── */
  .edu-list { display: flex; flex-direction: column; gap: 16px; }

  .edu-item {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 24px;
    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    gap: 16px;
    transition: border-color .25s, box-shadow .2s;
  }

  .edu-item:hover {
    border-color: rgba(14,165,233,.35);
    box-shadow: 0 4px 20px rgba(14,165,233,.1);
  }

  .edu-degree { font-size: .95rem; font-weight: 700; color: #e2e8f0; }
  .edu-school { font-size: .8rem; color: var(--muted); margin-top: 3px; }
  .edu-score {
    font-family: var(--mono);
    font-size: .85rem;
    color: var(--sky);
    white-space: nowrap;
    font-weight: 700;
  }

  /* ── ACHIEVEMENTS ── */
  .ach-list { display: flex; flex-direction: column; gap: 12px; }
  .ach-item {
    display: flex;
    align-items: center;
    gap: 14px;
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 8px;
    padding: 14px 20px;
    transition: border-color .25s, box-shadow .2s;
  }

  .ach-item:hover {
    border-color: rgba(14,165,233,.35);
    box-shadow: 0 4px 20px rgba(14,165,233,.1);
  }

  .ach-trophy { font-size: 1.3rem; }
  .ach-text { font-size: .88rem; color: #94a3b8; line-height: 1.5; }
  .ach-text strong { color: #e2e8f0; }

  /* ── PUBLICATIONS ── */
  .pub-list { display: flex; flex-direction: column; gap: 16px; }
  .pub-item {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 20px 24px;
    transition: border-color .25s;
  }
  .pub-item:hover { border-color: rgba(14,165,233,.35); }
  .pub-title { font-weight: 700; font-size: .9rem; color: #e2e8f0; margin-bottom: 6px; }
  .pub-meta { font-family: var(--mono); font-size: .7rem; color: var(--sky); }
  .pub-meta a { color: var(--sky); text-decoration: none; }
  .pub-meta a:hover { text-decoration: underline; }

  /* ── PATENT ── */
  .patent-box {
    background: linear-gradient(135deg, rgba(14,165,233,.06), rgba(14,165,233,.02));
    border: 1px solid rgba(14,165,233,.3);
    border-radius: 12px;
    padding: 28px;
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 20px;
    align-items: center;
  }
  .patent-icon { font-size: 2.8rem; }
  .patent-name { font-size: 1.05rem; font-weight: 700; color: #e2e8f0; margin-bottom: 10px; }
  .patent-details { display: flex; flex-wrap: wrap; gap: 8px; }
  .patent-detail {
    font-family: var(--mono);
    font-size: .68rem;
    color: var(--muted);
    background: rgba(255,255,255,.04);
    border: 1px solid var(--border);
    border-radius: 4px;
    padding: 4px 10px;
  }
  .patent-detail span { color: var(--sky); }

  /* ── STATS ── */
  .stats-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
  }

  .stat-card {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 24px;
    text-align: center;
  }

  .stat-num {
    font-family: var(--mono);
    font-size: 2.2rem;
    font-weight: 700;
    color: var(--sky);
    display: block;
    line-height: 1;
    margin-bottom: 6px;
  }

  .stat-lbl {
    font-size: .75rem;
    color: var(--muted);
    letter-spacing: .06em;
    text-transform: uppercase;
  }

  /* ── PHILOSOPHY ── */
  .philosophy-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
    gap: 14px;
  }

  .phil-item {
    background: var(--bg2);
    border: 1px solid var(--border);
    border-radius: 10px;
    padding: 22px 18px;
    text-align: center;
    transition: border-color .25s, box-shadow .2s, transform .2s;
  }

  .phil-item:hover {
    border-color: rgba(14,165,233,.4);
    box-shadow: 0 8px 24px rgba(14,165,233,.12);
    transform: translateY(-4px);
  }

  .phil-icon { font-size: 1.8rem; margin-bottom: 12px; }
  .phil-text { font-size: .82rem; color: #94a3b8; line-height: 1.6; font-style: italic; }

  /* ── TYPING ── */
  .typing::after {
    content: '|';
    color: var(--sky);
    animation: blink .7s step-end infinite;
  }

  @keyframes blink {
    0%, 100% { opacity: 1; }
    50%       { opacity: 0; }
  }

  /* ── FOOTER ── */
  footer {
    margin-top: 80px;
    text-align: center;
    font-family: var(--mono);
    font-size: .68rem;
    color: var(--muted);
    letter-spacing: .1em;
    animation: fadeUp 1s 1s ease both;
  }

  /* ── ANIMATIONS ── */
  @keyframes fadeUp {
    from { opacity: 0; transform: translateY(20px); }
    to   { opacity: 1; transform: none; }
  }

  /* ── SCROLLBAR ── */
  ::-webkit-scrollbar { width: 6px; }
  ::-webkit-scrollbar-track { background: var(--bg); }
  ::-webkit-scrollbar-thumb { background: rgba(14,165,233,.3); border-radius: 3px; }
  ::-webkit-scrollbar-thumb:hover { background: var(--sky); }
</style>
</head>
<body>

<canvas id="bg-canvas"></canvas>

<div class="wrap">

  <!-- HERO -->
  <header class="hero">
    <div class="avatar-ring"><span>⚡</span></div>
    <h1 class="name">Nagella Nagavenkat</h1>
    <p class="tagline" id="tagline"></p>
    <div class="contacts">
      <a href="tel:+917670933781">📞 +91 7670933781</a>
      <a href="mailto:nagellanagavenkat@gmail.com">✉ nagellanagavenkat@gmail.com</a>
      <a>📍 Tirupathi, Andhra Pradesh</a>
      <a href="http://www.linkedin.com/in/nagella-nagavenkat26" target="_blank">🔗 LinkedIn</a>
    </div>
    <div class="btn-row">
      <a href="https://nagellanagavenkat.vercel.app/" target="_blank" class="btn">🌐 Portfolio</a>
      <a href="https://napariyojana.onrender.com/" target="_blank" class="btn">🔧 NaPariyojana</a>
      <a href="https://github.com/NagavenkatNagella" target="_blank" class="btn ghost">⌥ GitHub</a>
    </div>
  </header>

  <!-- STATS -->
  <section>
    <p class="sec-label">At a Glance</p>
    <div class="stats-grid">
      <div class="stat-card">
        <span class="stat-num" data-count="20">0</span>
        <span class="stat-lbl">Hardware Projects</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-count="5">0</span>
        <span class="stat-lbl">Software Projects</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-count="3">0</span>
        <span class="stat-lbl">Research Papers</span>
      </div>
      <div class="stat-card">
        <span class="stat-num" data-count="1">0</span>
        <span class="stat-lbl">Granted Patent</span>
      </div>
    </div>
  </section>

  <!-- OBJECTIVE -->
  <section>
    <p class="sec-label">Objective</p>
    <h2 class="sec-title">Who I Am</h2>
    <div class="objective-box">
      Motivated and enthusiastic fresher pursuing a B.Tech in Computer Science with a specialisation in AI & ML. I seek opportunities to apply my skills in software development and hardware-based innovations — bridging real-time embedded systems, machine intelligence, and full-stack web development to create impactful, scalable technology solutions.
      <br><br>
      Founder of <strong style="color:#e2e8f0">NaPariyojana</strong> — an electronics innovation platform delivering automation-based project solutions. Inventor of a patented Vertical Axis Wind Turbine (VAWT) concept under the <strong style="color:#e2e8f0">GreenFlow</strong> initiative, designed for sustainable urban energy harvesting.
    </div>
  </section>

  <!-- SKILLS -->
  <section>
    <p class="sec-label">Skills & Technologies</p>
    <h2 class="sec-title">Tech Stack</h2>
    <div class="pills">
      <div class="pill">Java</div>
      <div class="pill">Python</div>
      <div class="pill">JavaScript</div>
      <div class="pill">TypeScript</div>
      <div class="pill">C++</div>
      <div class="pill">Node.js</div>
      <div class="pill">Express</div>
      <div class="pill">MongoDB</div>
      <div class="pill">HTML / CSS</div>
      <div class="pill">SQL</div>
      <div class="pill">ESP8266</div>
      <div class="pill">NodeMCU</div>
      <div class="pill">Arduino</div>
      <div class="pill">Embedded Systems</div>
      <div class="pill">IoT Architecture</div>
      <div class="pill">Sensor Automation</div>
      <div class="pill">RFID</div>
      <div class="pill">Bluetooth / Wi-Fi</div>
      <div class="pill">OOP</div>
      <div class="pill">Git / GitHub</div>
      <div class="pill">Machine Learning</div>
      <div class="pill">Generative AI</div>
    </div>
  </section>

  <!-- EDUCATION -->
  <section>
    <p class="sec-label">Education</p>
    <h2 class="sec-title">Academic Background</h2>
    <div class="edu-list">
      <div class="edu-item">
        <div>
          <div class="edu-degree">B.Tech – Computer Science &amp; Engineering (AI &amp; ML)</div>
          <div class="edu-school">Kalasalingam Academy of Research &amp; Education, Krishnan Koil, T.N. · 2022–2026</div>
        </div>
        <div class="edu-score">8.35 / 10</div>
      </div>
      <div class="edu-item">
        <div>
          <div class="edu-degree">Intermediate – MPC</div>
          <div class="edu-school">Narayana Junior College, Tirupathi, A.P. · 2022</div>
        </div>
        <div class="edu-score">82.7%</div>
      </div>
      <div class="edu-item">
        <div>
          <div class="edu-degree">Secondary School of Education</div>
          <div class="edu-school">Model Academy EM School, Renigunta, A.P. · 2020</div>
        </div>
        <div class="edu-score">96.83%</div>
      </div>
    </div>
  </section>

  <!-- SOFTWARE PROJECTS -->
  <section>
    <p class="sec-label">Projects · Software</p>
    <h2 class="sec-title">Software Engineering</h2>
    <div class="cards">
      <div class="card">
        <div class="card-icon">🏥</div>
        <div class="card-title">Hospital Management System</div>
        <div class="card-desc">Console-based system for patient registration, appointment booking, and billing using Core Java, OOP, and ArrayList.</div>
        <span class="card-tag">Java · OOP</span>
      </div>
      <div class="card">
        <div class="card-icon">🎮</div>
        <div class="card-title">Number Guessing Game</div>
        <div class="card-desc">Java Swing game with gradient UI, animations, progress tracking, hints, guess history, and replay options.</div>
        <span class="card-tag">Java Swing</span>
      </div>
      <div class="card">
        <div class="card-icon">🤖</div>
        <div class="card-title">Conversational Q&amp;A Chatbot</div>
        <div class="card-desc">Interactive chatbot using Python and Generative AI API for answering user queries intelligently.</div>
        <span class="card-tag">Python · Gen AI</span>
      </div>
      <div class="card">
        <div class="card-icon">💬</div>
        <div class="card-title">LAN-Based Chat Application</div>
        <div class="card-desc">Real-time chat using Python socket programming with login, file sharing, and client-side message control.</div>
        <span class="card-tag">Python · Sockets</span>
      </div>
      <div class="card">
        <div class="card-icon">🛒</div>
        <div class="card-title">NaPariyojana</div>
        <div class="card-desc">Responsive web app for browsing, customising, and purchasing Arduino/IoT projects with integrated email ordering.</div>
        <span class="card-tag">HTML · CSS · JS</span>
      </div>
    </div>
  </section>

  <!-- HARDWARE PROJECTS -->
  <section>
    <p class="sec-label">Projects · Hardware</p>
    <h2 class="sec-title">Embedded & IoT Engineering</h2>
    <div class="cards">
      <div class="card">
        <div class="card-icon">🌱</div>
        <div class="card-title">Auto Irrigation + Laser Security</div>
        <div class="card-desc">Automated soil moisture-based irrigation with laser intrusion detection for crop safety using sensors and relays.</div>
        <span class="card-tag">ESP8266 · Sensors</span>
      </div>
      <div class="card">
        <div class="card-icon">❤️</div>
        <div class="card-title">Digital Stethoscope</div>
        <div class="card-desc">Wi-Fi-enabled MAX9814 &amp; ESP8266 device capturing heart/lung sounds with LCD readout and live waveform dashboard.</div>
        <span class="card-tag">ESP8266 · MAX9814</span>
      </div>
      <div class="card">
        <div class="card-icon">🌬️</div>
        <div class="card-title">Customised VAWT – Patented</div>
        <div class="card-desc">Vertical Axis Wind Turbine designed for urban use, converting wind energy into storable electricity. Patent granted 2026.</div>
        <span class="card-tag">Patent #474355-001</span>
      </div>
      <div class="card">
        <div class="card-icon">🤟</div>
        <div class="card-title">Sign Language Recognition</div>
        <div class="card-desc">Flex sensor-based system detecting finger bends and transmitting corresponding letters to LCD and mobile via Bluetooth.</div>
        <span class="card-tag">Arduino · Bluetooth</span>
      </div>
      <div class="card">
        <div class="card-icon">💨</div>
        <div class="card-title">Air Quality Monitoring</div>
        <div class="card-desc">MQ135 sensor with ESP8266 displaying live pollution data (CO₂, NH₃, etc.) on an LCD with cloud logging.</div>
        <span class="card-tag">ESP8266 · MQ135</span>
      </div>
      <div class="card">
        <div class="card-icon">🦺</div>
        <div class="card-title">SEGOL – Smart Security System</div>
        <div class="card-desc">Intelligent surveillance with motion, touch, pressure, accelerometer, GPS, GSM, RFID locking, and cloud data transfer.</div>
        <span class="card-tag">IoT · GSM · GPS</span>
      </div>
      <div class="card">
        <div class="card-icon">🏭</div>
        <div class="card-title">Edge AI – Textile Fault Detection</div>
        <div class="card-desc">Edge-AI system analyzing vibration, temperature, speed, and load data to detect faults and optimise production efficiency.</div>
        <span class="card-tag">Edge AI · ML</span>
      </div>
      <div class="card">
        <div class="card-icon">🚿</div>
        <div class="card-title">Acoustic Stress Monitor</div>
        <div class="card-desc">Voice and sound analysis to assess stress levels, automatically triggering a smart water delivery system.</div>
        <span class="card-tag">Audio · Automation</span>
      </div>
      <div class="card">
        <div class="card-icon">♻️</div>
        <div class="card-title">Plastic Bottle Vending Machine</div>
        <div class="card-desc">Accepts plastic bottles via IR/proximity sensors, dispensing a reward coupon as a recycling incentive.</div>
        <span class="card-tag">IR Sensors</span>
      </div>
      <div class="card">
        <div class="card-icon">🚗</div>
        <div class="card-title">EV Wireless Charging Lane</div>
        <div class="card-desc">Prototype wireless charging lane for electric vehicles using embedded coils and power control logic.</div>
        <span class="card-tag">Power Electronics</span>
      </div>
    </div>
  </section>

  <!-- ACHIEVEMENTS -->
  <section>
    <p class="sec-label">Recognition</p>
    <h2 class="sec-title">Achievements & Awards</h2>
    <div class="ach-list">
      <div class="ach-item">
        <span class="ach-trophy">🥇</span>
        <div class="ach-text"><strong>First Prize</strong> — KARE IEEE RAS Project Showcase 2.0</div>
      </div>
      <div class="ach-item">
        <span class="ach-trophy">🥈</span>
        <div class="ach-text"><strong>Second Prize</strong> — Grand Finale, KARE IEEE Robotics &amp; Automation Society</div>
      </div>
      <div class="ach-item">
        <span class="ach-trophy">🥈</span>
        <div class="ach-text"><strong>Second Prize</strong> — IEEE Project Expo 2025, IEEE Computer Society</div>
      </div>
      <div class="ach-item">
        <span class="ach-trophy">⭐</span>
        <div class="ach-text"><strong>Child Scientist Award — Golden Star</strong> — Recognised for scientific innovation at school level</div>
      </div>
    </div>
  </section>

  <!-- PUBLICATIONS -->
  <section>
    <p class="sec-label">Research</p>
    <h2 class="sec-title">Publications</h2>
    <div class="pub-list">
      <div class="pub-item">
        <div class="pub-title">Personalized Ayurvedic Medicine Recommendations Using Decision Tree Algorithms and Prakriti Analysis</div>
        <div class="pub-meta">Presented at IEEE Conference · DOI: <a href="https://ieeexplore.ieee.org/document/10895343?denied=" target="_blank">10.1109/ICERCS63125.2024.10895343</a></div>
      </div>
      <div class="pub-item">
        <div class="pub-title">Sustainable Smart Vertical Axis Wind Turbine System for Highways with IoT-Based Monitoring and Energy Management</div>
        <div class="pub-meta">Research Paper · In Progress</div>
      </div>
      <div class="pub-item">
        <div class="pub-title">Bridging the Silence: Real-Time Gesture-to-Speech Sign Language Translation for the Deaf using K-NN Classifier</div>
        <div class="pub-meta">Research Paper</div>
      </div>
    </div>
  </section>

  <!-- PATENT -->
  <section>
    <p class="sec-label">Intellectual Property</p>
    <h2 class="sec-title">Design Patent</h2>
    <div class="patent-box">
      <div class="patent-icon">🏛️</div>
      <div>
        <div class="patent-name">Wind-Powered Wireless Charging System for Electric Vehicles</div>
        <div class="patent-details">
          <span class="patent-detail">Design No. <span>474355-001</span></span>
          <span class="patent-detail">Class <span>13-02</span></span>
          <span class="patent-detail">Issued <span>19 Jan 2026</span></span>
          <span class="patent-detail">Authority <span>Patent Office, Govt. of India</span></span>
        </div>
      </div>
    </div>
  </section>

  <!-- PHILOSOPHY -->
  <section>
    <p class="sec-label">Engineering Ethos</p>
    <h2 class="sec-title">Philosophy</h2>
    <div class="philosophy-grid">
      <div class="phil-item">
        <div class="phil-icon">🔗</div>
        <div class="phil-text">Build intelligent systems, not isolated projects.</div>
      </div>
      <div class="phil-item">
        <div class="phil-icon">🌿</div>
        <div class="phil-text">Engineer sustainability, not temporary solutions.</div>
      </div>
      <div class="phil-item">
        <div class="phil-icon">🔄</div>
        <div class="phil-text">Integrate hardware, software, and user experience seamlessly.</div>
      </div>
    </div>
  </section>

  <footer>
    <p>Engineering Sustainable &amp; Intelligent Systems for Real-World Impact</p>
    <p style="margin-top:6px; color: rgba(100,116,139,.5);">Nagella Nagavenkat · Tirupathi, A.P. · nagellanagavenkat@gmail.com</p>
  </footer>

</div>

<script>
/* ── PARTICLE CANVAS ── */
const canvas = document.getElementById('bg-canvas');
const ctx = canvas.getContext('2d');
let W, H, particles = [];

function resize() {
  W = canvas.width  = window.innerWidth;
  H = canvas.height = window.innerHeight;
}

function initParticles() {
  particles = [];
  for (let i = 0; i < 80; i++) {
    particles.push({
      x: Math.random() * W,
      y: Math.random() * H,
      r: Math.random() * 1.5 + .4,
      vx: (Math.random() - .5) * .3,
      vy: (Math.random() - .5) * .3,
      a: Math.random()
    });
  }
}

function drawParticles() {
  ctx.clearRect(0, 0, W, H);
  particles.forEach(p => {
    p.x += p.vx; p.y += p.vy;
    if (p.x < 0) p.x = W; if (p.x > W) p.x = 0;
    if (p.y < 0) p.y = H; if (p.y > H) p.y = 0;
    ctx.beginPath();
    ctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
    ctx.fillStyle = `rgba(14,165,233,${p.a * .7})`;
    ctx.fill();
  });

  // draw connecting lines
  for (let i = 0; i < particles.length; i++) {
    for (let j = i + 1; j < particles.length; j++) {
      const dx = particles[i].x - particles[j].x;
      const dy = particles[i].y - particles[j].y;
      const d  = Math.sqrt(dx*dx + dy*dy);
      if (d < 120) {
        ctx.beginPath();
        ctx.moveTo(particles[i].x, particles[i].y);
        ctx.lineTo(particles[j].x, particles[j].y);
        ctx.strokeStyle = `rgba(14,165,233,${.15 * (1 - d/120)})`;
        ctx.lineWidth = .5;
        ctx.stroke();
      }
    }
  }
  requestAnimationFrame(drawParticles);
}

resize();
initParticles();
drawParticles();
window.addEventListener('resize', () => { resize(); initParticles(); });

/* ── TYPEWRITER ── */
const phrases = [
  'IoT Systems Engineer',
  'Renewable Energy Innovator',
  'Full Stack Developer',
  'Embedded Hardware Enthusiast',
  'AI & ML Practitioner'
];
let pi = 0, ci = 0, deleting = false;
const el = document.getElementById('tagline');
el.classList.add('typing');

function type() {
  const phrase = phrases[pi];
  if (!deleting) {
    el.textContent = phrase.slice(0, ++ci);
    if (ci === phrase.length) { deleting = true; setTimeout(type, 1800); return; }
  } else {
    el.textContent = phrase.slice(0, --ci);
    if (ci === 0) { deleting = false; pi = (pi + 1) % phrases.length; }
  }
  setTimeout(type, deleting ? 45 : 80);
}
type();

/* ── SCROLL REVEAL ── */
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => { if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); } });
}, { threshold: .08 });

document.querySelectorAll('section').forEach(s => observer.observe(s));

/* ── COUNT-UP ── */
const countObserver = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (!e.isIntersecting) return;
    const el = e.target;
    const target = +el.dataset.count;
    let current = 0;
    const step = target / 40;
    const timer = setInterval(() => {
      current = Math.min(current + step, target);
      el.textContent = Math.round(current);
      if (current >= target) clearInterval(timer);
    }, 30);
    countObserver.unobserve(el);
  });
}, { threshold: .5 });

document.querySelectorAll('.stat-num').forEach(el => countObserver.observe(el));
</script>
</body>
</html>
