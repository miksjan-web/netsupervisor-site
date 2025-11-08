<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>NetSupervisor for macOS</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="description" content="NetSupervisor — advanced network monitoring and diagnostics for macOS.">
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
    }

    header img {
      width: 80px;
      height: 80px;
      border-radius: 16px;
      box-shadow: 0 4px 18px rgba(0,0,0,0.12);
    }

    header h1 {
      margin: 15px 0 6px;
      font-size: 42px;
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
  <img src="icon-1024_v2.png" alt="NetSupervisor icon">
  <h1>NetSupervisor</h1>
  <p>Network monitoring &amp; diagnostics for macOS</p>
</header>

<main>

  <section>
    <h2>Keep your network under control</h2>
    <p>
      NetSupervisor combines speed testing, device discovery, monitoring and diagnostics into one clean,
      native macOS application.
    </p>
    <ul>
      <li>Instant overview of connection, latency and uptime</li>
      <li>Automatic monitoring and clear alerts before users notice issues</li>
      <li>All key tools in one place – simple, fast and privacy-friendly</li>
    </ul>

    <div class="hero-card">
      <div class="hero-label">Example network snapshot</div>
      <div class="hero-metric-row">
        <div class="hero-metric">
          <strong>9.3 Mb/s</strong>
          <span>Average download</span>
        </div>
        <div class="hero-metric">
          <strong>2.1 Mb/s</strong>
          <span>Average upload</span>
        </div>
        <div class="hero-metric">
          <strong>42 ms</strong>
          <span>Ping</span>
        </div>
      </div>
      <div class="hero-metric-row">
        <div class="hero-metric">
          <strong>4</strong>
          <span>Monitored hosts</span>
        </div>
        <div class="hero-metric">
          <strong>0</strong>
          <span>Incidents</span>
        </div>
        <div class="hero-metric">
          <strong>6</strong>
          <span>LAN devices</span>
        </div>
      </div>
      <small style="color:var(--muted);">Visualization based on the real NetSupervisor dashboard interface.</small>
    </div>
  </section>

  <section>
    <h2>Why NetSupervisor?</h2>
    <div class="cards">
      <div class="card">
        <h3>Instant clarity</h3>
        <p>One dashboard for connection details, recent tests, monitored hosts and alerts.</p>
      </div>
      <div class="card">
        <h3>Fewer outages</h3>
        <p>Continuous monitoring and clear thresholds help you react before users complain.</p>
      </div>
      <div class="card">
        <h3>Professional toolkit</h3>
        <p>Ping, traceroute, port scan, DNS, Whois, Wake-on-LAN and exportable reports – all in one app.</p>
      </div>
      <div class="card">
        <h3>Privacy built-in</h3>
        <p>Everything runs locally on your Mac. No accounts, no analytics, no data collection.</p>
      </div>
    </div>
  </section>

  <section>
    <h2>Main Features</h2>
    <p>Explore all key tools included in NetSupervisor.</p>
    <div class="features-grid">
      <div><strong>Dashboard</strong><br>Overview of connection, tests and monitoring.</div>
      <div><strong>Speed Test</strong><br>Download, upload, ping &amp; jitter with history.</div>
      <div><strong>LAN Scanner</strong><br>Find all devices in your local network.</div>
      <div><strong>Monitoring</strong><br>Set thresholds and get alerts on issues.</div>
      <div><strong>Topology</strong><br>Visualize how your devices connect.</div>
      <div><strong>Ping &amp; Traceroute</strong><br>Diagnose network paths and delays.</div>
      <div><strong>DNS &amp; Whois</strong><br>Get detailed information about domains.</div>
      <div><strong>Reports</strong><br>Export data for documentation or analysis.</div>
    </div>
  </section>

  <section>
    <h2>Who is it for?</h2>
    <ul>
      <li>Network &amp; system administrators</li>
      <li>ISPs and IT support teams</li>
      <li>Small businesses managing their own infrastructure</li>
      <li>Advanced users who want full insight into their home network</li>
    </ul>
  </section>

  <section>
    <h2>Privacy &amp; Transparency</h2>
    <p>
      NetSupervisor runs fully on your Mac. No cloud services, no tracking, no hidden data collection.
      Learn more in the <a href="privacy.html">Privacy Policy</a>.
    </p>
  </section>

</main>

<footer>
  <p>
    <a href="support.html">Support</a> • 
    <a href="privacy.html">Privacy Policy</a>
  </p>
  <p>© Jan Mikš • NetSupervisor for macOS</p>
</footer>

</body>
</html>
