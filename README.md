 Jura & Cakes
<!DOCTYPE html>
<html lang="en">
<head <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Jura and Cakes — Cakes Worth the Occasion</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Fraunces:ital,opsz,wght@0,9..144,300;0,9..144,500;0,9..144,600;1,9..144,500&family=Work+Sans:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --espresso:#2E2018;
    --cream:#44dad5;
    --cream-2:#23aaaa;
    --berry:#1b5198;
    --berry-dark:#df43c0;
    --gold:#cc1dd2;
    --sage:#74806A;
    --white:#8ef5dc;
    --radius:2px;
  }
  *{box-sizing:border-box;}
  html{scroll-behavior:smooth;}
  body{
    margin:0;
    background:var(--blue);
    color:var(--espresso);
    font-family:'Work Sans', sans-serif;
    font-weight:400;
    line-height:1.5;
  }
  h1,h2,h3, .display{
    font-family:'Fraunces', serif;
    font-weight:500;
    margin:0;
  }
  .italic-accent{ font-style:italic; font-weight:500; color:var(--dark); }
  a{ color:inherit; text-decoration:none; }
  img{max-width:100%;display:block;}
  .eyebrow{
    font-size:.72rem;
    letter-spacing:.18em;
    text-transform:uppercase;
    color:var(--sage);
    font-weight:600;
  }
  .wrap{ max-width:1180px; margin:0 auto; padding:0 32px; }
  @media (max-width:640px){ .wrap{ padding:0 20px; } }

  /* ---------- Signature tier mark ---------- */
  .tier-mark{ display:inline-flex; flex-direction:column; align-items:center; gap:3px; }
  .tier-mark span{ display:block; background:var(--gold); border-radius:1px; }
  .tier-mark .t1{ width:18px; height:4px; }
  .tier-mark .t2{ width:12px; height:4px; }
  .tier-mark .t3{ width:6px;  height:4px; }

  /* ---------- Header ---------- */
  header{
    position:sticky; top:0; z-index:50;
    background:rgb(246, 225, 247);
    backdrop-filter:blur(6px);
    border-bottom:1px solid rgba(48, 142, 114, 0.1);
  }
  .nav-row{
    display:flex; align-items:center; justify-content:space-between;
    padding:18px 0;
  }
  .logo{
    font-family:'Fraunces', serif;
    font-size:1.3rem;
    letter-spacing:.01em;
    display:flex; align-items:center; gap:10px;
    white-space:nowrap;
  }
  nav.links{ display:flex; gap:34px; }
  nav.links a{
    font-size:.86rem; letter-spacing:.03em; position:relative; padding:4px 0;
  }
  nav.links a::after{
    content:''; position:absolute; left:0; bottom:0; height:2px; width:0;
    background:var(--berry); transition:width .28s ease;
  }
  nav.links a:hover::after{ width:100%; }
  .header-actions{ display:flex; align-items:center; gap:20px; }
  .cart-btn{
    display:flex; align-items:center; gap:8px;
    font-size:.86rem; letter-spacing:.02em;
    border:1px solid var(--espresso); padding:9px 16px;
    border-radius:20px; cursor:pointer; background:transparent;
    font-family:'Work Sans', sans-serif; color:var(--espresso);
    transition:background .2s ease, color .2s ease;
  }
  .cart-btn:hover{ background:var(--espresso); color:var(--cream); }
  .cart-count{
    background:var(--berry); color:#135a5f; border-radius:50%;
    width:18px; height:18px; font-size:.68rem; display:flex;
    align-items:center; justify-content:center;
  }
  .menu-toggle{ display:none; background:none; border:none; cursor:pointer; }
  @media (max-width: 880px){
    nav.links{ display:none; }
    .menu-toggle{ display:block; }
  }

  /* ---------- Hero ---------- */
  .hero{
    padding:90px 0 70px;
    display:grid; grid-template-columns:1.05fr .95fr; gap:60px; align-items:center;
  }
  @media (max-width:880px){ .hero{ grid-template-columns:1fr; padding:50px 0 40px; gap:36px; } }
  .hero h1{
    font-size:clamp(2.6rem, 5vw, 4.4rem);
    line-height:1.02;
    letter-spacing:-.01em;
  }
  .hero p.lede{
    max-width:440px; margin-top:22px; font-size:1.05rem; color:#2f454a;
  }
  .hero-ctas{ display:flex; gap:16px; margin-top:34px; flex-wrap:wrap; }
  .btn{
    display:inline-block; padding:14px 26px; font-size:.88rem;
    letter-spacing:.04em; text-transform:uppercase; border-radius:2px;
    transition:transform .25s ease, background .25s ease, color .25s ease;
    cursor:pointer; border:1px solid var(--espresso);
  }
  .btn-solid{ background:var(--espresso); color:var(--cream); }
  .btn-solid:hover{ background:var(--berry); border-color:var(--berry); transform:translateY(-2px); }
  .btn-line{ background:transparent; color:var(--espresso); }
  .btn-line:hover{ background:var(--espresso); color:var(--cream); transform:translateY(-2px); }

  /* Hero cake illustration */
  .cake-illustration{ display:flex; justify-content:center; align-items:flex-end; position:relative; height:420px; }
  .candle-flame{
    animation:flicker 2.4s ease-in-out infinite;
    transform-origin:center bottom;
  }
  @media (prefers-reduced-motion: reduce){ .candle-flame{ animation:none; } }
  @keyframes flicker{
    0%,100%{ transform:scaleY(1) translateX(0); opacity:1; }
    50%{ transform:scaleY(1.12) translateX(1px); opacity:.9; }
  }

  /* ---------- Marquee strip ---------- */
  .marquee{
    background:var(--espresso); color:var(--cream);
    padding:14px 0; overflow:hidden; white-space:nowrap;
  }
  .marquee-inner{ display:inline-block; animation:scroll 26s linear infinite; font-family:'Fraunces', serif; font-style:italic; font-size:1.05rem; }
  @media (prefers-reduced-motion: reduce){ .marquee-inner{ animation:none; } }
  .marquee-inner span{ margin:0 28px; color:var(--gold); }
  @keyframes scroll{ from{ transform:translateX(0); } to{ transform:translateX(-50%); } }

  /* ---------- Section heading ---------- */
  .section{ padding:88px 0; }
  .section-head{ display:flex; justify-content:space-between; align-items:flex-end; margin-bottom:46px; gap:20px; flex-wrap:wrap; }
  .section-head h2{ font-size:clamp(2rem,3.4vw,2.7rem); margin-top:10px; }

  /* ---------- Collections grid ---------- */
  .collections{ display:grid; grid-template-columns:repeat(3,1fr); gap:26px; }
  @media (max-width:880px){ .collections{ grid-template-columns:repeat(2,1fr); } }
  @media (max-width:560px){ .collections{ grid-template-columns:1fr; } }
  .collection-card{
    position:relative; border-radius:var(--radius); overflow:hidden;
    aspect-ratio:4/5; display:flex; flex-direction:column; justify-content:flex-end;
    padding:26px; cursor:pointer; isolation:isolate;
  }
  .collection-card::before{
    content:''; position:absolute; inset:0; z-index:-1;
    transition:transform .5s cubic-bezier(.2,.7,.2,1);
  }
  .collection-card:hover::before{ transform:scale(1.06); }
  .collection-card::after{
    content:''; position:absolute; inset:0; z-index:-1;
    background:linear-gradient(180deg, rgba(46,32,24,0) 30%, rgba(46,32,24,.78) 100%);
  }
  .collection-card h3{ color:#fff; font-size:1.5rem; }
  .collection-card p{ color:var(--cream-2); font-size:.85rem; margin-top:6px; }
  .c1::before{ background:linear-gradient(155deg,#7b3a8b,#5f2530); }
  .c2::before{ background:linear-gradient(155deg,#9c4bc7,#2c8a7d); }
  .c3::before{ background:linear-gradient(155deg,#74806A,#454e3d); }
  .c3::before{ background:linear-gradient(155deg,#74806A,#4a352a); }
  .c4::before{ background:linear-gradient(155deg,#2c182ed6,#2a4a38); }
  .c5::before{ background:linear-gradient(155deg,#906eb7,#7c4650); }
  .c6::before{ background:linear-gradient(155deg,#598b9c,#5f4c30); }

  /* ---------- Split promo (custom order) ---------- */
  .promo{
    background:var(--espresso); color:var(--cream); border-radius:var(--radius);
    display:grid; grid-template-columns:1fr 1fr; overflow:hidden;
  }
  @media (max-width:880px){ .promo{ grid-template-columns:1fr; } }
  .promo-copy{ padding:64px 56px; }
  @media (max-width:640px){ .promo-copy{ padding:44px 28px; } }
  .promo-copy h2{ font-size:2.2rem; color:var(--cream); margin-top:14px; }
  .promo-copy p{ margin-top:18px; color:#cbb9a8; max-width:420px; }
  .promo-visual{
    background:linear-gradient(140deg, var(--berry), var(--berry-dark));
    display:flex; align-items:center; justify-content:center; min-height:280px;
  }
  .steps-mini{ display:flex; gap:26px; margin-top:30px; flex-wrap:wrap; }
  .steps-mini div{ font-size:.78rem; color:var(--gold); letter-spacing:.04em; }
  .steps-mini strong{ display:block; font-family:'Fraunces',serif; font-size:1.5rem; color:#fff; font-weight:500; }

  /* ---------- Gifts / corporate strip ---------- */
  .two-col{ display:grid; grid-template-columns:1fr 1fr; gap:26px; }
  @media (max-width:760px){ .two-col{ grid-template-columns:1fr; } }
  .feature-card{
    background:var(--white); border:1px solid rgba(46,32,24,.1); border-radius:var(--radius);
    padding:40px; transition:box-shadow .25s ease, transform .25s ease;
  }
  .feature-card:hover{ box-shadow:0 18px 40px rgba(80, 170, 161, 0.08); transform:translateY(-3px); }
  .feature-card .eyebrow{ margin-bottom:14px; }
  .feature-card h3{ font-size:1.5rem; margin-bottom:12px; }
  .feature-card p{ color:#5b493c; font-size:.95rem; }
  .feature-card a.more{ display:inline-block; margin-top:20px; font-size:.85rem; border-bottom:1px solid var(--berry); color:var(--berry); }

  /* ---------- About ---------- */
  .about{ display:grid; grid-template-columns:.9fr 1.1fr; gap:60px; align-items:center; }
  @media (max-width:880px){ .about{ grid-template-columns:1fr; } }
  .about-visual{
    aspect-ratio:1/1; border-radius:var(--radius);
    background:linear-gradient(160deg, var(--cream-2), var(--gold) 140%);
    position:relative; overflow:hidden;
  }
  .about p{ color:#4a3a2f; margin-top:18px; }
  .stat-row{ display:flex; gap:44px; margin-top:34px; flex-wrap:wrap; }
  .stat-row div strong{ display:block; font-family:'Fraunces',serif; font-size:2rem; font-weight:500; }
  .stat-row div span{ font-size:.78rem; color:var(--sage); letter-spacing:.03em; text-transform:uppercase; }

  /* ---------- Newsletter ---------- */
  .newsletter{
    background:var(--cream-2); border-radius:var(--radius); padding:60px 56px;
    display:flex; justify-content:space-between; align-items:center; gap:30px; flex-wrap:wrap;
  }
  .newsletter h3{ font-size:1.7rem; max-width:360px; }
  .newsletter form{ display:flex; gap:10px; flex:1; min-width:280px; max-width:420px; 5f4c30}
  .newsletter input{
    flex:1; padding:13px 16px; border:1px solid rgba(46,32,24,.25);
    border-radius:2px; font-family:'Work Sans',sans-serif; background:#fff;
  }
  .newsletter input:focus{ outline:2px solid var(--berry); outline-offset:1px; }

  /* ---------- Footer ---------- */
  footer{ background:var(--espresso); color:var(--cream-2); padding:64px 0 30px; margin-top:40px; }
  .footer-grid{ display:grid; grid-template-columns:1.4fr repeat(3,1fr); gap:40px; }
  @media (max-width:760px){ .footer-grid{ grid-template-columns:repeat(2,1fr); } }
  footer h4{ color:#ecaaaa; font-size:.8rem; letter-spacing:.08em; text-transform:uppercase; margin-bottom:16px; font-family:'Work Sans',sans-serif; font-weight:600; }
  footer ul{ list-style:none; padding:0; margin:0; display:flex; flex-direction:column; gap:10px; }
  footer a{ font-size:.9rem; color:#e1c5ab; }
  footer a:hover{ color:#987272; }
  .footer-bottom{ margin-top:50px; padding-top:24px; border-top:1px solid rgba(255,255,255,.12); display:flex; justify-content:space-between; font-size:.78rem; color:#a5917f; flex-wrap:wrap; gap:10px; }

  /* ---------- Cart drawer ---------- */
  .overlay{ position:fixed; inset:0; background:rgba(46,32,24,.4); z-index:90; opacity:0; pointer-events:none; transition:opacity .3s ease; }
  .overlay.open{ opacity:1; pointer-events:auto; }
  .drawer{
    position:fixed; top:0; right:0; height:100%; width:380px; max-width:90vw;
    background:var(--cream); z-index:100; box-shadow:-10px 0 30px rgba(0,0,0,.15);
    transform:translateX(100%); transition:transform .35s cubic-bezier(.2,.7,.2,1);
    display:flex; flex-direction:column;
  }
  .drawer.open{ transform:translateX(0); }
  .drawer-head{ display:flex; justify-content:space-between; align-items:center; padding:24px; border-bottom:1px solid rgba(46,32,24,.1); }
  .drawer-head h3{ font-size:1.3rem; }
  .drawer-close{ background:none; border:none; cursor:pointer; font-size:1.3rem; }
  .drawer-body{ padding:24px; overflow-y:auto; flex:1; }
  .drawer-empty{ text-align:center; color:#8a7867; padding:60px 10px; font-size:.9rem; }
  .cart-item{ display:flex; justify-content:space-between; align-items:center; padding:14px 0; border-bottom:1px solid rgba(46,32,24,.08); }
  .cart-item .name{ font-family:'Fraunces',serif; font-size:1rem; }
  .cart-item .price{ font-size:.85rem; color:var(--sage); }
  .cart-item button{ background:none; border:none; color:var(--berry); cursor:pointer; font-size:.8rem; }
  .drawer-foot{ padding:24px; border-top:1px solid rgba(46,32,24,.1); }
  .drawer-foot .btn{ width:100%; text-align:center; }
  .whatsapp-float{
  position:fixed;
  bottom:24px;
  right:24px;
  width:60px;
  height:60px;
  background:#25D366;
  border-radius:50%;
  display:flex;
  align-items:center;
  justify-content:center;
  box-shadow:0 6px 16px rgba(0,0,0,.3);
  z-index:200;
}
.whatsapp-float:hover{
  background:#1ebe57;
}


</style>
</head>
<body style="background-color: #e6e5e8d6;" div style="background-image:('WhatsApp Image 2026-09-14 at 4.10.30 PM (1).jpeg')" >
   
<header>
  <div class="wrap nav-row">
    <a href="#top" class="logo">
      <span class="tier-mark"><span class="t1"></span><span class="t2"></span><span class="t3"></span></span>
      Jura and Cakes
    </a>
    <nav class="links">
      <a href="#collections">Collections</a>
      <a href="#custom">Custom Order</a>
      <a href="#gifts">Gifts &amp; Corporate</a>
      <a href="#about">About</a>
      <a href="#contact">Contact</a>
    </nav>
    <div class="header-actions">
      <button class="cart-btn" id="cartOpenBtn" aria-haspopup="dialog" aria-controls="cartDrawer">
        Cart <span class="cart-count" id="cartCount">0</span>
      </button>
      <button class="menu-toggle" aria-label="Open menu">☰</button>
    </div>
  </div>
</header>

<main id="top">

  <!-- HERO -->
  <section class="wrap hero">
    <div>
      <p class="eyebrow">Artisan Cake Studio</p>
      <h1>Cakes made<br><span class="italic-accent">for the moment</span><br>you're celebrating.</h1>
      <p class="lede">Jura and Cakes bakes small-batch, made-to-order cakes — from weekday indulgences to wedding centerpieces — using real butter, real fruit, and no shortcuts.</p>
      <div class="hero-ctas">
        <a href="#collections" class="btn btn-solid">Shop Collections</a>
        <a href="#custom" class="btn btn-line">Start a Custom Order</a>
      </div>
    </div>
    <div class="cake-illustration" aria-hidden="true">
      <svg viewBox="0 0 320 400" width="100%" height="100%" style="max-width:320px">
        <ellipse cx="160" cy="365" rx="120" ry="16" fill="#2E2018" opacity="0.08"/>
        <rect x="55" y="255" width="210" height="90" rx="4" fill="#8B3A4A"/>
        <rect x="55" y="255" width="210" height="14" fill="#C79A4B"/>
        <rect x="85" y="165" width="150" height="90" rx="4" fill="#C79A4B"/>
        <rect x="85" y="165" width="150" height="12" fill="#F7EDE1"/>
        <rect x="115" y="90" width="90" height="75" rx="4" fill="#74806A"/>
        <rect x="115" y="90" width="90" height="10" fill="#F7EDE1"/>
        <rect x="157" y="55" width="6" height="38" fill="#E9D9BE"/>
        <g class="candle-flame">
          <path d="M160 30 C165 40 168 46 160 55 C152 46 155 40 160 30 Z" fill="#C79A4B"/>
          <path d="M160 36 C163 42 164 46 160 51 C156 46 157 42 160 36 Z" fill="#F7EDE1"/>
        </g>
        <circle cx="130" cy="200" r="4" fill="#F7EDE1"/>
        <circle cx="160" cy="210" r="4" fill="#F7EDE1"/>
        <circle cx="190" cy="200" r="4" fill="#F7EDE1"/>
        <circle cx="100" cy="290" r="4" fill="#F7EDE1"/>
        <circle cx="220" cy="290" r="4" fill="#F7EDE1"/>
      </svg>
    </div>
  </section>

  <div class="marquee">
    <div class="marquee-inner">
      <span>◆</span>Same-week custom orders<span>◆</span>Nationwide shipping on classics<span>◆</span>Made fresh, never frozen<span>◆</span>Wedding tastings by appointment
      <span>◆</span>Same-week custom orders<span>◆</span>Nationwide shipping on classics<span>◆</span>Made fresh, never frozen<span>◆</span>Wedding tastings by appointment
    </div>
  </div>

  <!-- COLLECTIONS -->
  <section class="wrap section" id="collections">
    <div class="section-head">
      <div>
        <p class="eyebrow">Signature Offerings</p>
        <h2>Explore Collections</h2>
      </div>
    </div>
    <div class="collections">
      <div class="collection-card c1" data-name="Classic Layer Cakes" data-price="58"
           style="background-image:url('wedding-cake.jpg'); background-size:cover; background-position:center;">
       <img src="WhatsApp Image 2026-09-14 at 4.10.29 PM.jpg"height="300">
         <h3>Classic</h3> <p>Timeless flavors, done properly</p>
      </div>
      <div class="collection-card c2" data-name="Wedding Cakes" data-price="480"
           style="background-image:url('wedding-cake.jpg'); background-size:cover; background-position:center;">
        <img src="wedding-cake.jpg " width="1200"height="300">
        <h3>Wedding</h3><p>Tiered cakes for the big day</p>
      </div>
      <div class="collection-card c3" data-name="Celebration Cakes" data-price="72"
           style="background-image:url('images/celebration.jpg'); background-size:cover; background-position:center;">
       <img src="WhatsApp Image 2026-09-14 at 4.10.30 PM (3).jpg"height="300">
           <h3>Celebration</h3><p>Birthdays, showers, milestones</p>
      </div>
      <div class="collection-card c4" data-name="Custom Sculpted Cakes" data-price="145"
           style="background-image:url('images/custom.jpg'); background-size:cover; background-position:center;">
       <img src="WhatsApp Image 2026-09-14 at 4.10.31 PM (1).jpg"height="300">
           <h3>Custom</h3><p>Your idea, built from scratch</p>
      </div>
      <div class="collection-card c5" data-name="Seasonal Cakes" data-price="64"
           style="background-image:url('images/seasonal.jpg'); background-size:cover; background-position:center;">
       <img src="WhatsApp Image 2026-09-14 at 4.10.32 PM (1).jpg"height="300">
           <h3>Seasonal</h3><p>Fruit and flavor, by the month</p>
      </div>
      <div class="collection-card c6" data-name="Gift Boxes" data-price="38"
           style="background-image:url('images/gift-box.jpg'); background-size:cover; background-position:center;">
        <img src="WhatsApp Image 2026-09-14 at 4.10.32 PM (2).jpg"height="300">
           <h3>Gift Boxes</h3><p>Mini cakes, sent anywhere</p>
      </div>
    </div>
  </section>

  <!-- CUSTOM ORDER PROMO -->
  <section class="wrap" id="custom">
    <div class="promo">
      <div class="promo-copy">
        <p class="eyebrow" style="color:var(--gold)">Custom Order</p>
        <h2>Tell us the<br>occasion. We'll<br>design the cake.</h2>
        <p>Share your date, guest count, and flavor preferences — our cake designers reply with a proposal and quote within 48 hours.</p>
        <div class="steps-mini">
          <div><strong>01</strong>Submit details</div>
          <div><strong>02</strong>Review design &amp; quote</div>
          <div><strong>03</strong>Taste &amp; confirm</div>
          <div><strong>04</strong>We deliver</div>
        </div>
        <div style="margin-top:34px;">
          <a href="#contact" class="btn btn-solid" style="background:var(--gold);border-color:var(--gold);color:var(--espresso);">Start Your Order</a>
        </div>
      </div>
      <div class="promo-visual">
        <span class="tier-mark" style="transform:scale(3);" aria-hidden="true"><span class="t1"></span><span class="t2"></span><span class="t3"></span></span>
      </div>
    </div>
  </section>

  <!-- GIFTS / CORPORATE -->
  <section class="section wrap" id="gifts">
    <div class="section-head">
      <div>
        <p class="eyebrow">Beyond the Cake</p>
        <h2>Gifting &amp; corporate</h2>
      </div>
    </div>
    <div class="two-col">
      <div class="feature-card">
        <p class="eyebrow">Gifts</p>
        <h3>Send a Jura box</h3>
        <p>Mini cakes and pastries packed for shipping, with a note card included. Ready in 24 hours, delivered nationwide.</p>
        <a href="#" class="more">Browse gift boxes →</a>
      </div>
      <div class="feature-card">
        <p class="eyebrow">Corporate Partners</p>
        <h3>Client &amp; team gifting</h3>
        <p>Volume pricing, branded packaging, and a single point of contact for recurring office and client orders.</p>
        <a href="#" class="more">See corporate program →</a>
      </div>
    </div>
  </section>

  <!-- ABOUT -->
  <section class="section wrap" id="about">
    <div class="about">
      <div class="about-visual" aria-hidden="true"></div>
      <div>
        <p class="eyebrow">About Jura and Cakes</p>
        <h2 style="font-size:2.4rem;margin-top:10px;">Baked in small batches, on purpose.</h2>
        <p>Jura and Cakes started as a single kitchen making wedding cakes on weekends. Today every order still passes through the same hands, using the same ratio of real butter to sugar we started with — nothing scaled down to survive mass production.</p>
        <div class="stat-row">
          <div><strong>9</strong><span>Years Baking</span></div>
          <div><strong>3,200+</strong><span>Cakes Delivered</span></div>
          <div><strong>4.9</strong><span>Average Rating</span></div>
        </div>
      </div>
    </div>
  </section>

  <!-- NEWSLETTER -->
  <section class="wrap" style="padding-bottom:90px;">
    <div class="newsletter">
      <h3>Get flavor drops &amp; seasonal menus in your inbox.</h3>
      <form onsubmit="event.preventDefault(); this.reset(); alert('Thanks — you\'re on the list.');">
        <input type="email" placeholder="you@email.com" required>
        <button type="submit" class="btn btn-solid" style="border-radius:2px;">Sign Up</button>
      </form>
    </div>
  </section>

  <!-- CONTACT -->
  <section class="section wrap" id="contact">
    <div class="section-head">
      <div>
        <p class="eyebrow">Get in Touch</p>
        <h2>Let's talk cake.</h2>
      </div>
    </div>
    <div class="two-col">
      <div class="feature-card">
        <h3>Visit or write</h3>
        <p>Studio hours: Tue–Sat, 9am–5pm.<br>hello@juraandcakes.com<br>+254 700 000 000</p>
      </div>
      <div class="feature-card">
        <h3>Quick enquiry</h3>
        <form onsubmit="event.preventDefault(); this.reset(); alert('Thanks — we\'ll be in touch within 48 hours.');" style="display:flex;flex-direction:column;gap:12px;margin-top:6px;">
          <input required placeholder="Your name" style="padding:12px 14px;border:1px solid rgba(46,32,24,.25);border-radius:2px;font-family:'Work Sans',sans-serif;">
          <input required type="email" placeholder="Email" style="padding:12px 14px;border:1px solid rgba(46,32,24,.25);border-radius:2px;font-family:'Work Sans',sans-serif;">
          <textarea placeholder="What are you celebrating?" rows="3" style="padding:12px 14px;border:1px solid rgba(46,32,24,.25);border-radius:2px;font-family:'Work Sans',sans-serif;resize:vertical;"></textarea>
          <button class="btn btn-solid" type="submit">Send Enquiry</button>
        </form>
      </div>
    </div>
  </section>

</main>

<footer>
  <div class="wrap footer-grid">
    <div>
      <a href="#top" class="logo" style="color:#fff;">
        <span class="tier-mark"><span class="t1"></span><span class="t2"></span><span class="t3"></span></span>
        Jura and Cakes
      </a>
      <p style="color:#a5917f;font-size:.88rem;margin-top:16px;max-width:260px;">Small-batch cakes for weddings, celebrations, and everyday indulgence.</p>
    </div>
    <div>
      <h4>Shop</h4>
      <ul>
        <li><a href="#collections">Classic</a></li>
        <li><a href="#collections">Wedding</a></li>
        <li><a href="#collections">Celebration</a></li>
        <li><a href="#collections">Custom</a></li>
      </ul>
    </div>
    <div>
      <h4>Company</h4>
      <ul>
        <li><a href="#about">About</a></li>
        <li><a href="#gifts">Corporate</a></li>
        <li><a href="#custom">Custom Order</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </div>
    <div>
      <h4>Follow</h4>
      <ul>
        <li><a href="#">Instagram</a></li>
        <li><a href="#">Pinterest</a></li>
        <li><a href="#">TikTok</a></li>
      </ul>
    </div>
  </div>
  <div class="wrap footer-bottom">
    <span>© 2026 Jura and Cakes. All rights reserved.</span>
    <span>Nairobi, Kenya</span>
  </div>
</footer>

<!-- CART DRAWER -->
<div class="overlay" id="overlay"></div>
<div class="drawer" id="cartDrawer" role="dialog" aria-label="Shopping cart">
  <div class="drawer-head">
    <h3>Your Cart</h3>
    <button class="drawer-close" id="cartCloseBtn" aria-label="Close cart">✕</button>
  </div>
  <div class="drawer-body" id="cartBody">
    <div class="drawer-empty">Your cart is empty.<br>Browse a collection and add a cake.</div>
  </div>
  <div class="drawer-foot">
    <a href="#contact" class="btn btn-solid" id="checkoutBtn">Checkout</a>
  </div>
</div>
     
<script>
  const cart = [];
  const cartOpenBtn = document.getElementById('cartOpenBtn');
  const cartCloseBtn = document.getElementById('cartCloseBtn');
  const drawer = document.getElementById('cartDrawer');
  const overlay = document.getElementById('overlay');
  const cartBody = document.getElementById('cartBody');
  const cartCount = document.getElementById('cartCount');

  function openDrawer(){ drawer.classList.add('open'); overlay.classList.add('open'); }
  function closeDrawer(){ drawer.classList.remove('open'); overlay.classList.remove('open'); }
  cartOpenBtn.addEventListener('click', openDrawer);
  cartCloseBtn.addEventListener('click', closeDrawer);
  overlay.addEventListener('click', closeDrawer);

  function renderCart(){
    cartCount.textContent = cart.length;
    if(cart.length === 0){
      cartBody.innerHTML = '<div class="drawer-empty">Your cart is empty.<br>Browse a collection and add a cake.</div>';
      return;
    }
    cartBody.innerHTML = cart.map((item, i) => `
      <div class="cart-item">
        <div>
          <div class="name">${item.name}</div>
          <div class="price">$${item.price}</div>
        </div>
        <button onclick="removeItem(${i})">Remove</button>
      </div>
    `).join('');
  }
  function removeItem(i){ cart.splice(i,1); renderCart(); }

  document.querySelectorAll('.collection-card').forEach(card => {
    card.addEventListener('click', () => {
      cart.push({ name: card.dataset.name, price: card.dataset.price });
      renderCart();
      openDrawer();
    });
  });

  renderCart();
</script>
<a href="https://wa.me/254700000000" class="whatsapp-float" target="_blank" aria-label="Chat on WhatsApp">
  <svg viewBox="0 0 24 24" width="34" height="34" fill="#fff" xmlns="http://www.w3.org/2000/svg">
    <path d="M12.04 2C6.58 2 2.13 6.45 2.13 11.91c0 1.75.46 3.45 1.32 4.95L2.05 22l5.25-1.38c1.45.79 3.08 1.21 4.74 1.21h.01c5.46 0 9.91-4.45 9.91-9.91C21.96 6.45 17.5 2 12.04 2zm5.77 14.13c-.24.68-1.4 1.3-1.93 1.38-.49.08-1.11.11-1.79-.11-.41-.13-.95-.31-1.63-.6-2.87-1.24-4.74-4.14-4.88-4.33-.14-.19-1.17-1.55-1.17-2.96 0-1.41.74-2.1 1-2.39.26-.29.57-.36.76-.36h.55c.18 0 .41-.01.63.48.23.51.77 1.85.84 1.99.07.14.12.3.02.49-.09.19-.14.31-.28.48-.14.17-.29.37-.42.5-.14.14-.28.29-.12.57.16.28.71 1.17 1.53 1.9 1.05.94 1.93 1.23 2.21 1.37.28.14.44.12.6-.07.16-.19.68-.8.87-1.07.18-.28.36-.23.6-.14.24.09 1.54.73 1.81.86.26.14.44.2.5.31.07.11.07.66-.17 1.3z"/>
  </svg>
</a>
</body>
</html>
