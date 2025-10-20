<!doctype html>
<html lang="tr">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Atilla Taşdemir — Kişisel Sayfa</title>
  <meta name="description" content="Atilla Taşdemir — Yarı zamanlı geliştirici. Portfolyo, iletişim ve GitHub metrikleri." />
  <style>
    /* Reset */
    *{box-sizing:border-box;margin:0;padding:0}
    html,body,#app{height:100%}
    body{
      font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      color:#e6eef8;
      background:black;
      overflow-x:hidden;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
    }

    /* Canvas full-bleed for starfield */
    #starfield{position:fixed;inset:0;z-index:0}

    /* Glass card layout */
    .container{
      position:relative;
      z-index:2;
      max-width:980px;
      margin:48px auto;
      padding:28px;
      backdrop-filter: blur(6px) saturate(120%);
      background:linear-gradient(180deg, rgba(22,6,38,0.42), rgba(14,6,30,0.28));
      border-radius:16px;
      box-shadow:0 10px 30px rgba(6,2,20,0.6);
      border:1px solid rgba(255,255,255,0.04);
    }

    header{display:flex;align-items:center;gap:18px}
    header img.logo{height:76px}
    h1{font-size:28px;margin-bottom:6px}
    h3{font-size:15px;color:#c9d6f8;margin-top:0}

    .badges{margin-top:16px;display:flex;gap:10px;flex-wrap:wrap}

    .metrics{margin-top:18px;display:flex;flex-direction:column;gap:12px;align-items:center}
    .metrics img{max-width:100%;border-radius:12px;border:1px solid rgba(255,255,255,0.04)}

    section{margin-top:18px}

    /* contact */
    .contacts{display:flex;gap:12px;flex-wrap:wrap}

    /* tech row */
    .techs{display:flex;gap:10px;flex-wrap:wrap;margin-top:12px}

    /* footer */
    footer{margin-top:18px;text-align:center;font-size:13px;color:#c9d6f8}

    /* subtle floating animation for content */
    @keyframes floaty{0%{transform:translateY(0)}50%{transform:translateY(-6px)}100%{transform:translateY(0)}}
    .container{animation:floaty 10s ease-in-out infinite}

    /* Responsive */
    @media (max-width:640px){
      .container{margin:18px;padding:18px}
      header img.logo{height:56px}
    }

    /* CTA buttons */
    .btn{display:inline-flex;align-items:center;gap:8px;padding:8px 12px;border-radius:10px;background:linear-gradient(90deg, rgba(120,69,200,0.18), rgba(90,40,180,0.12));border:1px solid rgba(255,255,255,0.04);color:inherit;text-decoration:none}

    /* small helper */
    .row{display:flex;gap:12px;align-items:center}
  </style>
</head>
<body>
  <canvas id="starfield"></canvas>

  <main id="app">
    <div class="container">
      <header>
        <img class="logo" src="https://raw.githubusercontent.com/AtillaTasdemir/AtillaTasdemir/main/header.svg" alt="Header Banner" />
        <div>
          <h1>Selam, ben Atilla Taşdemir 👋</h1>
          <h3>Yarı zamanlı olarak kod yazıyor ve kendimi sürekli geliştiriyorum.</h3>
          <div class="badges">
            <a href="mailto:atilla12339@outlook.com" target="_blank" rel="noreferrer" class="btn">
              <img src="https://img.shields.io/badge/Microsoft_Outlook-0078D4?style=for-the-badge&logo=microsoft-outlook&logoColor=white" alt="outlook" style="height:28px">
            </a>
            <a href="https://www.instagram.com/hadesdenost/" target="_blank" rel="noreferrer" class="btn">
              <img src="https://img.shields.io/badge/Instagram-%23E4405F.svg?style=for-the-badge&logo=Instagram&logoColor=white" alt="instagram" style="height:28px">
            </a>
          </div>
        </div>
      </header>

      <section class="techs">
        <a href="https://www.python.org" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54" alt="python" /></a>
        <a href="https://www.php.net" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/php-%23777BB4.svg?style=for-the-badge&logo=php&logoColor=white" alt="php" /></a>
        <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white" alt="html5" /></a>
        <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"><img src="https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white" alt="css3" /></a>
      </section>

      <section class="metrics">
        <h4 style="margin:0;color:#dbe8ff">📊 GitHub Metriklerim</h4>
        <img src="https://metrics.lecoq.io/AtillaTasdemir?template=classic&config_timezone=Europe/Istanbul&theme=tokyonight" alt="GitHub Metrics" />
      </section>

      <section style="margin-top:18px">
        <p style="color:#c9d6f8">Kısa özet: Bu sayfa tek dosyalık, morumsu uzay temasına sahip, kayan yıldız efektli ve GitHub metrik görselini gösteriyor. GitHub Pages veya local olarak çalışır.</p>
        <div style="margin-top:12px" class="row">
          <a class="btn" href="https://github.com/AtillaTasdemir" target="_blank" rel="noreferrer">GitHub Profilime Git</a>
          <a class="btn" href="#" onclick="downloadHTML()">README Olarak İndir</a>
        </div>
      </section>

      <footer>
        © <span id="year"></span> Atilla Taşdemir — Hazır sayfa (tek dosya). İstediğin değişiklikleri yaparım.
      </footer>
    </div>
  </main>

  <script>
    // set year
    document.getElementById('year').textContent = new Date().getFullYear();

    // Download the current HTML as a file (client-side)
    function downloadHTML(){
      const html = '<!doctype html>\n' + document.documentElement.outerHTML;
      const blob = new Blob([html], {type:'text/html'});
      const url = URL.createObjectURL(blob);
      const a = document.createElement('a');
      a.href = url;
      a.download = 'index.html';
      document.body.appendChild(a);
      a.click();
      a.remove();
      URL.revokeObjectURL(url);
    }

    /* -----------------------------
       Starfield canvas (fast, lightweight)
       - purple gradient background drawn behind canvas via clearRect + globalComposite.
       - particles drift left to right and slowly fall to create 'akıyor' hissi.
       ------------------------------*/
    const canvas = document.getElementById('starfield');
    const ctx = canvas.getContext('2d');
    let W = canvas.width = innerWidth;
    let H = canvas.height = innerHeight;

    window.addEventListener('resize', ()=>{ W = canvas.width = innerWidth; H = canvas.height = innerHeight; initStars() });

    const TAU = Math.PI*2;
    const COLORS = ['#c89bff','#a07bff','#7fa0ff','#d6b3ff'];

    let stars = [];
    const STAR_COUNT = Math.round((window.innerWidth*window.innerHeight)/50000) + 120; // density scale

    function rand(min,max){return Math.random()*(max-min)+min}

    function initStars(){
      stars = [];
      const scale = Math.max(1, window.devicePixelRatio || 1);
      for(let i=0;i<STAR_COUNT;i++){
        const r = rand(0.6,2.8);
        stars.push({
          x:rand(-W*0.2,W*1.2),
          y:rand(-H*0.2,H*1.2),
          z:rand(0.4,1),
          r:r,
          a:rand(0.2,1),
          vx:rand( -0.2, -0.6 ) * (Math.random()>0.5?1: -1),
          vy:rand(0.02,0.4),
          color:COLORS[Math.floor(rand(0,COLORS.length))]
        })
      }
    }

    function drawGradient(){
      const g = ctx.createLinearGradient(0,0,0,H);
      g.addColorStop(0,'#12021f');
      g.addColorStop(0.2,'#2a0636');
      g.addColorStop(0.5,'#3b0f46');
      g.addColorStop(1,'#0e0614');
      ctx.fillStyle = g;
      ctx.fillRect(0,0,W,H);

      // subtle moving light streak
      const lg = ctx.createLinearGradient(0,0,W,H);
      lg.addColorStop(0,'rgba(120,60,200,0.03)');
      lg.addColorStop(0.5,'rgba(190,120,255,0.03)');
      lg.addColorStop(1,'rgba(30,10,40,0.03)');
      ctx.fillStyle = lg; ctx.fillRect(0,0,W,H);
    }

    let t = 0;
    function frame(){
      t += 0.012;
      drawGradient();

      // draw streaks moving across (long thin particles) to give 'flow' feel
      for(let i=0;i<stars.length;i++){
        const s = stars[i];
        s.x += s.vx * (1 + Math.sin(t*0.6 + i) * 0.4) * (1/s.z);
        s.y += s.vy * (1 + Math.cos(t*0.4 + i) * 0.4) * (1/s.z);

        // wrap around edges
        if(s.x < -W*0.25) s.x = W + rand(0,W*0.2);
        if(s.x > W + W*0.25) s.x = -rand(0,W*0.2);
        if(s.y > H + H*0.25) s.y = -rand(0,H*0.2);
        if(s.y < -H*0.25) s.y = H + rand(0,H*0.2);

        // draw glow
        const rad = s.r * (1 + (1-s.z)*1.8);
        ctx.beginPath();
        const g = ctx.createRadialGradient(s.x,s.y,0,s.x,s.y,rad*5);
        g.addColorStop(0, hexToRgba(s.color, s.a));
        g.addColorStop(0.35, hexToRgba(s.color, s.a*0.4));
        g.addColorStop(1, 'rgba(0,0,0,0)');
        ctx.fillStyle = g;
        ctx.arc(s.x,s.y,rad*4,0,TAU);
        ctx.fill();

        // small bright core
        ctx.beginPath();
        ctx.fillStyle = hexToRgba('#ffffff', Math.min(0.9, s.a+0.2));
        ctx.arc(s.x,s.y,rad*0.5,0,TAU);
        ctx.fill();
      }

      // soft flow overlay (transparent lines)
      ctx.globalCompositeOperation = 'lighter';
      for(let i=0;i<6;i++){
        ctx.beginPath();
        ctx.moveTo(0, (H/6)*i + (Math.sin(t*0.8 + i)*40));
        ctx.bezierCurveTo(W*0.25,(H/6)*i + 40, W*0.75,(H/6)*i - 40, W, (H/6)*i + (Math.cos(t*0.6+i)*40));
        ctx.lineWidth = 1.2;
        ctx.strokeStyle = 'rgba(160,100,255,0.02)';
        ctx.stroke();
      }
      ctx.globalCompositeOperation = 'source-over';

      requestAnimationFrame(frame);
    }

    function hexToRgba(h, a){
      // accepts #rrggbb
      const r = parseInt(h.slice(1,3),16);
      const g = parseInt(h.slice(3,5),16);
      const b = parseInt(h.slice(5,7),16);
      return `rgba(${r},${g},${b},${a})`;
    }

    initStars();
    frame();

    // re-init when page becomes visible (fix some mobile throttling edgecases)
    document.addEventListener('visibilitychange', ()=>{ if(!document.hidden) initStars(); });
  </script>
</body>
</html>
