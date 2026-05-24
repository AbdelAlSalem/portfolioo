<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio | Abdelqader Al-Salem</title>
    <link rel="icon" type="image/png" href="a-FAVICON.png">
    <link rel="apple-touch-icon" href="a-FAVICON.png">
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&family=Playfair+Display:wght@700;800;900&display=swap" rel="stylesheet">
    <style>
        *,*::before,*::after{margin:0;padding:0;box-sizing:border-box}
        :root{
            --bg:#05080f;--surface:#0c1220;--surface2:#111a2e;--border:#1e2d4a;
            --cyan:#00e5ff;--cyan-dim:#00b8cc;--gold:#f0a500;--gold-dim:#c98a00;
            --text:#e8f0fe;--muted:#7b92b2;--r:12px;
        }
        html{scroll-behavior:smooth}
        body{font-family:'Poppins',sans-serif;background:var(--bg);color:var(--text);overflow-x:hidden}
        ::-webkit-scrollbar{width:5px}::-webkit-scrollbar-track{background:var(--bg)}::-webkit-scrollbar-thumb{background:var(--cyan);border-radius:3px}
        body::before{content:'';position:fixed;inset:0;z-index:-1;pointer-events:none;
            background:radial-gradient(ellipse 80% 60% at 10% 10%,rgba(0,229,255,.07) 0%,transparent 60%),
                       radial-gradient(ellipse 60% 50% at 90% 90%,rgba(240,165,0,.06) 0%,transparent 60%)}
        /* NAV */
        header{position:fixed;top:0;left:0;right:0;z-index:999;background:rgba(5,8,15,.88);backdrop-filter:blur(18px);border-bottom:1px solid var(--border);height:70px;display:flex;align-items:center;padding:0 3rem}
        nav{width:100%;max-width:1200px;margin:0 auto;display:flex;justify-content:space-between;align-items:center}
        .logo{font-size:1.4rem;font-weight:700;color:var(--cyan);text-decoration:none;letter-spacing:-.5px}
        .logo span{color:var(--gold)}
        nav ul{list-style:none;display:flex;gap:2.5rem}
        nav a{color:var(--muted);text-decoration:none;font-size:.9rem;font-weight:500;transition:color .25s;position:relative;padding-bottom:4px}
        nav a::after{content:'';position:absolute;bottom:0;left:0;width:0;height:2px;background:var(--cyan);transition:width .3s}
        nav a:hover{color:var(--cyan)}nav a:hover::after{width:100%}
        /* LAYOUT */
        .container{max-width:1200px;margin:0 auto;padding:0 2rem}
        section{padding:7rem 0}
        /* HERO */
        #home{min-height:100vh;display:flex;align-items:center;padding-top:70px}
        .hero-inner{display:grid;grid-template-columns:1fr 1fr;gap:5rem;align-items:center}
        .hero-eyebrow{display:inline-flex;align-items:center;gap:.6rem;color:var(--gold);font-size:.82rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;margin-bottom:1.2rem;animation:fadeUp .7s ease both}
        .hero-eyebrow::before{content:'';width:30px;height:2px;background:var(--gold)}
        .hero-name{font-family:'Playfair Display',serif;font-size:clamp(2.8rem,5vw,4.5rem);font-weight:900;line-height:1.05;color:var(--text);margin-bottom:.8rem;animation:fadeUp .7s .1s ease both}
        .hero-name .hl{color:var(--cyan)}
        .hero-role{font-size:1.1rem;font-weight:600;color:var(--gold);margin-bottom:1.8rem;animation:fadeUp .7s .2s ease both}
        .hero-desc{font-size:.98rem;line-height:1.85;color:var(--muted);margin-bottom:2.5rem;animation:fadeUp .7s .3s ease both}
        .hero-btns{display:flex;gap:1rem;flex-wrap:wrap;animation:fadeUp .7s .4s ease both}
        .btn{display:inline-flex;align-items:center;gap:.5rem;padding:.85rem 2rem;border-radius:8px;font-family:inherit;font-size:.95rem;font-weight:600;text-decoration:none;cursor:pointer;border:none;transition:all .3s}
        .btn-primary{background:var(--cyan);color:#05080f;box-shadow:0 0 24px rgba(0,229,255,.35)}
        .btn-primary:hover{background:var(--cyan-dim);box-shadow:0 0 36px rgba(0,229,255,.55);transform:translateY(-2px)}
        .btn-outline{background:transparent;color:var(--gold);border:2px solid var(--gold)}
        .btn-outline:hover{background:rgba(240,165,0,.1);transform:translateY(-2px)}
        .hero-socials{display:flex;gap:1rem;margin-top:2rem;flex-wrap:wrap;animation:fadeUp .7s .5s ease both}
        .social-pill{display:inline-flex;align-items:center;gap:.5rem;padding:.5rem 1.2rem;border:1px solid var(--border);border-radius:50px;color:var(--muted);font-size:.82rem;text-decoration:none;transition:all .3s}
        .social-pill:hover{border-color:var(--cyan);color:var(--cyan);background:rgba(0,229,255,.05)}
        /* IMAGE */
        .hero-img-wrap{position:relative;animation:fadeRight .8s .2s ease both;max-width:430px;justify-self:end}
        .hero-img-frame{position:relative;aspect-ratio:4/5;border-radius:36% 64% 44% 56%/42% 36% 64% 58%;overflow:hidden;background:linear-gradient(145deg,rgba(0,229,255,.16),rgba(240,165,0,.12));box-shadow:0 28px 70px rgba(0,0,0,.45),0 0 0 1px rgba(255,255,255,.08)}
        .hero-img-frame::before{content:'';position:absolute;inset:0;z-index:2;background:linear-gradient(180deg,rgba(5,8,15,.02) 35%,rgba(5,8,15,.42) 100%),radial-gradient(circle at 22% 12%,rgba(255,255,255,.18),transparent 30%);pointer-events:none}
        .hero-img-frame::after{content:'';position:absolute;inset:16px;border:1px solid rgba(255,255,255,.16);border-radius:inherit;z-index:3;pointer-events:none}
        .hero-img-frame img{width:100%;height:100%;display:block;object-fit:cover;object-position:center top;filter:brightness(1.06) contrast(1.08) saturate(1.08);animation:slowZoom 14s ease-in-out infinite alternate}
        .hero-img-wrap::before{content:'';position:absolute;inset:-18px 22px 20px -22px;z-index:-1;border-radius:32% 68% 38% 62%/48% 34% 66% 52%;background:linear-gradient(135deg,var(--cyan),var(--gold));opacity:.92;filter:blur(.2px);transform:rotate(-7deg)}
        .hero-img-wrap::after{content:'';position:absolute;right:-28px;bottom:-30px;width:150px;height:150px;z-index:-2;border:1px solid rgba(0,229,255,.32);border-radius:50%;background:rgba(0,229,255,.05)}
        .img-badge{position:absolute;bottom:18px;right:-18px;z-index:10;background:rgba(5,8,15,.86);backdrop-filter:blur(14px);color:var(--text);font-size:.78rem;font-weight:700;padding:.75rem 1.15rem;border:1px solid rgba(240,165,0,.55);border-radius:999px;box-shadow:0 12px 30px rgba(0,0,0,.35);animation:float 3s ease-in-out infinite;line-height:1.3}
        .img-badge span{display:block;font-size:1.1rem;font-weight:900}
        /* SECTION TITLES */
        .section-label{display:inline-flex;align-items:center;gap:.6rem;color:var(--gold);font-size:.78rem;font-weight:700;letter-spacing:2px;text-transform:uppercase;margin-bottom:1rem}
        .section-label::before{content:'';width:24px;height:2px;background:var(--gold)}
        .section-title{font-family:'Playfair Display',serif;font-size:clamp(2rem,4vw,3rem);font-weight:800;color:var(--text);margin-bottom:1rem;line-height:1.1}
        .section-title .hl{color:var(--cyan)}
        .section-sub{color:var(--muted);font-size:1rem;line-height:1.7;max-width:540px}
        /* ABOUT */
        #about{background:linear-gradient(180deg,transparent,rgba(0,229,255,.025) 50%,transparent)}
        .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:4rem;margin-top:3.5rem}
        .about-text p{color:var(--muted);line-height:1.85;font-size:.97rem;margin-bottom:1.5rem}
        .about-text p b{color:var(--cyan);font-weight:600}
        .expertise-cards{display:grid;grid-template-columns:1fr 1fr;gap:1.2rem}
        .exp-card{padding:1.4rem;background:var(--surface);border:1px solid var(--border);border-radius:var(--r);transition:all .3s}
        .exp-card:hover{border-color:var(--cyan);background:rgba(0,229,255,.04);transform:translateY(-4px);box-shadow:0 12px 30px rgba(0,229,255,.08)}
        .exp-card h4{color:var(--cyan);font-size:.82rem;font-weight:700;letter-spacing:.5px;text-transform:uppercase;margin-bottom:.5rem}
        .exp-card p{color:var(--muted);font-size:.84rem;line-height:1.6}
        /* SKILLS */
        .skills-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(210px,1fr));gap:1.5rem;margin-top:3.5rem}
        .skill-card{padding:2rem 1.8rem;background:var(--surface);border:1px solid var(--border);border-radius:var(--r);transition:all .35s;position:relative;overflow:hidden}
        .skill-card::before{content:'';position:absolute;top:0;left:0;right:0;height:3px;background:linear-gradient(90deg,var(--cyan),var(--gold));transform:scaleX(0);transform-origin:left;transition:transform .35s}
        .skill-card:hover::before{transform:scaleX(1)}
        .skill-card:hover{border-color:var(--cyan);transform:translateY(-6px);box-shadow:0 16px 40px rgba(0,229,255,.1)}
        .skill-card h3{color:var(--cyan);font-size:.98rem;font-weight:700;margin-bottom:1.2rem}
        .skill-list{list-style:none}
        .skill-list li{color:var(--muted);font-size:.86rem;padding:.4rem 0 .4rem 1.4rem;position:relative;border-bottom:1px solid rgba(255,255,255,.03)}
        .skill-list li:last-child{border-bottom:none}
        .skill-list li::before{content:'▸';position:absolute;left:0;color:var(--gold)}
        /* PROJECTS */
        #projects{background:linear-gradient(180deg,transparent,rgba(240,165,0,.02) 50%,transparent)}
        .projects-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(300px,1fr));gap:2rem;margin-top:3.5rem}
        .proj-card{background:var(--surface);border:1px solid var(--border);border-radius:var(--r);overflow:hidden;transition:all .35s;display:flex;flex-direction:column}
        .proj-card:hover{border-color:var(--gold);transform:translateY(-8px);box-shadow:0 20px 50px rgba(240,165,0,.1)}
        .proj-header{background:linear-gradient(135deg,rgba(0,229,255,.07),rgba(240,165,0,.07));padding:1.8rem 2rem 1.4rem;border-bottom:1px solid var(--border)}
        .proj-num{font-size:.72rem;color:var(--gold);font-weight:700;letter-spacing:2px;text-transform:uppercase;margin-bottom:.5rem}
        .proj-title{color:var(--text);font-size:1.2rem;font-weight:700;margin-bottom:.3rem}
        .proj-subtitle{color:var(--muted);font-size:.84rem}
        .proj-body{padding:1.8rem 2rem;flex-grow:1;display:flex;flex-direction:column}
        .proj-desc{color:var(--muted);font-size:.89rem;line-height:1.75;margin-bottom:1.5rem;flex-grow:1}
        .proj-tags{display:flex;flex-wrap:wrap;gap:.6rem;margin-bottom:1.5rem}
        .tag{background:rgba(0,229,255,.1);color:var(--cyan);padding:.3rem .8rem;border-radius:50px;font-size:.73rem;font-weight:600}
        .proj-link{color:var(--gold);font-size:.87rem;font-weight:600;text-decoration:none;display:inline-flex;align-items:center;gap:.4rem;transition:gap .25s}
        .proj-link:hover{gap:.8rem}
        /* STATS */
        .stats-row{display:grid;grid-template-columns:repeat(3,1fr);gap:2rem;margin-top:5rem}
        .stat-card{text-align:center;padding:2.5rem 1rem;background:var(--surface);border:1px solid var(--border);border-radius:var(--r);transition:all .3s}
        .stat-card:hover{border-color:var(--cyan);box-shadow:0 0 30px rgba(0,229,255,.1)}
        .stat-num{font-family:'Playfair Display',serif;font-size:3rem;font-weight:900;color:var(--cyan);line-height:1;margin-bottom:.5rem}
        .stat-lbl{color:var(--muted);font-size:.88rem;font-weight:500}
        /* EXPERIENCE */
        .exp-timeline{margin-top:3.5rem;position:relative;padding-left:2rem}
        .exp-timeline::before{content:'';position:absolute;left:0;top:0;bottom:0;width:2px;background:linear-gradient(180deg,var(--cyan),var(--gold),transparent)}
        .exp-item{position:relative;padding-bottom:3rem;padding-left:2rem}
        .exp-dot{position:absolute;left:-2.62rem;top:4px;width:14px;height:14px;border-radius:50%;background:var(--cyan);border:3px solid var(--bg);box-shadow:0 0 10px rgba(0,229,255,.6);transition:all .3s}
        .exp-item:hover .exp-dot{background:var(--gold);box-shadow:0 0 16px rgba(240,165,0,.7)}
        .exp-period{color:var(--gold);font-size:.78rem;font-weight:700;letter-spacing:1px;text-transform:uppercase;margin-bottom:.4rem}
        .exp-title-h{color:var(--text);font-size:1.12rem;font-weight:700;margin-bottom:.2rem}
        .exp-company{color:var(--cyan);font-size:.88rem;margin-bottom:.8rem}
        .exp-desc{color:var(--muted);font-size:.88rem;line-height:1.7;margin-bottom:1rem}
        .exp-points{list-style:none}
        .exp-points li{color:var(--muted);font-size:.86rem;padding:.3rem 0 .3rem 1.4rem;position:relative}
        .exp-points li::before{content:'→';position:absolute;left:0;color:var(--gold)}
        /* CONTACT */
        #contact{background:linear-gradient(180deg,transparent,rgba(0,229,255,.03) 50%,transparent)}
        .contact-inner{max-width:680px;margin:3.5rem auto 0}
        .contact-lead{color:var(--muted);font-size:1.02rem;line-height:1.8;margin-bottom:2.5rem;text-align:center}
        .contact-cards{display:grid;grid-template-columns:1fr 1fr;gap:1.5rem;margin-bottom:3rem}
        .c-card{padding:2rem;background:var(--surface);border:1px solid var(--border);border-radius:var(--r);text-decoration:none;transition:all .3s;display:block}
        .c-card:hover{border-color:var(--cyan);background:rgba(0,229,255,.04);transform:translateY(-4px)}
        .c-label{color:var(--cyan);font-size:.76rem;font-weight:700;letter-spacing:1.5px;text-transform:uppercase;margin-bottom:.7rem;display:block}
        .c-val{color:var(--text);font-size:.93rem;font-weight:500}
        .contact-cta{text-align:center}
        /* FOOTER */
        footer{border-top:1px solid var(--border);padding:2.5rem 2rem}
        .footer-inner{max-width:1200px;margin:0 auto;display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:1rem}
        .footer-copy{color:var(--muted);font-size:.83rem}
        .footer-copy span{color:var(--cyan)}
        .footer-nav{display:flex;gap:2rem;list-style:none}
        .footer-nav a{color:var(--muted);text-decoration:none;font-size:.83rem;transition:color .25s}
        .footer-nav a:hover{color:var(--cyan)}
        /* ANIMATIONS */
        @keyframes fadeUp{from{opacity:0;transform:translateY(24px)}to{opacity:1;transform:translateY(0)}}
        @keyframes fadeRight{from{opacity:0;transform:translateX(30px)}to{opacity:1;transform:translateX(0)}}
        @keyframes rotateBorder{from{transform:rotate(0deg)}to{transform:rotate(360deg)}}
        @keyframes float{0%,100%{transform:translateY(0)}50%{transform:translateY(-8px)}}
        @keyframes slowZoom{from{transform:scale(1)}to{transform:scale(1.07)}}
        .reveal{opacity:0;transform:translateY(28px);transition:opacity .7s ease,transform .7s ease}
        .revealed{opacity:1;transform:none}
        /* RESPONSIVE */
        @media(max-width:900px){
            header{padding:0 1.5rem}
            nav ul{display:none}
            .hero-inner{grid-template-columns:1fr}
            .hero-img-wrap{order:-1;max-width:340px;margin:0 auto}
            .about-grid{grid-template-columns:1fr}
            .expertise-cards{grid-template-columns:1fr}
            .stats-row,.contact-cards{grid-template-columns:1fr}
        }
        @media(max-width:600px){section{padding:5rem 0}.container{padding:0 1.2rem}}
    </style>
