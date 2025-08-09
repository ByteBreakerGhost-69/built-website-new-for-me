      <!DOCTYPE html>
      <html lang="id">
      <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width,initial-scale=1" />
        <title>Maulana Y. A. A. Yudho — Portfolio</title>
        <meta name="description" content="Portofolio Maulana Yasyfa'u Al Azhiim — Web Developer & Ethical Hacker" />
        <!-- Tailwind CDN -->
        <script src="https://cdn.tailwindcss.com"></script>
        <!-- Fonts -->
        <link href="https://fonts.googleapis.com/css2?family=Fira+Code:wght@300;400;600&family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
      
        <style>
          :root{
            --dark:#0b0b0d;
            --dark-blue:#0f3a5a;
            --neon:#4A90E2;
            --accent-red:#E24A4A;
            --muted:rgba(255,255,255,0.06);
            --glass: rgba(255,255,255,0.04);
          }
      
          /* Base */
          html,body{height:100%}
          body{
            margin:0;
            font-family: 'Poppins', system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
            background: linear-gradient(180deg, #06060a 0%, #0b0b0d 100%);
            color: #E6EEF8;
            overflow:hidden; /* disable until splash done */
            -webkit-font-smoothing:antialiased;
            -moz-osx-font-smoothing:grayscale;
          }
      
          /* ---------- SPLASH ---------- */
          .splash-screen{
            position:fixed;
            inset:0;
            display:flex;
            align-items:center;
            justify-content:center;
            z-index:9999;
            background: radial-gradient( circle at 20% 20%, rgba(74,144,226,0.12), transparent 15%),
                        linear-gradient(135deg, var(--dark-blue) 0%, #04040a 100%);
            gap:2rem;
            padding:2rem;
            flex-direction:column;
            transition:opacity .9s ease, transform .9s ease;
          }
          .splash-inner{
            display:flex;
            gap:1.5rem;
            align-items:center;
            justify-content:center;
            flex-direction:column;
            text-align:center;
          }
          .splash-logo {
            display:flex;
            align-items:center;
            gap:1rem;
          }
          .splash-logo img{width:72px;height:72px;border-radius:14px; box-shadow:0 10px 30px rgba(0,0,0,0.6); transform:translateY(0); animation:logoBounce 2.4s infinite;}
          @keyframes logoBounce {0%{transform:translateY(0)}50%{transform:translateY(-8px)}100%{transform:translateY(0)}}
      
          .splash-name{
            font-family:'Fira Code', monospace;
            font-size:1.55rem;
            letter-spacing:0.6px;
            color: #fff;
            text-shadow: 0 6px 18px rgba(74,144,226,0.12), 0 0 8px rgba(74,144,226,0.06);
          }
      
          .typing-small { font-family: 'Poppins'; font-weight:600; margin-top:.5rem; display:inline-block; }
          #typing-text{display:inline-block; min-width:220px; font-weight:600; letter-spacing:0.2px;}
          .cursor{display:inline-block; width:2px; height:1.1em; background:var(--neon); margin-left:8px; animation:blink 1s step-end infinite;}
          @keyframes blink {50%{opacity:0}}
      
          .loading-bar{width:260px; height:6px; background:rgba(255,255,255,0.06); border-radius:6px; margin-top:16px; overflow:hidden;}
          .loading-progress{height:100%; background:linear-gradient(90deg,var(--neon),var(--accent-red)); width:0; animation:progressAnim 3.6s ease forwards;}
          @keyframes progressAnim { to { width:100% } }
      
          /* ---------- STARS + PARTICLES ---------- */
          .stars{position:fixed; inset:0; z-index:0; pointer-events:none; overflow:hidden}
          .star{position:absolute; background:rgba(255,255,255,0.9); border-radius:50%; opacity:var(--opacity,0.6); transform:translateZ(0); box-shadow:0 0 8px rgba(74,144,226,0.06)}
          canvas#sparks{position:fixed; inset:0; pointer-events:none; z-index:1; mix-blend-mode:screen}
      
          /* ---------- NAVBAR ---------- */
          nav.navbar{
            position:fixed; top:0; left:0; right:0; z-index:60;
            backdrop-filter: blur(6px); -webkit-backdrop-filter: blur(6px);
            background: linear-gradient(180deg, rgba(6,6,8,0.25), rgba(6,6,8,0.12));
            border-bottom:1px solid rgba(255,255,255,0.03);
            transition: all .3s ease;
          }
          nav.navbar.scrolled{
            background: linear-gradient(180deg, rgba(0,0,0,0.7), rgba(4,4,6,0.55));
            transform: translateY(0);
            box-shadow: 0 8px 30px rgba(2,6,23,0.6);
          }
          nav .brand{font-family:'Fira Code'; letter-spacing:0.6px; font-weight:700; color:#fff}
          nav a{color: #cfe7ff; transition: all .18s ease}
          nav a:hover{color:var(--neon)}
      
          /* ---------- HERO ---------- */
          .hero{
            min-height:calc(100vh - 72px);
            display:flex; align-items:center; justify-content:center; padding-top:72px;
            position:relative; z-index:10;
            background: linear-gradient(180deg, rgba(11,20,30,0.18), transparent 40%);
          }
          .hero-card{
            max-width:1200px; margin:0 auto; display:flex; gap:2rem; align-items:center; padding:2.2rem;
            background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
            border-radius:18px; border:1px solid rgba(74,144,226,0.06);
            box-shadow: 0 20px 60px rgba(2,6,23,0.7);
          }
          .hero-left h1{font-size:2.4rem; font-weight:800; line-height:1.02; font-family:'Fira Code';}
          .rotating-text{display:inline-block; font-family:'Fira Code'; color:var(--neon); font-weight:700}
      
          /* neon button */
          .btn-neon{
            background:linear-gradient(90deg,var(--neon), rgba(74,144,226,0.18));
            color: #001019; font-weight:700; padding:.7rem 1.1rem; border-radius:999px;
            box-shadow: 0 6px 28px rgba(74,144,226,0.12), 0 0 18px rgba(74,144,226,0.06);
            transition: transform .18s ease, box-shadow .18s ease;
          }
          .btn-neon:hover{ transform: translateY(-4px) scale(1.02); box-shadow: 0 18px 50px rgba(74,144,226,0.2); }
      
          /* floating portrait */
          .portrait{width:320px; border-radius:12px; overflow:hidden; border:2px solid rgba(74,144,226,0.12); box-shadow: 0 10px 30px rgba(0,0,0,0.6)}
          .portrait .tag{position:absolute; right:1rem; bottom:1rem; background:var(--neon); color:#000; padding:.45rem .75rem; border-radius:999px; font-weight:700; font-size:.8rem; box-shadow:0 10px 40px rgba(74,144,226,0.06)}
      
          /* ---------- SECTIONS ---------- */
          section{padding:4rem 0}
          .container{max-width:1200px; margin:0 auto; padding:0 1rem;}
      
          /* cards, hover effects, tilt */
          .card{
            background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
            border:1px solid rgba(255,255,255,0.03);
            padding:1.25rem; border-radius:12px; transition: transform .28s cubic-bezier(.2,.9,.2,1), box-shadow .28s;
            transform-style:preserve-3d;
          }
          .card:hover{ transform: translateY(-10px); box-shadow: 0 20px 60px rgba(2,6,23,0.7) }
      
          .glow-border{
            position:relative;
            overflow:hidden;
          }
          .glow-border::after{
            content:""; position:absolute; inset:0; pointer-events:none; border-radius:12px;
            box-shadow: 0 0 40px rgba(74,144,226,0.09), inset 0 0 18px rgba(74,144,226,0.02);
            opacity:0; transition: opacity .28s ease;
          }
          .glow-border:hover::after{ opacity:1 }
      
          /* skill bars */
          .skill-bar{height:8px; background:rgba(255,255,255,0.04); border-radius:999px; overflow:hidden}
          .skill-progress{height:100%; width:0; background:linear-gradient(90deg,var(--neon),var(--accent-red)); border-radius:999px; transition: width 1.8s cubic-bezier(.2,.9,.2,1)}
      
          /* tools slider */
          .tools-slider { overflow:hidden; position:relative }
          .tools-track { display:flex; gap:1rem; will-change:transform; align-items:center }
          .tool-item{ min-width:120px; padding:1rem; border-radius:12px; text-align:center; background:rgba(255,255,255,0.02); border:1px solid rgba(74,144,226,0.06); transition: transform .18s ease }
          .tool-item:hover{ transform: translateY(-6px) scale(1.04) }
      
          /* fade-in on scroll */
          .reveal{opacity:0; transform: translateY(18px); transition: all 0.8s cubic-bezier(.2,.9,.2,1) }
          .reveal.visible{opacity:1; transform: translateY(0) }
      
          /* responsive */
          @media (max-width: 960px){
            .hero-card{flex-direction:column; padding:1.4rem}
            .portrait{width:260px}
          }
      
        </style>
      </head>
      <body>
      
        <!-- STARS & PARTICLES -->
        <div class="stars" id="stars-container"></div>
        <canvas id="sparks"></canvas>
      
        <!-- SPLASH -->
        <div class="splash-screen" id="splashScreen" aria-hidden="false">
          <div class="splash-inner">
            <div class="splash-logo">
              <img src="https://i.postimg.cc/X7sGDfhG/Chat-GPT-Image-9-Agu-2025-18-30-40.png" alt="Logo">
              <div>
                <div class="splash-name">Maulana Yasyfa'u Al Azhiim</div>
                <div class="typing-small"><span id="typing-text"></span><span class="cursor" id="typing-cursor"></span></div>
              </div>
            </div>
      
            <div class="loading-bar" aria-hidden="true">
              <div class="loading-progress"></div>
            </div>
            <div style="margin-top:14px;color:rgba(255,255,255,0.6);font-size:.9rem">Web Developer &amp; Ethical Hacker</div>
          </div>
        </div>
      
        <!-- NAVBAR -->
        <nav class="navbar">
          <div class="container flex items-center justify-between py-4">
            <a href="#" class="brand text-white text-xl">my website</a>
            <div class="hidden md:flex items-center gap-8 text-sm">
              <a href="#home" class="hover:underline">Home</a>
              <a href="#about" class="hover:underline">Tentang</a>
              <a href="#skills" class="hover:underline">Keahlian</a>
              <a href="#portfolio" class="hover:underline">Portofolio</a>
              <a href="#contact" class="hover:underline">Kontak</a>
            </div>
      
            <button id="mobileBtn" class="md:hidden p-2 rounded bg-transparent text-white">
              <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
            </button>
          </div>
          <!-- mobile menu -->
          <div id="mobileMenu" class="hidden md:hidden px-6 pb-4">
            <a href="#home" class="block py-2">Home</a>
            <a href="#about" class="block py-2">Tentang</a>
            <a href="#skills" class="block py-2">Keahlian</a>
            <a href="#portfolio" class="block py-2">Portofolio</a>
            <a href="#contact" class="block py-2">Kontak</a>
          </div>
        </nav>
      
        <!-- MAIN CONTENT -->
        <main class="main-content" style="display:none; position:relative; z-index:5;">
      
          <!-- HERO -->
          <header id="home" class="hero">
            <div class="hero-card container reveal" >
              <div class="hero-left md:w-1/2">
                <h1 class="mb-4">Maulana Yasyfa'u Al Azhiim <br/><span style="font-size:1.1rem;color:rgba(255,255,255,0.7); font-weight:600">Web Developer & Ethical Hacker</span></h1>
      
                <p class="mb-6" style="max-width:56ch; color:rgba(230,238,248,0.85)">Saya membangun website modern dan sistem keamanan siber dengan dasar etika profesional. Saya suka membuat solusi yang cepat, aman, dan estetis.</p>
      
                <div class="mb-6">
                  <span class="rotating-text" id="rotatingText">Web Developer</span>
                  <span class="text-sm ml-3 text-gray-300">•</span>
                  <span class="text-sm ml-3 text-gray-400" id="typing-role">Ethical Hacker</span>
                </div>
      
                <div class="flex gap-4">
                  <a class="btn-neon" href="#contact">Hubungi Saya</a>
                  <a class="card glow-border" href="#portfolio">Lihat Portofolio</a>
                </div>
              </div>
      
              <div class="md:w-1/2 flex justify-center relative">
                <div class="portrait floating" style="position:relative;">
                  <img src="https://placehold.co/400x480" alt="Potret Maulana" class="w-full h-full object-cover">
                  <div class="tag">Web & Security Expert</div>
                </div>
              </div>
            </div>
          </header>
      
          <!-- ABOUT -->
          <section id="about" class="bg-black/40">
            <div class="container">
              <h2 class="text-3xl font-bold text-center mb-8 reveal">Tentang Saya</h2>
              <div class="flex flex-col md:flex-row gap-8 items-center">
                <div class="md:w-1/3 flex justify-center reveal">
                  <img src="https://placehold.co/300x300" alt="Foto" class="rounded-full border-4 border-blue-400 w-64 h-64 object-cover">
                </div>
                <div class="md:w-2/3 reveal">
                  <h3 class="text-2xl font-bold mb-4 text-blue-400">Profil Profesional</h3>
                  <p class="mb-4 text-gray-300">Saya adalah seorang profesional ... (ringkasan singkatmu di sini).</p>
      
                  <div class="grid grid-cols-1 md:grid-cols-2 gap-4 mb-6">
                    <div class="card card-tilt glow-border">
                      <h4 class="font-bold">SMA Islam Plus Hidayatut Thullab</h4>
                      <p class="text-gray-300 text-sm">Fokus pada matematika & teknologi</p>
                    </div>
                    <div class="card card-tilt glow-border">
                      <h4 class="font-bold">SMP Islam Plus Hidayatut Thullab</h4>
                      <p class="text-gray-300 text-sm">Dasar pendidikan teknologi</p>
                    </div>
                  </div>
      
                  <div class="card bg-dark-blue p-6">
                    <h4 class="font-bold text-blue-300">Filosofi Kerja</h4>
                    <p class="italic text-gray-200">""Dalam setiap kode yang saya tulis dan setiap sistem yang saya amankan, saya selalu berusaha untuk menyertakan nilai-nilai kejujuran, etika profesional, dan komitmen untuk memberikan yang terbaik."</p>
                  </div>
                </div>
              </div>
            </div>
          </section>
      
          <!-- SKILLS -->
          <section id="skills" class="pt-12">
            <div class="container">
              <h2 class="text-3xl font-bold text-center mb-8 reveal">Keahlian</h2>
      
              <div class="grid grid-cols-1 md:grid-cols-2 gap-8">
                <div class="card reveal">
                  <div class="flex items-center gap-4 mb-4">
                    <div class="bg-blue-500 p-3 rounded-full"><svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10 20l4-16"></path></svg></div>
                    <h3 class="text-xl font-bold text-blue-400">Web Development</h3>
                  </div>
      
                  <div class="space-y-4">
                    <div>
                      <p class="mb-1 text-sm">HTML</p>
                      <div class="skill-bar"><div class="skill-progress" data-progress="95%"></div></div>
                    </div>
                    <div>
                      <p class="mb-1 text-sm">CSS</p>
                      <div class="skill-bar"><div class="skill-progress" data-progress="85%"></div></div>
                    </div>
                    <div>
                      <p class="mb-1 text-sm">JavaScript</p>
                      <div class="skill-bar"><div class="skill-progress" data-progress="90%"></div></div>
                    </div>
                  </div>
                </div>
      
                <div class="card reveal">
                  <div class="flex items-center gap-4 mb-4">
                    <div class="bg-blue-500 p-3 rounded-full"><svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 15v2m-6 4h12"></path></svg></div>
                    <h3 class="text-xl font-bold text-blue-400">Ethical Hacking</h3>
                  </div>
      
                  <div class="space-y-4">
                    <div>
                      <p class="mb-1 text-sm">Penetration Testing</p>
                      <div class="skill-bar"><div class="skill-progress" data-progress="90%"></div></div>
                    </div>
                    <div>
                      <p class="mb-1 text-sm">Network Security</p>
                      <div class="skill-bar"><div class="skill-progress" data-progress="88%"></div></div>
                    </div>
                  </div>
                </div>
              </div>
      
              <!-- Tools slider -->
              <div class="mt-10 reveal">
                <h4 class="font-bold mb-4">Tools & Technologies</h4>
                <div class="tools-slider">
                  <div class="tools-track" id="toolsTrack">
                    <!-- Duplicate the row twice to enable smooth loop -->
                    <div class="flex gap-4 items-center">
                      <!-- icons simplified -->
                      <div class="tool-item"><img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">HTML</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/DzzY55Gp/download-css.png" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">CSS</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/nLcc2808/images-javascript.png" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">JS</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/rm46CQXX/images.png" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">Kali</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/qMyRMxzF/images-commix.png" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">commix</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/J4f1fDxQ/images-sqlmap.png" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">sqlmap</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/Ghk2jfHc/XR0u-Nrj3-400x400.jpg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">hashcat</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/DZHZCkrz/Ghidra-logo-svg.png" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">ghidra</div></div>
                    </div>
      
                    <!-- copy for looping -->
                    <div class="flex gap-4 items-center">
                      <div class="tool-item"><img src="https://i.postimg.cc/P5w42cVq/0-Fp841-N-400x400-blackarch-linux.jpg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">BlackArch Linux</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/MGG1gFdR/imagesnmap.jpg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">Nmap</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/x1wsQYNH/images-msfconsole.png" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">Metasploit</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/4NtP1qSx/images-brup-suite.jpg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">Burp Suite</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/7Yw2M5Ff/st-small-507x507-pad-600x600-f8f8f8-u4.jpg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">wireshark</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/tC0JWbRS/images.jpg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">theHarvester</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/g0MrZ6r8/image3-1.webp" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">SET</div></div>
                      <div class="tool-item"><img src="https://i.postimg.cc/4xgKkgr7/image-750x-6235ddcb6adaf.jpg" class="mx-auto w-10 h-10"><div class="mt-2 text-xs">bettercap</div></div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </section>
      
          <!-- PORTFOLIO -->
          <section id="portfolio" class="bg-black/20">
            <div class="container">
              <h2 class="text-3xl font-bold text-center mb-8 reveal">Portofolio</h2>
      
              <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
                <div class="card card-tilt reveal glow-border">
                  <div class="relative overflow-hidden rounded-lg">
                    <img src="https://placehold.co/600x400" alt="Project" class="w-full h-44 object-cover">
                    <div class="absolute top-2 right-2 bg-blue-500 text-white px-2 py-1 rounded text-sm">Web</div>
                  </div>
                  <div class="mt-4">
                    <h3 class="font-bold">Sistem E-Commerce</h3>
                    <p class="text-gray-300 text-sm">Platform e-commerce dengan admin dashboard.</p>
                  </div>
                </div>
      
                <div class="card card-tilt reveal glow-border">
                  <div class="relative overflow-hidden rounded-lg">
                    <img src="https://placehold.co/600x400" alt="Project" class="w-full h-44 object-cover">
                    <div class="absolute top-2 right-2 bg-red-500 text-white px-2 py-1 rounded text-sm">Security</div>
                  </div>
                  <div class="mt-4">
                    <h3 class="font-bold">Security Monitoring System</h3>
                    <p class="text-gray-300 text-sm">Sistem monitoring real-time & alert.</p>
                  </div>
                </div>
      
                <div class="card card-tilt reveal glow-border">
                  <div class="relative overflow-hidden rounded-lg">
                    <img src="https://placehold.co/600x400" alt="Project" class="w-full h-44 object-cover">
                    <div class="absolute top-2 right-2 bg-blue-500 text-white px-2 py-1 rounded text-sm">Mobile</div>
                  </div>
                  <div class="mt-4">
                    <h3 class="font-bold">Aplikasi Edukasi</h3>
                    <p class="text-gray-300 text-sm">Aplikasi mobile edukasi keamanan siber.</p>
                  </div>
                </div>
              </div>
            </div>
          </section>
      
          <!-- CONTACT -->
          <section id="contact">
            <div class="container">
              <h2 class="text-3xl font-bold text-center mb-8 reveal">Hubungi Saya</h2>
      
              <div class="flex flex-col lg:flex-row gap-8 bg-black/30 p-6 rounded-xl">
                <!-- info -->
                <div class="lg:w-1/2 reveal">
                  <h3 class="text-2xl font-bold text-blue-400">Let's Collaborate</h3>
                  <p class="text-gray-300">Untuk project web development atau konsultasi keamanan siber, hubungi saya melalui:</p>
      
                  <div class="mt-6 space-y-4">
                    <div class="flex items-start gap-3">
                      <div class="bg-blue-500 p-2 rounded-full"><svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8"></path></svg></div>
                      <div>
                        <h4 class="font-bold text-white">Email</h4>
                        <p class="text-gray-300"><a href="mailto:yasyfinance.9@gmail.com">yasyfinance.9@gmail.com</a></p>
                      </div>
                    </div>
      
                    <div class="flex items-start gap-3">
                      <div class="bg-blue-500 p-2 rounded-full"><svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28"></path></svg></div>
                      <div>
                        <h4 class="font-bold text-white">WhatsApp</h4>
                        <p class="text-gray-300"><a href="https://wa.me/6281215853104" target="_blank">+62 812-1585-3104</a></p>
                      </div>
                    </div>
      
                    <div class="flex items-start gap-3">
                      <div class="bg-blue-500 p-2 rounded-full"><svg class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M17.657 16.657L13.414 20.9"></path></svg></div>
                      <div>
                        <h4 class="font-bold text-white">Lokasi</h4>
                        <p class="text-gray-300">Kediri, Jawa Timur, Indonesia</p>
                      </div>
                    </div>
      
                  </div>
      
                  <div class="pt-6">
                    <h4 class="font-bold text-white mb-2">Follow Me</h4>
                    <div class="flex gap-3">
                      <a class="p-3 rounded-full bg-[#1877F2] text-white"><svg class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor"><path d="M22 12c0-5.523-4.477-10-10-10S2 6.477 2 12c0 4.991 3.657 9.128 8.438 9.878v-6.987h-2.54V12h2.54V9.797"></path></svg></a>
                      <a class="p-3 rounded-full bg-gradient-to-r from-purple-500 to-pink-500 text-white"><svg class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919"></path></svg></a>
                      <a class="p-3 rounded-full bg-gray-800 text-white"><svg class="w-4 h-4" viewBox="0 0 24 24" fill="currentColor"><path d="M12 2C6.477 2 2 6.484 2 12.017c0 4.425 2.865 8.18 6.839 9.504"></path></svg></a>
                    </div>
                  </div>
                </div>
      
                <!-- form -->
                <div class="lg:w-1/2 reveal">
                  <form id="contactForm" class="space-y-4">
                    <div>
                      <label class="block text-sm text-gray-300 mb-1">Nama Lengkap*</label>
                      <input id="name" name="name" required placeholder="Masukkan nama Anda" class="w-full px-4 py-3 rounded-lg bg-gray-900 border border-gray-800 text-white" />
                    </div>
                    <div>
                      <label class="block text-sm text-gray-300 mb-1">Email*</label>
                      <input id="email" name="email" type="email" required placeholder="email@contoh.com" class="w-full px-4 py-3 rounded-lg bg-gray-900 border border-gray-800 text-white" />
                    </div>
                    <div>
                      <label class="block text-sm text-gray-300 mb-1">Subjek</label>
                      <select id="subject" name="subject" class="w-full px-4 py-3 rounded-lg bg-gray-900 border border-gray-800 text-white">
                        <option value="">Pilih subjek...</option>
                        <option value="web">Web Development</option>
                        <option value="security">Keamanan Siber</option>
                      </select>
                    </div>
                    <div>
                      <label class="block text-sm text-gray-300 mb-1">Pesan*</label>
                      <textarea id="message" name="message" required rows="4" class="w-full px-4 py-3 rounded-lg bg-gray-900 border border-gray-800 text-white"></textarea>
                    </div>
      
                    <button type="submit" class="w-full py-3 rounded-lg btn-neon">
                      <svg class="w-5 h-5 inline-block mr-2" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 8l7.89 5.26a2 2 0 002.22 0L21 8"></path></svg>
                      Kirim Pesan
                    </button>
                  </form>
                </div>
              </div>
            </div>
          </section>
      
          <!-- VIDEO (placeholder) -->
          <section class="bg-black/10">
            <div class="container">
              <h2 class="text-3xl font-bold text-center mb-8 reveal">Video Saya</h2>
              <div class="grid grid-cols-1 md:grid-cols-2 gap-6 reveal">
                <div class="card">
                  <div class="w-full h-56 bg-gray-800 rounded-lg overflow-hidden">
                    <iframe src="https://www.youtube.com/embed/VIDEO_ID_1" class="w-full h-full" frameborder="0" allowfullscreen></iframe>
                  </div>
                  <div class="mt-3"><h4 class="font-bold">Judul Video 1</h4><p class="text-gray-300 text-sm">Deskripsi singkat</p></div>
                </div>
      
                <div class="card">
                  <div class="w-full h-56 bg-gray-800 rounded-lg overflow-hidden">
                    <iframe src="https://www.youtube.com/embed/VIDEO_ID_2" class="w-full h-full" frameborder="0" allowfullscreen></iframe>
                  </div>
                  <div class="mt-3"><h4 class="font-bold">Judul Video 2</h4><p class="text-gray-300 text-sm">Deskripsi singkat</p></div>
                </div>
              </div>
            </div>
          </section>
      
          <!-- FOOTER -->
          <footer class="bg-black/60 py-8 mt-12">
            <div class="container flex flex-col md:flex-row justify-between items-center gap-6">
              <div>
                <a class="brand text-white text-2xl">my website</a>
                <p class="text-gray-400 mt-2">Web Developer &amp; Ethical Hacker</p>
              </div>
              <div class="text-gray-400">&copy; 2025 Maulana Y. A. A. Yudho Leksono. All rights reserved.</div>
            </div>
          </footer>
      
        </main>
      
        <!-- SCRIPTS -->
        <script>
          /***********************
           * Utility & Init
           ***********************/
          // Convenience
          const $ = (s, ctx=document) => ctx.querySelector(s);
          const $$ = (s, ctx=document) => [...ctx.querySelectorAll(s)];
      
          /* ---------------- SPLASH typing (name) ---------------- */
          (function splashType(){
            const splash = $('#splashScreen');
            const typingEl = $('#typing-text');
            const cursor = $('#typing-cursor');
            const text = "Web Developer & Ethical Hacker";
            let i = 0;
            // type slowly for effect
            function step(){
              if(i < text.length){
                typingEl.textContent += text.charAt(i);
                i++;
                setTimeout(step, 90);
              } else {
                // done: fade out cursor
                cursor.style.opacity = '0';
              }
            }
            // start after small delay to show logo
            setTimeout(step, 400);
          })();
      
          /* ---------------- splash hide & show main ---------------- */
          (function splashFlow(){
            // ensure splash is visible at start
            const splash = document.getElementById('splashScreen');
            const main = document.querySelector('.main-content');
      
            // Wait until window loads fully (images, fonts)
            window.addEventListener('load', () => {
              // total time: keep splash visible long enough to show progress animation
              setTimeout(() => {
                splash.style.opacity = '0';
                // reveal main after fade
                setTimeout(() => {
                  splash.style.display = 'none';
                  main.style.display = 'block';
                  document.body.style.overflow = 'auto';
                  // reveal elements after main shown
                  requestAnimationFrame(() => {
                    revealOnLoad();
                    initToolsSlider(); // start slider
                    startSparks(); // start particle canvas
                  });
                }, 800);
              }, 2000); // at least 2s
            });
          })();
      
          /* ---------------- NAVBAR scroll effect & mobile menu ---------------- */
          (function navSetup(){
            const nav = document.querySelector('nav.navbar');
            window.addEventListener('scroll', () => {
              if(window.scrollY > 50) nav.classList.add('scrolled'); else nav.classList.remove('scrolled');
            });
      
            const mobileBtn = document.getElementById('mobileBtn');
            const mobileMenu = document.getElementById('mobileMenu');
            mobileBtn.addEventListener('click', () => {
              mobileMenu.classList.toggle('hidden');
            });
          })();
      
          /* ---------------- STARS generator (parallax) ---------------- */
          (function starsGen(){
            const starsContainer = document.getElementById('stars-container');
            if(!starsContainer) return;
            const count = 120;
            for(let i=0;i<count;i++){
              const s = document.createElement('div');
              s.className = 'star';
              const size = Math.random()*2 + 0.8;
              s.style.width = s.style.height = size + 'px';
              s.style.left = (Math.random()*100) + '%';
              s.style.top = (Math.random()*100) + '%';
              s.style.opacity = (Math.random()*0.8 + 0.15).toString();
              s.style.setProperty('--opacity', s.style.opacity);
              const dur = (Math.random()*6 + 4).toFixed(2) + 's';
              s.style.animation = `twinkle ${dur} linear infinite`;
              starsContainer.appendChild(s);
            }
      
            // small parallax effect on mouse move
            document.addEventListener('mousemove', (e) => {
              const cx = window.innerWidth/2;
              const cy = window.innerHeight/2;
              const dx = (e.clientX - cx)/cx;
              const dy = (e.clientY - cy)/cy;
              // translate container slightly
              starsContainer.style.transform = `translate(${dx*6}px, ${dy*6}px)`;
            });
          })();
      
          /* ---------------- PARTICLE sparks canvas ---------------- */
          function startSparks(){
            const canvas = document.getElementById('sparks');
            if(!canvas) return;
            canvas.width = innerWidth;
            canvas.height = innerHeight;
            const ctx = canvas.getContext('2d');
            let particles = [];
      
            function rand(min,max){return Math.random()*(max-min)+min}
      
            // create some ambient particles
            for(let i=0;i<60;i++){
              particles.push({
                x: Math.random()*canvas.width,
                y: Math.random()*canvas.height,
                vx: rand(-0.15,0.15),
                vy: rand(-0.05,0.05),
                life: rand(4,12),
                size: rand(0.3,1.8),
                hue: rand(200,220)
              });
            }
      
            function tick(){
              ctx.clearRect(0,0,canvas.width,canvas.height);
              for(let p of particles){
                p.x += p.vx;
                p.y += p.vy;
                p.life -= 0.01;
                if(p.life <= 0){
                  p.x = Math.random()*canvas.width;
                  p.y = Math.random()*canvas.height;
                  p.life = rand(4,12);
                  p.vx = rand(-0.2,0.2);
                  p.vy = rand(-0.1,0.1);
                  p.size = rand(0.3,1.6);
                }
                ctx.beginPath();
                ctx.fillStyle = `hsla(${p.hue}, 90%, 65%, ${Math.max(0.06, Math.min(0.22, p.life/12))})`;
                ctx.arc(p.x, p.y, p.size, 0, Math.PI*2);
                ctx.fill();
              }
              requestAnimationFrame(tick);
            }
            tick();
      
            // resize
            window.addEventListener('resize', () => {
              canvas.width = innerWidth;
              canvas.height = innerHeight;
            });
          }
      
          /* ---------------- fade-in reveal on scroll ---------------- */
          function revealOnLoad(){
            const reveals = $$('.reveal');
            const obs = new IntersectionObserver((entries) => {
              entries.forEach(en => {
                if(en.isIntersecting){
                  en.target.classList.add('visible');
                  obs.unobserve(en.target);
                }
              });
            }, {threshold:0.12});
            reveals.forEach(el => obs.observe(el));
          }
      
          /* ---------------- skill progress when visible ---------------- */
          (function skillsObserver(){
            const skills = $$('.skill-progress');
            const obs = new IntersectionObserver((entries) => {
              entries.forEach(entry => {
                if(entry.isIntersecting){
                  const el = entry.target;
                  const prog = el.dataset.progress || '80%';
                  el.style.width = prog;
                  obs.unobserve(el);
                }
              });
            }, {threshold:0.2});
            skills.forEach(s => obs.observe(s));
          })();
      
          /* ---------------- rotating text effect ---------------- */
          (function rotatingText(){
            const words = ['Web Developer', 'Ethical Hacker', 'Security Enthusiast', 'Full-Stack Dev', 'Open Source Lover'];
            let idx = 0;
            const el = document.getElementById('rotatingText');
            setInterval(() => {
              idx = (idx+1) % words.length;
              el.style.opacity = '0';
              setTimeout(()=>{ el.textContent = words[idx]; el.style.opacity='1'; }, 350);
            }, 2900);
          })();
      
          /* ---------------- tools slider auto scroll ---------------- */
          function initToolsSlider(){
            const track = document.getElementById('toolsTrack');
            if(!track) return;
            let px = 0;
            const speed = 0.35; // px per frame
            // duplicate already in markup; ensure track width is enough
            function frame(){
              px += speed;
              if(px >= track.scrollWidth/2) px = 0;
              track.style.transform = `translateX(-${px}px)`;
              requestAnimationFrame(frame);
            }
            requestAnimationFrame(frame);
          }
      
          /* ---------------- tilt 3D for .card-tilt elements ---------------- */
          (function tiltSetup(){
            const tilts = $$('.card-tilt');
            tilts.forEach(el => {
              el.style.transformStyle = 'preserve-3d';
              el.addEventListener('mousemove', (ev) => {
                const r = el.getBoundingClientRect();
                const cx = r.left + r.width/2;
                const cy = r.top + r.height/2;
                const dx = (ev.clientX - cx) / (r.width/2);
                const dy = (ev.clientY - cy) / (r.height/2);
                const rotY = dx * 8; // degrees
                const rotX = -dy * 8;
                el.style.transform = `rotateX(${rotX}deg) rotateY(${rotY}deg) translateZ(6px)`;
              });
              el.addEventListener('mouseleave', () => {
                el.style.transform = '';
              });
            });
          })();
      
          /* ---------------- contact form handler ---------------- */
          (function contactForm(){
            const form = document.getElementById('contactForm');
            if(!form) return;
            form.addEventListener('submit', (e) => {
              e.preventDefault();
              const fd = new FormData(form);
              const obj = {};
              for(const [k,v] of fd.entries()) obj[k]=v;
              console.log('Contact form', obj);
              alert('Pesan telah dikirim! Terima kasih. (demo — hubungkan backend untuk kirim nyata)');
              form.reset();
            });
          })();
      
          /* ---------------- smooth anchor scrolling ---------------- */
          (function smoothAnchors(){
            $$('a[href^="#"]').forEach(a => {
              a.addEventListener('click', function(e){
                const href = this.getAttribute('href');
                if(!href || href === '#') return;
                const el = document.querySelector(href);
                if(el){ e.preventDefault(); el.scrollIntoView({behavior:'smooth', block:'start'}); }
                // close mobile menu if open
                const mobileMenu = $('#mobileMenu');
                if(mobileMenu && !mobileMenu.classList.contains('hidden')) mobileMenu.classList.add('hidden');
              });
            });
          })();
      
          /* ---------------- initial page reveals after main shown ---------------- */
          function revealOnLoad(){
            // small staggered reveal
            $$('.reveal').forEach((el, i) => {
              setTimeout(()=> el.classList.add('visible'), 120 + (i*90));
            });
          }
      
          /* ---------------- responsive adjustments ---------------- */
          window.addEventListener('resize', () => {
            // keep canvas full-screen
            const c = document.getElementById('sparks');
            if(c){ c.width = innerWidth; c.height = innerHeight; }
          });
      
          // ensure sparks start when main shown if splash skipped
          document.addEventListener('DOMContentLoaded', () => {
            // fallback start if load already fired earlier
            setTimeout(() => {
              if(document.querySelector('.main-content').style.display === 'block'){
                startSparks();
                initToolsSlider();
              }
            }, 1200);
          });
      
        </script>
      </body>
      </html>
      
