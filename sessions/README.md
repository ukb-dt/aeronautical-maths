```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Ukubona LLC: Aeronautics Math Internship</title>
  <meta name="color-scheme" content="dark light" />
  <meta name="theme-color" content="#0a0a0f" />
  <link rel="preconnect" href="https://fonts.googleapis.com" crossorigin>
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
    :root{
        --primary-gradient: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        --secondary-gradient: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
        --accent-blue: #667eea;
        --accent-purple: #764ba2;
   
        --dark-bg:#0a0a0f;
        --dark-surface:rgba(15,15,25,.8);
        --dark-glass:rgba(255,255,255,.05);
        --dark-border:rgba(255,255,255,.1);
        --dark-text:#ffffff;
        --dark-text-secondary:rgba(255,255,255,.7);
        --light-bg:#fafafa;
        --light-surface:rgba(255,255,255,.9);
        --light-glass:rgba(0,0,0,.02);
        --light-border:rgba(0,0,0,.08);
        --light-text:#1a1a1a;
        --light-text-secondary:rgba(0,0,0,.7);
        --blur: 20px;
        --radius: 16px;
        --shadow: 0 8px 32px rgba(0,0,0,.12);
        --transition: all .3s cubic-bezier(.4,0,.2,1);
        --header-h: 80px;
        --logo-size: 140px;
        --logo-spin-duration: 60s;
   
        /* Spacing scale */
        --space-xs: 0.5rem;
        --space-sm: 1rem;
        --space-md: 1.5rem;
        --space-lg: 2.5rem;
        --space-xl: 4rem;
        --space-2xl: 6rem;
    }
    [data-theme="light"]{
        --bg:var(--light-bg);
        --surface:var(--light-surface);
        --glass:var(--light-glass);
        --border:var(--light-border);
        --text:var(--light-text);
        --text-secondary:var(--light-text-secondary);
    }
    [data-theme="dark"]{
        --bg:var(--dark-bg);
        --surface:var(--dark-surface);
        --glass:var(--dark-glass);
        --border:var(--dark-border);
        --text:var(--dark-text);
        --text-secondary:var(--dark-text-secondary);
    }
    *{box-sizing:border-box; margin:0; padding:0;}
    html,body{height:100%}
    body{
        margin:0;
        font-family:'Inter',system-ui,-apple-system,Segoe UI,Roboto,Arial,sans-serif;
        background:var(--bg);
        color:var(--text);
        line-height:1.7;
        overflow-x:hidden;
        transition:var(--transition);
        font-size: 16px;
    }
    .wrap-max{
        max-width:900px;
        margin:0 auto;
        padding:0 var(--space-lg);
    }
    .bg-pattern{position:fixed;inset:0;z-index:-2;background:var(--bg)}
    .bg-pattern::before{
        content:''; position:absolute; inset:0;
        background:
        radial-gradient(circle at 20% 20%, rgba(102,126,234,.10) 0%, transparent 50%),
        radial-gradient(circle at 80% 80%, rgba(118,75,162,.10) 0%, transparent 50%),
        radial-gradient(circle at 40% 60%, rgba(240,147,251,.08) 0%, transparent 50%);
        animation:bgFloat 20s ease-in-out infinite;
    }
    @keyframes bgFloat{
        0%,100%{transform:translate(0,0) rotate(0deg)}
        33%{transform:translate(-20px,-20px) rotate(1deg)}
        66%{transform:translate(20px,-10px) rotate(-1deg)}
    }
    .scroll-indicator{position:fixed;top:0;left:0;width:100%;height:3px;z-index:1000;background:var(--glass)}
    .scroll-progress{height:100%;width:0%;background:var(--primary-gradient);transition:width .3s ease}
    /* HEADER */
    .header{
        position:fixed;top:0;left:0;width:100%;z-index:100;
        backdrop-filter: blur(var(--blur)); -webkit-backdrop-filter: blur(var(--blur));
        background:var(--surface); border-bottom:1px solid var(--border); min-height:var(--header-h);
    }
    .nav-container{height:var(--header-h); display:flex; align-items:center; justify-content:space-between}
    #logo.logo{
        width:var(--logo-size); height:var(--logo-size); object-fit:contain;
        transform-origin:center center; animation:spin var(--logo-spin-duration) linear infinite;
        display: block;
    }
    @keyframes spin{ to{ transform:rotate(360deg) } }
    .nav-links{display:flex;list-style:none;gap:2rem;margin:0;padding:0}
    .nav-link{
        color:var(--text-secondary);
        text-decoration:none;
        font-weight:500;
        transition:var(--transition);
        position:relative;
    }
    .nav-link::after{
        content:'';position:absolute;bottom:-4px;left:0;width:0;height:2px;
        background:var(--primary-gradient);transition:width .3s ease;
    }
    .nav-link:hover{color:var(--text)}
    .nav-link:hover::after{width:100%}
    .top-right{display:flex;align-items:center;gap:1rem}
    .menu-icon{
        display:grid;grid-template-columns:repeat(3,6px);gap:3px;padding:8px;
        background:var(--glass);border:1px solid var(--border);
        border-radius:8px;cursor:pointer;transition:var(--transition);
    }
    .menu-icon div{width:6px;height:6px;background:var(--text);border-radius:50%;transition:var(--transition)}
    .menu-icon:hover{background:var(--primary-gradient);transform:scale(1.05)}
    .menu-icon:hover div{background:white}
    #toggle-theme{
        padding:8px 12px;background:var(--glass);border:1px solid var(--border);
        border-radius:8px;cursor:pointer;font-size:16px;transition:var(--transition);
    }
    #toggle-theme:hover{background:var(--secondary-gradient);color:#fff;transform:scale(1.05)}
    .app-grid{
        position:fixed;top:calc(var(--header-h) + 8px);right:2rem;display:grid;grid-template-columns:repeat(3,1fr);
        gap:1rem;padding:1rem;background:var(--surface);backdrop-filter:blur(var(--blur));-webkit-backdrop-filter:blur(var(--blur));
        border:1px solid var(--border);border-radius:var(--radius);box-shadow:var(--shadow);
        opacity:0;visibility:hidden;transform:translateY(-10px) scale(.95);transition:var(--transition);min-width:300px;
        z-index: 1000;
       
        /* === THE FIX === */
        max-height: 80dvh; /* Takes ~80% of screen height */
        overflow-y: auto; /* Scroll inside the menu when needed */
        overscroll-behavior: contain; /* Don't let menu scroll affect page */
    }
    .app-grid.active{opacity:1;visibility:visible;transform:translateY(0) scale(1)}
    .app-grid a{
        display:flex;flex-direction:column;align-items:center;gap:.5rem;padding:1rem;text-decoration:none;color:var(--text);
        background:var(--glass);border:1px solid var(--border);border-radius:12px;transition:var(--transition);font-size:14px;font-weight:500;
    }
    .app-grid a:hover{background:var(--primary-gradient);color:#fff;transform:translateY(-2px);box-shadow:0 8px 25px rgba(102,126,234,.3)}
    .icon-box{font-size:24px;width:48px;height:48px;display:flex;align-items:center;justify-content:center;background:var(--glass);border-radius:12px;transition:var(--transition)}
    /* Nice subtle scrollbar for the app grid */
    .app-grid::-webkit-scrollbar {
        width: 8px;
    }
    .app-grid::-webkit-scrollbar-track {
        background: transparent;
    }
    .app-grid::-webkit-scrollbar-thumb {
        background: rgba(255,255,255,0.2);
        border-radius: 4px;
    }
    .app-grid::-webkit-scrollbar-thumb:hover {
        background: rgba(255,255,255,0.4);
    }
    /* MAIN CONTENT */
    .page{
        padding-top:calc(var(--header-h) + var(--space-xl));
        padding-bottom:var(--space-2xl);
    }
   
    .card{
        background:var(--surface);
        border:1px solid var(--border);
        border-radius:var(--radius);
        padding:var(--space-xl);
        margin:var(--space-xl) 0;
        box-shadow:var(--shadow);
    }
    /* Typography */
    .card h1{
        font-size:2.5rem;
        font-weight:800;
        margin-bottom:var(--space-lg);
        background:var(--primary-gradient);
        -webkit-background-clip:text;
        -webkit-text-fill-color:transparent;
        background-clip:text;
        letter-spacing:-0.02em;
    }
   
    .card h2{
        font-size:1.75rem;
        font-weight:700;
        margin-top:var(--space-lg);
        margin-bottom:var(--space-md);
        color:var(--text);
        border-left:4px solid var(--accent-blue);
        padding-left:var(--space-md);
    }
   
    .card h3{
        font-size:1.25rem;
        font-weight:600;
        margin-top:var(--space-md);
        margin-bottom:var(--space-sm);
        color:var(--accent-purple);
    }
   
    .card p{
        margin-bottom:var(--space-md);
        color:var(--text-secondary);
    }
   
    .card ul, .card ol{
        margin:var(--space-md) 0;
        padding-left:var(--space-lg);
    }
   
    .card li{
        margin-bottom:var(--space-xs);
        color:var(--text-secondary);
    }
   
    .card a{
        color:var(--accent-blue);
        text-decoration:none;
        border-bottom:1px solid transparent;
        transition:var(--transition);
    }
    .card a:hover{
        border-bottom-color:var(--accent-blue);
    }
   
    .card hr{
        border:none;
        height:1px;
        background:var(--border);
        margin:var(--space-lg) 0;
    }
   
    .card blockquote{
        border-left:4px solid var(--accent-purple);
        padding-left:var(--space-md);
        margin:var(--space-lg) 0;
        font-style:italic;
        color:var(--text-secondary);
    }
   
    .card pre{
        background:var(--glass);
        border:1px solid var(--border);
        border-radius:8px;
        padding:var(--space-md);
        overflow-x:auto;
        margin:var(--space-md) 0;
    }
   
    .card code{
        font-family:'SF Mono',Monaco,Consolas,monospace;
        font-size:0.9em;
        background:var(--glass);
        padding:2px 6px;
        border-radius:4px;
    }
    /* KPI badges */
    .kpis{display:flex;flex-wrap:wrap;gap:var(--space-xs);margin:var(--space-md) 0}
    .kpi{
        background:var(--primary-gradient);
        color:#fff;
        padding:6px 12px;
        border-radius:999px;
        font-size:0.875rem;
        font-weight:500;
    }
    /* Tables */
    table {
        width: 100%;
        border-collapse: collapse;
        margin: var(--space-lg) 0;
        border: 1px solid var(--border);
        border-radius:var(--radius);
        overflow:hidden;
        background:var(--glass);
    }
    th, td {
        border: 1px solid var(--border);
        padding: var(--space-md);
        text-align: left;
    }
    th {
        background: rgba(102,126,234,0.15);
        font-weight:600;
        color:var(--text);
    }
    td{
        color:var(--text-secondary);
    }
    table a {
        color: var(--accent-blue);
        text-decoration: none;
        border-bottom:1px solid transparent;
        transition:var(--transition);
    }
    table a:hover {
        border-bottom-color:var(--accent-blue);
    }
    /* Video container */
    .video-container{
        position:relative;
        width:100%;
        padding-bottom:56.25%;
        margin:var(--space-lg) 0;
        border-radius:var(--radius);
        overflow:hidden;
        background:var(--glass);
        border:1px solid var(--border);
    }
    .video-container iframe{
        position:absolute;
        top:0;left:0;
        width:100%;height:100%;
    }
    /* Details/accordion */
    details{
        border:1px dashed var(--border);
        border-radius:12px;
        padding:var(--space-md);
        margin:var(--space-md) 0;
        background:var(--glass);
    }
    details>summary{
        cursor:pointer;
        color:#97d7ff;
        font-weight:600;
        list-style:none;
        padding:var(--space-sm);
    }
    details[open]{
        border-style:solid;
        border-color:var(--accent-blue);
    }
    /* Grid layouts */
    .grid{display:grid;gap:var(--space-md)}
    .two{grid-template-columns:1fr 1fr}
   
    /* Image gallery */
    .image-gallery{
        display:flex;
        flex-wrap:wrap;
        gap:var(--space-md);
        justify-content:center;
        margin:var(--space-lg) 0;
    }
    .image-gallery img{
        flex:1 1 300px;
        max-width:30%;
        height:auto;
        object-fit:cover;
        border-radius:var(--radius);
        border:1px solid var(--border);
        transition:var(--transition);
    }
    .image-gallery img:hover{
        transform:translateY(-4px);
        box-shadow:0 12px 40px rgba(102,126,234,.3);
    }
    /* FOOTER */
    .footer{
        border-top:1px solid var(--border);
        margin-top:var(--space-2xl);
        padding:var(--space-xl) 0;
        text-align:center;
        color:var(--text-secondary);
    }
    .footer-chorus{
        margin-bottom:var(--space-md);
    }
    .footer .chip{
        display:inline-block;
        padding:8px 14px;
        border:1px solid var(--border);
        border-radius:9999px;
        margin:4px;
        background:var(--glass);
        font-size:0.9rem;
    }
    /* Responsive */
    @media (max-width:768px){
        .wrap-max{padding:0 var(--space-md)}
        .nav-links{display:none}
        .app-grid{
        right:1rem;left:1rem;
        grid-template-columns:repeat(2,1fr);
        min-width:auto;
       
        /* Same fix on mobile */
        max-height: 80dvh;
        overflow-y: auto;
        overscroll-behavior: contain;
        }
        #logo.logo { width: 100px; height: 100px; }
        .card{padding:var(--space-lg)}
        .card h1{font-size:2rem}
        .card h2{font-size:1.5rem}
        .two{grid-template-columns:1fr}
        .image-gallery img{max-width:100%}
        th, td{padding:var(--space-sm);font-size:0.9rem}
    }
   
    /* Force visibility */
    .card, table, th, td {
        opacity: 1 !important;
        visibility: visible !important;
    }
    </style>
  <script>
  window.MathJax = {
    tex: {
      inlineMath: [['$', '$'], ['\\(', '\\)']],
      displayMath: [['$$','$$'], ['\\[','\\]']],
      processEscapes: true
    },
    options: {
      skipHtmlTags: ['script','noscript','style','textarea','pre','code']
    }
  };
</script>
<script id="MathJax-script" async
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
</script>
</head>
<body>
  <div class="scroll-indicator"><div class="scroll-progress"></div></div>
  <div class="bg-pattern"></div>
  <header class="header">
    <div class="nav-container wrap-max">
      <img src="https://abikesa.github.io/logos/assets/ukubona-dark.png"
           alt="Ukubona LLC Logo"
           id="logo"
           class="logo" />
      <div class="top-right">
        <ul class="nav-links">
          <li><a href="/" class="nav-link" data-nav="home">Home</a></li>
        </ul>
        <button class="menu-icon" id="menuIcon" role="button" aria-label="Open navigation menu" aria-expanded="false">
          <div></div><div></div><div></div>
          <div></div><div></div><div></div>
          <div></div><div></div><div></div>
        </button>
        <button id="toggle-theme" aria-label="Toggle theme">🌙</button>
      </div>
    </div>
    <div class="app-grid wrap-max" id="gridMenu" aria-hidden="true">
      <a href="session1.html"><div class="icon-box">1️⃣</div>Session 1</a>
      <a href="session2.html"><div class="icon-box">2️⃣</div>Session 2</a>
      <a href="session3.html"><div class="icon-box">3️⃣</div>Session 3</a>
      <a href="session4.html"><div class="icon-box">4️⃣</div>Session 4</a>
      <a href="session5.html"><div class="icon-box">5️⃣</div>Session 5</a>
      <a href="session6.html"><div class="icon-box">6️⃣</div>Session 6</a>
      <a href="session7.html"><div class="icon-box">7️⃣</div>Session 7</a>
      <a href="session8.html"><div class="icon-box">8️⃣</div>Session 8</a>
      <a href="https://ukubona-llc.github.io"><div class="icon-box">📊</div>Ukubona Home</a>
    </div>
  </header>
  <main class="page wrap-max">
    <!-- Overview -->
    <section class="card">
      <h1>Aeronautics Math Internship</h1>
      <h2>Welcome</h2>
      <p>This 8-session program prepares you for aeronautical engineering by building a solid mathematics foundation through modeling and simulation. Each session is 30 minutes via Zoom, focusing on key concepts with Python code to "feel" the math. End with a capstone presentation.</p>
      <p>Goal: Excite about coding as a tool for math, applied to flight design. Math isn't abstract—it's for creation.</p>
      <p>Use the app grid to access each session's module.</p>
    </section>
    <!-- Captain's Notes -->
    <section class="card">
      <h2>Aeronautics Landscape</h2>
      <h3>Do</h3>
      <ul>
        <li><strong>Pilot (Flying)</strong>: Publicly available in Uganda</li>
        <li><strong>Maintenance Engineer (Aircraft maintenance)</strong>: Publicly available in Uganda (Soroti). No concepts developed. Only maintenance.</li>
      </ul>
      <h3>Create (Engineer Conception)</h3>
      <ul>
        <li><strong>Designer (Aeronautical Engineer)</strong>: Not available in Uganda. Options elsewhere: Australia, Brazil, Canada, China, Europe, US</li>
      </ul>
      <h3>Pilot</h3>
      <p>Not recommended by Captain</p>
      <h3>Maintenance</h3>
      <p>Not well-compensated (pay) in Uganda and abroad. Can study at Embry-Riddle Aeronautical University in Florida. Or can study mechanical engineering anywhere then pivot to aeronautical for further study</p>
      <h3>Designer</h3>
      <p>Very solid mathematics foundation: Internship in mathematical modeling (doesn't have to be at University). AI bootcamp courses available in Uganda from January. But any quick, cheap access to AI-supported training. Even Ukubona LLC can offer an internship (did so for Jonathan Gasaatura). Some physics. And chemistry as well.</p>
      <p>-- Captain Gad</p>
    </section>
    <!-- Critique -->
    <section class="card">
      <h2>Critique</h2>
      <p>Yes — a few grounded comments, both affirming and corrective. I’ll keep this practical and age-appropriate.</p>
      <h3>Big picture (the most important thing)</h3>
      <p>For a 17-year-old high school graduate, this set of notes is actually surprisingly mature. It avoids the most common mistake: confusing exposure with trajectory.</p>
      <p>The insider correctly separates:</p>
      <ul>
        <li>Doing (pilot, maintenance)</li>
        <li>Creating (engineer conception / design)</li>
      </ul>
      <p>That distinction alone puts this kid ahead of many first-year engineering students.</p>
      <h3>On the three paths</h3>
      <ol>
        <li><strong>Pilot</strong><br>The note “Not recommended by Captain” matters more than it looks. This likely reflects: High cost of flight hours. Narrow job funnel. Fragility to health, regulation, and market cycles. For a Ugandan context, pilot is a passion path, not a robust development path unless backed by strong resources. So: good to acknowledge, good not to push.</li>
        <li><strong>Maintenance (Aircraft Maintenance Engineer)</strong><br>The insider is blunt, and rightly so. Maintenance in Uganda = procedural competence, not conceptual growth. Even abroad, AME compensation often caps early unless one specializes heavily. It builds hands-on discipline, but not design authority. That said, for a 17-year-old, a short exposure to maintenance is not useless — it can: Build respect for systems. Ground later design intuition. Prevent “paper engineer syndrome”. The note correctly treats maintenance as a means, not an end.</li>
        <li><strong>Designer / Aeronautical Engineer (the real north star)</strong><br>This is the strongest part of the notes.<br>a) Not available in Uganda: True — and important to say early, so expectations don’t rot. Uganda currently offers: Operation, Maintenance, Training. But not: Aircraft systems design, Aerodynamic modeling pipelines, Certification-grade engineering environments. So the idea of preparing locally, then exporting talent is exactly right.<br>b) Mathematics as the core: This is the single best insight in the whole document. For aeronautical design: Math is the substrate. Physics rides on math. Software rides on math. AI rides on math. An internship in mathematical modeling — even informal, even scrappy — is far more valuable at 17 than anything with an airplane logo slapped on it.<br>c) AI as leverage (not hype): The notes handle AI soberly, which is rare. Not “AI instead of engineering”. But AI as acceleration of modeling, simulation, and intuition. Cheap AI-supported training in Uganda is a huge advantage right now: Python, Numerical methods, Optimization, Simulation thinking. This builds transferable cognitive tools, not credentials fluff.</li>
      </ol>
      <h3>On internships (what “internship” should mean here)</h3>
      <p>For a 17-year-old awaiting college, an internship should not mean: Corporate hierarchy, Formal titles, Long hours of clerical work. It should mean: Structured thinking, Exposure to abstraction, Producing artifacts (models, code, analyses). What matters is: Can he explain, six months later, how a system behaves under constraints? If yes — it worked.</p>
      <h3>One missing but important note</h3>
      <p>Writing and explanation skills. Aeronautical designers live or die by: Clear reasoning, Defensible assumptions, Communicating uncertainty. Encouraging him to write short technical notes, explain models in plain language, and diagram systems would round this out beautifully.</p>
      <h3>Final assessment</h3>
      <p>This plan is realistic, non-romantic, cognitively sound, and age-appropriate. Most importantly, it avoids locking a 17-year-old into a premature identity and instead invests in capability accumulation.</p>
      <p>-- GPT 5.1</p>
    </section>
  </main>
  <footer class="footer">
    <div class="wrap-max footer-wrap">
      <div class="footer-chorus" aria-label="Ukubona chorus">
        <span class="chip">"Ukubona" means</span>
        <span class="chip"><em>to see, to witness</em> —</span>
        <span class="chip">to look into the mirror.</span>
      </div>
      <div class="footer-extra" hidden></div>
      <div class="footer-footnote" aria-live="polite"></div>
      <div class="footer-micro" style="margin-top:12px">
        <p>© 2025 Ukubona LLC · <a href="/assets/files/ukubona.vcf" download>vCard</a> · Johns Hopkins Enterprise Vendor (June 2025)</p>
      </div>
    </div>
  </footer>
  <script>
    (function(){
      const doc=document, win=window, html=doc.documentElement;
      const $=(s,r=doc)=>r.querySelector(s);
      /* Scroll progress */
      const bar=$('.scroll-progress');
      function onScroll(){
        const d=doc.documentElement, max=d.scrollHeight-d.clientHeight;
        const pct=max>0?(d.scrollTop/max)*100:0;
        if(bar) bar.style.width=pct+'%';
      }
      win.addEventListener('scroll', onScroll, {passive:true}); onScroll();
      /* App grid toggle */
      const menu=$('#gridMenu'), btn=$('#menuIcon');
      function open(){ menu.classList.add('active'); menu.setAttribute('aria-hidden','false'); btn.setAttribute('aria-expanded','true'); }
      function close(){ menu.classList.remove('active'); menu.setAttribute('aria-hidden','true'); btn.setAttribute('aria-expanded','false'); }
      if(btn && menu){
        btn.addEventListener('click', e=>{ e.stopPropagation(); menu.classList.contains('active')?close():open(); });
        doc.addEventListener('click', e=>{ if(!menu.contains(e.target) && !btn.contains(e.target)) close(); });
        doc.addEventListener('keydown', e=>{ if(e.key==='Escape') close(); });
        menu.addEventListener('click', e=>{ const a=e.target.closest('a[href]'); if(a) close(); });
      }
      /* Theme toggle + logo swap */
      const LIGHT_LOGO='https://abikesa.github.io/logos/assets/ukubona-light.png';
      const DARK_LOGO ='https://abikesa.github.io/logos/assets/ukubona-dark.png';
      const logo=$('#logo');
      const toggleBtn=$('#toggle-theme');
      function setTheme(theme){
        html.setAttribute('data-theme', theme);
        try{ localStorage.setItem('theme', theme); }catch(_){}
        if(logo) logo.src=(theme==='dark')?DARK_LOGO:LIGHT_LOGO;
        if(toggleBtn) toggleBtn.textContent=(theme==='dark')?'🌙':'🌞';
      }
     
      // Initialize theme with better error handling
      function initTheme() {
        try {
          const saved = localStorage.getItem('theme');
          const prefersDark = window.matchMedia('(prefers-color-scheme: dark)').matches;
          return saved || (prefersDark ? 'dark' : 'light');
        } catch {
          return 'dark';
        }
      }
     
      setTheme(initTheme());
     
      if(toggleBtn){
        toggleBtn.addEventListener('click', ()=> {
          const currentTheme = html.getAttribute('data-theme');
          setTheme(currentTheme === 'dark' ? 'light' : 'dark');
        });
      }
     
      // Force visibility of critical elements (GH Pages fix)
      setTimeout(() => {
        const cards = document.querySelectorAll('.card');
        const tables = document.querySelectorAll('table');
        cards.forEach(card => card.style.opacity = '1');
        tables.forEach(table => table.style.visibility = 'visible');
      }, 100);
    })();
  </script>
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Same head as index.html, copy-paste the entire <head> section here for consistency -->
  <title>Ukubona LLC: Session 1 - Foundations</title>
  <!-- Include the style and scripts -->
</head>
<body>
  <!-- Same header as index.html, with app-grid linking back to index and other sessions -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 1: Foundations – Why Math Powers Design (Vectors & Basics)</h1>
      <h2>Discuss</h2>
      <p>Review Captain's notes—math as core for creation (not available in Uganda, so build it now). Tie to Jonathan: "He used math to uncover a 'hidden effect' in baseball; you'll do it for flight."</p>
      <h2>Code</h2>
      <pre><code>import numpy as np
import matplotlib.pyplot as plt

# Basic vectors for forces (thrust vs gravity)
thrust = np.array([100, 50])  # Tweak these!
gravity = np.array([0, -9.81])

# Plot
fig, ax = plt.subplots()
ax.quiver(0, 0, thrust[0], thrust[1], angles='xy', scale_units='xy', scale=1, color='b', label='Thrust')
ax.quiver(0, 0, gravity[0], gravity[1], angles='xy', scale_units='xy', scale=1, color='r', label='Gravity')
ax.set_xlim(-10, 110)
ax.set_ylim(-20, 60)
ax.set_xlabel('X Force')
ax.set_ylabel('Y Force')
ax.legend()
plt.title('Basic Aero Forces: Vectors')
plt.grid(True)
plt.show()</code></pre>
      <p>Onboard to dev env. Run this script plotting basic vectors (e.g., thrust vs. gravity). Tweak angles to see lift changes.</p>
      <h2>Excite</h2>
      <p>"See how changing one number makes the 'plane' climb? That's math designing reality."</p>
      <h2>Homework</h2>
      <p>Adjust script for different forces; commit to GitHub.</p>
      <h2>Math Focus</h2>
      <p>Vectors (direction/magnitude for aero forces).</p>
    </section>
  </main>
  <!-- Same footer -->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Copy head -->
  <title>Ukubona LLC: Session 2 - Rates of Change</title>
</head>
<body>
  <!-- Copy header -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 2: Rates of Change – Calculus in Motion</h1>
      <h2>Discuss</h2>
      <p>How calculus models acceleration (e.g., takeoff speed). "Pilots feel it; designers predict it."</p>
      <h2>Code</h2>
      <pre><code>import numpy as np
import matplotlib.pyplot as plt

t = np.linspace(0, 10, 100)
velocity = 10 * t - 0.5 * 9.81 * t**2  # Simple projectile velocity
accel = np.gradient(velocity, t)  # Derivative for acceleration

plt.plot(t, velocity, label='Velocity')
plt.plot(t, accel, label='Acceleration')
plt.xlabel('Time (s)')
plt.ylabel('Value (m/s or m/s²)')
plt.title('Rates of Change: Calculus in Flight')
plt.legend()
plt.grid(True)
plt.show()</code></pre>
      <p>Extend Session 1—use numpy to compute derivatives for velocity curves. Plot a simple parabolic flight path (like a thrown ball, bridging to baseball).</p>
      <h2>Excite</h2>
      <p>Animate the path with matplotlib—watch it "fly" on screen.</p>
      <h2>Homework</h2>
      <p>Add wind variable; observe path changes.</p>
    </section>
  </main>
  <!-- Footer -->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Copy head -->
  <title>Ukubona LLC: Session 3 - Systems Under Constraints</title>
</head>
<body>
  <!-- Copy header -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 3: Systems Under Constraints – Differential Equations Intro</h1>
      <h2>Discuss</h2>
      <p>Real flight involves equations for drag/gravity. "This is where AI helps simulate."</p>
      <h2>Code</h2>
      <pre><code>from scipy.integrate import odeint
import numpy as np
import matplotlib.pyplot as plt

def ode(y, t):
    return [y[1], -9.81]  # Position and velocity ODE

t = np.linspace(0, 10, 100)
sol = odeint(ode, [0, 50], t)  # Initial height 0, velocity 50 m/s

plt.plot(t, sol[:, 0], label='Height')
plt.xlabel('Time')
plt.ylabel('Height (m)')
plt.title('Basic ODE: Projectile Motion')
plt.legend()
plt.grid(True)
plt.show()</code></pre>
      <p>Use scipy.integrate to solve a basic ODE for projectile motion with air resistance.</p>
      <h2>Excite</h2>
      <p>"Tweak resistance—see how it shortens the flight? That's testing designs safely."</p>
      <h2>Homework</h2>
      <p>Model a "drone drop" scenario.</p>
    </section>
  </main>
  <!-- Footer -->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Copy head -->
  <title>Ukubona LLC: Session 4 - Optimization</title>
</head>
<body>
  <!-- Copy header -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 4: Optimization – Making Math Decide</h1>
      <h2>Discuss</h2>
      <p>Aero engineers optimize (e.g., best wing shape). Tie to Ukubona: "Like personalizing risk models."</p>
      <h2>Code</h2>
      <pre><code>from scipy.optimize import minimize_scalar
import numpy as np

def objective(angle):
    return -np.sin(angle)  # Maximize sine for range (simplified)

res = minimize_scalar(objective, bounds=(0, np.pi/2), method='bounded')
print(f'Optimal angle: {np.rad2deg(res.x):.2f} degrees')</code></pre>
      <p>Use scipy.optimize to find max range for a trajectory (e.g., ideal launch angle).</p>
      <h2>Excite</h2>
      <p>Run "what if" loops—graph how fuel changes affect distance.</p>
      <h2>Homework</h2>
      <p>Optimize for a constraint (e.g., max altitude under weight).</p>
    </section>
  </main>
  <!-- Footer -->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Copy head -->
  <title>Ukubona LLC: Session 5 - Matrices & Transformations</title>
</head>
<body>
  <!-- Copy header -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 5: Matrices & Transformations – Linear Algebra for Structures</h1>
      <h2>Discuss</h2>
      <p>Wings/forces as matrices (e.g., stress analysis). "Math for building unbreakable designs."</p>
      <h2>Code</h2>
      <pre><code>import numpy as np
import matplotlib.pyplot as plt

matrix = np.array([[0.5, -0.5], [0.5, 0.5]])  # Rotation matrix
vector = np.array([1, 0])
transformed = matrix @ vector

plt.quiver(0, 0, vector[0], vector[1], color='b', label='Original')
plt.quiver(0, 0, transformed[0], transformed[1], color='r', label='Transformed')
plt.xlim(-1, 1)
plt.ylim(-1, 1)
plt.legend()
plt.grid(True)
plt.title('Linear Algebra: Force Transformation')
plt.show()</code></pre>
      <p>Use numpy.linalg for simple transformations (e.g., rotate a force vector). Integrate into flight model.</p>
      <h2>Excite</h2>
      <p>Visualize 2D "wing stress" plot—color-code safe/unsafe zones.</p>
      <h2>Homework</h2>
      <p>Apply to a multi-force scenario.</p>
    </section>
  </main>
  <!-- Footer -->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Copy head -->
  <title>Ukubona LLC: Session 6 - Uncertainty & Stats</title>
</head>
<body>
  <!-- Copy header -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 6: Uncertainty & Stats – Probabilistic Thinking</h1>
      <h2>Discuss</h2>
      <p>Real aero has variability (wind, errors). "Designers communicate uncertainty—like in your capstone."</p>
      <h2>Code</h2>
      <pre><code>import numpy as np
import matplotlib.pyplot as plt

data = np.random.normal(0, 1, 1000)  # Simulated wind noise
plt.hist(data, bins=30)
plt.title('Uncertainty: Normal Distribution for Wind')
plt.xlabel('Value')
plt.ylabel('Frequency')
plt.grid(True)
plt.show()</code></pre>
      <p>Add random noise (numpy.random) to simulations; compute means/variances for reliability.</p>
      <h2>Excite</h2>
      <p>Run Monte Carlo sims—see distribution of landing spots. "This is gamified risk!"</p>
      <h2>Homework</h2>
      <p>Analyze limitations (e.g., "What if wind is extreme?").</p>
    </section>
  </main>
  <!-- Footer -->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Copy head -->
  <title>Ukubona LLC: Session 7 - Integration & Polish</title>
</head>
<body>
  <!-- Copy header -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 7: Integration & Polish – Building the Artifact</h1>
      <h2>Discuss</h2>
      <p>Pull it together—math as a system. Prep capstone structure (like Jonathan's: question/data/code/results).</p>
      <h2>Code</h2>
      <pre><code># Combine previous codes into a full script
# Example: User input for angle, output trajectory plot
import numpy as np
import matplotlib.pyplot as plt

angle = float(input('Enter angle (deg): '))
rad = np.deg2rad(angle)
t = np.linspace(0, 10, 100)
x = 100 * np.cos(rad) * t
y = 100 * np.sin(rad) * t - 0.5 * 9.81 * t**2
plt.plot(x, y)
plt.title('Full Trajectory')
plt.xlabel('Distance (m)')
plt.ylabel('Height (m)')
plt.grid(True)
plt.show()</code></pre>
      <p>Combine into a full script: User inputs (e.g., angle, speed), outputs plots/insights. Add comments for clarity.</p>
      <h2>Excite</h2>
      <p>"This is your 'digital twin' of a flight—test decisions without crashing."</p>
      <h2>Homework</h2>
      <p>Refine and document (e.g., write a short tech note on assumptions).</p>
    </section>
  </main>
  <!-- Footer -->
</body>
</html>
```

