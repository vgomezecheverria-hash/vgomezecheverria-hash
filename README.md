<img width="1535" height="200" alt="image" src="https://github.com/user-attachments/assets/6e36b556-2e15-462a-a039-c42254c571f5" />
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Valerie Gómez — Senior AI Architect · Cooweb</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=Lora:ital,wght@0,400;1,400;1,500&family=DM+Mono:wght@300;400&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0}
html{scroll-behavior:smooth}
 
:root{
  --bg:#080808;
  --surface:#0f0f0f;
  --card:#151515;
  --border:rgba(255,255,255,0.07);
  --border2:rgba(255,255,255,0.12);
  --white:#f4f2ee;
  --muted:rgba(244,242,238,0.42);
  --muted2:rgba(244,242,238,0.22);
  --accent:#e8a87c;   /* warm amber */
  --accent2:#7ec8b4;  /* teal */
  --accent3:#c47eb0;  /* mauve */
  --glow:rgba(232,168,124,0.18);
  --sans:'Syne',sans-serif;
  --serif:'Lora',Georgia,serif;
  --mono:'DM Mono',monospace;
}
 
body{
  background:var(--bg);
  color:var(--white);
  font-family:var(--sans);
  overflow-x:hidden;
  cursor:none;
}
 
/* ─ cursor ─ */
#cur{
  position:fixed;width:10px;height:10px;
  background:var(--accent);border-radius:50%;
  pointer-events:none;z-index:9999;
  transform:translate(-50%,-50%);
  transition:transform .15s,background .3s,width .3s,height .3s;
  mix-blend-mode:screen;
}
#cur-ring{
  position:fixed;width:38px;height:38px;
  border:1px solid rgba(232,168,124,0.35);border-radius:50%;
  pointer-events:none;z-index:9998;
  transform:translate(-50%,-50%);
  transition:transform .18s ease-out;
}
body:hover #cur{opacity:1}
 
/* ─ scroll progress ─ */
#prog{
  position:fixed;top:0;left:0;height:2px;width:0%;
  background:linear-gradient(90deg,var(--accent),var(--accent2),var(--accent3));
  z-index:1000;transition:width .08s linear;
}
 
/* ─ nav ─ */
nav{
  position:fixed;top:0;left:0;right:0;z-index:500;
  display:flex;justify-content:space-between;align-items:center;
  padding:24px 60px;
  background:linear-gradient(to bottom,rgba(8,8,8,0.95),transparent);
}
.nav-logo{
  font-family:var(--sans);font-size:13px;font-weight:700;
  letter-spacing:0.15em;text-transform:uppercase;color:var(--white);
}
.nav-logo span{color:var(--accent);}
.nav-links{
  display:flex;gap:36px;
  font-family:var(--mono);font-size:10px;letter-spacing:0.12em;
  color:var(--muted);text-transform:uppercase;
}
.nav-links a{
  color:var(--muted);text-decoration:none;
  transition:color .3s;cursor:pointer;
}
.nav-links a:hover{color:var(--accent);}
 
/* ─ side dots ─ */
#side-dots{
  position:fixed;right:28px;top:50%;transform:translateY(-50%);
  z-index:400;display:flex;flex-direction:column;gap:12px;
}
.sdot{
  width:6px;height:6px;border-radius:50%;
  background:rgba(255,255,255,0.18);border:1px solid rgba(255,255,255,0.2);
  cursor:pointer;transition:all .3s;
}
.sdot.on{background:var(--accent);border-color:var(--accent);transform:scale(1.5);}
 
/* ═══════════════════════════════
   S0: HERO  – tech image + canvas
════════════════════════════════ */
#hero{
  position:relative;height:100vh;overflow:hidden;
  display:flex;align-items:center;justify-content:center;
}
#hero-canvas{
  position:absolute;inset:0;z-index:1;
}
.hero-img-wrap{
  position:absolute;inset:0;z-index:0;
}
.hero-img-wrap img{
  width:100%;height:100%;object-fit:cover;
  filter:brightness(0.22) saturate(0.6);
}
.hero-img-wrap::after{
  content:'';position:absolute;inset:0;
  background:linear-gradient(to bottom,
    rgba(8,8,8,0.3) 0%,
    rgba(8,8,8,0.05) 40%,
    rgba(8,8,8,0.7) 80%,
    rgba(8,8,8,1) 100%);
}
 
.hero-content{
  position:relative;z-index:3;
  text-align:center;max-width:900px;
  padding:0 40px;
}
.hero-eyebrow{
  font-family:var(--mono);font-size:10px;letter-spacing:0.3em;
  text-transform:uppercase;color:var(--accent);
  margin-bottom:28px;opacity:0;
  animation:fadeUp .9s .3s forwards;
}
.hero-name{
  font-family:var(--sans);font-size:clamp(56px,8vw,110px);
  font-weight:800;line-height:0.92;letter-spacing:-2px;
  color:var(--white);
  opacity:0;animation:fadeUp .9s .5s forwards;
}
.hero-name em{
  font-family:var(--serif);font-style:italic;font-weight:400;
  color:var(--accent);
}
.hero-role{
  font-family:var(--mono);font-size:11px;letter-spacing:0.25em;
  text-transform:uppercase;color:var(--muted);
  margin-top:20px;
  opacity:0;animation:fadeUp .9s .7s forwards;
}
.hero-desc{
  font-family:var(--serif);font-style:italic;font-size:17px;
  color:var(--muted);line-height:1.65;max-width:520px;
  margin:28px auto 0;
  opacity:0;animation:fadeUp .9s .9s forwards;
}
.hero-cta{
  display:flex;gap:16px;justify-content:center;margin-top:44px;
  opacity:0;animation:fadeUp .9s 1.1s forwards;
}
.btn{
  font-family:var(--mono);font-size:10px;letter-spacing:0.15em;
  text-transform:uppercase;padding:13px 30px;border-radius:2px;
  text-decoration:none;transition:all .3s;cursor:pointer;
}
.btn-primary{
  background:var(--accent);color:#0a0a0a;border:1px solid var(--accent);
}
.btn-primary:hover{background:transparent;color:var(--accent);}
.btn-ghost{
  background:transparent;color:var(--white);
  border:1px solid var(--border2);
}
.btn-ghost:hover{border-color:var(--accent);color:var(--accent);}
 