</head>
<body>

<header>
  <nav>
    <a href="#home" class="logo">Abdelqader <span>.</span></a>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#skills">Skills</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#experience">Experience</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>
</header>

<!-- HERO -->
<section id="home">
  <div class="container">
    <div class="hero-inner">
      <div>
        <div class="hero-eyebrow">Software Engineer &amp; AI Specialist</div>
        <h1 class="hero-name">Abdelqader<br><span class="hl">Al-Salem</span></h1>
        <p class="hero-role">Building intelligent products · AI + Full-Stack</p>
        <p class="hero-desc">I build end-to-end digital products — from pixel-perfect React frontends to robust Node.js backends — with a strong focus on LLM integration and prompt engineering. Co-founder of <b style="color:var(--cyan)">Dardeshly</b>, an AI-powered WhatsApp marketing platform.</p>
        <div class="hero-btns">
          <a href="mailto:abdelalsalem09@gmail.com" class="btn btn-primary">✉ Send Email</a>
          <a href="#projects" class="btn btn-outline">View My Work</a>
        </div>
        <div class="hero-socials">
          <a href="https://wa.me/905521511094" target="_blank" class="social-pill">💬 WhatsApp</a>
          <a href="https://property-byabdel.vercel.app/" target="_blank" class="social-pill">🌐 Portfolio</a>
          <a href="https://dardeshly.com" target="_blank" class="social-pill">🚀 Dardeshly</a>
        </div>
      </div>
      <div class="hero-img-wrap">
        <div class="hero-img-frame">
          <img src="abdelqader.jpg" alt="Abdelqader Al-Salem">
        </div>
        <div class="img-badge"><span>Open</span>to Collaborate</div>
      </div>
    </div>
  </div>
