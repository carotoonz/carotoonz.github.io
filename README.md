
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CULTURA — Connecting US Buyers to Latin America</title>
<meta name="description" content="Independent property concierge connecting qualified US buyers with trusted real estate partners across Latin America. Starting in Riviera Nayarit, México.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet">

<style>
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

:root {
  --sand: #F5F0E8;
  --sand-mid: #EAE3D5;
  --stone: #C8BCA8;
  --earth: #8C7B68;
  --deep: #2C2720;
  --ocean: #1A3A3A;
  --accent: #B8956A;
  --accent-light: #D4B08C;
  --white: #FDFCF9;
  --serif: 'Cormorant Garamond', Georgia, serif;
  --sans: 'Jost', sans-serif;
}

html { scroll-behavior: smooth; }
body { font-family: var(--sans); background: var(--white); color: var(--deep); font-weight: 300; overflow-x: hidden; }

/* NAV */
nav {
  position: fixed; top: 0; left: 0; right: 0; z-index: 200;
  padding: 1.5rem 3rem;
  display: flex; justify-content: space-between; align-items: center;
  transition: background 0.4s, padding 0.4s, box-shadow 0.4s;
}
nav.scrolled {
  background: rgba(253,252,249,0.97);
  padding: 1rem 3rem;
  box-shadow: 0 1px 0 var(--sand-mid);
}
.nav-logo {
  font-family: var(--serif); font-size: 1.5rem; font-weight: 400;
  letter-spacing: 0.08em; color: var(--white); text-decoration: none;
  transition: color 0.4s; z-index: 201; position: relative;
}
nav.scrolled .nav-logo { color: var(--deep); }
.nav-links { display: flex; gap: 2.5rem; list-style: none; }
.nav-links a {
  font-size: 0.72rem; letter-spacing: 0.15em; text-transform: uppercase;
  color: rgba(255,255,255,0.8); text-decoration: none; transition: color 0.3s;
}
nav.scrolled .nav-links a { color: var(--earth); }
.nav-links a:hover { color: var(--accent-light); }
nav.scrolled .nav-links a:hover { color: var(--accent); }

.nav-toggle {
  display: none; flex-direction: column; gap: 5px;
  cursor: pointer; z-index: 201; background: none; border: none; padding: 4px;
}
.nav-toggle span {
  display: block; width: 22px; height: 1.5px; background: var(--white);
  transition: background 0.4s, transform 0.3s, opacity 0.3s;
}
nav.scrolled .nav-toggle span { background: var(--deep); }
.nav-toggle.open span:nth-child(1) { transform: translateY(6.5px) rotate(45deg); }
.nav-toggle.open span:nth-child(2) { opacity: 0; }
.nav-toggle.open span:nth-child(3) { transform: translateY(-6.5px) rotate(-45deg); }