.hero-scroll{
  position:absolute;bottom:36px;left:50%;transform:translateX(-50%);
  display:flex;flex-direction:column;align-items:center;gap:8px;
  z-index:4;
  font-family:var(--mono);font-size:8px;letter-spacing:0.2em;
  text-transform:uppercase;color:var(--muted2);
  animation:fadeUp .9s 1.4s both;
}
.scroll-line{
  width:1px;height:44px;
  background:linear-gradient(to bottom,var(--accent),transparent);
  animation:scrollPulse 2s ease-in-out infinite;
}
@keyframes scrollPulse{
  0%,100%{opacity:0.4;transform:scaleY(1);}
  50%{opacity:1;transform:scaleY(1.15);}
}
 
/* ─ stats strip below hero ─ */
.stats-strip{
  display:grid;grid-template-columns:repeat(4,1fr);
  border-top:1px solid var(--border);
  border-bottom:1px solid var(--border);
  background:var(--surface);
}
.stat-cell{
  padding:32px 40px;
  border-right:1px solid var(--border);
  transition:background .4s;
}
.stat-cell:last-child{border-right:none;}
.stat-cell:hover{background:rgba(232,168,124,0.04);}
.stat-num{
  font-family:var(--sans);font-size:42px;font-weight:800;
  color:var(--accent);letter-spacing:-1px;line-height:1;
}
.stat-label{
  font-family:var(--mono);font-size:9px;letter-spacing:0.15em;
  text-transform:uppercase;color:var(--muted);margin-top:8px;
}
 
/* ═══ generic section ═══ */
.section{
  padding:120px 0;position:relative;overflow:hidden;
}
.container{max-width:1100px;margin:0 auto;padding:0 60px;}
 
.s-eyebrow{
  font-family:var(--mono);font-size:9px;letter-spacing:0.3em;
  text-transform:uppercase;color:var(--accent);
  margin-bottom:20px;
  display:flex;align-items:center;gap:14px;
}
.s-eyebrow::before{
  content:'';width:28px;height:1px;background:var(--accent);
}
h2.s-title{
  font-family:var(--sans);font-size:clamp(38px,5vw,64px);
  font-weight:800;line-height:1.0;letter-spacing:-1.5px;
  color:var(--white);
}
h2.s-title em{
  font-family:var(--serif);font-style:italic;font-weight:400;
  color:var(--accent);
}
 
/* ─ reveal ─ */
.rv{
  opacity:0;transform:translateY(36px);
  transition:opacity .85s cubic-bezier(.16,1,.3,1),transform .85s cubic-bezier(.16,1,.3,1);
}
.rv.on{opacity:1;transform:none;}
.rv.d1{transition-delay:.12s}
.rv.d2{transition-delay:.24s}
.rv.d3{transition-delay:.36s}
.rv.d4{transition-delay:.48s}
 
/* ═══ S1: QUIEN ═══ */
#quien{background:var(--bg);}
.quien-grid{
  display:grid;grid-template-columns:1fr 1fr;
  gap:80px;align-items:center;margin-top:64px;
}
.quien-quote{
  font-family:var(--serif);font-style:italic;
  font-size:clamp(20px,2.2vw,28px);line-height:1.55;
  color:var(--white);
}
.quien-quote span{color:var(--accent);}
.quien-pills{
  display:flex;flex-wrap:wrap;gap:10px;margin-top:32px;
}
.quien-pill{
  font-family:var(--mono);font-size:9px;letter-spacing:0.12em;
  text-transform:uppercase;padding:8px 18px;
  border:1px solid var(--border2);color:var(--muted);
  border-radius:2px;transition:all .3s;
}
.quien-pill:hover{border-color:var(--accent);color:var(--accent);}
 
.quien-cards-v{display:flex;flex-direction:column;gap:16px;}
.quien-card{
  background:var(--card);border:1px solid var(--border);
  padding:24px 28px;border-radius:4px;
  display:flex;align-items:flex-start;gap:20px;
  transition:border-color .4s,transform .4s;
}
.quien-card:hover{
  border-color:rgba(232,168,124,0.3);
  transform:translateX(6px);
}
.qc-icon{
  font-size:22px;flex-shrink:0;
  margin-top:2px;
}
.qc-title{
  font-family:var(--sans);font-size:13px;font-weight:700;
  color:var(--white);margin-bottom:5px;letter-spacing:0.02em;
}
.qc-text{
  font-family:var(--serif);font-size:13px;font-style:italic;
  color:var(--muted);line-height:1.6;
}
 
/* ═══ S2: TIMELINE ═══ */
#recorrido{background:var(--surface);}
.bg-line{
  position:absolute;top:0;bottom:0;left:50%;
  width:1px;background:var(--border);
  pointer-events:none;
}
 