</section>

<!-- ABOUT -->
<section id="about">
  <div class="container">
    <div class="reveal">
      <div class="section-label">Get to know me</div>
      <h2 class="section-title">About <span class="hl">Me</span></h2>
    </div>
    <div class="about-grid reveal">
      <div class="about-text">
        <p>I'm a <b>full-stack software engineer</b> based in Istanbul, Turkey, passionate about building scalable web applications and AI-powered products. My stack spans React frontends to Node.js backends, REST APIs, and database design.</p>
        <p>As <b>co-founder of Dardeshly</b>, I lead product and engineering direction — designing intelligent prompt pipelines, integrating cutting-edge LLMs (Claude, GPT, DeepSeek, Grok), and shipping complete solutions end-to-end.</p>
        <p>I combine technical depth with real-world <b>business acumen</b> built through sales experience, which sharpens my ability to understand customer needs and translate them into impactful shipped code.</p>
      </div>
      <div>
        <h3 style="color:var(--text);font-size:1.05rem;font-weight:700;margin-bottom:1.5rem;">Core Expertise</h3>
        <div class="expertise-cards">
          <div class="exp-card"><h4>AI Engineering</h4><p>Prompt design, LLM integration, RAG systems and AI-powered product features</p></div>
          <div class="exp-card"><h4>Full Stack</h4><p>React, Next.js, Node.js, REST APIs, PostgreSQL & MongoDB end-to-end</p></div>
          <div class="exp-card"><h4>Product Thinking</h4><p>Translating customer needs into requirements and shipping features that matter</p></div>
          <div class="exp-card"><h4>Communication</h4><p>Sales background brings negotiation, client management &amp; pitch skills</p></div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- SKILLS -->