/* HERO */
.hero {
  height: 100vh; min-height: 640px; position: relative;
  display: flex; align-items: flex-end; padding: 0 3rem 5rem; overflow: hidden;
}
.hero-bg {
  position: absolute; inset: 0; z-index: 0;
  background: linear-gradient(160deg, #1A3A3A 0%, #2C4A3A 30%, #3A4A35 55%, #1A2A2A 100%);
}
.hero-bg::after {
  content: ''; position: absolute; inset: 0;
  background:
    radial-gradient(ellipse at 60% 40%, rgba(184,149,106,0.13) 0%, transparent 60%),
    radial-gradient(ellipse at 15% 75%, rgba(74,94,74,0.2) 0%, transparent 50%),
    linear-gradient(to bottom, rgba(26,42,42,0.1) 0%, rgba(26,42,42,0.72) 100%);
}
.hero-content { position: relative; z-index: 2; max-width: 720px; }
.hero-eyebrow {
  font-size: 0.68rem; letter-spacing: 0.28em; text-transform: uppercase;
  color: var(--accent-light); margin-bottom: 1.25rem;
  opacity: 0; animation: fadeUp 0.8s 0.3s forwards;
}
.hero-title {
  font-family: var(--serif); font-size: clamp(2.8rem, 6vw, 5.5rem);
  font-weight: 300; line-height: 1.05; color: var(--white); margin-bottom: 1.5rem;
  opacity: 0; animation: fadeUp 0.9s 0.5s forwards;
}
.hero-title em { font-style: italic; color: var(--accent-light); }
.hero-sub {
  font-size: 1rem; font-weight: 300; color: rgba(253,252,249,0.7);
  line-height: 1.75; max-width: 520px; margin-bottom: 2.5rem;
  opacity: 0; animation: fadeUp 0.9s 0.7s forwards;
}
.hero-cta {
  display: inline-block; padding: 0.9rem 2.5rem;
  border: 0.5px solid var(--accent-light); color: var(--accent-light);
  font-family: var(--sans); font-size: 0.7rem; font-weight: 400;
  letter-spacing: 0.22em; text-transform: uppercase; text-decoration: none;
  transition: background 0.3s, color 0.3s, border-color 0.3s;
  opacity: 0; animation: fadeUp 0.9s 0.9s forwards;
}
.hero-cta:hover { background: var(--accent); border-color: var(--accent); color: var(--white); }

/* MISSION */
.mission { 
  display: grid; grid-template-columns: 1fr 1fr; 
  min-height: 70vh; background: var(--white);
}
.mission-text {
  padding: 6rem 4rem 6rem 5rem;
  display: flex; flex-direction: column; justify-content: center;
}
.section-label {
  font-size: 0.65rem; letter-spacing: 0.25em; text-transform: uppercase;
  color: var(--accent); margin-bottom: 1.25rem;
}
.section-title {
  font-family: var(--serif); font-size: clamp(1.9rem, 3vw, 2.9rem);
  font-weight: 300; line-height: 1.15; color: var(--deep); margin-bottom: 1.75rem;
}
.section-title em { font-style: italic; }
.section-body {
  font-size: 0.93rem; font-weight: 300; color: var(--earth);
  line-height: 1.9; max-width: 460px; margin-bottom: 1.5rem;
}
.mission-visual {
  background: var(--sand); position: relative; overflow: hidden;
  display: flex; align-items: center; justify-content: center; padding: 4rem;
}
.mission-stats {
  display: grid; grid-template-columns: 1fr 1fr; gap: 2rem;
  width: 100%;
}
.stat-box {
  background: var(--white); padding: 2rem;
  border-left: 2px solid var(--accent);
}
.stat-num { 
  font-family: var(--serif); font-size: 2.2rem; 
  font-weight: 300; color: var(--deep); line-height: 1; 
}
.stat-label { 
  font-size: 0.7rem; letter-spacing: 0.12em; 
  text-transform: uppercase; color: var(--earth); margin-top: 0.5rem; 
}

/* SERVICES */
.services { background: var(--deep); padding: 7rem 5rem; }
.services-header { 
  text-align: center; max-width: 700px; margin: 0 auto 4.5rem; 
}
.services-title {
  font-family: var(--serif); font-size: clamp(2rem, 3vw, 3.2rem);
  font-weight: 300; line-height: 1.15; color: var(--white); margin-bottom: 1rem;
}
.services-sub { 
  font-size: 0.9rem; font-weight: 300; 
  color: rgba(253,252,249,0.5); line-height: 1.9; 
}
.service-grid {
  display: grid; grid-template-columns: repeat(3, 1fr); gap: 1.5rem;
}
.service-card {
  background: rgba(253,252,249,0.03);
  border: 0.5px solid rgba(253,252,249,0.08);
  padding: 2.5rem 2rem;
  transition: all 0.4s ease;
}
.service-card:hover {
  background: rgba(253,252,249,0.05);
  border-color: rgba(184,149,106,0.3);
  transform: translateY(-4px);
}
.service-tier {
  font-size: 0.62rem; letter-spacing: 0.2em; text-transform: uppercase;
  color: var(--accent-light); margin-bottom: 1rem;
}
.service-name {
  font-family: var(--serif); font-size: 1.6rem; font-weight: 400;
  color: var(--white); margin-bottom: 0.75rem; line-height: 1.2;
}
.service-price {
  font-family: var(--serif); font-size: 2.2rem; font-weight: 300;
  color: var(--accent); margin-bottom: 1.5rem;
}
.service-desc {
  font-size: 0.86rem; font-weight: 300; color: rgba(253,252,249,0.5);
  line-height: 1.8; margin-bottom: 1.75rem;
}
.service-features {
  list-style: none; margin-bottom: 2rem;
}
.service-features li {
  font-size: 0.8rem; color: rgba(253,252,249,0.6);
  padding: 0.5rem 0; padding-left: 1.25rem; position: relative;
}
.service-features li::before {
  content: '·'; position: absolute; left: 0;
  color: var(--accent); font-size: 1.2rem;
}
.service-cta {
  display: inline-block; width: 100%;
  padding: 0.85rem 2rem; text-align: center;
  border: 0.5px solid rgba(253,252,249,0.2);
  color: var(--white); background: transparent;
  font-size: 0.68rem; letter-spacing: 0.18em;
  text-transform: uppercase; text-decoration: none;
  transition: all 0.3s;
}
.service-cta:hover {
  background: var(--accent); border-color: var(--accent);
}

/* VISION */
.vision {
  display: grid; grid-template-columns: 5fr 7fr; min-height: 65vh;
}
.vision-visual {
  background: linear-gradient(170deg, #2C4A3A 0%, #1A3A3A 100%);
  position: relative; display: flex; flex-direction: column;
  justify-content: flex-end; padding: 3rem; overflow: hidden;
}
.vision-visual::before {
  content: ''; position: absolute; inset: 0;
  background: radial-gradient(ellipse at 30% 25%, rgba(184,149,106,0.14) 0%, transparent 55%);
}
.vision-quote {
  position: relative; font-family: var(--serif); font-size: 1.5rem;
  font-weight: 300; font-style: italic; color: rgba(253,252,249,0.82);
  line-height: 1.45; margin-bottom: 0.85rem;
}
.vision-attr { 
  position: relative; font-size: 0.67rem; letter-spacing: 0.16em; 
  text-transform: uppercase; color: var(--accent-light); 
}
.vision-content { 
  padding: 5rem 4rem 5rem 5rem; background: var(--white); 
  display: flex; flex-direction: column; justify-content: center; 
}
.vision-pillars { 
  display: flex; flex-direction: column; gap: 1.75rem; margin-top: 2.25rem; 
}
.pillar { 
  display: grid; grid-template-columns: 2.5rem 1fr; 
  gap: 1.1rem; align-items: start; 
}
.pillar-icon {
  font-family: var(--serif); font-size: 1.2rem; 
  font-weight: 300; color: var(--accent); padding-top: 0.05rem;
}
.pillar-title { 
  font-size: 0.95rem; font-weight: 500; 
  color: var(--deep); margin-bottom: 0.4rem; 
}
.pillar-body { 
  font-size: 0.84rem; font-weight: 300; 
  color: var(--earth); line-height: 1.8; 
}

/* CTA SECTION */
.cta-section {
  background: var(--sand-mid); padding: 6rem 5rem;
  text-align: center;
}
.cta-title {
  font-family: var(--serif); font-size: clamp(2rem, 3vw, 2.8rem);
  font-weight: 300; line-height: 1.2; color: var(--deep);
  margin-bottom: 1.5rem;
}
.cta-sub {
  font-size: 0.92rem; font-weight: 300; color: var(--earth);
  line-height: 1.8; max-width: 560px; margin: 0 auto 2.5rem;
}
.cta-buttons {
  display: flex; gap: 1.25rem; justify-content: center;
  flex-wrap: wrap;
}
.cta-btn-primary {
  display: inline-block; padding: 1rem 2.8rem;
  background: var(--deep); color: var(--white);
  font-size: 0.7rem; letter-spacing: 0.2em;
  text-transform: uppercase; text-decoration: none;
  transition: background 0.3s;
}
.cta-btn-primary:hover { background: var(--ocean); }
.cta-btn-secondary {
  display: inline-block; padding: 1rem 2.8rem;
  border: 0.5px solid var(--deep); color: var(--deep);
  background: transparent;
  font-size: 0.7rem; letter-spacing: 0.2em;
  text-transform: uppercase; text-decoration: none;
  transition: all 0.3s;
}
.cta-btn-secondary:hover {
  background: var(--deep); color: var(--white);
}

/* FOOTER */
footer {
  background: #1A1610; padding: 2.25rem 5rem;
  display: flex; justify-content: space-between; align-items: center;
  flex-wrap: wrap; gap: 1rem;
}
.footer-logo { 
  font-family: var(--serif); font-size: 1.1rem; 
  font-weight: 400; letter-spacing: 0.08em; 
  color: rgba(253,252,249,0.35); 
}
.footer-copy { 
  font-size: 0.68rem; color: rgba(253,252,249,0.18); 
  letter-spacing: 0.05em; 
}
.footer-links { display: flex; gap: 1.75rem; list-style: none; }
.footer-links a { 
  font-size: 0.65rem; letter-spacing: 0.14em; 
  text-transform: uppercase; color: rgba(253,252,249,0.28); 
  text-decoration: none; transition: color 0.3s; 
}
.footer-links a:hover { color: var(--accent-light); }

/* REVEAL */
.reveal { 
  opacity: 0; transform: translateY(22px); 
  transition: opacity 0.7s ease, transform 0.7s ease; 
}
.reveal.visible { opacity: 1; transform: translateY(0); }

/* KEYFRAMES */
@keyframes fadeUp { 
  from { opacity:0; transform:translateY(20px); } 
  to { opacity:1; transform:translateY(0); } 
}

/* MOBILE */
@media (max-width: 900px) {
  nav { padding: 1.2rem 1.5rem; }
  nav.scrolled { padding: 1rem 1.5rem; }
  .nav-links {
    display: none; position: fixed; inset: 0; background: var(--deep);
    flex-direction: column; align-items: center; justify-content: center; gap: 2.5rem;
  }
  .nav-links.open { display: flex; }
  .nav-links a { font-size: 1rem; color: rgba(253,252,249,0.75); }
  .nav-toggle { display: flex; }

  .hero { padding: 0 1.5rem 4rem; }
  
  .mission { grid-template-columns: 1fr; }
  .mission-text { padding: 4rem 1.5rem; }
  .mission-visual { padding: 3rem 1.5rem; }
  
  .services { padding: 5rem 1.5rem; }
  .service-grid { grid-template-columns: 1fr; }
  
  .vision { grid-template-columns: 1fr; }
  .vision-visual { min-height: 240px; padding: 2.5rem; }
  .vision-content { padding: 3.5rem 1.5rem; }
  
  .cta-section { padding: 5rem 1.5rem; }
  .cta-buttons { flex-direction: column; align-items: stretch; }
  
  footer { 
    padding: 2rem 1.5rem; flex-direction: column; 
    align-items: flex-start; gap: 1.25rem; 
  }
}
</style>
</head>
<body>

<!-- NAV -->
<nav id="nav">
  <a href="#" class="nav-logo">CULTURA</a>
  <ul class="nav-links" id="navLinks">
    <li><a href="#mission" onclick="closeMenu()">Mission</a></li>
    <li><a href="#services" onclick="closeMenu()">Services</a></li>
    <li><a href="#vision" onclick="closeMenu()">Vision</a></li>
    <li><a href="#contact" onclick="closeMenu()">Contact</a></li>
  </ul>
  <button class="nav-toggle" id="navToggle" aria-label="Open menu">
    <span></span><span></span><span></span>
  </button>
</nav>

<!-- HERO -->
<section class="hero">
  <div class="hero-bg"></div>
  <div class="hero-content">
    <p class="hero-eyebrow">Independent Property Concierge</p>
    <h1 class="hero-title">Bridging cultures,<br><em>building wealth.</em></h1>
    <p class="hero-sub">CULTURA connects qualified US buyers with trusted real estate partners across Latin America. We handle research, logistics, and translation — so every transaction feels clear, personal, and right.</p>
    <a href="#contact" class="hero-cta">Start your search</a>
  </div>
</section>

<!-- MISSION -->
<section class="mission" id="mission">
  <div class="mission-text">
    <p class="section-label reveal">Our Mission</p>
    <h2 class="section-title reveal">Make Latin America <em>accessible</em> for American investors.</h2>
    <p class="section-body reveal">Too many incredible properties go unseen by US buyers. Too many deals fall apart due to language barriers, legal confusion, or broken trust.</p>
    <p class="section-body reveal">CULTURA exists to fix that. We're dual citizens, bilingual professionals who live on the ground — bringing you vetted opportunities, transparent guidance, and seamless coordination from first call to closing day.</p>
  </div>
  <div class="mission-visual">
    <div class="mission-stats">
      <div class="stat-box reveal">
        <div class="stat-num">Dual</div>
        <div class="stat-label">US & Mexican Citizenship</div>
      </div>
      <div class="stat-box reveal">
        <div class="stat-num">100%</div>
        <div class="stat-label">Transparent Fees</div>
      </div>
      <div class="stat-box reveal">
        <div class="stat-num">On Ground</div>
        <div class="stat-label">Riviera Nayarit Based</div>
      </div>
      <div class="stat-box reveal">
        <div class="stat-num">Expanding</div>
        <div class="stat-label">Across Latin America</div>
      </div>
    </div>
  </div>
</section>

<!-- SERVICES -->
<section class="services" id="services">
  <div class="services-header">
    <h2 class="services-title reveal">How we work with you</h2>
    <p class="services-sub reveal">Choose the level of support that fits your needs. Every package includes bilingual coordination, trusted partner introductions, and complete transparency.</p>
  </div>
  
  <div class="service-grid">
    <div class="service-card reveal">
      <p class="service-tier">Starter</p>
      <h3 class="service-name">Market Intelligence</h3>
      <div class="service-price">$297</div>
      <p class="service-desc">Perfect for buyers exploring whether Latin America is right for them.</p>
      <ul class="service-features">
        <li>45-minute consultation call</li>
        <li>Market overview for Riviera Nayarit</li>
        <li>Neighborhood comparison (3 areas)</li>
        <li>Investment potential analysis</li>
        <li>Recommended next steps</li>
        <li>Email follow-up resources</li>
      </ul>
      <a href="#contact" class="service-cta">Get started</a>
    </div>

    <div class="service-card reveal">
      <p class="service-tier">Most Popular</p>
      <h3 class="service-name">Property Scout</h3>
      <div class="service-price">$997</div>
      <p class="service-desc">We find properties, tour them for you, and deliver detailed reports.</p>
      <ul class="service-features">
        <li>Everything in Market Intelligence</li>
        <li>On-ground visits to 3-5 properties</li>
        <li>Professional photo & video documentation</li>
        <li>ROI analysis for each property</li>
        <li>Neighborhood assessment reports</li>
        <li>Introduction to trusted attorney</li>
        <li>60-day email support</li>
      </ul>
      <a href="#contact" class="service-cta">Get started</a>
    </div>

    <div class="service-card reveal">
      <p class="service-tier">Comprehensive</p>
      <h3 class="service-name">Full Concierge</h3>
      <div class="service-price">$2,497</div>
      <p class="service-desc">White-glove service from search to closing. We handle everything.</p>
      <ul class="service-features">
        <li>Everything in Property Scout</li>
        <li>Unlimited property visits (60 days)</li>
        <li>In-person or virtual property tours</li>
        <li>Attorney & notary coordination</li>
        <li>Translation of all documents</li>
        <li>Inspection coordination</li>
        <li>Transaction oversight</li>
        <li>6-month ongoing support</li>
        <li>Plus: 1-3% referral commission when deal closes</li>
      </ul>
      <a href="#contact" class="service-cta">Get started</a>
    </div>
  </div>
</section>

<!-- VISION -->
<section class="vision" id="vision">
  <div class="vision-visual">
    <p class="vision-quote">"The best investment opportunities in the Americas are still being missed by those who need them most."</p>
    <p class="vision-attr">Our Founding Belief</p>
  </div>
  <div class="vision-content">
    <p class="section-label reveal">Our Vision</p>
    <h2 class="section-title reveal">Scale across <em>all</em> of Latin America.</h2>
    <div class="vision-pillars">
      <div class="pillar reveal">
        <div class="pillar-icon">I</div>
        <div>
          <p class="pillar-title">Start in Riviera Nayarit</p>
          <p class="pillar-body">We're building our foundation in Mexico's most undervalued coastal market — then expanding to Tulum, Playa del Carmen, and beyond.</p>
        </div>
      </div>
      <div class="pillar reveal">
        <div class="pillar-icon">II</div>
        <div>
          <p class="pillar-title">Expand to Colombia, Costa Rica, Uruguay</p>
          <p class="pillar-body">The same model works everywhere Americans want to invest but struggle with language, legal systems, and trust. We'll be there.</p>
        </div>
      </div>
      <div class="pillar reveal">
        <div class="pillar-icon">III</div>
        <div>
          <p class="pillar-title">Build the most trusted brand</p>
          <p class="pillar-body">CULTURA will be synonymous with safe, transparent, profitable Latin American real estate for English-speaking buyers. One deal at a time.</p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- CTA -->
<section class="cta-section" id="contact">
  <h2 class="cta-title reveal">Ready to explore Latin America?</h2>
  <p class="cta-sub reveal">Whether you're buying your first investment property or building a portfolio, we're here to make it seamless.</p>
  <div class="cta-buttons reveal">
    <a href="mailto:hello@culturaproperties.com" class="cta-btn-primary">Schedule consultation</a>
    <a href="mailto:hello@culturaproperties.com?subject=Download Buyer's Guide" class="cta-btn-secondary">Download free buyer's guide</a>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-logo">CULTURA</div>
  <ul class="footer-links">
    <li><a href="#mission">Mission</a></li>
    <li><a href="#services">Services</a></li>
    <li><a href="#vision">Vision</a></li>
    <li><a href="#contact">Contact</a></li>
  </ul>
  <p class="footer-copy">© 2025 CULTURA · Independent Property Concierge · Not a licensed broker</p>
</footer>

<script>
// Nav scroll + mobile
const nav = document.getElementById('nav');
const navToggle = document.getElementById('navToggle');
const navLinks = document.getElementById('navLinks');

window.addEventListener('scroll', () => {
  nav.classList.toggle('scrolled', window.scrollY > 50);
});
navToggle.addEventListener('click', () => {
  const open = navToggle.classList.toggle('open');
  navLinks.classList.toggle('open', open);
  navToggle.setAttribute('aria-label', open ? 'Close menu' : 'Open menu');
});
function closeMenu() {
  navToggle.classList.remove('open');
  navLinks.classList.remove('open');
}

// Scroll reveal
const revealObserver = new IntersectionObserver(entries => {
  entries.forEach(e => { 
    if (e.isIntersecting) { 
      e.target.classList.add('visible'); 
      revealObserver.unobserve(e.target); 
    } 
  });
}, { threshold: 0.1 });
document.querySelectorAll('.reveal').forEach(el => revealObserver.observe(el));
</script>
</body>
</html>