.tl-wrap{margin-top:80px;position:relative;}
.tl-line{
  position:absolute;left:40px;top:0;bottom:0;
  width:1px;
  background:linear-gradient(to bottom,var(--accent),var(--accent2),var(--accent3));
  opacity:0.6;
}
.tl-item{
  display:grid;grid-template-columns:80px 1fr;
  gap:36px;margin-bottom:64px;
}
.tl-dot-wrap{
  display:flex;flex-direction:column;align-items:center;
  padding-top:4px;
}
.tl-dot{
  width:42px;height:42px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:16px;flex-shrink:0;
  border:1px solid var(--border2);
  background:var(--card);
  transition:transform .3s,border-color .3s;
  position:relative;z-index:2;
}
.tl-item:hover .tl-dot{
  transform:scale(1.2);border-color:var(--accent);
}
.tl-body{
  background:var(--card);border:1px solid var(--border);
  padding:28px 32px;border-radius:4px;
  transition:border-color .4s;
}
.tl-item:hover .tl-body{border-color:rgba(232,168,124,0.25);}
.tl-date{
  font-family:var(--mono);font-size:9px;letter-spacing:0.2em;
  text-transform:uppercase;color:var(--accent);margin-bottom:8px;
}
.tl-role{
  font-family:var(--sans);font-size:20px;font-weight:700;
  color:var(--white);margin-bottom:4px;
}
.tl-place{
  font-family:var(--mono);font-size:10px;letter-spacing:0.1em;
  color:var(--muted);margin-bottom:14px;
}
.tl-text{
  font-family:var(--serif);font-style:italic;font-size:13.5px;
  color:rgba(244,242,238,0.65);line-height:1.75;max-width:580px;
  margin-bottom:16px;
}
.chips{display:flex;flex-wrap:wrap;gap:7px;}
.chip{
  font-family:var(--mono);font-size:8.5px;letter-spacing:0.08em;
  padding:4px 12px;border-radius:2px;
  background:rgba(255,255,255,0.05);color:var(--muted);
  border:1px solid var(--border);transition:all .3s;
}
.chip.a{background:rgba(232,168,124,0.1);color:var(--accent);border-color:rgba(232,168,124,0.25);}
.chip:hover{background:rgba(232,168,124,0.12);color:var(--accent);border-color:rgba(232,168,124,0.3);}
 
/* ═══ S3: SKILLS ═══ */
#skills{background:var(--bg);}
.skills-intro{
  font-family:var(--serif);font-style:italic;font-size:17px;
  color:var(--muted);max-width:560px;line-height:1.7;
  margin-top:16px;margin-bottom:64px;
}
.skills-grid{
  display:grid;grid-template-columns:repeat(3,1fr);gap:2px;
  border:2px solid var(--border);
}
.sk-cell{
  background:var(--surface);padding:36px 32px;
  border-right:1px solid var(--border);
  border-bottom:1px solid var(--border);
  transition:background .4s;position:relative;overflow:hidden;
}
.sk-cell::before{
  content:'';position:absolute;inset:0;
  background:radial-gradient(circle at 0% 100%,var(--glow),transparent 60%);
  opacity:0;transition:opacity .5s;
}
.sk-cell:hover::before{opacity:1;}
.sk-cell:hover{background:var(--card);}
.sk-num{
  font-family:var(--mono);font-size:9px;letter-spacing:0.15em;
  color:var(--muted2);margin-bottom:14px;
}
.sk-name{
  font-family:var(--sans);font-size:14px;font-weight:700;
  color:var(--white);margin-bottom:16px;letter-spacing:0.02em;
}
.sk-list{
  display:flex;flex-direction:column;gap:6px;
}
.sk-item{
  font-family:var(--mono);font-size:10px;
  color:var(--muted);letter-spacing:0.04em;
  display:flex;align-items:center;gap:8px;
}
.sk-item::before{
  content:'';width:4px;height:4px;border-radius:50%;
  background:var(--accent);flex-shrink:0;opacity:0.6;
}
 
/* ═══ S4: PROJECTS ═══ */
#proyectos{background:var(--surface);}
.proj-list{margin-top:72px;display:flex;flex-direction:column;gap:2px;}
.proj-item{
  display:grid;grid-template-columns:80px 1fr 160px;
  align-items:center;gap:40px;
  padding:32px 40px;
  background:var(--card);
  border:1px solid var(--border);
  border-bottom:none;
  transition:background .4s,border-left-color .4s;
  border-left:3px solid transparent;
  cursor:default;
}
.proj-item:last-child{border-bottom:1px solid var(--border);}
.proj-item:hover{
  background:rgba(232,168,124,0.03);
  border-left-color:var(--accent);
}
.proj-n{
  font-family:var(--sans);font-size:52px;font-weight:800;
  color:rgba(255,255,255,0.05);line-height:1;letter-spacing:-2px;
  transition:color .4s;
}
.proj-item:hover .proj-n{color:rgba(232,168,124,0.15);}
.proj-info{}
.proj-name{
  font-family:var(--sans);font-size:17px;font-weight:700;
  color:var(--white);margin-bottom:6px;letter-spacing:0.01em;
}
.proj-desc{
  font-family:var(--serif);font-style:italic;font-size:13px;
  color:var(--muted);line-height:1.6;max-width:480px;
  margin-bottom:12px;
}
.proj-tags{display:flex;gap:6px;flex-wrap:wrap;}
.ptag{
  font-family:var(--mono);font-size:8px;letter-spacing:0.1em;
  text-transform:uppercase;padding:3px 10px;
  background:rgba(255,255,255,0.04);color:var(--muted);
  border:1px solid var(--border);border-radius:1px;
}
.proj-kpi{text-align:right;}
.kpi-val{
  font-family:var(--sans);font-size:36px;font-weight:800;
  color:var(--accent);letter-spacing:-1px;line-height:1;
}
.kpi-label{
  font-family:var(--mono);font-size:8px;letter-spacing:0.12em;
  text-transform:uppercase;color:var(--muted);margin-top:4px;
}
 
/* ═══ S5: VISION ═══ */
#vision{
  background:var(--bg);
  min-height:100vh;display:flex;align-items:center;
}
.vision-inner{
  display:grid;grid-template-columns:1fr 1fr;
  gap:100px;align-items:center;
}
.vision-left{}
.vision-q{
  font-family:var(--serif);font-size:clamp(22px,2.8vw,34px);
  font-style:italic;font-weight:400;
  color:var(--white);line-height:1.45;margin-top:32px;
}
.vision-q strong{
  font-family:var(--sans);font-style:normal;font-weight:800;
  color:var(--accent);
}
 
