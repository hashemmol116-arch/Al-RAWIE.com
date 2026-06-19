# Al-RAWIE.com
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>الراوي — قصص تفاعلية من الصحراء</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Lalezar&family=Tajawal:wght@300;400;500;700;900&family=Reem+Kufi:wght@400;700&display=swap" rel="stylesheet">
<style>
  :root{
    --night:#161B2E; --night-deep:#0E1120;
    --sand:#CE9A4F; --sand-light:#E9C685;
    --terracotta:#A8442E; --parchment:#EFE3C4; --teal:#235048;
  }
  *{margin:0;padding:0;box-sizing:border-box;}
  body{background:var(--night-deep); color:var(--parchment); font-family:'Tajawal',sans-serif; overflow-x:hidden;}
  h1,h2,h3{font-family:'Lalezar',cursive; font-weight:400;}
  .eyebrow{font-family:'Reem Kufi'; font-size:0.78rem; letter-spacing:3px; color:var(--sand); text-transform:uppercase;}
  a{color:inherit; text-decoration:none;}
  .wrap{max-width:1100px; margin:0 auto; padding:0 28px;}

  header{position:fixed; top:0; right:0; left:0; z-index:50; padding:18px 0; background:linear-gradient(rgba(14,17,32,.92),rgba(14,17,32,0)); backdrop-filter:blur(6px);}
  nav.wrap{display:flex; align-items:center; justify-content:space-between;}
  .logo{display:flex; align-items:center; gap:10px; font-family:'Lalezar'; font-size:1.5rem; color:var(--sand-light);}
  .logo svg{width:30px;height:30px;}
  .navlinks{display:none; gap:30px; font-size:0.95rem;}
  @media(min-width:760px){.navlinks{display:flex;}}
  .navlinks a:hover{color:var(--sand);}
  .nav-cta{border:1px solid var(--sand); padding:9px 20px; border-radius:999px; font-size:0.88rem;}
  .nav-cta:hover{background:var(--sand); color:var(--night-deep);}

  .hero{min-height:92vh; display:flex; flex-direction:column; justify-content:center; position:relative; text-align:center;
    background:radial-gradient(ellipse at 50% 0%, #283157 0%, var(--night) 45%, var(--night-deep) 100%); overflow:hidden;}
  .stars{position:absolute; inset:0;}
  .star{position:absolute; width:2px; height:2px; background:var(--parchment); border-radius:50%; animation:tw 4s ease-in-out infinite;}
  @keyframes tw{0%,100%{opacity:.15}50%{opacity:.9}}
  .hero-content{position:relative; z-index:2; padding:0 24px;}
  .hero-content h1{font-size:clamp(3rem,11vw,6.5rem); color:var(--sand-light); text-shadow:0 0 40px rgba(206,154,79,.3);}
  .hero-sub{max-width:540px; margin:20px auto 0; color:#D9CCA8; font-weight:300; line-height:1.9; font-size:1.05rem;}
  .hero-actions{display:flex; gap:16px; justify-content:center; margin-top:34px; flex-wrap:wrap;}
  .btn{padding:14px 30px; border-radius:14px; font-weight:700; font-size:.98rem; transition:transform .2s;}
  .btn-primary{background:var(--sand); color:var(--night-deep);}
  .btn-primary:hover{transform:translateY(-3px);}
  .btn-ghost{border:1px solid rgba(239,227,196,.35);}
  .btn-ghost:hover{border-color:var(--sand); transform:translateY(-3px);}

  section{padding:110px 0;}
  .section-head{max-width:600px; margin-bottom:54px;}
  .section-head h2{font-size:clamp(2rem,5vw,2.8rem); color:var(--sand-light); margin-top:12px;}
  .section-head p{margin-top:16px; color:#C9BC9C; font-weight:300; line-height:1.85;}

  .about{background:var(--night);}
  .about-grid{display:grid; gap:40px;}
  @media(min-width:860px){.about-grid{grid-template-columns:1fr 1fr; align-items:center;}}
  .about-art{aspect-ratio:1/1; border-radius:22px; border:1px solid rgba(206,154,79,.2);
    background:radial-gradient(circle at 70% 20%, rgba(206,154,79,.25), transparent 55%), linear-gradient(160deg,#1d2440,#0e1120 70%);
    display:flex; align-items:center; justify-content:center;}
  .about-art svg{width:60%;}
  .about-text p{color:#D9CCA8; font-weight:300; line-height:2; margin-bottom:14px; font-size:1.02rem;}
  .about-text strong{color:var(--sand-light);}

  .games{background:var(--night-deep);}
  .game-card{display:grid; gap:0; border:1px solid rgba(206,154,79,.2); border-radius:22px; overflow:hidden; background:linear-gradient(165deg, rgba(40,46,80,.4), rgba(14,17,32,.85));}
  @media(min-width:760px){.game-card{grid-template-columns:1fr 1fr;}}
  .game-cover{position:relative; min-height:260px; background:linear-gradient(160deg,#2a2e1c,#0e1120 70%); display:flex; align-items:center; justify-content:center;}
  .game-cover .sun{position:absolute; top:18%; left:50%; transform:translateX(-50%); width:70px; height:70px; border-radius:50%; background:var(--sand-light); box-shadow:0 0 50px 10px rgba(233,198,133,.5);}
  .game-cover .hill1{position:absolute; bottom:0; left:0; right:0; height:42%; background:var(--terracotta); border-radius:50% 50% 0 0/100% 100% 0 0; opacity:.85;}
  .game-cover .hill2{position:absolute; bottom:0; left:0; right:0; height:26%; background:var(--sand); border-radius:50% 50% 0 0/100% 100% 0 0;}
  .game-info{padding:38px 36px; display:flex; flex-direction:column; justify-content:center;}
  .game-tag{display:inline-block; font-family:'Reem Kufi'; font-size:.68rem; letter-spacing:2px; color:var(--night-deep); background:var(--sand); padding:4px 12px; border-radius:999px; margin-bottom:14px; width:fit-content;}
  .game-info h3{font-family:'Lalezar'; font-size:1.8rem; color:var(--sand-light); margin-bottom:12px;}
  .game-info p{color:#C9BC9C; font-weight:300; line-height:1.85; margin-bottom:22px; font-size:.96rem;}
  .game-info .btn{align-self:flex-start;}

  .features{background:var(--night);}
  .feat-grid{display:grid; grid-template-columns:1fr; gap:1px; background:rgba(206,154,79,.18); border:1px solid rgba(206,154,79,.18); border-radius:18px; overflow:hidden;}
  @media(min-width:640px){.feat-grid{grid-template-columns:1fr 1fr;}}
  @media(min-width:980px){.feat-grid{grid-template-columns:1fr 1fr 1fr;}}
  .feat-cell{background:var(--night); padding:32px 26px;}
  .feat-cell svg{width:36px; height:36px; color:var(--sand); margin-bottom:16px;}
  .feat-cell h4{font-weight:700; color:var(--parchment); margin-bottom:8px; font-size:1.05rem;}
  .feat-cell p{font-size:.9rem; color:#A99C7C; font-weight:300; line-height:1.8;}

  .cta{background:linear-gradient(180deg, var(--night) 0%, #20140f 100%); text-align:center; padding:130px 0;}
  .cta h2{font-size:clamp(2.2rem,6vw,3.6rem); color:var(--sand-light); margin-bottom:16px;}
  .cta p{max-width:460px; margin:0 auto 32px; color:#D9CCA8; font-weight:300; line-height:1.9;}

  footer{background:var(--night-deep); padding:46px 0; border-top:1px solid rgba(206,154,79,.14);}
  .foot-row{display:flex; flex-direction:column; gap:16px; align-items:center; text-align:center;}
  @media(min-width:700px){.foot-row{flex-direction:row; justify-content:space-between; text-align:right;}}
  .foot-logo{font-family:'Lalezar'; font-size:1.2rem; color:var(--sand-light);}
  .foot-links{display:flex; gap:24px; font-size:.88rem; color:#A99C7C;}
  .foot-links a:hover{color:var(--sand);}
  .foot-note{font-size:.78rem; color:#675B3F;}
</style>
</head>
<body>

<header>
  <nav class="wrap">
    <div class="logo">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M4 18c3-6 6-9 8-9s5 3 8 9" stroke-linecap="round"/><circle cx="12" cy="6" r="2.4"/></svg>
      الراوي
    </div>
    <div class="navlinks">
      <a href="#about">من نحن</a>
      <a href="#games">الألعاب</a>
      <a href="#features">المزايا</a>
    </div>
    <a href="#games" class="nav-cta">شاهد اللعبة</a>
  </nav>
</header>

<section class="hero">
  <div class="stars" id="stars"></div>
  <div class="hero-content">
    <span class="eyebrow">منصّة قصص تفاعلية عربية</span>
    <h1 style="margin-top:14px;">الراوي</h1>
    <p class="hero-sub">منصة تحكي قصص الصحراء والقوافل بصوت عربي أصيل، من خلال ألعاب وتجارب تفاعلية مبنية على رحلات حقيقية من تراثنا.</p>
    <div class="hero-actions">
      <a href="#games" class="btn btn-primary">شاهد لعبة طريق الحرير</a>
      <a href="#about" class="btn btn-ghost">تعرّف على الراوي</a>
    </div>
  </div>
</section>

<section class="about" id="about">
  <div class="wrap about-grid">
    <div class="about-art">
      <svg viewBox="0 0 200 200" fill="none">
        <circle cx="100" cy="100" r="90" stroke="#CE9A4F" stroke-width="1.5" opacity="0.5"/>
        <path d="M60 130 Q100 60 140 130" stroke="#E9C685" stroke-width="2" fill="none"/>
        <circle cx="100" cy="60" r="6" fill="#A8442E"/>
        <circle cx="60" cy="130" r="5" fill="#CE9A4F"/>
        <circle cx="140" cy="130" r="5" fill="#CE9A4F"/>
      </svg>
    </div>
    <div class="about-text">
      <span class="eyebrow">من نحن</span>
      <h2 style="margin:14px 0 20px; font-size:2.2rem; color:var(--sand-light);">صوت يحكي حكايات الطريق</h2>
      <p><strong>الراوي</strong> منصة عربية لنشر الألعاب والقصص التفاعلية، تستلهم محتواها من نصوص الرحالة القدامى كابن بطوطة وابن فضلان وناصر خسرو.</p>
      <p>كل لعبة على المنصة مبنية بأسلوب بصري هادئ منخفض التفاصيل، وقرارات متفرعة تجعل كل رحلة مختلفة عن سابقتها.</p>
      <p>نبدأ بأول إصدار: <strong>طريق الحرير</strong> — رحلة قافلة من سمرقند إلى طنجة.</p>
    </div>
  </div>
</section>

<section class="games" id="games">
  <div class="wrap">
    <div class="section-head">
      <span class="eyebrow">الإصدار الأول</span>
      <h2>طريق الحرير</h2>
      <p>قُد قافلتك عبر أربع محطات صحراوية، وكل قرار يقودك إلى واحدة من أربع نهايات مختلفة.</p>
    </div>
    <div class="game-card">
      <div class="game-cover">
        <div class="hill1"></div><div class="hill2"></div><div class="sun"></div>
      </div>
      <div class="game-info">
        <span class="game-tag">قصة تفاعلية</span>
        <h3>طريق الحرير</h3>
        <p>قافلة تعبر الصحراء من سمرقند إلى طنجة، مستوحاة من رحلات ابن بطوطة وابن فضلان وناصر خسرو. راقب الماء والذهب وصحة القافلة، وقراراتك تحدد مصيرك.</p>
        <a href="#" class="btn btn-primary">العب الآن</a>
      </div>
    </div>
  </div>
</section>

<section class="features" id="features">
  <div class="wrap">
    <div class="section-head">
      <span class="eyebrow">لماذا الراوي</span>
      <h2>منصة بهوية عربية كاملة</h2>
    </div>
    <div class="feat-grid">
      <div class="feat-cell">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M4 19h16M4 19V8l8-5 8 5v11" stroke-linecap="round" stroke-linejoin="round"/></svg>
        <h4>محتوى أصيل</h4>
        <p>قصص وحوارات مكتوبة بالعربية، مبنية على نصوص رحلات تاريخية موثّقة.</p>
      </div>
      <div class="feat-cell">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 3v18M3 12h18" stroke-linecap="round"/><circle cx="12" cy="12" r="9"/></svg>
        <h4>قرارات متفرعة</h4>
        <p>كل اختيار يقود لمسار مختلف، مع نهايات متعددة قابلة لإعادة اللعب.</p>
      </div>
      <div class="feat-cell">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="4" y="4" width="16" height="16" rx="3"/><path d="M9 9h6v6H9z"/></svg>
        <h4>أسلوب بصري هادئ</h4>
        <p>تصميم منخفض التفاصيل بألوان ترابية وذهبية، يبرز أجواء الصحراء.</p>
      </div>
      <div class="feat-cell">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M5 12h14M12 5v14" stroke-linecap="round"/></svg>
        <h4>إصدارات جديدة</h4>
        <p>قصص ومحطات جديدة تُضاف دورياً عبر نفس محرك القافلة.</p>
      </div>
      <div class="feat-cell">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M3 9l9-6 9 6v11a1 1 0 01-1 1h-4a1 1 0 01-1-1v-5H9v5a1 1 0 01-1 1H4a1 1 0 01-1-1z" stroke-linejoin="round"/></svg>
        <h4>تعمل دون اتصال</h4>
        <p>حمّل القصة والعبها أثناء التنقل دون حاجة لاتصال دائم.</p>
      </div>
      <div class="feat-cell">
        <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M4 4h16v12H7l-3 3z" stroke-linejoin="round"/></svg>
        <h4>تعليق صوتي عربي</h4>
        <p>أصوات شخصيات كاملة لتعزيز الانغماس في الحكاية.</p>
      </div>
    </div>
  </div>
</section>

<section class="cta">
  <div class="wrap">
    <span class="eyebrow">ابدأ الآن</span>
    <h2 style="margin-top:14px;">انضم لقافلة الراوي</h2>
    <p>تابع الراوي لأول إشعار عند نشر إصدارات جديدة من قصص الصحراء.</p>
    <a href="#games" class="btn btn-primary">العب طريق الحرير الآن</a>
  </div>
</section>

<footer>
  <div class="wrap foot-row">
    <div class="foot-logo">الراوي</div>
    <div class="foot-links">
      <a href="#about">من نحن</a>
      <a href="#games">الألعاب</a>
      <a href="#features">المزايا</a>
    </div>
    <div class="foot-note">صُنع بشغف لمحبي القصص العربية</div>
  </div>
</footer>

<script>
  const starsEl = document.getElementById('stars');
  for(let i=0;i<80;i++){
    const s = document.createElement('div');
    s.className = 'star';
    s.style.top = Math.random()*70 + '%';
    s.style.right = Math.random()*100 + '%';
    s.style.animationDelay = (Math.random()*4) + 's';
    s.style.width = s.style.height = (Math.random()*1.6+1) + 'px';
    starsEl.appendChild(s);
  }
</script>

</body>
</html>