<section id="skills">
  <div class="container">
    <div class="reveal">
      <div class="section-label">What I work with</div>
      <h2 class="section-title">Technical <span class="hl">Skills</span></h2>
    </div>
    <div class="skills-grid">
      <div class="skill-card reveal"><h3>🤖 AI &amp; LLMs</h3><ul class="skill-list"><li>Prompt Engineering</li><li>Claude &amp; OpenAI APIs</li><li>DeepSeek, Grok, Sora</li><li>RAG Systems</li><li>AI-Powered Chatbots</li><li>Anthropic SDK</li></ul></div>
      <div class="skill-card reveal"><h3>⚛️ Frontend</h3><ul class="skill-list"><li>React.js &amp; Next.js</li><li>JavaScript (ES6+)</li><li>HTML5 &amp; CSS3</li><li>Tailwind CSS</li><li>Responsive Design</li><li>Performance Opt.</li></ul></div>
      <div class="skill-card reveal"><h3>⚙️ Backend</h3><ul class="skill-list"><li>Node.js &amp; Express</li><li>REST APIs</li><li>WebSockets</li><li>PostgreSQL</li><li>MongoDB</li><li>Auth &amp; Security</li></ul></div>
      <div class="skill-card reveal"><h3>🛠 Tools</h3><ul class="skill-list"><li>Git &amp; GitHub</li><li>VS Code</li><li>Agile / Scrum</li><li>Vite &amp; npm</li><li>Postman</li><li>Deployment</li></ul></div>
      <div class="skill-card reveal"><h3>🤝 Soft Skills</h3><ul class="skill-list"><li>Problem Solving</li><li>Client Communication</li><li>Sales &amp; Negotiation</li><li>Team Collaboration</li><li>Time Management</li><li>End-to-End Ownership</li></ul></div>
      <div class="skill-card reveal"><h3>🌐 Languages</h3><ul class="skill-list"><li>Arabic — Native</li><li>English — Advanced</li><li>Turkish — Beginner</li></ul></div>
      <div class="skill-card reveal"><h3>🛂 Passport</h3><ul class="skill-list"><li>Türkiye</li><li>Jordan</li></ul></div>
    </div>
  </div>
