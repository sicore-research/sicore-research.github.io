<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>SiCore Research</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body { margin: 0; font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; background-color: #dcdcdc; color: #222; }
    header { display: flex; justify-content: space-between; align-items: center; padding: 20px 40px; font-size: 16px; }
    header a { margin-left: 20px; text-decoration: none; color: #222; }
    .container { display: flex; flex-wrap: wrap; align-items: center; gap: 40px; padding: 80px 24px; max-width: 1280px; margin: 0 auto; min-height: 80vh; }
    .text-section { flex: 1 1 50%; padding: 20px; }
    .text-section h1 { font-size: 56px; font-weight: 700; margin: 0 0 20px 0; }
    .text-section h2 { font-size: 22px; font-weight: 400; color: #555; margin: -10px 0 30px 0; }
    .text-section p { font-size: 16px; line-height: 1.6; margin-bottom: 30px; }
    .btn { display: inline-block; padding: 14px 32px; background-color: #111; color: #fff; border-radius: 40px; text-decoration: none; font-weight: bold; font-size: 14px; }
    .image-section { flex: 1 1 50%; padding: 20px; text-align: center; }
    .image-section img { max-width: 100%; border-radius: 12px; box-shadow: 0 4px 20px rgba(0,0,0,0.2); }
    footer { text-align: center; padding: 20px; font-size: 14px; background: #111; color: #fff; margin-top: 40px; }
    .section { padding: 80px 60px; }
    .two-col { display: grid; grid-template-columns: 1fr 1fr; gap: 40px; max-width: 1280px; margin: 0 auto; padding: 0 24px; }
    @media (max-width: 900px) { .two-col { grid-template-columns: 1fr; } }
    .kicker { color:#666; letter-spacing:.04em; font-size:14px; text-transform:uppercase; }
    .display { font-size: 48px; font-weight: 700; margin: 10px 0 20px; }
    .subtext { color:#444; line-height:1.7; max-width: 640px; }
    form { display: grid; gap: 16px; max-width: 700px; }
    .row { display: flex; gap: 16px; flex-wrap: wrap; }
    .row > div { flex: 1; min-width: 200px; }
    input, textarea { width: 100%; border: 1px solid #bbb; background: #eee; padding: 14px 16px; border-radius: 10px; font-size: 16px; outline: none; box-sizing: border-box; }
    textarea { min-height: 140px; resize: vertical; }
    .btn.primary { background:#111; color:#fff; border-radius: 40px; padding: 14px 28px; border:none; cursor:pointer; font-weight:700; }
    .image-frame { border-radius: 14px; overflow: hidden; box-shadow: 0 8px 28px rgba(0,0,0,.25); background: linear-gradient(#fff,#cfcfcf); }
    html { scroll-behavior: smooth; }
    header { position: sticky; top: 0; backdrop-filter: blur(6px); }
    @media (min-width: 1200px) { .text-section h1 { font-size: 64px; } }
    /* modal */
    .modal { display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,.6); justify-content:center; align-items:center; z-index:1000; animation: fadeIn .5s ease forwards; }
    .modal-content { background:#fff; padding:40px; border-radius:12px; max-width:400px; text-align:center; box-shadow:0 8px 30px rgba(0,0,0,.3); transform: scale(0.8); opacity:0; animation: popIn .4s ease forwards; }
    .modal-content h3 { margin-top:0; }
    .close-btn { margin-top:20px; padding:10px 20px; border:none; background:#111; color:#fff; border-radius:6px; cursor:pointer; }
    @keyframes fadeIn { from {background:rgba(0,0,0,0);} to {background:rgba(0,0,0,.6);} }
    @keyframes popIn { to {transform: scale(1); opacity:1;} }
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
      <p>SiCore Research specializes in high-performance silicon carbide (SiC) power electronics engineered for extreme environments. Our designs eliminate costly devices, delivering unmatched ruggedness, efficiency, and scalability. From military-grade systems to next-generation electrification platforms, we accelerate innovation in renewable energy, electric vehicles, and defense applications.</p>
      <a href="#about" class="btn">LEARN MORE</a>
    </div>
    <div class="image-section">
      <img src="images/hero.jpg" alt="SiCore Inverter PCB">
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
        <img src="images/about.jpg" alt="Inverter and power electronics hardware" style="width:100%;display:block;">
      </div>
    </div>
  </section>

  <!-- CONTACT -->
  <section id="contact" class="section">
    <div class="two-col">
      <div>
        <div class="display">Contact Us</div>
        <p class="subtext">Interested in working together? Fill out some info and we will be in touch shortly. We can’t wait to hear from you!</p>
        <form id="contact-form" action="https://formsubmit.co/contact@sicore-research.com" method="POST" target="hidden_iframe" onsubmit="showModal()">
          <input type="hidden" name="_subject" value="New inquiry from SiCore website">
          <input type="hidden" name="_captcha" value="true">
          <input type="text" name="_honey" style="display:none">
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
        <iframe name="hidden_iframe" style="display:none;"></iframe>
      </div>
      <div class="image-frame">
        <img src="images/contact.jpg" alt="Electronics and inverter array" style="width:100%;display:block;">
      </div>
    </div>
  </section>

  <div class="modal" id="thankyouModal">
    <div class="modal-content">
      <h3>Thank you!</h3>
      <p>Your message has been sent successfully.</p>
      <button class="close-btn" onclick="closeModal()">Close</button>
    </div>
  </div>

  <footer>
    ©2025 SiCore Research, LLC
  </footer>

  <script>
    function showModal() {
      setTimeout(function(){
        document.getElementById('thankyouModal').style.display = 'flex';
        document.getElementById('contact-form').reset();
      }, 1000);
    }
    function closeModal() {
      document.getElementById('thankyouModal').style.display = 'none';
    }
  </script>
</body>
</html>