.edu-list{margin-top:48px;display:flex;flex-direction:column;gap:20px;}
.edu-item{
  display:flex;gap:20px;align-items:flex-start;
  padding-bottom:20px;border-bottom:1px solid var(--border);
}
.edu-item:last-child{border-bottom:none;}
.edu-yr{
  font-family:var(--mono);font-size:9px;letter-spacing:0.1em;
  color:var(--accent);padding-top:3px;min-width:44px;
}
.edu-deg{
  font-family:var(--sans);font-size:13px;font-weight:700;
  color:var(--white);margin-bottom:3px;
}
.edu-place{
  font-family:var(--mono);font-size:10px;color:var(--muted);
  letter-spacing:0.04em;
}
 
.vision-right{}
.lang-section{margin-bottom:52px;}
.lang-row{margin-bottom:20px;}
.lang-top{
  display:flex;justify-content:space-between;align-items:center;
  margin-bottom:8px;
}
.lang-name{
  font-family:var(--sans);font-size:12px;font-weight:600;
  color:var(--white);letter-spacing:0.05em;
}
.lang-lvl{
  font-family:var(--mono);font-size:9px;color:var(--muted);
  letter-spacing:0.1em;
}
.lang-track{
  height:1px;background:var(--border2);overflow:hidden;
}
.lang-fill{
  height:1px;background:linear-gradient(90deg,var(--accent),var(--accent2));
  transform-origin:left;transform:scaleX(0);
  transition:transform 1.2s cubic-bezier(.16,1,.3,1);
}
.lang-fill.on{transform:scaleX(1);}
 
.contact-grid{
  display:grid;grid-template-columns:1fr 1fr;gap:12px;
}
.c-link{
  font-family:var(--mono);font-size:9px;letter-spacing:0.12em;
  text-transform:uppercase;padding:14px 20px;
  border:1px solid var(--border2);color:var(--muted);
  text-decoration:none;text-align:center;border-radius:2px;
  transition:all .3s;
}
.c-link:hover{
  border-color:var(--accent);color:var(--accent);
  background:rgba(232,168,124,0.05);
}
 
/* ─ footer ─ */
footer{
  background:var(--surface);
  border-top:1px solid var(--border);
  padding:32px 60px;
  display:flex;justify-content:space-between;align-items:center;
}
.f-name{
  font-family:var(--sans);font-size:16px;font-weight:800;
  letter-spacing:0.05em;color:var(--white);
}
.f-name span{color:var(--accent);}
.f-mono{
  font-family:var(--mono);font-size:9px;letter-spacing:0.15em;
  color:var(--muted2);text-transform:uppercase;
}
 
/* ─ glow orb bg ─ */
.orb{
  position:absolute;border-radius:50%;pointer-events:none;
  filter:blur(80px);opacity:0.12;
}
 
@keyframes fadeUp{
  from{opacity:0;transform:translateY(30px);}
  to{opacity:1;transform:translateY(0);}
}
 
@media(max-width:768px){
  nav{padding:20px 24px;}
  .nav-links{display:none;}
  .container{padding:0 24px;}
  .quien-grid,.vision-inner{grid-template-columns:1fr;gap:48px;}
  .skills-grid{grid-template-columns:1fr;}
  .proj-item{grid-template-columns:1fr;gap:16px;}
  .proj-n{display:none;}
  .proj-kpi{text-align:left;}
  .stats-strip{grid-template-columns:1fr 1fr;}
  .contact-grid{grid-template-columns:1fr;}
  .hero-name{font-size:52px;}
  #side-dots{display:none;}
}
</style>
</head>
<body>
 
<div id="cur"></div>
<div id="cur-ring"></div>
<div id="prog"></div>
 
<nav>
  <div class="nav-logo">VG<span>.</span></div>
  <div class="nav-links">
    <a onclick="scroll2('quien')">Perfil</a>
    <a onclick="scroll2('recorrido')">Recorrido</a>
    <a onclick="scroll2('skills')">Skills</a>
    <a onclick="scroll2('proyectos')">Proyectos</a>
    <a onclick="scroll2('vision')">Visión</a>
  </div>
</nav>
 
<div id="side-dots">
  <div class="sdot on"  data-s="hero"></div>
  <div class="sdot" data-s="quien"></div>
  <div class="sdot" data-s="recorrido"></div>
  <div class="sdot" data-s="skills"></div>
  <div class="sdot" data-s="proyectos"></div>
  <div class="sdot" data-s="vision"></div>
</div>
 
<!-- ═══ HERO ═══ -->
<section id="hero">
  <!-- Tech reference image via Unsplash (free, no auth) -->
  <div class="hero-img-wrap">
    <img 
      src="https://images.unsplash.com/photo-1518770660439-4636190af475?w=1600&q=80&auto=format&fit=crop"
      alt="Technology circuit board — imagen de referencia"
      loading="eager"
    />
  </div>
  <canvas id="hero-canvas"></canvas>
 
  <div class="hero-content">
    <div class="hero-eyebrow">AI · Data Science · Software Engineering · Cooweb</div>
    <h1 class="hero-name">Valerie<br/><em>Gómez</em></h1>
    <div class="hero-role">Senior AI Architect · Cooweb · Bogotá, Colombia</div>
    <p class="hero-desc">
      Transformo datos complejos en decisiones que mueven organizaciones.<br/>
      Donde la lógica se encuentra con la creatividad.
    </p>
    <div class="hero-cta">
      <a class="btn btn-primary" onclick="scroll2('recorrido')">Ver mi historia</a>
      <a class="btn btn-ghost" onclick="scroll2('vision')">Conectar</a>
    </div>
  </div>
  <div class="hero-scroll">
    <span>Scroll</span>
    <div class="scroll-line"></div>
  </div>