</section>

<!-- PROJECTS -->
<section id="projects">
  <div class="container">
    <div class="reveal">
      <div class="section-label">What I've built</div>
      <h2 class="section-title">Featured <span class="hl">Projects</span></h2>
    </div>
    <div class="projects-grid">
      <div class="proj-card reveal">
        <div class="proj-header"><div class="proj-num">01 — Featured</div><div class="proj-title">Dardeshly</div><div class="proj-subtitle">WhatsApp Marketing Platform</div></div>
        <div class="proj-body"><p class="proj-desc">Co-founded Dardeshly — an AI-powered WhatsApp marketing platform that sends personalized promotions to thousands of customers automatically. Built for restaurants, real estate agents, and e-commerce teams.</p>
        <div class="proj-tags"><span class="tag">Claude API</span><span class="tag">React.js</span><span class="tag">Node.js</span><span class="tag">LLM Pipelines</span><span class="tag">WhatsApp API</span></div>
        <a href="https://dardeshly.com" target="_blank" class="proj-link">Visit Platform →</a></div>
      </div>
      <div class="proj-card reveal">
        <div class="proj-header"><div class="proj-num">02 — AI</div><div class="proj-title">AI Integration Suite</div><div class="proj-subtitle">LLM-Powered Applications</div></div>
        <div class="proj-body"><p class="proj-desc">Multiple AI-powered applications built with prompt engineering, intelligent chatbots, and automation. Expertise in integrating Claude, GPT, and DeepSeek with custom business logic for reliable, on-brand responses.</p>
        <div class="proj-tags"><span class="tag">Prompt Eng.</span><span class="tag">RAG</span><span class="tag">Automation</span><span class="tag">Anthropic API</span></div>
        <a href="mailto:abdelalsalem09@gmail.com" class="proj-link">Get in touch →</a></div>
      </div>
      <div class="proj-card reveal">
        <div class="proj-header"><div class="proj-num">03 — Web</div><div class="proj-title">E-Commerce Platform</div><div class="proj-subtitle">Full-Stack Web App</div></div>
        <div class="proj-body"><p class="proj-desc">Developed responsive e-commerce product pages with dynamic JavaScript, cart management, and interactive shopping features. Focused on performance, cross-browser compatibility, and user experience.</p>
        <div class="proj-tags"><span class="tag">React</span><span class="tag">JavaScript</span><span class="tag">CSS3</span><span class="tag">Responsive</span></div>
        <a href="mailto:abdelalsalem09@gmail.com" class="proj-link">View Details →</a></div>
      </div>
    </div>
    <div class="stats-row reveal">
      <div class="stat-card"><div class="stat-num">3+</div><div class="stat-lbl">Years Experience</div></div>
      <div class="stat-card"><div class="stat-num">10+</div><div class="stat-lbl">Projects Shipped</div></div>
      <div class="stat-card"><div class="stat-num">1</div><div class="stat-lbl">Active Startup</div></div>
    </div>
  </div>
