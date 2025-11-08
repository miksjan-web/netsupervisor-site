<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>NetSupervisor for macOS</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="NetSupervisor — network monitoring and diagnostics for macOS.">
  <style>
    :root {
      --bg: #f5f5f7;
      --card-bg: #ffffff;
      --border: #e5e5ea;
      --text-main: #1d1d1f;
      --muted: #6e6e73;
      --accent: #0071e3;
      --radius: 14px;
      --shadow-soft: 0 6px 24px rgba(0, 0, 0, 0.06);
      --font: -apple-system, BlinkMacSystemFont, system-ui, sans-serif;
    }

    body {
      margin: 0;
      font-family: var(--font);
      background-color: var(--bg);
      color: var(--text-main);
      line-height: 1.6;
    }

    a {
      color: var(--accent);
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }

    header {
      background: linear-gradient(140deg, #ffffff, #eef3ff);
      border-bottom: 1px solid var(--border);
      text-align: center;
      padding: 40px 20px 30px;
      position: relative;
    }

    .lang-switch {
      position: absolute;
      top: 20px;
      right: 20px;
      display: inline-flex;
      border-radius: 999px;
      padding: 2px;
      background: rgba(0, 0, 0, 0.05);
      font-size: 12px;
    }

    .lang-btn {
      border: none;
      background: transparent;
      padding: 4px 10px;
      border-radius: 999px;
      cursor: pointer;
      color: var(--muted);
      font-family: var(--font);
      font-size: 13px;
    }

    .lang-btn.active {
      background: #ffffff;
      color: var(--accent);
      box-shadow: 0 1px 4px rgba(0, 0, 0, 0.12);
    }

    header h1 {
      margin: 15px 0 6px;
      font-size: 48px;
      font-weight: 700;
      letter-spacing: -0.02em;
    }

    header p {
      color: var(--muted);
      font-size: 16px;
      margin: 0;
    }

    main {
      max-width: 1080px;
      margin: 0 auto;
      padding: 30px 20px 40px;
    }

    section {
      margin-bottom: 40px;
    }

    h2 {
      font-size: 24px;
      margin-bottom: 8px;
    }

    p {
      color: #3a3a3c;
      font-size: 15px;
      margin-bottom: 10px;
    }

    ul {
      color: #3a3a3c;
      font-size: 14px;
      padding-left: 18px;
    }

    .hero-card {
      background: var(--card-bg);
      border-radius: var(--radius);
      padding: 16px;
      border: 1px solid var(--border);
      box-shadow: var(--shadow-soft);
      font-size: 13px;
      margin: 20px auto;
      max-width: 420px;
      text-align: left;
    }

    .hero-label {
      font-size: 11px;
      color: var(--muted);
      margin-bottom: 6px;
      text-transform: uppercase;
      letter-spacing: 0.14em;
    }

    .hero-metric-row {
      display: flex;
      justify-content: space-between;
      margin-bottom: 6px;
    }

    .hero-metric strong {
      display: block;
      font-size: 15px;
    }

    .hero-metric span {
      font-size: 11px;
      color: var(--muted);
    }

    .cards {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 16px;
    }

    .card {
      background: var(--card-bg);
      border-radius: var(--radius);
      padding: 16px;
      border: 1px solid var(--border);
      box-shadow: var(--shadow-soft);
      font-size: 14px;
    }

    .card h3 {
      margin-top: 0;
      margin-bottom: 6px;
      font-size: 16px;
    }

    .features-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
      gap: 14px;
      margin-top: 14px;
    }

    .features-grid div {
      background: var(--card-bg);
      border-radius: var(--radius);
      border: 1px solid var(--border);
      padding: 12px;
      box-shadow: 0 3px 10px rgba(0,0,0,0.04);
    }

    footer {
      text-align: center;
      font-size: 12px;
      color: var(--muted);
      padding: 30px 10px 40px;
      border-top: 1px solid var(--border);
    }

    footer a {
      margin: 0 8px;
      color: var(--accent);
    }
  </style>
</head>
<body>

<header>
  <div class="lang-switch">
    <button class="lang-btn active" data-lang="en" onclick="setLang('en')">EN</button>
    <button class="lang-btn" data-lang="cz" onclick="setLang('cz')">CZ</button>
  </div>
  <h1>NetSupervisor</h1>
  <p>Network monitoring &amp; diagnostics for macOS</p>
</header>