</section>
 
<!-- stats -->
<div class="stats-strip">
  <div class="stat-cell rv">
    <div class="stat-num">10+</div>
    <div class="stat-label">Años de experiencia</div>
  </div>
  <div class="stat-cell rv d1">
    <div class="stat-num">30+</div>
    <div class="stat-label">Proyectos entregados</div>
  </div>
  <div class="stat-cell rv d2">
    <div class="stat-num">91%</div>
    <div class="stat-label">Accuracy modelo ML</div>
  </div>
  <div class="stat-cell rv d3">
    <div class="stat-num">−20%</div>
    <div class="stat-label">Reducción tiempo manual</div>
  </div>
</div>
 
<!-- ═══ QUIEN SOY ═══ -->
<section id="quien" class="section">
  <div class="orb" style="width:600px;height:600px;top:-10%;left:-15%;background:var(--accent);"></div>
  <div class="container">
    <div class="s-eyebrow rv">¿Quién soy?</div>
    <div class="quien-grid">
      <div>
        <p class="quien-quote rv">
          "No soy solo una arquitecta de IA que diseña sistemas.<br/>
          Soy alguien que <span>construye el futuro digital</span><br/>
          con las personas que lo van a vivir."
        </p>
        <div class="quien-pills rv d1">
          <div class="quien-pill">Analítica</div>
          <div class="quien-pill">Estratégica</div>
          <div class="quien-pill">Disruptiva</div>
          <div class="quien-pill">Liderazgo técnico</div>
          <div class="quien-pill">Colaborativa</div>
        </div>
      </div>
      <div class="quien-cards-v">
        <div class="quien-card rv d1">
          <div class="qc-icon">🔍</div>
          <div>
            <div class="qc-title">Pensamiento analítico</div>
            <div class="qc-text">Los datos me cuentan historias que otros no ven. Mi obsesión es encontrar el patrón detrás del ruido.</div>
          </div>
        </div>
        <div class="quien-card rv d2">
          <div class="qc-icon">🌱</div>
          <div>
            <div class="qc-title">Mentalidad de crecimiento</div>
            <div class="qc-text">No temo la curva de aprendizaje. La abrazo como parte inevitable del proceso de crear algo que valga la pena.</div>
          </div>
        </div>
        <div class="quien-card rv d3">
          <div class="qc-icon">⚡</div>
          <div>
            <div class="qc-title">Orientada a resultados</div>
            <div class="qc-text">El código bonito que no resuelve nada real no me interesa. Busco impacto medible en cada entrega.</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- ═══ RECORRIDO ═══ -->
<section id="recorrido" class="section">
  <div class="orb" style="width:500px;height:500px;top:30%;right:-10%;background:var(--accent2);"></div>
  <div class="container">
    <div class="s-eyebrow rv">Mi recorrido</div>
    <h2 class="s-title rv d1">Una historia<br/>de <em>evolución</em></h2>
    <div class="tl-wrap">
      <div class="tl-line"></div>
 
      <div class="tl-item rv">
        <div class="tl-dot-wrap"><div class="tl-dot">🎓</div></div>
        <div class="tl-body">
          <div class="tl-date">2016 — 2021</div>
          <div class="tl-role">Ingeniería de Sistemas</div>
          <div class="tl-place">Universidad Nacional de Colombia</div>
          <div class="tl-text">Donde entendí que la tecnología no es el fin, sino el medio. Aprendí a estructurar problemas antes de escribir una sola línea de código. Aquí nació mi obsesión por la eficiencia.</div>
          <div class="chips">
            <span class="chip a">Algoritmos</span>
            <span class="chip a">Bases de Datos</span>
            <span class="chip">Estructuras de datos</span>
            <span class="chip">Redes</span>
          </div>
        </div>
      </div>
 
      <div class="tl-item rv d1">
        <div class="tl-dot-wrap"><div class="tl-dot">📊</div></div>
        <div class="tl-body">
          <div class="tl-date">2020 — 2022</div>
          <div class="tl-role">Analista de Datos Jr.</div>
          <div class="tl-place">Sector Financiero · Bogotá</div>
          <div class="tl-text">Mi primer contacto con el poder real de los datos. Procesé más de 1M de registros para análisis de riesgo crediticio y automaticé reportes ejecutivos que antes tomaban horas manuales cada semana.</div>
          <div class="chips">
            <span class="chip a">SQL</span>
            <span class="chip a">Power BI</span>
            <span class="chip">Python</span>
            <span class="chip">Análisis de riesgo</span>
          </div>
        </div>
      </div>
 
      <div class="tl-item rv d2">
        <div class="tl-dot-wrap"><div class="tl-dot">🤖</div></div>
        <div class="tl-body">
          <div class="tl-date">2022</div>
          <div class="tl-role">Especialización en Data Science</div>
          <div class="tl-place">DeepLearning.AI · Coursera</div>
          <div class="tl-text">Machine Learning dejó de ser un concepto abstracto. Se convirtió en mi herramienta favorita para resolver problemas que antes parecían imposibles de modelar.</div>
          <div class="chips">
            <span class="chip a">ML</span>
            <span class="chip a">Deep Learning</span>
            <span class="chip">NLP</span>
            <span class="chip">TensorFlow</span>
          </div>
        </div>
      </div>
 
      <div class="tl-item rv d3">
        <div class="tl-dot-wrap"><div class="tl-dot">🚀</div></div>
        <div class="tl-body">
          <div class="tl-date">2022 — 2026</div>
          <div class="tl-role">Software Developer &amp; Data Analyst</div>
          <div class="tl-place">Freelance · Consultoría Independiente</div>
          <div class="tl-text">Trabajé con clientes que necesitaban más que código: necesitaban claridad. Optimicé aplicaciones un 35%, automaticé procesos reduciendo trabajo manual en 20%, y construí modelos predictivos que hablaban el idioma del negocio.</div>
          <div class="chips">
            <span class="chip a">Full-stack</span>
            <span class="chip a">ML en producción</span>
            <span class="chip">AWS</span>
            <span class="chip">Docker</span>
            <span class="chip">Scrum</span>
          </div>
        </div>
      </div>
 
      <div class="tl-item rv d4">
        <div class="tl-dot-wrap"><div class="tl-dot">🌐</div></div>
        <div class="tl-body">
          <div class="tl-date">2026 — Presente</div>
          <div class="tl-role">Senior AI Architect</div>
          <div class="tl-place">Cooweb · Bogotá, Colombia</div>
          <div class="tl-text">Lidero la arquitectura de soluciones de IA a escala en Cooweb, diseñando sistemas que integran modelos generativos, pipelines de datos en tiempo real y experiencias digitales inteligentes. Dirijo un equipo multidisciplinario de 8 personas y soy referente técnico en decisiones estratégicas de producto.</div>
          <div class="chips">
            <span class="chip a">AI Architecture</span>
            <span class="chip a">LLMs en producción</span>
            <span class="chip">Kubernetes</span>
            <span class="chip">MLOps</span>
            <span class="chip">Tech Lead</span>
          </div>
        </div>
      </div>
 
    </div>
  </div>