</section>

<!-- EXPERIENCE -->
<section id="experience">
  <div class="container">
    <div class="reveal">
      <div class="section-label">My journey</div>
      <h2 class="section-title">Work <span class="hl">Experience</span></h2>
    </div>
    <div class="exp-timeline reveal">
      <div class="exp-item">
        <div class="exp-dot"></div>
        <div class="exp-period">2026 — Present</div>
        <div class="exp-title-h">Co-Founder &amp; Software Engineer</div>
        <div class="exp-company">Dardeshly · dardeshly.com</div>
        <p class="exp-desc">Co-founded Dardeshly, an AI-powered WhatsApp marketing platform. Lead all product and engineering decisions from ideation to production deployment.</p>
        <ul class="exp-points">
          <li>Designed prompt pipelines for reliable, on-brand LLM responses</li>
          <li>Integrated Claude, GPT, DeepSeek, and Grok APIs</li>
          <li>Built full-stack platform with React.js frontend and Node.js backend</li>
          <li>Managed end-to-end product lifecycle including deployment</li>
        </ul>
      </div>
      <div class="exp-item">
        <div class="exp-dot"></div>
        <div class="exp-period">2025</div>
        <div class="exp-title-h">Real Estate Sales Consultant</div>
        <div class="exp-company">Real Estate Company · Istanbul</div>
        <p class="exp-desc">High-performance sales role advising clients on property investments, developing skills directly transferable to tech product work.</p>
        <ul class="exp-points">
          <li>Closed multiple property transactions through relationship building</li>
          <li>Developed client communication and negotiation expertise</li>
          <li>Learned to translate customer needs into clear requirements</li>
        </ul>
      </div>
      <div class="exp-item">
        <div class="exp-dot"></div>
        <div class="exp-period">Jun 2024 — Sep 2024</div>
        <div class="exp-title-h">Front-End Developer Intern</div>
        <div class="exp-company">Futeric · Amman, Jordan</div>
        <p class="exp-desc">Developed and maintained responsive web interfaces in a professional agile environment.</p>
        <ul class="exp-points">
          <li>Built responsive UIs with React.js</li>
          <li>Improved website performance and cross-browser compatibility</li>
          <li>Participated in Agile ceremonies and sprint reviews</li>
        </ul>
      </div>
    </div>
  </div>