```html
<!DOCTYPE html>
<html lang="en" data-theme="dark">
<head>
  <!-- Copy head -->
  <title>Ukubona LLC: Session 8 - Review & Capstone Prep</title>
</head>
<body>
  <!-- Copy header -->
  <main class="page wrap-max">
    <section class="card">
      <h1>Session 8: Review & Capstone Prep – Explanation Skills</h1>
      <h2>Discuss</h2>
      <p>Critique progress (affirm growth, correct gaps). Emphasize writing/explaining (missing note from PDF).</p>
      <h2>Code</h2>
      <pre><code># Final model with comments
# Debug and add conclusion in comments
# Example from Session 7, with additions</code></pre>
      <p>Debug final model; add a "conclusion" section in code comments.</p>
      <h2>Excite</h2>
      <p>Demo his sim to mom in the Zoom—show buy-in.</p>
      <h2>Homework</h2>
      <p>Build presentation. Example title: "Math Takes Flight: Simulating Aero Designs."</p>
      <h3>Capstone Idea: "The Flight Design Effect"</h3>
      <p>Inspired by Jonathan's "Soto–Judge Effect": Model how "protection" factors (e.g., wind assistance vs. drag) affect a plane's performance. Use data from simple aero datasets. Output: Rolling average plots of efficiency, "what if" sims.</p>
      <p>Deliverable: Web/PPT with QR to GitHub repo. Sections: Question, Data, Code, Results, Conclusions.</p>
    </section>
  </main>
  <!-- Footer -->
</body>
</html>
```