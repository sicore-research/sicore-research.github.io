<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>SiCore Research</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif;
      background-color: #dcdcdc; /* light gray background */
      color: #222;
    }
    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 20px 40px;
      background: transparent;
      font-size: 16px;
    }
    header a {
      margin-left: 20px;
      text-decoration: none;
      color: #222;
    }
    .container {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: center;
      padding: 60px;
    }
    .text-section {
      flex: 1 1 400px;
      max-width: 600px;
      padding: 20px;
    }
    .text-section h1 {
      font-size: 56px;
      font-weight: 700;
      margin: 0 0 20px 0;
    }
    .text-section h2 {
      font-size: 22px;
      font-weight: 400;
      color: #555;
      margin: -10px 0 30px 0;
    }
    .text-section p {
      font-size: 16px;
      line-height: 1.6;
      margin-bottom: 30px;
    }
    .btn {
      display: inline-block;
      padding: 14px 32px;
      background-color: #111;
      color: #fff;
      border-radius: 40px;
      text-decoration: none;
      font-weight: bold;
      font-size: 14px;
    }
    .image-section {
      flex: 1 1 400px;
      max-width: 600px;
      padding: 20px;
      text-align: center;
    }
    .image-section img {
      max-width: 100%;
      height: auto;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.2);
    }
    footer {
      text-align: center;
      padding: 20px;
      font-size: 14px;
      background: #111;
      color: #fff;
      margin-top: 40px;
    }
      /* --- Sections --- */
    .section {
      padding: 80px 60px;
    }
    .two-col {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 40px;
      align-items: start;
    }
    @media (max-width: 900px) {
      .two-col { grid-template-columns: 1fr; }
    }
    .kicker { color:#666; letter-spacing:.04em; font-size:14px; text-transform:uppercase; }
    .display { font-size: 48px; font-weight: 700; margin: 10px 0 20px; }
    .subtext { color:#444; line-height:1.7; max-width: 640px; }

    /* form */
    form { display: grid; gap: 16px; max-width: 700px; }
    .row { display: flex; gap: 16px; flex-wrap: wrap; }
    .row > div { flex: 1; min-width: 200px; }
    input, textarea {
      width: 100%;
      border: 1px solid #bbb;
      background: #eee;
      padding: 14px 16px;
      border-radius: 10px;
      font-size: 16px;
      outline: none;
      box-sizing: border-box;
    }
    textarea { min-height: 140px; resize: vertical; }
    .btn.primary { background:#111; color:#fff; border-radius: 40px; padding: 14px 28px; border:none; cursor:pointer; font-weight:700; }

    .image-frame {
      border-radius: 14px;
      overflow: hidden;
      box-shadow: 0 8px 28px rgba(0,0,0,.25);
      background: linear-gradient(#fff,#cfcfcf);
    }

    /* sticky header + smooth scroll */
    html { scroll-behavior: smooth; }
    header { position: sticky; top: 0; backdrop-filter: blur(6px); }
  </style>
</head>
<body>
  <header>
    <div><strong>SiCore Research</strong> - Rugged Power Electronics</div>
    <nav>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>
  </header>

  <div class="container">
    <div class="text-section">
      <h1>SiCore</h1>
      <h2>“Innovative Rugged Power”</h2>
      <p>
        SiCore Research specializes in high-performance silicon carbide (SiC) power electronics engineered for extreme environments. 
        Our designs slash cost, 
        delivering unmatched ruggedness, efficiency, and scalability. 
        From military-grade systems to next-generation electrification platforms, 
        we accelerate innovation in renewable energy, electric vehicles, and defense applications.
      </p>
      <a href="#about" class="btn">LEARN MORE</a>
    </div>
    <div class="image-section">
      <img src="https://images.unsplash.com/photo-1587202372775-98927ec9b44d?q=80&w=1200&auto=format&fit=crop" alt="SiCore Inverter PCB">
    </div>
  </div>

  <!-- ABOUT -->
  <section id="about" class="section">
    <div class="two-col">
      <div>
        <div class="kicker">Who we are</div>
        <div class="display">Engineering for extreme environments</div>
        <p class="subtext">SiCore Research designs and builds silicon carbide (SiC) power electronics that thrive where others fail: high temperature, high shock, and mission-critical duty cycles. Our architecture improves reliability while slashing cost and footprint. We partner with integrators across defense, mobility, and energy to accelerate electrification programs from concept to production.</p>
      </div>
      <div class="image-frame">
        <img src="https://images.unsplash.com/photo-1627401229250-35c96f8aeecc?q=80&w=1600&auto=format&fit=crop" alt="Inverter and power electronics hardware" style="width:100%;display:block;">
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="section">
    <div class="two-col">
      <div>
        <div class="display">Contact Us</div>
        <p class="subtext">Tell us about your application and timelines. We’ll follow up within two business days.</p>
        <form action="https://formsubmit.co/contact@sicore-research.com" method="POST">
          <!-- FormSubmit controls -->
          <input type="hidden" name="_subject" value="New inquiry from SiCore website">
          <input type="hidden" name="_captcha" value="true">
          <div class="row">
            <div>
              <label for="first">First Name</label>
              <input id="first" name="first" required>
            </div>
            <div>
              <label for="last">Last Name</label>
              <input id="last" name="last" required>
            </div>
          </div>
          <div>
            <label for="email">Email</label>
            <input id="email" type="email" name="email" required>
          </div>
          <div>
            <label for="message">Message</label>
            <textarea id="message" name="message" required></textarea>
          </div>
          <button class="btn primary" type="submit">SEND</button>
        </form>
      </div>
      <div class="image-frame">
        <img src="https://images.unsplash.com/photo-1624976282768-6ea8657fca29?q=80&w=1600&auto=format&fit=crop" alt="Electronics and inverter array" style="width:100%;display:block;">
      </div>
    </div>
  </section>

  <footer>
    ©2025 SiCore Research, LLC
  </footer>
</body>
</html>