</section>

<!-- CONTACT -->
<section id="contact">
  <div class="container">
    <div class="reveal" style="text-align:center">
      <div class="section-label" style="justify-content:center">Let's connect</div>
      <h2 class="section-title">Get In <span class="hl">Touch</span></h2>
    </div>
    <div class="contact-inner reveal">
      <p class="contact-lead">I'm always open to new projects, collaboration opportunities, and interesting conversations. Whether you want to build something together or just say hi — reach out!</p>
      <div class="contact-cards">
        <a href="mailto:abdelalsalem09@gmail.com" class="c-card"><span class="c-label">✉ Email</span><div class="c-val">abdelalsalem09@gmail.com</div></a>
        <a href="tel:+905521511094" class="c-card"><span class="c-label">📱 Phone</span><div class="c-val">+90 552 151 10 94</div></a>
      </div>
      <div class="contact-cta">
        <a href="mailto:abdelalsalem09@gmail.com" class="btn btn-primary" style="font-size:1rem;padding:1rem 2.5rem">✉ Send Me an Email</a>
      </div>
    </div>
  </div>
</section>

<footer>
  <div class="footer-inner">
    <p class="footer-copy">© 2026 <span>Abdelqader Al-Salem</span> · All rights reserved</p>
    <ul class="footer-nav">
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </div>
</footer>

<script>
document.querySelectorAll('a[href^="#"]').forEach(a=>{
  a.addEventListener('click',e=>{const t=document.querySelector(a.getAttribute('href'));if(t){e.preventDefault();t.scrollIntoView({behavior:'smooth'})}});
});
const obs=new IntersectionObserver(entries=>{entries.forEach(en=>{if(en.isIntersecting){en.target.classList.add('revealed');obs.unobserve(en.target)}})},{threshold:.1,rootMargin:'0px 0px -60px 0px'});
document.querySelectorAll('.reveal').forEach(el=>obs.observe(el));
const secs=document.querySelectorAll('section[id]');
const links=document.querySelectorAll('nav a');
window.addEventListener('scroll',()=>{let cur='';secs.forEach(s=>{if(window.scrollY>=s.offsetTop-120)cur=s.id});links.forEach(a=>{a.style.color=a.getAttribute('href')==='#'+cur?'var(--cyan)':''})});
</script>
</body>
</html>