</section>
 
<!-- ═══ SKILLS ═══ -->
<section id="skills" class="section">
  <div class="orb" style="width:700px;height:700px;top:20%;left:30%;background:var(--accent3);"></div>
  <div class="container">
    <div class="s-eyebrow rv">Stack técnico</div>
    <h2 class="s-title rv d1">Lo que sé<br/><em>construir</em></h2>
    <p class="skills-intro rv d2">Las herramientas son el vocabulario. Lo que importa es cómo construyes el argumento con ellas.</p>
    <div class="skills-grid">
      <div class="sk-cell rv">
        <div class="sk-num">01</div>
        <div class="sk-name">Lenguajes & Backend</div>
        <div class="sk-list">
          <div class="sk-item">Python</div>
          <div class="sk-item">SQL · PostgreSQL</div>
          <div class="sk-item">Java</div>
          <div class="sk-item">JavaScript · Node</div>
          <div class="sk-item">R · FastAPI</div>
        </div>
      </div>
      <div class="sk-cell rv d1">
        <div class="sk-num">02</div>
        <div class="sk-name">IA & Machine Learning</div>
        <div class="sk-list">
          <div class="sk-item">Scikit-learn · XGBoost</div>
          <div class="sk-item">TensorFlow · PyTorch</div>
          <div class="sk-item">LLMs · RAG · Agents</div>
          <div class="sk-item">HuggingFace · NLP</div>
          <div class="sk-item">MLflow · Airflow · MLOps</div>
        </div>
      </div>
      <div class="sk-cell rv d2">
        <div class="sk-num">03</div>
        <div class="sk-name">Data & Visualización</div>
        <div class="sk-list">
          <div class="sk-item">Power BI · Tableau</div>
          <div class="sk-item">Plotly · Matplotlib</div>
          <div class="sk-item">dbt · Spark</div>
          <div class="sk-item">ETL Pipelines</div>
          <div class="sk-item">Data Warehousing</div>
        </div>
      </div>
      <div class="sk-cell rv">
        <div class="sk-num">04</div>
        <div class="sk-name">Cloud & DevOps</div>
        <div class="sk-list">
          <div class="sk-item">AWS · S3 · Lambda</div>
          <div class="sk-item">Azure · GCP</div>
          <div class="sk-item">Docker · Kubernetes</div>
          <div class="sk-item">Git · GitHub Actions</div>
          <div class="sk-item">Linux · CLI</div>
        </div>
      </div>
      <div class="sk-cell rv d1">
        <div class="sk-num">05</div>
        <div class="sk-name">Metodologías</div>
        <div class="sk-list">
          <div class="sk-item">Scrum · Kanban</div>
          <div class="sk-item">Clean Code · TDD</div>
          <div class="sk-item">Design Thinking</div>
          <div class="sk-item">CI/CD Pipelines</div>
          <div class="sk-item">Pair Programming</div>
        </div>
      </div>
      <div class="sk-cell rv d2">
        <div class="sk-num">06</div>
        <div class="sk-name">Soft Skills</div>
        <div class="sk-list">
          <div class="sk-item">Comunicación técnica</div>
          <div class="sk-item">Resolución de problemas</div>
          <div class="sk-item">Liderazgo de proyectos</div>
          <div class="sk-item">Trabajo en equipo</div>
          <div class="sk-item">Adaptabilidad</div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- ═══ PROYECTOS ═══ -->
