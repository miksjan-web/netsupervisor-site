<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>NetSupervisor for macOS</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <meta name="description"
          content="NetSupervisor is an all-in-one network monitoring and diagnostics tool for macOS.">
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

        a { color: var(--accent); text-decoration: none; }
        a:hover { text-decoration: underline; }

        header {
            background: linear-gradient(140deg, #ffffff, #eef3ff);
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
            flex-wrap: wrap;
        }

        .brand {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .brand img {
            width: 32px;
            height: 32px;
            border-radius: 9px;
            box-shadow: 0 4px 14px rgba(0,0,0,0.15);
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
        }

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
            font-family: var(--font);
        }

        .lang-btn.active {
            background: #ffffff;
            color: var(--accent);
            box-shadow: 0 1px 4px rgba(0,0,0,0.12);
        }

        /* HERO */

        .hero {
            display: grid;
            grid-template-columns: minmax(0, 3fr) minmax(0, 2.8fr);
            gap: 24px;
            align-items: center;
            padding: 10px 0 24px;
        }

        h1 {
            font-size: 28px;
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
            padding-left: 18px;
        }

        .hero-list li { margin-bottom: 4px; }

        .btn-row {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            align-items: center;
        }

        .btn-outline {
            padding: 8px 16px;
            border-radius: 999px;
            border: 1px solid var(--accent);
            background: transparent;
            color: var(--accent);
            font-size: 13px;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            cursor: pointer;
            text-decoration: none;
        }

        .btn-soft {
            padding: 8px 14px;
            border-radius: 999px;
            border: 1px solid var(--border);
            background: #ffffffaa;
            color: var(--accent);
            font-size: 12px;
            display: inline-flex;
            align-items: center;
            gap: 6px;
            cursor: pointer;
            text-decoration: none;
        }

        .hero-card {
            background: rgba(255,255,255,0.98);
            border-radius: var(--radius);
            padding: 14px 14px 10px;
            box-shadow: var(--shadow-soft);
            border: 1px solid var(--border);
            font-size: 12px;
        }

        .hero-label {
            font-size: 10px;
            color: var(--muted);
            margin-bottom: 4px;
            text-transform: uppercase;
            letter-spacing: 0.14em;
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
            font-size: 10px;
            color: var(--muted);
            margin-top: 6px;
        }

        /* SECTIONS */

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

        .who-section ul {
            padding-left: 18px;
            font-size: 13px;
            color: #3a3a3c;
        }

        .cta-section {
            margin: 32px 0 18px;
            text-align: center;
            padding: 18px 16px 20px;
            background: linear-gradient(135deg, #ffffff, #e9f3ff);
            border-radius: var(--radius);
            border: 1px solid var(--border);
            box-shadow: var(--shadow-soft);
        }

        .cta-section h2 {
            margin: 0 0 6px;
            font-size: 21px;
        }

        .cta-section p {
            margin: 0 0 10px;
            font-size: 14px;
            color: #3a3a3c;
        }

        footer {
            padding: 14px 20px 22px;
            font-size: 11px;
            color: var(--muted);
            text-align: center;
        }

        footer a { margin: 0 6px; }

        /* Responsive */

        @media (max-width: 800px) {
            .hero {
                grid-template-columns: 1fr;
            }
            .cards {
                grid-template-columns: 1fr 1fr;
            }
            .features-grid {
                grid-template-columns: 1fr 1fr;
            }
        }

        @media (max-width: 540px) {
            .cards {
                grid-template-columns: 1fr;
            }
            .features-grid {
                grid-template-columns: 1fr;
            }
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
                <!-- Ikona aplikace -->
                <img src="icon-1024_v2.png" alt="NetSupervisor icon">
                <div>
                    <div class="brand-title">NetSupervisor</div>
                    <div class="brand-sub">Network monitoring &amp; diagnostics for macOS</div>
                </div>
            </div>
            <div>
                <nav>
                    <a href="#top">Home</a>
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
                    <h1>Keep your network under control.</h1>
                    <p class="hero-sub">
                        NetSupervisor brings speed testing, device discovery, monitoring and diagnostics
                        into one clean, native macOS app.
                    </p>
                    <ul class="hero-list">
                        <li>Instant overview of connection, latency and uptime</li>
                        <li>Automatic monitoring and clear alerts before users notice issues</li>
                        <li>All core tools in one place – no complex setup</li>
                    </ul>
                    <div class="btn-row">
                        <a class="btn-outline" href="#features">Explore features</a>
                        <a class="btn-soft" href="support.html">Need details or help? Support →</a>
                    </div>
                </div>
                <!-- CZ -->
                <div class="lang-block" data-lang-content="cz" style="display:none">
                    <h1>Mějte svou síť pod kontrolou.</h1>
                    <p class="hero-sub">
                        NetSupervisor spojuje test rychlosti, skenování zařízení, monitoring a diagnostiku
                        do jedné přehledné aplikace pro macOS.
                    </p>
                    <ul class="hero-list">
                        <li>Okamžitý přehled o připojení, latenci a dostupnosti</li>
                        <li>Automatický monitoring a upozornění dřív, než si problému všimnou uživatelé</li>
                        <li>Všechny klíčové nástroje na jednom místě – bez složitého nastavování</li>
                    </ul>
                    <div class="btn-row">
                        <a class="btn-outline" href="#features">Prohlédnout funkce</a>
                        <a class="btn-soft" href="support.html">Potřebujete poradit? Podpora →</a>
                    </div>
                </div>
            </div>

            <!-- Mini vizualizace dashboardu -->
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
                <div class="note">
                    Visualization based on the real NetSupervisor dashboard interface.
                </div>
            </div>
        </section>
    </div>
</header>

<main>
    <div class="container">

        <!-- BENEFITS -->
        <section class="section" id="features">
            <h2 data-lang-content="en">Why NetSupervisor?</h2>
            <h2 data-lang-content="cz" style="display:none">Proč právě NetSupervisor?</h2>

            <div class="cards">
                <div class="card">
                    <h3 data-lang-content="en">Instant clarity</h3>
                    <h3 data-lang-content="cz" style="display:none">Okamžitý přehled</h3>
                    <p class="lang-block" data-lang-content="en">
                        One dashboard for connection details, recent tests, monitored hosts and alerts.
                    </p>
                    <p class="lang-block" data-lang-content="cz" style="display:none">
                        Jeden přehled pro informace o připojení, poslední testy, sledované cíle a upozornění.
                    </p>
                    <small>Designed to answer “what’s wrong?” in seconds.</small>
                </div>

                <div class="card">
                    <h3 data-lang-content="en">Fewer outages</h3>
                    <h3 data-lang-content="cz" style="display:none">Méně výpadků</h3>
                    <p class="lang-block" data-lang-content="en">
                        Continuous monitoring and clear thresholds help you react before users complain.
                    </p>
                    <p class="lang-block" data-lang-content="cz" style="display:none">
                        Průběžný monitoring a přehledné prahy umožní reagovat dřív, než si problému všimnou uživatelé.
                    </p>
                    <small>Perfect for servers, routers, VPNs and key services.</small>
                </div>

                <div class="card">
                    <h3 data-lang-content="en">Professional toolkit</h3>
                    <h3 data-lang-content="cz" style="display:none">Profesionální výbava</h3>
                    <p class="lang-block" data-lang-content="en">
                        Ping, traceroute, port scan, DNS, Whois, Wake-on-LAN and exportable reports – all in one app.
                    </p>
                    <p class="lang-block" data-lang-content="cz" style="display:none">
                        Ping, Traceroute, Port Scan, DNS, Whois, Wake-on-LAN a export reportů – vše v jedné aplikaci.
                    </p>
                    <small>No need to jump between multiple tools.</small>
                </div>
            </div>
        </section>

        <!-- TOOLS OVERVIEW -->
        <section class="section">
            <h2 data-lang-content="en">What NetSupervisor can do</h2>
            <h2 data-lang-content="cz" style="display:none">Co NetSupervisor umí</h2>

            <p class="lang-block" data-lang-content="en">
                Use NetSupervisor as your central hub for testing, monitoring and documenting your network.
            </p>
            <p class="lang-block" data-lang-content="cz" style="display:none">
                Použijte NetSupervisor jako centrální místo pro testování, monitoring a dokumentaci vaší sítě.
            </p>

            <div class="features-grid">
                <div>
                    <strong>Dashboard</strong>
                    <span data-lang-content="en">Overview of connection, tests and monitoring.</span>
                    <span data-lang-content="cz" style="display:none">Přehled připojení, testů a monitoringu.</span>
                </div>
                <div>
                    <strong>Speed Test</strong>
                    <span data-lang-content="en">Download, upload, ping &amp; jitter with history.</span>
                    <span data-lang-content="cz" style="display:none">Download, upload, ping a jitter s historií.</span>
                </div>
                <div>
                    <strong>LAN Scanner</strong>
                    <span data-lang-content="en">Find every device in your network.</span>
                    <span data-lang-content="cz" style="display:none">Najděte všechna zařízení v síti.</span>
                </div>
                <div>
                    <strong>Monitoring</strong>
                    <span data-lang-content="en">Targets, thresholds, alerts and uptime.</span>
                    <span data-lang-content="cz" style="display:none">Cíle, prahy, upozornění a dostupnost.</span>
                </div>
                <div>
                    <strong>Topology</strong>
                    <span data-lang-content="en">Visual map of your network.</span>
                    <span data-lang-content="cz" style="display:none">Vizualizace struktury sítě.</span>
                </div>
                <div>
                    <strong>Ping &amp; Traceroute</strong>
                    <span data-lang-content="en">Diagnose routes and response times.</span>
                    <span data-lang-content="cz" style="display:none">Diagnostika cest a odezvy.</span>
                </div>
                <div>
                    <strong>DNS &amp; Whois</strong>
                    <span data-lang-content="en">Domain and record details.</span>
                    <span data-lang-content="cz" style="display:none">Detailní informace o doménách.</span>
                </div>
                <div>
                    <strong>Port Scan &amp; Reports</strong>
                    <span data-lang-content="en">Open ports and exportable results.</span>
                    <span data-lang-content="cz" style="display:none">Otevřené porty a export výsledků.</span>
                </div>
            </div>

            <p class="note">
                Use your application screenshots alongside these sections to visually demonstrate the clean interface.
            </p>
        </section>

        <!-- FOR WHOM -->
        <section class="section who-section">
            <h2 data-lang-content="en">Made for</h2>
            <h2 data-lang-content="cz" style="display:none">Vhodné pro</h2>
            <ul class="lang-block" data-lang-content="en">
                <li>Network &amp; system administrators</li>
                <li>ISPs and IT support teams</li>
                <li>Small businesses managing their own infrastructure</li>
                <li>Power users who want full insight into their home network</li>
            </ul>
            <ul class="lang-block" data-lang-content="cz" style="display:none">
                <li>Správce sítí a systémové administrátory</li>
                <li>ISP a interní IT týmy</li>
                <li>Menší firmy se svou infrastrukturou</li>
                <li>Pokročilé domácí uživatele, kteří chtějí znát stav své sítě</li>
            </ul>
        </section>

        <!-- PRIVACY & SUPPORT -->
        <section class="section">
            <h2 data-lang-content="en">Privacy &amp; Transparency</h2>
            <h2 data-lang-content="cz" style="display:none">Soukromí &amp; Transparentnost</h2>
            <p class="lang-block" data-lang-content="en">
                NetSupervisor runs fully on your Mac. No accounts, no analytics, no selling of your data.
                Learn more in the <a href="privacy.html">Privacy Policy</a>.
            </p>
            <p class="lang-block" data-lang-content="cz" style="display:none">
                NetSupervisor běží kompletně na vašem Macu. Žádné účty, žádná analytika, žádný prodej dat.
                Více informací najdete v <a href="privacy.html">Zásadách ochrany soukromí</a>.
            </p>
        </section>

        <!-- CTA (bez download textu) -->
        <section class="cta-section">
            <h2 data-lang-content="en">Ready to explore your network?</h2>
            <h2 data-lang-content="cz" style="display:none">Připraveni poznat svou síť?</h2>
            <p class="lang-block" data-lang-content="en">
                Use NetSupervisor to gain full visibility, prevent outages and simplify your daily work.
            </p>
            <p class="lang-block" data-lang-content="cz" style="display:none">
                S NetSupervisorem získáte přehled, předejdete výpadkům a zjednodušíte si práci.
            </p>
            <div class="btn-row" style="justify-content:center;">
                <a class="btn-soft" href="support.html">Learn more &amp; get support →</a>
            </div>
        </section>
    </div>
</main>

<footer>
    <div>
        <a href="support.html">Support</a> •
        <a href="privacy.html">Privacy Policy</a>
    </div>
    <div>© Jan Mikš • NetSupervisor for macOS • All rights reserved</div>
</footer>

<script>
    function setLang(lang) {
        // toggle language buttons
        document.querySelectorAll('.lang-btn').forEach(btn => {
            btn.classList.toggle('active', btn.dataset.lang === lang);
        });

        // toggle elements by data-lang-content
        document.querySelectorAll('[data-lang-content]').forEach(el => {
            const contentLang = el.getAttribute('data-lang-content');
            el.style.display = (contentLang === lang) ? '' : 'none';
        });

        // toggle .lang-block elements
        document.querySelectorAll('.lang-block').forEach(el => {
            const contentLang = el.getAttribute('data-lang-content');
            el.style.display = (contentLang === lang) ? '' : 'none';
        });
    }
</script>

</body>
</html>