<main>

  <section>
    <div data-lang-content="en">
      <h2>Keep your network under control</h2>
      <p>
        NetSupervisor combines speed testing, device discovery, monitoring and diagnostics into one clean,
        native macOS application.
      </p>
      <ul>
        <li>Instant overview of connection, latency and uptime</li>
        <li>Automatic monitoring and alerts before users notice issues</li>
        <li>All key tools in one place – simple, fast and privacy-friendly</li>
      </ul>
    </div>

    <div data-lang-content="cz" style="display:none;">
      <h2>Mějte svou síť pod kontrolou</h2>
      <p>
        NetSupervisor spojuje test rychlosti, vyhledávání zařízení, monitoring a diagnostiku do jedné přehledné
        aplikace pro macOS.
      </p>
      <ul>
        <li>Okamžitý přehled o připojení, latenci a dostupnosti</li>
        <li>Automatický monitoring a upozornění dřív, než si problému všimnou uživatelé</li>
        <li>Všechny klíčové nástroje na jednom místě – jednoduché a přehledné</li>
      </ul>
    </div>

    <div class="hero-card">
      <div class="hero-label">Example network snapshot</div>
      <div class="hero-metric-row">
        <div class="hero-metric"><strong>9.3 Mb/s</strong><span>Average download</span></div>
        <div class="hero-metric"><strong>2.1 Mb/s</strong><span>Average upload</span></div>
        <div class="hero-metric"><strong>42 ms</strong><span>Ping</span></div>
      </div>
      <div class="hero-metric-row">
        <div class="hero-metric"><strong>4</strong><span>Monitored hosts</span></div>
        <div class="hero-metric"><strong>0</strong><span>Incidents</span></div>
        <div class="hero-metric"><strong>6</strong><span>LAN devices</span></div>
      </div>
      <small style="color:var(--muted);">Visualization based on the real NetSupervisor dashboard interface.</small>
    </div>
  </section>

  <section>
    <h2 data-lang-content="en">Why NetSupervisor?</h2>
    <h2 data-lang-content="cz" style="display:none;">Proč právě NetSupervisor?</h2>
    <div class="cards">
      <div class="card" data-lang-content="en">
        <h3>Instant clarity</h3>
        <p>One dashboard for connection details, recent tests, monitored hosts and alerts.</p>
      </div>
      <div class="card" data-lang-content="en">
        <h3>Fewer outages</h3>
        <p>Continuous monitoring helps you react before users complain.</p>
      </div>
      <div class="card" data-lang-content="en">
        <h3>Professional toolkit</h3>
        <p>Ping, traceroute, port scan, DNS, Whois, Wake-on-LAN and reports – all in one app.</p>
      </div>

      <div class="card" data-lang-content="cz" style="display:none;">
        <h3>Okamžitý přehled</h3>
        <p>Jeden panel pro připojení, testy, sledované cíle a upozornění.</p>
      </div>
      <div class="card" data-lang-content="cz" style="display:none;">
        <h3>Méně výpadků</h3>
        <p>Průběžný monitoring umožní reagovat dřív, než si problému někdo všimne.</p>
      </div>
      <div class="card" data-lang-content="cz" style="display:none;">
        <h3>Profesionální nástroje</h3>
        <p>Ping, Traceroute, Port Scan, DNS, Whois, Wake-on-LAN i reporty – vše v jedné aplikaci.</p>
      </div>
    </div>
  </section>

  <section>
    <h2 data-lang-content="en">Main Features</h2>
    <h2 data-lang-content="cz" style="display:none;">Hlavní funkce</h2>
    <div class="features-grid">
      <div><strong>Dashboard</strong><br><span data-lang-content="en">Overview of connection, tests and monitoring.</span><span data-lang-content="cz" style="display:none;">Přehled připojení, testů a monitoringu.</span></div>
      <div><strong>Speed Test</strong><br><span data-lang-content="en">Download, upload, ping &amp; jitter with history.</span><span data-lang-content="cz" style="display:none;">Download, upload, ping a jitter s historií.</span></div>
      <div><strong>LAN Scanner</strong><br><span data-lang-content="en">Find devices in your network.</span><span data-lang-content="cz" style="display:none;">Najděte zařízení ve vaší síti.</span></div>
      <div><strong>Monitoring</strong><br><span data-lang-content="en">Thresholds and alerts on issues.</span><span data-lang-content="cz" style="display:none;">Prahy a upozornění na problémy.</span></div>
      <div><strong>Topology</strong><br><span data-lang-content="en">Visual map of your network.</span><span data-lang-content="cz" style="display:none;">Vizualizace sítě.</span></div>
      <div><strong>Ping &amp; Traceroute</strong><br><span data-lang-content="en">Diagnose routes and response times.</span><span data-lang-content="cz" style="display:none;">Diagnostika cest a odezvy.</span></div>
      <div><strong>DNS &amp; Whois</strong><br><span data-lang-content="en">Domain and record details.</span><span data-lang-content="cz" style="display:none;">Informace o doménách a záznamech.</span></div>
      <div><strong>Reports</strong><br><span data-lang-content="en">Export results for analysis.</span><span data-lang-content="cz" style="display:none;">Export výsledků pro analýzu.</span></div>
    </div>
  </section>

  <section>
    <h2 data-lang-content="en">Who is it for?</h2>
    <h2 data-lang-content="cz" style="display:none;">Pro koho je určen</h2>
    <ul data-lang-content="en">
      <li>Network &amp; system administrators</li>
      <li>IT support and ISPs</li>
      <li>Small businesses managing their infrastructure</li>
      <li>Advanced home users</li>
    </ul>
    <ul data-lang-content="cz" style="display:none;">
      <li>Správce sítí a administrátory</li>
      <li>ISP a interní IT týmy</li>
      <li>Menší firmy se svou infrastrukturou</li>
      <li>Pokročilé domácí uživatele</li>
    </ul>
  </section>

  <section>
    <h2 data-lang-content="en">Privacy &amp; Transparency</h2>
    <h2 data-lang-content="cz" style="display:none;">Soukromí &amp; Transparentnost</h2>
    <p data-lang-content="en">NetSupervisor runs fully on your Mac. No tracking, no analytics, no cloud. Learn more in the <a href="privacy.html">Privacy Policy</a>.</p>
    <p data-lang-content="cz" style="display:none;">NetSupervisor běží zcela na vašem Macu. Žádné sledování, analytika ani cloud. Více v <a href="privacy.html">Zásadách ochrany soukromí</a>.</p>
  </section>

</main>

<footer>
  <p>
    <a href="support.html">Support</a> • 
    <a href="privacy.html">Privacy Policy</a>
  </p>
  <p>© Jan Mikš • NetSupervisor for macOS</p>
</footer>

<script>
function setLang(lang) {
  document.querySelectorAll('.lang-btn').forEach(btn => {
    btn.classList.toggle('active', btn.dataset.lang === lang);
  });
  document.querySelectorAll('[data-lang-content]').forEach(el => {
    el.style.display = (el.getAttribute('data-lang-content') === lang) ? '' : 'none';
  });
}
</script>

</body>
</html>