<section id="proyectos" class="section">
  <div class="container">
    <div class="s-eyebrow rv">Proyectos</div>
    <h2 class="s-title rv d1">Trabajo que<br/><em>dejó huella</em></h2>
    <div class="proj-list">
      <div class="proj-item rv">
        <div class="proj-n">01</div>
        <div class="proj-info">
          <div class="proj-name">Modelo Predictivo de Churn</div>
          <div class="proj-desc">Clasificador que identifica clientes en riesgo 30 días antes de que se vayan. No solo predice — da tiempo para actuar con estrategias de retención.</div>
          <div class="proj-tags">
            <span class="ptag">Python</span><span class="ptag">XGBoost</span><span class="ptag">Scikit-learn</span><span class="ptag">MLflow</span>
          </div>
        </div>
        <div class="proj-kpi">
          <div class="kpi-val">91%</div>
          <div class="kpi-label">accuracy</div>
        </div>
      </div>
      <div class="proj-item rv d1">
        <div class="proj-n">02</div>
        <div class="proj-info">
          <div class="proj-name">BI Dashboard Gerencial</div>
          <div class="proj-desc">Consolidé 12 fuentes de datos heterogéneas en una vista ejecutiva en tiempo real que redujo drásticamente el tiempo de toma de decisiones en reuniones directivas.</div>
          <div class="proj-tags">
            <span class="ptag">Power BI</span><span class="ptag">SQL</span><span class="ptag">DAX</span><span class="ptag">Azure</span>
          </div>
        </div>
        <div class="proj-kpi">
          <div class="kpi-val">12→1</div>
          <div class="kpi-label">fuentes unificadas</div>
        </div>
      </div>
      <div class="proj-item rv d2">
        <div class="proj-n">03</div>
        <div class="proj-info">
          <div class="proj-name">Plataforma de IA Conversacional — Cooweb</div>
          <div class="proj-desc">Diseñé e implementé la arquitectura de un asistente inteligente para clientes de Cooweb, basado en LLMs con RAG personalizado por industria. Redujo el tiempo de respuesta de soporte y aumentó la satisfacción de usuarios finales.</div>
          <div class="proj-tags">
            <span class="ptag">LLMs</span><span class="ptag">RAG</span><span class="ptag">FastAPI</span><span class="ptag">Kubernetes</span>
          </div>
        </div>
        <div class="proj-kpi">
          <div class="kpi-val">−60%</div>
          <div class="kpi-label">tiempo de soporte</div>
        </div>
      </div>
      <div class="proj-item rv d3">
        <div class="proj-n">04</div>
        <div class="proj-info">
          <div class="proj-name">API de NLP para Soporte</div>
          <div class="proj-desc">Microservicio que clasifica y enruta tickets automáticamente usando transformers. Liberó al equipo de soporte de tareas repetitivas, con integración directa al sistema existente.</div>
          <div class="proj-tags">
            <span class="ptag">FastAPI</span><span class="ptag">HuggingFace</span><span class="ptag">Docker</span><span class="ptag">AWS</span>
          </div>
        </div>
        <div class="proj-kpi">
          <div class="kpi-val">85%</div>
          <div class="kpi-label">automatización</div>
        </div>
      </div>
      <div class="proj-item rv d3">
        <div class="proj-n">05</div>
        <div class="proj-info">
          <div class="proj-name">Pipeline ETL Automatizado</div>
          <div class="proj-desc">Orquestación diaria de 5 fuentes externas hacia data warehouse con validación automática de calidad de datos. Eliminó errores manuales y redujo el tiempo de procesamiento.</div>
          <div class="proj-tags">
            <span class="ptag">Airflow</span><span class="ptag">AWS S3</span><span class="ptag">Pandas</span><span class="ptag">dbt</span>
          </div>
        </div>
        <div class="proj-kpi">
          <div class="kpi-val">−20%</div>
          <div class="kpi-label">tiempo manual</div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<!-- ═══ VISIÓN & CONTACTO ═══ -->
<section id="vision" class="section">
  <div class="orb" style="width:600px;height:600px;bottom:-20%;right:-10%;background:var(--accent);"></div>
  <div class="container">
    <div class="vision-inner">
      <div class="vision-left">
        <div class="s-eyebrow rv">Dónde estoy · Hacia dónde voy</div>
        <p class="vision-q rv d1">
          Como <strong>Senior AI Architect en Cooweb</strong>,<br/>
          lidero proyectos de IA con<br/>
          <em>impacto real en las personas.</em><br/>
          Mi próximo horizonte: construir<br/>
          <strong>productos que definan el estándar.</strong>
        </p>
        <div class="edu-list">
          <div class="edu-item rv d2">
            <div class="edu-yr">2021</div>
            <div>
              <div class="edu-deg">Ingeniería de Sistemas</div>
              <div class="edu-place">Universidad Nacional de Colombia</div>
            </div>
          </div>
          <div class="edu-item rv d3">
            <div class="edu-yr">2022</div>
            <div>
              <div class="edu-deg">Data Science Specialization</div>
              <div class="edu-place">DeepLearning.AI · Coursera</div>
            </div>
          </div>
          <div class="edu-item rv d4">
            <div class="edu-yr">2023</div>
            <div>
              <div class="edu-deg">AWS Cloud Practitioner</div>
              <div class="edu-place">Amazon Web Services</div>
            </div>
          </div>
          <div class="edu-item rv d4">
            <div class="edu-yr">2028</div>
            <div>
              <div class="edu-deg">Generative AI & LLM Systems</div>
              <div class="edu-place">Stanford Online · Certificación</div>
            </div>
          </div>
          <div class="edu-item rv d4">
            <div class="edu-yr">2026</div>
            <div>
              <div class="edu-deg">Senior AI Architect — Incorporación</div>
              <div class="edu-place">Cooweb · Bogotá, Colombia</div>
            </div>
          </div>
        </div>
      </div>
      <div class="vision-right">
        <div class="lang-section rv">
          <div class="s-eyebrow" style="margin-bottom:28px;">Idiomas</div>
          <div class="lang-row">
            <div class="lang-top">
              <div class="lang-name">Español</div>
              <div class="lang-lvl">Nativo · C2</div>
            </div>
            <div class="lang-track">
              <div class="lang-fill" data-w="1" style="width:100%"></div>
            </div>
          </div>
          <div class="lang-row" style="margin-top:20px;">
            <div class="lang-top">
              <div class="lang-name">English</div>
              <div class="lang-lvl">Upper-Intermediate · B2</div>
            </div>
            <div class="lang-track">
              <div class="lang-fill" data-w="0.78" style="width:78%"></div>
            </div>
          </div>
        </div>
        <div class="rv d1">
          <div class="s-eyebrow" style="margin-bottom:20px;">Contacto</div>
          <div class="contact-grid">
            <a href="/cdn-cgi/l/email-protection#3147505d5443585471545c50585d1f525e5c" class="c-link">Email</a>
            <a href="#" class="c-link">LinkedIn</a>
            <a href="#" class="c-link">GitHub</a>
            <a href="#" class="c-link">Descargar CV</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
 
