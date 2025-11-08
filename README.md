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
            --font: -apple-system, BlinkMacSystemFont, system-ui, -system-ui, -sans-serif, sans-serif;
        }

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

        /* TOP HERO TITLE */

        .hero-top {
            display: flex;
            align-items: center;
            gap: 16px;
            padding: 30px 0 10px;
        }

        .hero-top img {
            width: 60px;
            height: 60px;
            border-radius: 12px;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
        }

        .hero-top h1 {
            font-size: 40px;
            margin: 0;
            font-weight: 700;
            letter-spacing: -0.02em;
        }

        .hero-top-sub {
            color: var(--muted);
            font-size: 15px;
        }

        .nav-bar {
            display: flex;
            justify-content: flex-end;
            align-items: center;
            gap: 14px;
            margin-top: -40px;
        }

        .nav-bar a {
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

        /* HERO SECTION */

        .hero {
            display: grid;
            grid-template-columns: minmax(0, 3fr) minmax(0, 2.8fr);
            gap: 24px;
            align-items: center;
            padding: 10px 0 24px;
        }

        h2 {
            font-size: 22px;
            margin-bottom: 8px;
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

        /* FOOTER */
        footer {
            padding: 14px 20px 22px;
            font-size: 11px;
            color: var(--muted);
            text-align: center;
        }

        footer a { margin: 0 6px; }

        /* RESPONSIVE */
        @media (max-width: 800px) {
            .hero {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

<header>
    <div class="container">

        <!-- Nahoře logo + název -->
        <div class="hero-top">
            <img src="icon-1024_v2.png" alt="NetSupervisor icon">
            <div>
                <h1>NetSupervisor</h1>
                <div class="hero-top-sub">Network monitoring &amp; diagnostics for macOS</div>
            </div>
        </div>

        <!-- Pravá horní navigace -->
        <div class="nav-bar">
            <a href="#top">Home</a>
            <a href="support.html">Support</a>
            <a href="privacy.html">Privacy</a>
            <div class="lang-switch">
                <button class="lang-btn active" data-lang="en" onclick="setLang('en')">EN</button>
                <button class="lang-btn" data-lang="cz" onclick="setLang('cz')">CZ</button>
            </div>
        </div>

        <!-- HERO -->
        <section class="hero" id="top">
            <div>
                <div class="lang-block" data-lang-content="en">
                    <h2>Keep your network under control.</h2>
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
                        <a class="btn-soft" href="support.html">Need help? Support →</a>
                    </div>
                </div>

                <div class="lang-block" data-lang-content="cz" style="display:none">
                    <h2>Mějte svou síť pod kontrolou.</h2>
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

            <!-- Vizualizace -->
            <div class="hero-card">
                <div class="hero-label">Example network snapshot</div>
                <div class="hero-metric-row">
                    <div><strong>9.3 Mb/s</strong><span>Average download</span></div>
                    <div><strong>2.1 Mb/s</strong><span>Average upload</span></div>
                    <div><strong>42 ms</strong><span>Ping</span></div>
                </div>
                <div class="hero-metric-row">
                    <div><strong>4</strong><span>Monitored hosts</span></div>
                    <div><strong>0</strong><span>Incidents</span></div>
                    <div><strong>6</strong><span>LAN devices</span></div>
                </div>
                <div class="note">
                    Visualization based on the real NetSupervisor dashboard interface.
                </div>
            </div>
        </section>
    </div>
</header>

<footer>
    <a href="support.html">Support</a> •
    <a href="privacy.html">Privacy Policy</a><br>
    © Jan Mikš • NetSupervisor for macOS
</footer>

<script>
function setLang(lang) {
    document.querySelectorAll('.lang-btn').forEach(btn => {
        btn.classList.toggle('active', btn.dataset.lang === lang);
    });
    document.querySelectorAll('[data-lang-content]').forEach(el => {
        el.style.display = el.getAttribute('data-lang-content') === lang ? '' : 'none';
    });
}
</script>

</body>
</html>
