<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>SiCore Research</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap" rel="stylesheet">
  <style>
    /* Announcement bar */
    .announce{position:fixed;top:0;left:0;width:100%;background:#1b1b1b;color:#fff;padding:10px 56px 10px 16px;font:600 14px/1.4 'Inter',sans-serif;z-index:120;display:flex;justify-content:center;align-items:center;gap:16px;}
    .announce.hidden{display:none;}
    .announce .announce-close{position:absolute;right:12px;top:8px;background:transparent;border:none;color:#fff;font-size:22px;cursor:pointer;line-height:1;}

    body { margin:0; font-family: 'Inter', sans-serif; background:#000; color:#eee; }
    header { position:fixed; top:40px; left:0; width:100%; display:flex; justify-content:space-between; align-items:center; padding:14px 24px; z-index:100; transition:background .3s, top .3s; }
    header.scrolled { background:rgba(0,0,0,0.85); }
    header a { text-decoration:none; color:#eee; font-weight:500; }
    .hero { position:relative; display:flex; align-items:center; justify-content:center; text-align:center; color:#fff; height:100vh; overflow:hidden; padding-top:40px; }
    .hero-video { position:absolute; inset:0; width:100%; height:100%; object-fit:cover; filter:brightness(0.4); z-index:-2; }
    #scroll-cue{position:absolute; bottom:24px; left:50%; transform:translateX(-50%); font-size:12px; color:#bbb; letter-spacing:.08em;}
    .reveal{opacity:0; transform:translateY(24px); transition:opacity .6s ease, transform .6s ease;}
    .reveal.in{opacity:1; transform:none;}
    .hero::before { content:""; position:absolute; top:0; left:0; width:100%; height:100%; background:url('images/hero.jpg') center/cover no-repeat; filter:brightness(0.4); z-index:-2; }
    .hero-content { z-index:2; max-width:800px; padding:0 20px; }
    .hero h1 { font-size:72px; font-weight:700; margin:0 0 20px; letter-spacing:-1px; }
    .hero h2 { font-size:28px; font-weight:400; margin:0 0 30px; color:#ccc; }
    .hero p { font-size:20px; line-height:1.6; color:#ddd; margin-bottom:40px; }
    .btn { display:inline-block; padding:14px 32px; background:#fff; color:#000; border-radius:40px; text-decoration:none; font-weight:700; font-size:15px; box-shadow:none; }
    .section { padding:120px 60px; }
    .section.dark { background:#111; color:#eee; }
    .two-col { display:grid; grid-template-columns:1fr 1fr; gap:60px; max-width:1280px; margin:0 auto; align-items:center; }
    @media(max-width:900px){ .two-col { grid-template-columns:1fr; } }
    .display { font-size:46px; font-weight:700; margin:0 0 20px; }
    .subtext { font-size:18px; line-height:1.7; color:#ccc; }
    .image-frame img { width:100%; border-radius:12px; }
    form { display:grid; gap:16px; }
    input, textarea { background:#222; border:1px solid #555; color:#fff; padding:14px 16px; border-radius:8px; font-size:16px; }
    textarea { min-height:140px; resize:vertical; }
    .btn.primary { background:#fff; color:#000; border:none; cursor:pointer; }
    footer { background:#000; color:#aaa; text-align:center; padding:40px; font-size:14px; }
    /* modal */
    .modal { display:none; position:fixed; top:0; left:0; width:100%; height:100%; background:rgba(0,0,0,.6); justify-content:center; align-items:center; z-index:1000; animation: fadeIn .5s ease forwards; }
    .modal-content { background:#111; color:#fff; padding:40px; border-radius:12px; max-width:400px; text-align:center; box-shadow:0 8px 30px rgba(0,0,0,.3); transform:scale(0.8); opacity:0; animation: popIn .4s ease forwards; }
    .close-btn { margin-top:20px; padding:10px 20px; border:none; background:#fff; color:#000; border-radius:6px; cursor:pointer; }
    @keyframes fadeIn { from{background:rgba(0,0,0,0);} to{background:rgba(0,0,0,.6);} }
    @keyframes popIn { to{transform:scale(1); opacity:1;} }
      /* header layout */
    .brand {font-weight:700; letter-spacing:.2px;}
    .nav{display:none;}
    .actions{display:flex; gap:12px; align-items:center;}
    .get-started{background:#fff;color:#000;border-radius:24px;padding:10px 16px;font-weight:700;border:none;cursor:pointer}
    .menu-toggle{width:36px;height:36px;border:1px solid #444;border-radius:8px;background:#1c1c1c;color:#fff;display:flex;align-items:center;justify-content:center;cursor:pointer}
    .menu{position:absolute;top:56px;right:24px;background:#0f0f0f;border:1px solid #222;border-radius:12px;padding:10px;display:none;flex-direction:column;min-width:180px;z-index:110}
    .menu a{padding:8px 12px;border-radius:8px}
    .menu a:hover{background:#1f1f1f}
    /* Cards / capabilities */
    .cards{max-width:1280px;margin:0 auto;padding:0 24px;display:grid;grid-template-columns:repeat(4,1fr);gap:24px}
    .card{background:#0f0f0f;border:1px solid #1f1f1f;border-radius:12px;padding:24px}
    .card h3{margin:0 0 8px;font-size:20px}
    .card p{color:#cfcfcf;line-height:1.6}
    @media(max-width:1100px){.cards{grid-template-columns:repeat(2,1fr)}}
    @media(max-width:640px){.cards{grid-template-columns:1fr}}

    /* CTA band */
    .cta-band{background:linear-gradient(90deg,#0a0a0a,#171717);padding:80px 16px;text-align:center}
    .cta-inner{max-width:900px;margin:0 auto}
    .cta-inner h3{font-size:36px;margin:0 0 8px}
    .cta-inner p{color:#ccc;margin:0 0 20px}

    /* Footer */
    .site-footer{background:#000;padding:60px 24px;border-top:1px solid #111}
    .footer-grid{max-width:1280px;margin:0 auto;display:grid;grid-template-columns:2fr 1fr 1fr;gap:24px}
    .site-footer h4{margin:0 0 10px}
    .site-footer a{display:block;color:#aaa;text-decoration:none;margin:6px 0}
    .site-footer a:hover{color:#fff}
    .footnote{text-align:center;color:#777;margin-top:24px;font-size:14px}
    .footcopy{color:#aaa;max-width:420px}
    /* Section dots nav */
    .dots{position:absolute; bottom:56px; left:50%; transform:translateX(-50%); display:flex; gap:10px; z-index:2}
    .dot{width:10px; height:10px; border-radius:50%; background:#666; cursor:pointer; transition:transform .2s, background .2s}
    .dot.active{background:#fff; transform:scale(1.2)}
  </style>
</head>
<body>
  <!-- Dismissible broadcast bar -->
  <div class="announce" id="announceBar">
    <span id="announceMessage">Now accepting pilot programs for rugged SiC inverters — Q4 slots available.</span>
    <button class="announce-close" aria-label="Close announcement" onclick="dismissAnnounce()">×</button>
  </div>
  <header id="site-header">
    <div class="brand">SiCore Research</div>
    <div class="actions">
      <button class="get-started" onclick="document.querySelector('#contact').scrollIntoView({behavior:'smooth'})">Start Building</button>
      <button class="menu-toggle" id="menuBtn" aria-haspopup="true" aria-expanded="false">≡</button>
      <div class="menu" id="menu">
        <a href="#capabilities">Capabilities</a>
        <a href="#contact">Start Building</a>
        <a href="#" onclick="alert('Coming soon');return false;">Products</a>
      </div>
    </div>
  </header>

  <section class="hero">
    <video class="hero-video" autoplay muted playsinline loop poster="images/hero.jpg">
      <source src="media/hero.mp4" type="video/mp4" />
    </video>
    <div class="hero-content">
      <h1>SiCore</h1>
      <h2>Innovative Rugged Power</h2>
      <p>Delivering scalable silicon carbide inverter platforms for defense, aerospace, and electrification. Designed for high-temperature, high-shock, and mission-critical duty cycles.</p>
    </div>
    <div class="dots" aria-label="Section navigation">
      <span class="dot" data-target="#about" aria-label="About"></span>
      <span class="dot" data-target="#capabilities" aria-label="Capabilities"></span>
      <span class="dot" data-target="#contact" aria-label="Start Building"></span>
    </div>
    <div id="scroll-cue">Scroll to Explore</div>
  </section>

  <section id="about" class="section dark">
    <div class="two-col reveal">
      <div>
        <div class="display">Engineering for extreme environments</div>
        <p class="subtext">SiCore Research designs and builds silicon carbide (SiC) power electronics that thrive where others fail. By eliminating costly power modules, we improve reliability while slashing cost and footprint. We partner with integrators across defense, mobility, and energy to accelerate electrification programs from concept to production.</p>
      </div>
      <div class="image-frame">
        <img src="images/about.jpg" alt="Inverter hardware">
      </div>
    </div>
  </section>

  <!-- CAPABILITIES / FEATURE CARDS -->
  <section id="capabilities" class="section">
    <div class="cards reveal">
      <div class="card">
        <h3>Rugged by Design</h3>
        <p>-40°C to 150°C operation, shock & vibration tolerant packaging, and conformal coatings for harsh environments.</p>
      </div>
      <div class="card">
        <h3>State-of-the-Art SiC</h3>
        <p>Innovative manufacturing techniques eliminate expensive power modules while improving reliability and cost.</p>
      </div>
      <div class="card">
        <h3>Scalable Platforms</h3>
        <p>Reference designs scale from kilowatts to megawatts with common control and thermal architectures.</p>
      </div>
      <div class="card">
        <h3>Rapid Integration</h3>
        <p>Open interfaces, documentation, and co‑design support to accelerate lab bring‑up and fielding.</p>
      </div>
    </div>
  </section>

  <!-- SPLIT SECTION (ALT BACKGROUND) -->
  <section class="section dark">
    <div class="two-col reveal">
      <div>
        <div class="display">Defense‑adjacent focus</div>
        <p class="subtext">We partner with primes, tier‑1s, and fast‑moving programs where reliability matters most. From vehicle electrification to expeditionary power, our tech is built for the edge.</p>
      </div>
      <div class="image-frame"><img src="images/about.jpg" alt="Defense systems"></div>
    </div>
  </section>

  <!-- CTA BAND -->
  <section class="cta-band reveal">
    <div class="cta-inner">
      <h3>Ready to prototype?</h3>
      <p>Kick off a discovery call and get a proposed path to hardware in under two weeks.</p>
      <a href="#contact" class="btn">Start Building →</a>
    </div>
  </section>

  <section id="contact" class="section">
    <div class="two-col reveal">
      <div>
        <div class="display">Start Building</div>
        <p class="subtext">Ready to design the future with us? Tell us about your application and we’ll reach out to start building together.</p>
        <form id="contact-form" action="https://formsubmit.co/contact@sicore-research.com" method="POST" target="hidden_iframe" onsubmit="showModal()">
          <input type="hidden" name="_subject" value="New inquiry from SiCore website">
          <input type="hidden" name="_captcha" value="true">
          <input type="text" name="_honey" style="display:none">
          <input id="first" name="first" placeholder="First Name" required>
          <input id="last" name="last" placeholder="Last Name" required>
          <input id="email" type="email" name="email" placeholder="Email" required>
          <textarea id="message" name="message" placeholder="Message" required></textarea>
          <button class="btn primary" type="submit">SEND</button>
        </form>
        <iframe name="hidden_iframe" style="display:none;"></iframe>
      </div>
      <div class="image-frame">
        <img src="images/contact.jpg" alt="Electronics">
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

  <footer class="site-footer">
    <div class="footer-grid">
      <div>
        <div class="brand">SiCore Research</div>
        <p class="footcopy">Rugged silicon carbide power electronics for extreme environments.</p>
      </div>
      <div>
        <h4>Company</h4>
        <a href="#about">About</a>
        <a href="#capabilities">Capabilities</a>
        <a href="#contact">Start Building</a>
      </div>
      <div>
        <h4>Resources</h4>
        <a href="#" onclick="alert('Datasheets coming soon');return false;">Datasheets</a>
        <a href="#" onclick="alert('Careers coming soon');return false;">Careers</a>
        <a href="#" onclick="alert('News coming soon');return false;">News</a>
      </div>
    </div>
    <div class="footnote">©2025 SiCore Research, LLC</div>
  </footer>

  <script>
    // Header scroll style & top offset with announcement bar
    function applyHeaderTop(){
      const h = document.getElementById('site-header');
      const bar = document.getElementById('announceBar');
      h.style.top = (bar && !bar.classList.contains('hidden')) ? '40px' : '0';
    }
    window.addEventListener('scroll',function(){
      const h = document.getElementById('site-header');
      h.classList.toggle('scrolled', window.scrollY>50);
    });

    // Dismissible announcement bar (persists via localStorage)
    function dismissAnnounce(){
      const bar = document.getElementById('announceBar');
      bar.classList.add('hidden');
      localStorage.setItem('sicore_announce_dismissed','1');
      applyHeaderTop();
    }
    (function initAnnouncement(){
      if(localStorage.getItem('sicore_announce_dismissed')==='1'){
        const bar = document.getElementById('announceBar');
        if(bar) bar.classList.add('hidden');
      }
      applyHeaderTop();
    })();

    // Hamburger menu (desktop + mobile)
    const menuBtn = document.getElementById('menuBtn');
    const menu = document.getElementById('menu');
    function closeMenu(){ menu.style.display='none'; menuBtn.setAttribute('aria-expanded','false'); }
    menuBtn.addEventListener('click', (e)=>{
      e.stopPropagation();
      const open = menu.style.display==='flex';
      menu.style.display = open? 'none' : 'flex';
      menuBtn.setAttribute('aria-expanded', String(!open));
      menu.style.flexDirection = 'column';
    });
    document.addEventListener('click', (e)=>{ if(!menu.contains(e.target) && e.target!==menuBtn){ closeMenu(); } });
    window.addEventListener('scroll', closeMenu);

    // Dots nav behavior
    const dots = document.querySelectorAll('.dot');
    dots.forEach(d => d.addEventListener('click', () => {
      const target = document.querySelector(d.dataset.target);
      if(target){ target.scrollIntoView({behavior:'smooth'}); }
    }));
    const sections = ['#about','#capabilities','#contact']
      .map(sel => document.querySelector(sel))
      .filter(Boolean);
    function updateActiveDot(){
      let idx = 0; let min = Infinity;
      sections.forEach((sec,i)=>{
        const rect = sec.getBoundingClientRect();
        const dist = Math.abs(rect.top - window.innerHeight*0.3);
        if(dist < min){ min=dist; idx=i; }
      });
      dots.forEach((d,i)=> d.classList.toggle('active', i===idx));
    }
    window.addEventListener('scroll', updateActiveDot);
    updateActiveDot();

    // Reveal on scroll
    const io = new IntersectionObserver(entries => {
      entries.forEach(e => { if (e.isIntersecting) e.target.classList.add('in'); });
    }, { threshold: 0.12 });
    document.querySelectorAll('.reveal').forEach(el => io.observe(el));

    // Contact form modal
    function showModal(){ setTimeout(function(){ document.getElementById('thankyouModal').style.display='flex'; document.getElementById('contact-form').reset(); }, 700); }
    function closeModal(){ document.getElementById('thankyouModal').style.display='none'; }

    // Disable hero video on small screens (optional data saver)
    if (window.matchMedia('(max-width: 600px)').matches) {
      const v = document.querySelector('.hero-video'); if (v) v.remove();
    }
  </script>
</body>
</html>