<footer>
  <div class="f-name">VALERIE <span>GÓMEZ</span></div>
  <div class="f-mono">AI · Data · Software · 2031</div>
  <div class="f-mono">Bogotá, Colombia</div>
</footer>
 
<script data-cfasync="false" src="/cdn-cgi/scripts/5c5dd728/cloudflare-static/email-decode.min.js"></script><script>
/* ── cursor ── */
const cur=document.getElementById('cur'),ring=document.getElementById('cur-ring');
let mx=0,my=0,rx=0,ry=0;
document.addEventListener('mousemove',e=>{mx=e.clientX;my=e.clientY;});
document.querySelectorAll('a,.quien-card,.proj-item,.sk-cell,.btn').forEach(el=>{
  el.addEventListener('mouseenter',()=>{cur.style.width='24px';cur.style.height='24px';cur.style.background='rgba(232,168,124,0.5)';});
  el.addEventListener('mouseleave',()=>{cur.style.width='10px';cur.style.height='10px';cur.style.background='var(--accent)';});
});
(function animC(){
  cur.style.left=mx+'px';cur.style.top=my+'px';
  rx+=(mx-rx)*.12;ry+=(my-ry)*.12;
  ring.style.left=rx+'px';ring.style.top=ry+'px';
  requestAnimationFrame(animC);
})();
 
/* ── scroll progress ── */
const prog=document.getElementById('prog');
window.addEventListener('scroll',()=>{
  const p=window.scrollY/(document.documentElement.scrollHeight-window.innerHeight);
  prog.style.width=(p*100)+'%';
});
 
/* ── nav dots ── */
const secs=['hero','quien','recorrido','skills','proyectos','vision'];
const dots=document.querySelectorAll('.sdot');
dots.forEach((d,i)=>{
  d.addEventListener('click',()=>scroll2(secs[i]));
});
function scroll2(id){
  const el=document.getElementById(id);
  if(el)el.scrollIntoView({behavior:'smooth'});
}
const secObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      const i=secs.indexOf(e.target.id);
      dots.forEach(d=>d.classList.remove('on'));
      if(dots[i])dots[i].classList.add('on');
    }
  });
},{threshold:0.35});
secs.forEach(id=>{const el=document.getElementById(id);if(el)secObs.observe(el);});
 
/* ── reveal on scroll ── */
const rvObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{if(e.isIntersecting)e.target.classList.add('on');});
},{threshold:0.1,rootMargin:'0px 0px -50px 0px'});
document.querySelectorAll('.rv').forEach(el=>rvObs.observe(el));
setTimeout(()=>{
  document.querySelectorAll('#hero .rv, .stats-strip .rv').forEach(el=>el.classList.add('on'));
},200);
 
/* ── lang bars animate ── */
const langObs=new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){
      e.target.querySelectorAll('.lang-fill').forEach(f=>f.classList.add('on'));
    }
  });
},{threshold:0.5});
const langSec=document.getElementById('vision');
if(langSec)langObs.observe(langSec);
 
/* ── particle canvas ── */
const canvas=document.getElementById('hero-canvas');
const ctx=canvas.getContext('2d');
let W,H,particles=[];
 
function resize(){
  W=canvas.width=canvas.offsetWidth;
  H=canvas.height=canvas.offsetHeight;
}
resize();
window.addEventListener('resize',()=>{resize();});
 
function Particle(){
  this.x=Math.random()*W;
  this.y=Math.random()*H;
  this.vx=(Math.random()-.5)*0.35;
  this.vy=(Math.random()-.5)*0.35;
  this.r=Math.random()*1.4+0.4;
  this.alpha=Math.random()*0.5+0.15;
  this.color=Math.random()>.7?'232,168,124':Math.random()>.5?'126,200,180':'255,255,255';
}
Particle.prototype.update=function(){
  this.x+=this.vx;this.y+=this.vy;
  if(this.x<0)this.x=W;if(this.x>W)this.x=0;
  if(this.y<0)this.y=H;if(this.y>H)this.y=0;
};
Particle.prototype.draw=function(){
  ctx.beginPath();
  ctx.arc(this.x,this.y,this.r,0,Math.PI*2);
  ctx.fillStyle=`rgba(${this.color},${this.alpha})`;
  ctx.fill();
};
 
const N=120;
for(let i=0;i<N;i++)particles.push(new Particle());
 
function connect(){
  for(let i=0;i<N;i++){
    for(let j=i+1;j<N;j++){
      const dx=particles[i].x-particles[j].x;
      const dy=particles[i].y-particles[j].y;
      const dist=Math.sqrt(dx*dx+dy*dy);
      if(dist<110){
        ctx.beginPath();
        ctx.moveTo(particles[i].x,particles[i].y);
        ctx.lineTo(particles[j].x,particles[j].y);
        ctx.strokeStyle=`rgba(232,168,124,${(1-dist/110)*0.12})`;
        ctx.lineWidth=.6;
        ctx.stroke();
      }
    }
  }
}
 
let mouseX=W/2,mouseY=H/2;
canvas.addEventListener('mousemove',e=>{
  const r=canvas.getBoundingClientRect();
  mouseX=e.clientX-r.left;mouseY=e.clientY-r.top;
});
 
function loop(){
  ctx.clearRect(0,0,W,H);
  particles.forEach(p=>{
    // subtle attract to mouse
    const dx=mouseX-p.x,dy=mouseY-p.y;
    const d=Math.sqrt(dx*dx+dy*dy);
    if(d<180){p.vx+=dx/d*.006;p.vy+=dy/d*.006;}
    //


