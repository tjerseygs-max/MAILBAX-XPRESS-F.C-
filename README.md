<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>MAILBAX XPRESS F.C. – Official Landing</title>
  <meta name="description" content="MAILBAX XPRESS F.C. – Scan the bracelet. Choose your purpose. Business, Support or Sponsorship." />
  <style>
    :root {
      --bg: #0a0a0b;
      --card: #141416;
      --card-hover: #1c1c1f;
      --text: #f5f5f7;
      --muted: #a1a1a6;
      --accent: #f5c518;
      --blue: #0a84ff;
      --green: #30d158;
      --purple: #bf5af2;
      --border: #2c2c2e;
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      line-height: 1.5;
      -webkit-font-smoothing: antialiased;
    }

    .container {
      max-width: 480px;
      margin: 0 auto;
      padding: 24px 16px 48px;
    }

    /* Header / Scan banner */
    .scan-banner {
      background: linear-gradient(160deg, #0d1b2a 0%, #1b263b 100%);
      border-radius: 16px;
      padding: 28px 20px;
      text-align: center;
      margin-bottom: 20px;
      border: 1px solid var(--border);
      position: relative;
      overflow: hidden;
    }

    .scan-banner::before {
      content: "";
      position: absolute;
      inset: 0;
      background: radial-gradient(circle at 50% 0%, rgba(245, 197, 24, 0.08), transparent 70%);
      pointer-events: none;
    }

    .qr-icon {
      width: 48px;
      height: 48px;
      margin: 0 auto 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      border: 2px solid var(--accent);
      border-radius: 10px;
      font-size: 22px;
      color: var(--accent);
    }

    .scan-banner h1 {
      font-size: 1.35rem;
      font-weight: 700;
      letter-spacing: 0.04em;
      margin-bottom: 6px;
    }

    .scan-banner p {
      color: var(--muted);
      font-size: 0.95rem;
    }

    /* Arrow */
    .arrow {
      text-align: center;
      color: var(--muted);
      font-size: 1.4rem;
      margin: 12px 0;
      opacity: 0.7;
    }

    /* Main card */
    .main-card {
      background: var(--card);
      border-radius: 16px;
      padding: 24px 20px;
      border: 1px solid var(--border);
      margin-bottom: 20px;
      text-align: center;
    }

    .main-card h2 {
      font-size: 1.4rem;
      font-weight: 700;
      margin-bottom: 4px;
    }

    .main-card .subtitle {
      color: var(--muted);
      font-size: 1rem;
      margin-bottom: 8px;
    }

    .main-card .prompt {
      color: var(--text);
      font-size: 1.05rem;
      font-weight: 500;
      margin-top: 12px;
    }

    /* Action grid */
    .actions {
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      gap: 12px;
      margin-bottom: 28px;
    }

    .action-btn {
      background: var(--card);
      border: 1px solid var(--border);
      border-radius: 14px;
      padding: 18px 10px;
      text-align: center;
      text-decoration: none;
      color: var(--text);
      transition: background 0.2s, transform 0.15s, border-color 0.2s;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 8px;
      cursor: pointer;
    }

    .action-btn:hover,
    .action-btn:focus {
      background: var(--card-hover);
      border-color: #3a3a3c;
      transform: translateY(-2px);
    }

    .action-btn .icon {
      width: 36px;
      height: 36px;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
    }

    .action-btn.business .icon { background: rgba(10, 132, 255, 0.15); color: var(--blue); }
    .action-btn.support .icon { background: rgba(48, 209, 88, 0.15); color: var(--green); }
    .action-btn.sponsor .icon { background: rgba(191, 90, 242, 0.15); color: var(--purple); }

    .action-btn .label {
      font-weight: 600;
      font-size: 0.95rem;
      line-height: 1.2;
    }

    .action-btn .desc {
      font-size: 0.75rem;
      color: var(--muted);
      line-height: 1.25;
    }

    /* Sections that appear on click */
    .panel {
      display: none;
      background: var(--card);
      border-radius: 16px;
      padding: 24px 20px;
      border: 1px solid var(--border);
      margin-bottom: 20px;
      animation: fadeIn 0.25s ease;
    }

    .panel.active {
      display: block;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(8px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .panel h3 {
      font-size: 1.2rem;
      margin-bottom: 12px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .panel p {
      color: var(--muted);
      margin-bottom: 16px;
      font-size: 0.95rem;
    }

    .panel form {
      display: flex;
      flex-direction: column;
      gap: 12px;
    }

    .panel input,
    .panel textarea,
    .panel select {
      background: #1c1c1f;
      border: 1px solid var(--border);
      border-radius: 10px;
      padding: 12px 14px;
      color: var(--text);
      font-size: 0.95rem;
      width: 100%;
      outline: none;
    }

    .panel input:focus,
    .panel textarea:focus,
    .panel select:focus {
      border-color: var(--accent);
    }

    .panel textarea {
      min-height: 100px;
      resize: vertical;
    }

    .panel button[type="submit"] {
      background: var(--accent);
      color: #000;
      border: none;
      border-radius: 10px;
      padding: 13px;
      font-weight: 600;
      font-size: 1rem;
      cursor: pointer;
      transition: opacity 0.2s;
    }

    .panel button[type="submit"]:hover {
      opacity: 0.9;
    }

    .back-link {
      display: inline-block;
      margin-top: 16px;
      color: var(--muted);
      font-size: 0.9rem;
      text-decoration: none;
      cursor: pointer;
    }

    .back-link:hover {
      color: var(--text);
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 24px 16px;
      color: var(--muted);
      font-size: 0.8rem;
      border-top: 1px solid var(--border);
      margin-top: 20px;
    }

    footer a {
      color: var(--accent);
      text-decoration: none;
    }

    footer .tagline {
      margin-bottom: 8px;
      font-size: 0.85rem;
    }

    /* Success message */
    .success {
      display: none;
      text-align: center;
      background: var(--card);
      border-radius: 16px;
      padding: 32px 20px;
      border: 1px solid var(--border);
      margin-bottom: 20px;
    }

    .success.active {
      display: block;
      animation: fadeIn 0.25s ease;
    }

    .success .check {
      width: 56px;
      height: 56px;
      background: rgba(48, 209, 88, 0.15);
      color: var(--green);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
      margin: 0 auto 16px;
    }
  </style>
</head>
<body>
  <div class="container">

    <!-- Scan Banner -->
    <div class="scan-banner">
      <div class="qr-icon">▣</div>
      <h1>MAILBAX XPRESS F.C.</h1>
      <p>You scanned the official bracelet QR</p>
    </div>

    <div class="arrow">↓</div>

    <!-- Intro Card -->
    <div class="main-card" id="intro">
      <h2>Welcome</h2>
      <p class="subtitle">What brings you here today?</p>
      <p class="prompt">Choose your purpose</p>
    </div>

    <!-- Action Buttons -->
    <div class="actions" id="actions">
      <div class="action-btn business" onclick="showPanel('business')">
        <div class="icon">💼</div>
        <div class="label">MAILBAX</div>
        <div class="desc">Business</div>
      </div>
      <div class="action-btn support" onclick="showPanel('support')">
        <div class="icon">♥</div>
        <div class="label">Support</div>
        <div class="desc">Donate / Buy</div>
      </div>
      <div class="action-btn sponsor" onclick="showPanel('sponsor')">
        <div class="icon">🤝</div>
        <div class="label">Sponsor</div>
        <div class="desc">Partner</div>
      </div>
    </div>

    <!-- Business Panel -->
    <div class="panel" id="panel-business">
      <h3>💼 Business Inquiry</h3>
      <p>Interested in MAILBAX products, wholesale, or collaboration? Tell us how we can help.</p>
      <form onsubmit="submitForm(event, 'business')">
        <input type="text" name="name" placeholder="Your name" required />
        <input type="email" name="email" placeholder="Email address" required />
        <input type="text" name="company" placeholder="Company / Organization" />
        <textarea name="message" placeholder="How can we help?" required></textarea>
        <button type="submit">Send Inquiry</button>
      </form>
      <a class="back-link" onclick="hidePanels()">← Back to options</a>
    </div>

    <!-- Support Panel -->
    <div class="panel" id="panel-support">
      <h3>♥ Support the Club</h3>
      <p>Every contribution helps keep MAILBAX XPRESS F.C. competing and growing. Choose how you’d like to support.</p>
      <form onsubmit="submitForm(event, 'support')">
        <select name="type" required>
          <option value="">Select type…</option>
          <option value="donation">One-time donation</option>
          <option value="membership">Booster membership</option>
          <option value="merchandise">Purchase merchandise</option>
          <option value="other">Other</option>
        </select>
        <input type="text" name="name" placeholder="Your name" required />
        <input type="email" name="email" placeholder="Email address" required />
        <input type="number" name="amount" placeholder="Amount (optional)" min="1" step="1" />
        <textarea name="message" placeholder="Message (optional)"></textarea>
        <button type="submit">Continue</button>
      </form>
      <a class="back-link" onclick="hidePanels()">← Back to options</a>
    </div>

    <!-- Sponsor Panel -->
    <div class="panel" id="panel-sponsor">
      <h3>🤝 Sponsorship & Partnership</h3>
      <p>Partner with MAILBAX XPRESS F.C. and reach an engaged local community. Let’s explore opportunities together.</p>
      <form onsubmit="submitForm(event, 'sponsor')">
        <input type="text" name="name" placeholder="Your name" required />
        <input type="email" name="email" placeholder="Email address" required />
        <input type="text" name="company" placeholder="Company name" required />
        <select name="interest" required>
          <option value="">Sponsorship interest…</option>
          <option value="kit">Kit / jersey sponsor</option>
          <option value="stadium">Venue / board advertising</option>
          <option value="event">Match-day / event sponsor</option>
          <option value="digital">Digital & social partnership</option>
          <option value="other">Other / open discussion</option>
        </select>
        <textarea name="message" placeholder="Tell us about your goals" required></textarea>
        <button type="submit">Request Partnership Info</button>
      </form>
      <a class="back-link" onclick="hidePanels()">← Back to options</a>
    </div>

    <!-- Success state -->
    <div class="success" id="success">
      <div class="check">✓</div>
      <h3 style="margin-bottom:8px;">Thank you!</h3>
      <p style="color:var(--muted); margin-bottom:20px;">We’ve received your message and will get back to you shortly.</p>
      <a class="back-link" onclick="hidePanels()">← Back to options</a>
    </div>

  </div>

  <footer>
    <div class="tagline">MAILBAX XPRESS F.C. — Fictitious demo for the hinged QR bracelet prototype</div>
    <div>Built for GitHub Pages · Open source demo</div>
    <div style="margin-top:8px;">
      <a href="https://github.com/tjerseygs-max/MAILBAX-XPRESS-F.C-" target="_blank" rel="noopener">View on GitHub</a>
    </div>
  </footer>

  <script>
    function showPanel(id) {
      hidePanels();
      document.getElementById('intro').style.display = 'none';
      document.getElementById('actions').style.display = 'none';
      document.getElementById('panel-' + id).classList.add('active');
    }

    function hidePanels() {
      document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
      document.getElementById('success').classList.remove('active');
      document.getElementById('intro').style.display = 'block';
      document.getElementById('actions').style.display = 'grid';
    }

    function submitForm(e, type) {
      e.preventDefault();
      // Demo only – no real backend
      document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
      document.getElementById('success').classList.add('active');
      // Optional: console log the data
      const form = e.target;
      const data = Object.fromEntries(new FormData(form));
      console.log(`[MAILBAX XPRESS F.C.] ${type} submission:`, data);
    }
  </script>
</body>
</html>
