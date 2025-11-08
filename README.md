<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>NetSupervisor for macOS</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description"
          content="NetSupervisor is an all-in-one network diagnostics and monitoring tool for macOS.">
    <style>
        :root {
            --bg: #f5f5f7;
            --card-bg: #ffffff;
            --border: #e5e5ea;
            --text-main: #1d1d1f;
            --muted: #6e6e73;
            --accent: #0071e3;
            --radius: 14px;
            --shadow: 0 10px 30px rgba(0, 0, 0, 0.06);
            --font: -apple-system, BlinkMacSystemFont, system-ui, -system-ui, -sans-serif, sans-serif;
        }

        * { box-sizing: border-box; }

        body {
            margin: 0;
            font-family: var(--font);
            background-color: var(--bg);
            color: var(--text-main);
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, #ffffff, #f0f4ff);
            border-bottom: 1px solid var(--border);
        }

        .container {
            max-width: 1080px;
            margin: 0 auto;
            padding: 20px;
        }

        .nav-row {
            display: flex;
            align-items: center;
            justify-content: space-between;
            gap: 16px;
            margin-bottom: 10px;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .logo-pill {
            width: 30px;
            height: 30px;
            border-radius: 9px;
            background: #000;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 16px;
            color: #fff;
            box-shadow: 0 4px 12px rgba(0,0,0,0.35);
        }

        .brand-title {
            font-weight: 600;
            letter-spacing: 0.02em;
        }

        .brand-sub {
            font-size: 11px;
            color: var(--muted);
        }

        nav a {
            margin-left: 14px;
            font-size: 14px;
            text-decoration: none;
            color: var(--accent);
        }

        nav a:hover { text-decoration: underline; }

        .lang-switch {
            display: inline-flex;
            border-radius: 999px;
            padding: 2px;
            background: rgba(0,0,0,0.04);
            font-size: 12px;
        }

        .lang-btn {
            border: none;
            background: transparent;
            padding: 4px 10px;
            border-radius: 999px;
            cursor: pointer;
            color: var(--muted);
        }

        .lang-btn.active {
            background: #ffffff;
            color: var(--accent);
            box-shadow: 0 1px 4px rgba(0,0,0,0.12);
        }

        .hero {
            display: grid;
            grid-template-columns: minmax(0, 3fr) minmax(0, 2.8fr);
            gap: 24px;
            align-items: center;
            padding: 10px 0 24px;
        }

        h1 {
            font-size: 30px;
            margin: 0 0 8px;
        }

        .hero-sub {
            font-size: 16px;
            color: #3a3a3c;
            margin-bottom: 14px;
        }

        .hero-list {
            font-size: 14px;
            color: var(--muted);
            margin: 0 0 16px;
        }

        .hero-list li { margin-bottom: 2px; }

        .btn-row {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            align-items: center;
        }

        .btn-primary {
            padding: 9px 18px;
            border-radius: 999px;
            background: var(--accent);
            color: #fff;
            border: none;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 8px;
            box-shadow: var(--shadow);
        }

        .btn-primary span.icon { font-size: 16px; }

        .btn-ghost {
            padding: 8px 14px;
            border-radius: 999px;
            border: 1px solid var(--border);
            background: transparent;
            color: var(--accent);
            font-size: 13px;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            cursor: pointer;
        }

        .hero-card {
            background: rgba(255,255,255,0.96);
            border-radius: var(--radius);
            padding: 14px 14px 10px;
            box-shadow: var(--shadow);
            border: 1px solid var(--border);
            font-size: 12px;
        }

        .hero-label {
            font-size: 11px;
            color: var(--muted);
            margin-bottom: 4px;
            text-transform: uppercase;
            letter-spacing: 0.12em;
        }

        .hero-metric-row {
            display: flex;
            justify-content: space-between;
            gap: 8px;
            margin-bottom: 4px;
        }

        .hero-metric {
            flex: 1;
        }

        .hero-metric strong {
            display: block;
            font-size: 14px;
        }

        .hero-metric span {
            font-size: 10px;
            color: var(--muted);
        }

        .note {
            font-size: 11px;
            color: var(--muted);
            margin-top: 4px;
        }

        .section {
            margin: 26px 0;
        }

        .section h2 {
            font-size: 22px;
            margin-bottom: 8px;
        }

        .section p {
            color: #3a3a3c;
            font-size: 14px;
            margin-bottom: 10px;
        }

        .cards {
            display: grid;
            grid-template-columns: repeat(3, minmax(0, 1fr));
            gap: 14px;
        }

        .card {
            background: var(--card-bg);
            border-radius: var(--radius);
            padding: 14px 12px;
            border: 1px solid var(--border);
            box-shadow: 0 3px 12px rgba(0,0,0,0.04);
            font-size: 13px;
        }

        .card h3 {
            margin: 0 0 4px;
            font-size: 15px;
        }

        .card p {
            margin: 0 0 6px;
            font-size: 13px;
            color: #3a3a3c;
        }

        .card small {
            color: var(--muted);
            font-size: 11px;
        }

        .pill {
            display: inline-block;
            padding: 2px 8px;
            border-radius: 999px;
            font-size: 10px;
            background: #f2f2f7;
            color: var(--muted);
            margin-bottom: 4px;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(4, minmax(0,1fr));
            gap: 10px;
            font-size: 12px;
            margin-top: 10px;
        }

        .features-grid div {
            background: var(--card-bg);
            border-radius: 10px;
            padding: 8px 9px;
            border: 1px solid var(--border);
        }

        .features-grid strong {
            display: block;
            font-size: 13px;
            margin-bottom: 2px;
        }

        .cta-section {
            margin: 32px 0 10px;
            text-align: center;
            padding: 18px 16px 22px;
            background: linear-gradient(135deg, #ffffff, #e9f3ff);
            border-radius: var(--radius);
            border: 1px solid var(--border);
            box-shadow: var(--shadow);
        }

        .cta-section h2 {
            margin: 0 0 6px;
            font-size: 22px;
        }

        .cta-section p {
            margin: 0 0 12px;
            font-size: 14px;
            color: #3a3a3c;
        }

        footer {
            padding: 14px 20px 22px;
            font-size: 11px;
            color: var(--muted);
            text-align: center;
        }

        /* Responsive */
        @media (max-width: 800px) {
            .hero { grid-template-columns: 1fr; }
            .cards { grid-template-columns: 1fr 1fr; }
            .features-grid { grid-template-columns: 1fr 1fr; }
        }

        @media (max-width: 540px) {
            .cards { grid-template-columns: 1fr; }
            .features-grid { grid-template-columns: 1fr; }
            .nav-row {
                flex-direction: column;
                align-items: flex-start;
            }
        }
    </style>
</head>
<body>
<header>
    <div class="container">
        <div class="nav-row">
            <div class="brand">
                <div class="logo-pill">👁‍🗨</div>
                <div>
                    <div class="brand-title">NetSupervisor</div>
                    <div class="brand-sub">Network diagnostics &amp; monitoring for macOS</div>
                </div>
            </div>
            <div>
                <nav>
                    <a href="#top" onclick="scrollTo(0,0)">Home</a>
                    <a href="support.html">Support</a>
                    <a href="privacy.html">Privacy</a>
                </nav>
            </div>
            <div class="lang-switch">
                <button class="lang-btn active" data-lang="en" onclick="setLang('en')">EN</button>
                <button class="lang-btn" data-lang="cz" onclick="setLang('cz')">CZ</button>
            </div>
        </div>

        <!-- HERO -->
        <section class="hero" id="top">
            <div>
                <!-- EN -->
                <div class="lang-block" data-lang-content="en">
                    <h1>Control your network from one clean dashboard.</h1>
                    <p class="hero-sub">
                        NetSupervisor brings speed tests, monitoring, scanning and diagnostics
                        into a single, macOS-native app.
                    </p>
                    <ul class="hero-list">
                        <li>Measure download, upload, ping &amp; jitter</li>
                        <li>Discover devices in your LAN and monitor key hosts</li>
                        <li>Use pro tools: Ping, Traceroute, DNS, Whois, Port Scan, Wake-on-LAN</li>
                    </ul>
                </div>
                <!-- CZ -->
                <div class="lang-block" data-lang-content="cz" style="display:none">
                    <h1>Mějte svou síť pod kontrolou na jednom místě.</h1>
                    <p class="hero-sub">
                        NetSupervisor spojuje test rychlosti, monitoring, skenování a diagnostiku
                        do jedné přehledné aplikace pro macOS.
                    </p>
                    <ul class="hero-list">
                        <li>Změřte download, upload, ping a jitter</li>
                        <li>Najděte zařízení v LAN a sledujte jejich dostupnost</li>
                        <li>Využijte nástroje: Ping, Traceroute, DNS, Whois, Port Scan, Wake-on-LAN</li>
                    </ul>
                </div>

                <div class="btn-row">
                    <!-- TODO: doplň svůj App Store odkaz -->
                    <a class="btn-primary" href="#">
                        <span class="icon"></span>
                        <span>Download on the Mac App Store</span>
                    </a>
                    <a class="btn-ghost" href="support.html">Support &amp; Documentation →</a>
                </div>
            </div>

            <!-- jednoduchá grafika / mini dashboard -->
            <div class="hero-card">
                <div class="hero-label">Network overview</div>
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
                <div class="note">
                    UI inspired by the actual NetSupervisor dashboard.
                </div>
            </div>
        </section>
    </div>
</header>

<main>
    <div class="container">

        <!-- CORE BENEFITS -->
        <section class="section">
            <h2 data-lang-content="en">Everything you need to understand your network</h2>
            <h2 data-lang-content="cz" style="display:none">Vše, co potřebujete pro přehled o síti</h2>

            <p class="lang-block" data-lang-content="en">
                NetSupervisor combines essential network tools into one intuitive interface so you can
                quickly detect issues, verify performance and document results.
            </p>
            <p class="lang-block" data-lang-content="cz" style="display:none">
                NetSupervisor spojuje klíčové síťové nástroje do jednoho přehledného rozhraní, takže můžete
                rychle odhalit problémy, ověřit výkon a snadno vše zdokumentovat.
            </p>

            <div class="cards">
                <div class="card">
                    <div class="pill">Speed Test</div>
                    <h3>Accurate performance checks</h3>
                    <p class="lang-block" data-lang-content="en">
                        Measure download, upload, latency and jitter with history and charts.
                    </p>
                    <p class="lang-block" data-lang-content="cz" style="display:none">
                        Měří download, upload, latenci a jitter s historií a grafy.
                    </p>
                    <small>Ideal for verifying ISP performance.</small>
                </div>
                <div class="card">
                    <div class="pill">LAN Scanner</div>
                    <h3>See every device</h3>
                    <p class="lang-block" data-lang-content="en">
                        Discover devices in your local network with IP, MAC and vendor details.
                    </p>
                    <p class="lang-block" data-lang-content="cz" style="display:none">
                        Najděte zařízení ve vaší síti včetně IP, MAC adres a výrobce.
                    </p>
                    <small>Identify unknown or new clients instantly.</small>
                </div>
                <div class="card">
                    <div class="pill">Monitoring</div>
                    <h3>Stay ahead of outages</h3>
                    <p class="lang-block" data-lang-content="en">
                        Monitor hosts over time and get notified about latency spikes or downtime.
                    </p>
                    <p class="lang-block" data-lang-content="cz" style="display:none">
                        Sledujte dostupnost hostitelů a nechte se upozornit na výpadky či zvýšenou latenci.
                    </p>
                    <small>Perfect for servers, routers, VPNs.</small>
                </div>
            </div>
        </section>

        <!-- TOOLS OVERVIEW -->
        <section class="section">
            <h2 data-lang-content="en">Built-in professional tools</h2>
            <h2 data-lang-content="cz" style="display:none">Profesionální nástroje v jedné aplikaci</h2>

            <div class="features-grid">
                <div>
                    <strong>Ping</strong>
                    <span data-lang-content="en">Check responsiveness of any host.</span>
                    <span data-lang-content="cz" style="display:none">Ověření odezvy libovolného hostitele.</span>
                </div>
                <div>
                    <strong>Traceroute</strong>
                    <span data-lang-content="en">Visualize the path of your packets.</span>
                    <span data-lang-content="cz" style="display:none">Zobrazení cesty paketů sítí.</span>
                </div>
                <div>
                    <strong>Port Scan</strong>
                    <span data-lang-content="en">Find open and filtered ports.</span>
                    <span data-lang-content="cz" style="display:none">Zjištění otevřených a filtrovaných portů.</span>
                </div>
                <div>
                    <strong>DNS Lookup</strong>
                    <span data-lang-content="en">Resolve records (A, AAAA, MX, TXT, NS...).</span>
                    <span data-lang-content="cz" style="display:none">Dotazy na záznamy (A, AAAA, MX, TXT, NS...).</span>
                </div>
                <div>
                    <strong>Whois</strong>
                    <span data-lang-content="en">Check domain and IP ownership.</span>
                    <span data-lang-content="cz" style="display:none">Informace o vlastnících domén a IP.</span>
                </div>
                <div>
                    <strong>Wake-on-LAN</strong>
                    <span data-lang-content="en">Wake devices remotely.</span>
                    <span data-lang-content="cz" style="display:none">Vzdálené probouzení zařízení.</span>
                </div>
                <div>
                    <strong>Reports</strong>
                    <span data-lang-content="en">Export results to CSV or PDF.</span>
                    <span data-lang-content="cz" style="display:none">Export výsledků do CSV nebo PDF.</span>
                </div>
                <div>
                    <strong>Dashboard</strong>
                    <span data-lang-content="en">All key metrics on one screen.</span>
                    <span data-lang-content="cz" style="display:none">Klíčové metriky přehledně na jedné obrazovce.</span>
                </div>
            </div>

            <p class="note">
                Replace this note with real screenshots from NetSupervisor to visually present the interface.
            </p>
        </section>

        <!-- WHY NETSUPERVISOR -->
        <section class="section">
            <h2 data-lang-content="en">Why choose NetSupervisor?</h2>
            <h2 data-lang-content="cz" style="display:none">Proč právě NetSupervisor?</h2>
            <ul class="lang-block" data-lang-content="en">
                <li>Native macOS design – fast, responsive and familiar.</li>
                <li>Privacy-first – all analysis runs locally on your Mac.</li>
                <li>No ads, no bloat – focused on real work.</li>
                <li>Ideal for admins, small businesses, ISPs and advanced users.</li>
            </ul>
            <ul class="lang-block" data-lang-content="cz" style="display:none">
                <li>Nativní aplikace pro macOS – rychlá, přehledná a příjemná na používání.</li>
                <li>Soukromí na prvním místě – zpracování probíhá lokálně na vašem Macu.</li>
                <li>Bez reklam a zbytečností – zaměřeno na skutečnou práci.</li>
                <li>Vhodné pro administrátory, menší firmy, ISP i pokročilé uživatele.</li>
            </ul>
        </section>

        <!-- PRIVACY & SUPPORT -->
        <section class="section">
            <h2 data-lang-content="en">Privacy &amp; Support</h2>
            <h2 data-lang-content="cz" style="display:none">Soukromí &amp; Podpora</h2>
            <p class="lang-block" data-lang-content="en">
                NetSupervisor does not collect personal data or send your results to external servers.
                For full details, read the <a href="privacy.html">Privacy Policy</a>.
                If you need help, visit the <a href="support.html">Support page</a>.
            </p>
            <p class="lang-block" data-lang-content="cz" style="display:none">
                NetSupervisor neshromažďuje osobní údaje ani neodesílá výsledky na externí servery.
                Podrobnosti najdete v <a href="privacy.html">Zásadách ochrany soukromí</a>.
                S dotazy či problémy se obraťte na stránku <a href="support.html">Podpora</a>.
            </p>
        </section>

        <!-- FINAL CTA -->
        <section class="cta-section">
            <h2 data-lang-content="en">Get started with NetSupervisor</h2>
            <h2 data-lang-content="cz" style="display:none">Začněte používat NetSupervisor</h2>
            <p class="lang-block" data-lang-content="en">
                Monitor, test and visualize your network with confidence — directly from your Mac.
            </p>
            <p class="lang-block" data-lang-content="cz" style="display:none">
                Sledujte, testujte a vizualizujte svou síť s jistotou – přímo z vašeho Macu.
            </p>
            <div class="btn-row" style="justify-content:center;">
                <a class="btn-primary" href="#">
                    <span class="icon"></span>
                    <span>Download on the Mac App Store</span>
                </a>
                <a class="btn-ghost" href="support.html">Support &amp; Documentation →</a>
            </div>
        </section>
    </div>
</main>

<footer>
    © Jan Mikš • NetSupervisor for macOS • All rights reserved
</footer>

<script>
    function setLang(lang) {
        // toggle language buttons
        document.querySelectorAll('.lang-btn').forEach(btn => {
            btn.classList.toggle('active', btn.dataset.lang === lang);
        });

        // toggle all language-specific elements
        document.querySelectorAll('[data-lang-content]').forEach(el => {
            const l = el.getAttribute('data-lang-content');
            el.style.display = (l === lang) ? '' : 'none';
        });

        document.querySelectorAll('.lang-block').forEach(el => {
            const l = el.getAttribute('data-lang-content');
            el.style.display = (l === lang) ? '' : 'none';
        });
    }
</script>

</body>
</html>
