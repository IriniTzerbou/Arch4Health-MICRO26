<!-- index.md -->
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,500;12..96,700&family=Source+Sans+3:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">

<style>
  /* ---------- The theme prints _config.yml's title as a big blue heading above the page.
     The hero shows that title instead, so hide the theme's copy. ---------- */
  .markdown-body > h1:first-child,
  .a4h-theme-title-hidden { display: none !important; }

  /* ---------- Tokens ---------- */
  .a4h {
    --navy: #003156;
    --navy-deep: #00223D;
    --teal: #15A9BA;
    --teal-ink: #0B7480;
    --wash: #E7F6F8;
    --mist: #F4F8FA;
    --line: #D3E2E8;
    --ink: #1C2D3B;
    --muted: #4F6577;
    --display: "Bricolage Grotesque", "Segoe UI", "Helvetica Neue", Arial, sans-serif;
    --body: "Source Sans 3", "Segoe UI", "Helvetica Neue", Arial, sans-serif;
    font-family: var(--body);
    font-size: 1.05rem;
    line-height: 1.6;
    color: var(--ink);
  }
  .a4h *, .a4h *::before, .a4h *::after { box-sizing: border-box; }
  .a4h img { max-width: 100%; }
  .a4h a { color: var(--teal-ink); text-underline-offset: 3px; }
  .a4h a:focus-visible, .a4h summary:focus-visible { outline: 3px solid var(--teal); outline-offset: 3px; border-radius: 4px; }
  .a4h h2, .a4h h3, .a4h h4 { font-family: var(--display); font-weight: 700; color: var(--navy); letter-spacing: -0.01em; }
  .a4h p { margin: 0 0 0.9rem; }
  .a4h-program li + li, .a4h-chips li + li, .a4h-dates li + li { margin-top: 0; }

  /* ---------- Sticky nav ---------- */
  .a4h-nav {
    position: sticky; top: 0; z-index: 20;
    display: flex; gap: 0.35rem; overflow-x: auto; scrollbar-width: none;
    padding: 0.6rem 0; margin-bottom: 1.25rem;
    background: rgba(255,255,255,0.92); backdrop-filter: blur(8px);
    border-bottom: 1px solid var(--line);
  }
  .a4h-nav::-webkit-scrollbar { display: none; }
  .a4h-nav a {
    flex: none; padding: 0.35rem 0.6rem; border-radius: 999px;
    font-size: 0.88rem; font-weight: 600; color: var(--navy); text-decoration: none;
  }
  .a4h-nav a:hover { background: var(--wash); }
  .a4h-nav a.cta { background: var(--navy); color: #fff; margin-left: auto; }
  .a4h-nav a.cta:hover { background: var(--navy-deep); }

  /* ---------- Hero: the logo's navy square, with its circuit traces ---------- */
  .a4h-hero {
    position: relative; overflow: hidden; isolation: isolate;
    padding: 2rem 2rem 1.75rem; border-radius: 22px;
    background: radial-gradient(120% 90% at 100% 0%, #0A4470 0%, var(--navy) 55%, var(--navy-deep) 100%);
    color: #DDEBF3;
  }
  .a4h-hero .content { position: relative; z-index: 1; max-width: 560px; }
  .a4h-hero .plaque {
    display: inline-block; background: #fff; border-radius: 14px; padding: 0.6rem 0.9rem; margin-bottom: 1.6rem;
    box-shadow: 0 0 0 1px rgba(21,169,186,0.4), 0 12px 32px rgba(0,20,40,0.35);
  }
  .a4h-hero .logo { display: block; width: min(360px, 68vw); height: auto; }
  .a4h-hero h1 {
    font-family: var(--display); font-weight: 700; color: #fff;
    font-size: clamp(2.1rem, 5.4vw, 3.4rem); line-height: 1.04; letter-spacing: -0.03em;
    margin: 0 0 1rem; max-width: 16ch; border: 0; padding: 0; text-wrap: balance;
  }
  .a4h-hero h1 .edition {
    display: flex; align-items: center; gap: 0.6rem;
    font-size: clamp(1.05rem, 2.2vw, 1.35rem); font-weight: 500; letter-spacing: 0;
    color: var(--teal); margin-bottom: 0.45rem;
  }
  /* a short trace and node in front of the edition line, like the logo's wiring */
  .a4h-hero h1 .edition::before {
    content: ""; flex: none; width: 34px; height: 12px;
    background:
      radial-gradient(circle at calc(100% - 6px) 50%, var(--teal) 0 5px, transparent 5.5px),
      linear-gradient(var(--teal), var(--teal)) left center / calc(100% - 10px) 3px no-repeat;
  }
  .a4h-hero .lede { font-size: 1.15rem; color: #B6CFDD; max-width: 72ch; margin-bottom: 1.5rem; }
  .a4h-hero .actions { display: flex; flex-wrap: wrap; gap: 0.6rem; margin-bottom: 1.75rem; }
  .a4h-btn {
    display: inline-block; padding: 0.65rem 1.15rem; border-radius: 10px;
    font-weight: 700; font-size: 0.98rem; text-decoration: none !important;
  }
  .a4h-btn.solid { background: var(--navy); color: #fff !important; }
  .a4h-btn.solid:hover { background: var(--navy-deep); }
  .a4h-hero .a4h-btn.solid { background: var(--teal); color: var(--navy-deep) !important; }
  .a4h-hero .a4h-btn.solid:hover { background: #3BC2D1; }
  .a4h-btn.ghost { background: transparent; color: #fff !important; border: 1.5px solid rgba(255,255,255,0.7); }
  .a4h-btn.ghost:hover { background: rgba(255,255,255,0.1); border-color: #fff; }

  .a4h-facts {
    position: relative; z-index: 1;
    display: flex; flex-wrap: wrap;
    gap: 1px; background: rgba(255,255,255,0.16); border: 1px solid rgba(255,255,255,0.16);
    border-radius: 14px; overflow: hidden; margin-bottom: 1.25rem;
  }
  .a4h-facts div { flex: 1 1 140px; background: rgba(0,34,61,0.72); backdrop-filter: blur(6px); padding: 0.8rem 1rem; }
  .a4h-facts span { display: block; font-size: 0.85rem; color: #9FC3D3; }
  .a4h-facts strong { display: block; font-family: var(--display); font-weight: 500; color: #fff; font-size: 1.05rem; line-height: 1.3; }
  .a4h-facts a { color: #fff !important; text-decoration: underline; text-decoration-color: var(--teal); }

  .a4h-countdown { position: relative; z-index: 1; font-size: 0.95rem; color: #DDEBF3; font-weight: 600; margin: 0; min-height: 1.5em; }
  .a4h-countdown b { font-family: var(--display); font-size: 1.25rem; color: var(--teal); font-variant-numeric: tabular-nums; }

  /* Circuit traces from the logo, drawn in once on load */
  .a4h-circuit { position: absolute; z-index: 0; right: 0; top: 1.5rem; width: 50%; max-width: 500px; height: auto; pointer-events: none; }
  .a4h-circuit path { fill: none; stroke: var(--teal); stroke-width: 3; stroke-linecap: round; stroke-linejoin: round;
    stroke-dasharray: 320; stroke-dashoffset: 320; animation: a4h-draw 1.4s ease-out var(--d, 0s) forwards; }
  .a4h-circuit circle { fill: var(--teal); opacity: 0; animation: a4h-pop 0.35s ease-out calc(var(--d, 0s) + 1.1s) forwards; }
  .a4h-circuit .faint path { stroke: #2C6A8E; }
  .a4h-circuit .faint circle { fill: #2C6A8E; }
  @keyframes a4h-draw { to { stroke-dashoffset: 0; } }
  @keyframes a4h-pop { from { opacity: 0; transform: scale(0.4); } to { opacity: 1; transform: scale(1); } }
  .a4h-circuit circle { transform-box: fill-box; transform-origin: center; }
  @media (prefers-reduced-motion: reduce) {
    .a4h-circuit path { animation: none; stroke-dashoffset: 0; }
    .a4h-circuit circle { animation: none; opacity: 1; }
  }

  /* ---------- Sections ---------- */
  .a4h-section { padding: 2.75rem 0 0.5rem; scroll-margin-top: 4rem; }
  .a4h-section > h2 { font-size: clamp(1.6rem, 3vw, 2.1rem); font-weight: 700; margin: 0 0 1.25rem; padding: 0; border: 0; }
  .a4h-section > h2::after {
    content: ""; display: block; width: 72px; height: 12px; margin-top: 0.55rem;
    background:
      radial-gradient(circle at calc(100% - 6px) 50%, var(--teal) 0 5px, transparent 5.5px),
      linear-gradient(var(--teal), var(--teal)) left center / calc(100% - 10px) 3px no-repeat;
  }
  .a4h-section > .intro { font-size: 1.1rem; color: var(--muted); max-width: 62ch; margin-top: -0.5rem; }

  .a4h-about { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
  .a4h-about article { padding: 1.25rem 1.35rem; border-radius: 14px; background: var(--mist); border-left: 4px solid var(--teal); }
  .a4h-about article.wide { grid-column: 1 / -1; background: var(--navy); color: #DDEBF3; border-left-color: var(--teal); }
  .a4h-about article.wide h3 { color: #fff; }
  .a4h-about h3 { font-size: 1.15rem; margin: 0 0 0.5rem; }
  .a4h-about p { margin: 0; }

  /* ---------- Program timeline ---------- */
  .a4h-program { list-style: none; margin: 0; padding: 0; border-left: 2px solid var(--line); }
  .a4h-program li { position: relative; display: grid; grid-template-columns: 7.5rem 1fr; gap: 1rem; padding: 0.95rem 0 0.95rem 1.25rem; border-bottom: 1px solid #E9F0F3; }
  .a4h-program li::before { content: ""; position: absolute; left: -7px; top: 1.3rem; width: 12px; height: 12px; border-radius: 50%; background: #fff; border: 2px solid var(--navy); }
  .a4h-program .t { font-variant-numeric: tabular-nums; font-weight: 600; color: var(--muted); white-space: nowrap; padding-top: 0.1rem; }
  .a4h-program .title { font-family: var(--display); font-weight: 500; font-size: 1.12rem; line-height: 1.3; color: var(--navy); display: block; }
  .a4h-program .who { display: block; margin-top: 0.3rem; font-size: 0.97rem; }
  .a4h-program .aff { display: block; font-size: 0.9rem; color: var(--muted); }
  .a4h-program .presenter { text-decoration: underline; text-decoration-color: var(--teal); text-decoration-thickness: 2px; text-underline-offset: 3px; font-weight: 600; }
  .a4h-program .tag { display: inline-block; margin-bottom: 0.35rem; padding: 0.1rem 0.55rem; border-radius: 999px; font-size: 0.8rem; font-weight: 700; background: var(--wash); color: var(--teal-ink); }
  .a4h-program li.invited::before { background: var(--teal); border-color: var(--teal); width: 14px; height: 14px; left: -8px; }
  .a4h-program li.invited { background: linear-gradient(90deg, var(--wash), transparent 85%); }
  .a4h-program li.minor .title { font-size: 1rem; color: var(--muted); font-family: var(--body); font-weight: 600; }
  .a4h-program li.break { background: var(--mist); }
  .a4h-program li.break::before { border-style: dashed; }
  .a4h-program li.now { box-shadow: inset 4px 0 0 #2BB673; }
  .a4h-program li.now .t::after { content: "Live now"; display: block; color: #1E8A55; font-size: 0.8rem; font-weight: 700; }

  /* ---------- Livestream ---------- */
  .a4h-video { position: relative; aspect-ratio: 16 / 9; border-radius: 16px; overflow: hidden; background: var(--navy-deep); }
  .a4h-video iframe { position: absolute; inset: 0; width: 100%; height: 100%; border: 0; }

  /* ---------- Call for presentations ---------- */
  .a4h-cfp { display: grid; grid-template-columns: 1.5fr 1fr; gap: 1.5rem; align-items: start; }
  .a4h-topics { display: grid; gap: 0.9rem; margin-top: 1.25rem; }
  .a4h-topics h4 { font-size: 1rem; margin: 0 0 0.35rem; }
  .a4h-chips { display: flex; flex-wrap: wrap; gap: 0.4rem; margin: 0; padding: 0; list-style: none; }
  .a4h-chips li { padding: 0.25rem 0.7rem; border-radius: 999px; background: #fff; border: 1px solid var(--line); font-size: 0.92rem; }
  .a4h-chips.solo li { background: var(--wash); border-color: #C4E7EC; color: var(--navy); font-weight: 600; }

  .a4h-dates { padding: 1.35rem; border-radius: 16px; background: var(--navy); color: #DDEBF3; position: sticky; top: 4.5rem; }
  .a4h-dates h3 { color: #fff; font-size: 1.2rem; margin: 0 0 1rem; }
  .a4h-dates ol { list-style: none; margin: 0; padding: 0; }
  .a4h-dates li { position: relative; padding: 0 0 1.1rem 1.6rem; }
  .a4h-dates li:last-child { padding-bottom: 0; }
  .a4h-dates li::before { content: ""; position: absolute; left: 0; top: 0.35rem; width: 11px; height: 11px; border-radius: 50%; border: 2px solid var(--teal); }
  .a4h-dates li::after { content: ""; position: absolute; left: 5px; top: 1.2rem; bottom: 0; width: 1px; background: rgba(255,255,255,0.25); }
  .a4h-dates li:last-child::after { display: none; }
  .a4h-dates span { display: block; font-size: 0.9rem; color: #9FC3D3; }
  .a4h-dates strong { font-family: var(--display); font-weight: 500; font-size: 1.1rem; color: #fff; }
  .a4h-dates li.past strong { text-decoration: line-through; text-decoration-color: rgba(255,255,255,0.5); color: #9FC3D3; }
  .a4h-dates li.past::before { background: var(--teal); }

  /* ---------- Organizers ---------- */
  .a4h-people { display: grid; grid-template-columns: repeat(2, minmax(0, 1fr)); gap: 1rem; }
  .a4h-person { display: grid; grid-template-columns: 84px 1fr; gap: 0.9rem; align-items: start; padding: 1.1rem; border: 1px solid var(--line); border-radius: 14px; background: #fff; }
  .a4h-person img { width: 84px; height: 84px; object-fit: cover; border-radius: 18px; border: 3px solid var(--navy); box-shadow: 4px 4px 0 var(--teal); }
  .a4h-person h3 { font-size: 1.08rem; margin: 0.1rem 0 0.15rem; }
  .a4h-person h3 a { color: var(--navy); text-decoration: none; }
  .a4h-person h3 a:hover { text-decoration: underline; }
  .a4h-person .role { font-size: 0.93rem; color: var(--muted); margin: 0 0 0.3rem; line-height: 1.4; }
  .a4h-person .mail { font-size: 0.9rem; word-break: break-all; }
  .a4h-person details { grid-column: 1 / -1; margin-top: 0.2rem; border-top: 1px solid #E9F0F3; padding-top: 0.6rem; }
  .a4h-person summary { cursor: pointer; font-weight: 600; color: var(--navy); font-size: 0.95rem; }
  .a4h-person details p { font-size: 0.96rem; margin: 0.6rem 0 0; }

  /* ---------- Previous editions ---------- */
  .a4h-past { display: grid; grid-template-columns: repeat(auto-fit, minmax(180px, 1fr)); gap: 0.8rem; }
  .a4h-past a { display: block; padding: 1rem 1.1rem; border-radius: 12px; background: var(--mist); border: 1px solid var(--line); text-decoration: none; color: var(--ink); }
  .a4h-past a:hover { border-color: var(--teal); background: var(--wash); }
  .a4h-past strong { display: block; font-family: var(--display); font-weight: 700; color: var(--navy); font-size: 1.15rem; }
  .a4h-past span { font-size: 0.93rem; color: var(--muted); }

  .a4h-foot { margin-top: 3rem; padding: 1.25rem 0; border-top: 1px solid var(--line); font-size: 0.92rem; color: var(--muted); }

  /* ---------- Small screens ---------- */
  @media (max-width: 720px) {
    .a4h-hero { padding: 1.5rem 1.15rem 1.25rem; }
    .a4h-circuit { width: 70%; top: 0.5rem; right: -12%; opacity: 0.35; }
    .a4h-about, .a4h-cfp, .a4h-people { grid-template-columns: 1fr; }
    .a4h-dates { position: static; }
    .a4h-program li { grid-template-columns: 1fr; gap: 0.2rem; }
  }
</style>

<div class="a4h">

<nav class="a4h-nav" aria-label="Page sections">
  <a href="#description">About</a>
  <a href="#agenda-materials">Program</a>
  <a href="#call-for-presentations">Call for Presentations</a>
  <a href="#key-dates">Key Dates</a>
  <a href="#organizers">Organizers</a>
  <a href="#previous-iteration">Past Editions</a>
</nav>

<header class="a4h-hero">
  <svg class="a4h-circuit" viewBox="0 0 440 380" aria-hidden="true">
    <g class="faint">
      <path style="--d:.0s" d="M440 30 H380 L350 60 H300"/><circle style="--d:.0s" cx="292" cy="60" r="7"/>
      <path style="--d:.15s" d="M440 350 H360 L330 320 H270"/><circle style="--d:.15s" cx="262" cy="320" r="7"/>
    </g>
    <path style="--d:.1s"  d="M440 95 H360 L320 135 H230"/><circle style="--d:.1s"  cx="221" cy="135" r="9"/>
    <path style="--d:.25s" d="M440 150 H380 L355 175 H270"/><circle style="--d:.25s" cx="261" cy="175" r="9"/>
    <path style="--d:.4s"  d="M440 215 H300"/><circle style="--d:.4s"  cx="291" cy="215" r="9"/>
    <path style="--d:.55s" d="M440 280 H380 L355 255 H270"/><circle style="--d:.55s" cx="261" cy="255" r="9"/>
  </svg>
  <div class="content">
    <div class="plaque"><img class="logo" src="{{ 'arch4health-logo3.png' | relative_url }}" alt="Arch4Health"></div>
    {% assign a4h_title = site.title | default: "Fourth Workshop on Architecture for Health" %}
    {% assign a4h_parts = a4h_title | split: " on " %}
    <h1>{% if a4h_parts.size == 2 %}<span class="edition">{{ a4h_parts[0] }} on</span>{{ a4h_parts[1] }}{% else %}{{ a4h_title }}{% endif %}</h1>
    <p class="lede">A half-day workshop exploring<br>the key computational challenges in health-related applications and<br>the vital role of computer architecture in overcoming them to advance healthcare.</p>
    <div class="actions">
      <a class="a4h-btn solid" href="#agenda-materials">See the program</a>
    </div>
  </div>
  <div class="a4h-facts">
    <div><span>Date</span><strong>Sunday, 1 November 2026</strong></div>
    <div><span>Time</span><strong>13:00 – 17:00 EET</strong></div>
    <div><span>Location</span><strong>Athens, Greece</strong></div>
    <div><span>Room</span><strong>Ypsilon I</strong></div>
    <div><span>In conjunction with</span><strong><a href="https://www.microarch.org/micro59/index.php">MICRO 2026</a></strong></div>
  </div>
  <p class="a4h-countdown" id="a4h-countdown" aria-live="polite"></p>
</header>

<section class="a4h-section" id="description">
  <h2>About the workshop</h2>
  <div class="a4h-about">
    <article>
      <h3>Opportunities</h3>
      <p>Recent biotechnological advances enable high-throughput, low-cost, and accurate biological data generation (e.g., using genome sequencing, multimodal medical imaging, continuous wearable sensing). This wealth of data enables unique opportunities for advancing healthcare. These opportunities include, but are not limited to, precision medicine, bedside personalized care, discovering early warning signs of communicable diseases, continuous physiological tracking, and enhanced diagnostic capabilities.</p>
    </article>
    <article>
      <h3>Challenges</h3>
      <p>Despite these opportunities, efficiently analyzing large-scale biological data poses significant challenges for conventional computing systems. These systems often cannot keep up with the high-throughput rate at which data is generated, and they face additional constraints related to energy efficiency, scalability, privacy, and security. High-throughput processing is particularly crucial in clinical settings, where real-time data processing can significantly impact patient outcomes by improving both response times in time-critical scenarios as well as the decision-making processes for therapeutic schemes. Therefore, to facilitate the wide adoption of recent advances in healthcare, there is a need to optimize the computing systems to enable high-performance, energy-efficient, low-cost, private, and secure analysis of biological data.</p>
    </article>
    <article class="wide">
      <h3>Architecture for Health</h3>
      <p>This workshop will focus on identifying key computational challenges in health-related applications and discussing how computer architects can contribute to advancing healthcare by addressing these challenges. First, we will provide invited talks and keynotes that summarize (i) a series of research in computing system designs for healthcare applications and (ii) new trends and bottlenecks in data-intensive healthcare applications. Second, we will invite researchers to submit their ongoing work on these topics.</p>
    </article>
    <article style="grid-column: 1 / -1;">
      <h3>Fostering diverse and cross-disciplinary discussions</h3>
      <p>Since cross-disciplinary discussions are crucial for better identifying challenges in real-world health-related applications, we aim to foster open discussions and cooperation between researchers with diverse backgrounds (i.e., from both computer architecture and health sciences communities, industry, and academia).</p>
    </article>
  </div>
</section>

<section class="a4h-section" id="agenda-materials">
  <h2>Program</h2>
  <p class="intro">Sunday, 1 November 2026, 13:00 to 17:00 local time (EET, UTC+2), in room Ypsilon I. Presenting authors are underlined.</p>
  <ol class="a4h-program">
    <li class="minor" data-start="11:00" data-end="11:10"><span class="t">13:00 – 13:10</span><div><span class="title">Welcome</span><span class="aff">Organizers</span></div></li>
    <li class="invited" data-start="11:10" data-end="12:00"><span class="t">13:10 – 14:00</span><div><span class="title">Accelerating Genome Analysis</span><span class="who">Onur Mutlu</span><span class="aff">ETH Zurich</span></div></li>
    <li data-start="12:00" data-end="12:20"><span class="t">14:00 – 14:20</span><div><span class="title">BeSA: Benchmarks for Simulating Agent-based Models in Architecture Research</span><span class="who"><span class="presenter">Amina Sokoli</span>, Abdullah Giray Yağlıkçı</span><span class="aff">CISPA Helmholtz Center for Information Security</span></div></li>
    <li data-start="12:20" data-end="12:40"><span class="t">14:20 – 14:40</span><div><span class="title">From Wi-Fi Offloading to On-Device NPU Inference: A Working Wearable for Presbyopia Correction</span><span class="who"><span class="presenter">Arturo Vicente-Jaén</span>, Juan L. Aragón, Pablo Artal</span><span class="aff">Universidad de Murcia</span></div></li>
    <li data-start="12:40" data-end="13:00"><span class="t">14:40 – 15:00</span><div><span class="title">STAGE-Med: An Interactive Multi-Agent Framework for Medical Diagnosis Based on Structured Action Spaces and Global Exploration</span><span class="who"><span class="presenter">Weiqi Li</span><sup>1</sup>, Zihao Pu<sup>1</sup>, Mengyun Zhang<sup>2</sup>, Haiyu Mao<sup>1</sup></span><span class="aff"><sup>1</sup>King’s College London, <sup>2</sup>Tsinghua University</span></div></li>
    <li class="minor break" data-start="13:00" data-end="13:30"><span class="t">15:00 – 15:30</span><div><span class="title">☕ Coffee break</span></div></li>
    <li class="invited" data-start="13:30" data-end="14:15"><span class="t">15:30 – 16:15</span><div><span class="title">Sparse by Nature, Parallel by Design: HPC for the Life Sciences</span><span class="who">Giulia Guidi</span><span class="aff">Cornell University</span></div></li>
    <li data-start="14:15" data-end="14:35"><span class="t">16:15 – 16:35</span><div><span class="title">Benchmarking and Accelerating Single-Cell Analysis</span><span class="who"><span class="presenter">Wonyoung Cheon</span>, Timur Eke, Eirini Tzermpou, Konstantina Koliogeorgi, Nika Mansouri Ghiasi, Onur Mutlu</span><span class="aff">ETH Zurich</span></div></li>
    <li data-start="14:35" data-end="14:55"><span class="t">16:35 – 16:55</span><div><span class="title">Towards Fast and Efficient Genomic Analysis with Analog In-Memory Computing Hardware</span><span class="who">Peiyi He</span><span class="aff">The University of Hong Kong</span></div></li>
    <li class="minor" data-start="14:55" data-end="15:00"><span class="t">16:55 – 17:00</span><div><span class="title">Concluding remarks</span><span class="aff">Organizers</span></div></li>
  </ol>
</section>

<section class="a4h-section" id="call-for-presentations">
  <h2>Call for Presentations</h2>
  <div class="a4h-cfp">
    <div>
      <p>This workshop consists of talks on the general topic of computing system designs for healthcare applications and new trends and bottlenecks in data-intensive healthcare applications. There are a limited number of slots for talks. If you are interested in delivering a talk on related topics, <strong>please submit your talk’s title and extended abstract via the Google Form below</strong>. You may either paste the abstract directly into the form or upload a two-page PDF prepared in any standard conference template. Each submission must include the talk title, all authors’ names, and their affiliations.</p>
      <p><a class="a4h-btn solid" href="https://docs.google.com/forms/d/e/1FAIpQLSfy_IaEbtvIkF-QesWAZzZ4AcHL3KVgaHmNR3xFFx5_A7aFkA/viewform?usp=dialog">Submit an abstract</a></p>
      <p>We invite abstract submissions related to (but not limited to) the following topics:</p>
      <div class="a4h-topics">
        <div><h4>Computational biology</h4><ul class="a4h-chips"><li>Genomics</li><li>Metagenomics</li><li>Gene editing</li><li>Drug design and discovery</li><li>Proteomics</li><li>Other areas in precision medicine</li></ul></div>
        <div><h4>Neuroscience</h4><ul class="a4h-chips"><li>Brain-machine interfaces</li><li>Prosthetics</li></ul></div>
        <div><h4>Medical robotics</h4><ul class="a4h-chips"><li>Surgery</li><li>Haptics</li></ul></div>
        <div><h4>Medical imaging</h4><ul class="a4h-chips"><li>Brain scans</li><li>Radiology</li><li>Single-cell analysis</li></ul></div>
        <div><h4>Also welcome</h4><ul class="a4h-chips solo"><li>Wearable systems for health</li><li>Mental health</li><li>Agent-based simulations</li><li>Medical privacy</li><li>Bio-sensors</li></ul></div>
      </div>
    </div>
    <aside class="a4h-dates" id="key-dates">
      <h3>Key dates</h3>
      <ol>
        <li data-date="2026-10-04T23:59:59-12:00"><span>Extended abstract deadline</span><strong>4 October 2026</strong></li>
        <li data-date="2026-10-09T23:59:59-12:00"><span>Notification</span><strong>9 October 2026</strong></li>
        <li data-date="2026-11-01T15:00:00Z"><span>Workshop</span><strong>1 November 2026</strong></li>
      </ol>
    </aside>
  </div>
</section>

<section class="a4h-section" id="organizers">
  <h2>Organizers</h2>
  <div class="a4h-people">

    <div class="a4h-person">
      <img src="{{ 'nika_pic.jpeg' | relative_url }}" alt="Nika Mansouri Ghiasi">
      <div>
        <h3><a href="https://sites.google.com/view/nikamansourighiasi/">Dr. Nika Mansouri Ghiasi</a></h3>
        <p class="role">Senior Researcher, SAFARI Research Group, ETH Zurich</p>
        <a class="mail" href="mailto:nika.mansourighiasi@safari.ethz.ch">nika.mansourighiasi@safari.ethz.ch</a>
      </div>
      <details>
        <summary>Read bio</summary>
        <p>Nika Mansouri Ghiasi is a senior researcher in the SAFARI Research Group at ETH Zurich, where she recently obtained her PhD advised by Professor Onur Mutlu. Nika is currently on the academic job market for tenure-track faculty positions. Her research spans across the computing stack to tackle computational challenges in healthcare, life sciences, and beyond. She is especially excited about designing high-performance, energy-efficient, and low-cost systems for (i) widespread adoption of data-intensive applications in healthcare and life sciences and (ii) enabling new solutions that were out of reach before, both in these domains and in other critical domains, such as AI/ML. Her research has received various honors and recognitions, such as induction to the ISCA hall of fame in 2026, selected as one of the 20 young researchers to attend and present at the Heidelberg Laureate Forum in 2026, ETH Doc.Mobility Fellowship (supporting her visiting research period at Stanford University), and ACM SRC Grand Finalist at PACT 2024. For more information, please check her website: <a href="https://nikamgh.github.io/">https://nikamgh.github.io/</a>.</p>
      </details>
    </div>

    <div class="a4h-person">
      <img src="{{ 'konstantina_pic.jpeg' | relative_url }}" alt="Konstantina Koliogeorgi">
      <div>
        <h3><a href="https://ihpcs.ethz.ch/people/person-detail.MzQ0MTU2.TGlzdC8zOTQxLDc2NTU1MzE0Mg==.html">Dr. Konstantina Koliogeorgi</a></h3>
        <p class="role">Postdoctoral Researcher, SAFARI Research Group, ETH Zurich</p>
        <a class="mail" href="mailto:kkoliogeorgi@ethz.ch">kkoliogeorgi@ethz.ch</a>
      </div>
      <details>
        <summary>Read bio</summary>
        <p>Konstantina Koliogeorgi is a Postdoctoral Researcher at the SAFARI Research Group at ETH Zurich, led by Prof. Onur Mutlu. She received her Ph.D. degree in Electrical and Computer Engineering in 2023 at National Technical University of Athens (NTUA), advised by Prof. Dimitrios Soudris. Her research interests are in the field of computer systems and architecture, heterogeneous computing, and hardware acceleration. Her research has focused on hardware-software co-design, efficient high-level synthesis optimization, and design space exploration, targeting mainly genome analysis applications.</p>
      </details>
    </div>

    <div class="a4h-person">
      <img src="{{ 'eirini_pic.jpeg' | relative_url }}" alt="Eirini Tzermpou">
      <div>
        <h3><a href="https://ihpcs.ethz.ch/people/person-detail.Mzc3MTQ0.TGlzdC8zOTQxLDc2NTU1MzE0Mg==.html">Eirini Tzermpou</a></h3>
        <p class="role">Graduate Researcher, SAFARI Research Group, ETH Zurich</p>
        <a class="mail" href="mailto:etzermpou@ethz.ch">etzermpou@ethz.ch</a>
      </div>
      <details>
        <summary>Read bio</summary>
        <p>Eirini Tzermpou is currently a graduate researcher in the SAFARI Research Group at ETH Zurich, led by Prof. Onur Mutlu. She recently received her Integrated Master’s in Electrical and Computer Engineering from the National Technical University of Athens (NTUA) and her Bachelor’s in Biomedical Sciences from DEREE-The American College of Greece. Her research interests lie in the intersection of computer architecture with bioinformatics and biomedicine, with a focus on designing software-hardware co-designed systems for accelerating bio-analysis workflows.</p>
      </details>
    </div>

    <div class="a4h-person">
      <img src="{{ 'onur_pic.jpeg' | relative_url }}" alt="Onur Mutlu">
      <div>
        <h3><a href="https://people.inf.ethz.ch/omutlu/">Professor Onur Mutlu</a></h3>
        <p class="role">Professor of Computer Science, ETH Zurich</p>
        <a class="mail" href="mailto:omutlu@gmail.com">omutlu@gmail.com</a>
      </div>
      <details>
        <summary>Read bio</summary>
        <p>Onur Mutlu is a Professor of Computer Science at ETH Zurich. He previously held the William D. and Nancy W. Strecker Early Career Professorship at Carnegie Mellon University. His research interests are in computer architecture, computing systems, hardware security, memory &amp; storage systems, and bioinformatics, with a major focus on designing fundamentally energy-efficient, high-performance, and robust computing systems. He started the Computer Architecture Group at Microsoft Research (2006-2009), and held product, research, and visiting positions at Intel Corporation, Advanced Micro Devices, VMware, Google, and Stanford University. He received various honors for his research, including the 2025 IEEE Computer Society Harry H. Goode Memorial Award “for seminal contributions to computer architecture research and practice, especially in memory systems.” He is an ACM Fellow, IEEE Fellow, and an elected member of the Academy of Europe. He enjoys teaching, mentoring, and enabling &amp; democratizing access to high-quality research and education. He has supervised 24 PhD graduates, many of whom received major dissertation awards, 15 postdoctoral trainees, and more than 60 Master’s and Bachelor’s students. His computer architecture and digital logic design course lectures and materials are freely available on YouTube, and his research group makes a wide variety of artifacts freely available online. For more information, please see his webpage at <a href="https://people.inf.ethz.ch/omutlu/">https://people.inf.ethz.ch/omutlu/</a>.</p>
      </details>
    </div>

  </div>
</section>

<section class="a4h-section" id="previous-iteration">
  <h2>Past editions</h2>
  <div class="a4h-past">
    <a href="https://events.safari.ethz.ch/micro25-arch4health/" target="_blank" rel="noopener"><strong>MICRO 2025</strong><span>Seoul, South Korea</span></a>
    <a href="https://events.safari.ethz.ch/hpca26-arch4health/" target="_blank" rel="noopener"><strong>HPCA 2026</strong><span>Sydney, Australia</span></a>
    <a href="https://events.safari.ethz.ch/ics26-arch4health/" target="_blank" rel="noopener"><strong>ICS 2026</strong><span>Belfast, United Kingdom</span></a>
  </div>
</section>

<section class="a4h-section" id="livestream">
  <h2>Livestream</h2>
  <p class="intro">Can’t make it to Athens? The whole afternoon is streamed live on YouTube.</p>
  <div class="a4h-video">
    <iframe src="https://www.youtube.com/embed/L7hRn1h81bM" title="Arch4Health @ MICRO 2026 livestream" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen loading="lazy"></iframe>
  </div>
  <p style="margin-top:0.75rem;"><a href="https://youtube.com/live/L7hRn1h81bM">Open the stream on YouTube</a></p>
</section>

<footer class="a4h-foot">
  Arch4Health is organized by the SAFARI Research Group at ETH Zurich. Questions? Email <a href="mailto:nika.mansourighiasi@safari.ethz.ch">Nika Mansouri Ghiasi</a>.
</footer>

</div>

<script>
(function () {
  var start = Date.parse("2026-11-01T11:00:00Z");   /* 13:00 EET */
  var end   = Date.parse("2026-11-01T15:00:00Z");   /* 17:00 EET */
  var box = document.getElementById("a4h-countdown");

  function pad(n) { return n < 10 ? "0" + n : "" + n; }

  function tick() {
    var now = Date.now();
    if (box) {
      if (now < start) {
        var s = Math.floor((start - now) / 1000);
        var d = Math.floor(s / 86400), h = Math.floor(s % 86400 / 3600), m = Math.floor(s % 3600 / 60), sec = s % 60;
        box.innerHTML = "Starts in <b>" + (d > 0 ? d + "d " : "") + pad(h) + "h " + pad(m) + "m " + pad(sec) + "s</b>";
      } else if (now < end) {
        box.innerHTML = "<b>Happening now</b> — join us in Athens or on the livestream.";
      } else {
        box.textContent = "Thank you for joining us! The recording stays available on YouTube.";
      }
    }
    var rows = document.querySelectorAll(".a4h-program li[data-start]");
    for (var i = 0; i < rows.length; i++) {
      var a = Date.parse("2026-11-01T" + rows[i].getAttribute("data-start") + ":00Z");
      var b = Date.parse("2026-11-01T" + rows[i].getAttribute("data-end") + ":00Z");
      rows[i].classList.toggle("now", now >= a && now < b);
    }
  }

  /* Fallback: hide the theme's site-title heading, whatever the theme */
  var siteTitle = {{ site.title | jsonify }};
  if (siteTitle) {
    var heads = document.querySelectorAll("h1, .site-title, .project-name");
    for (var k = 0; k < heads.length; k++) {
      if (!heads[k].closest(".a4h") && heads[k].textContent.trim() === siteTitle.trim()) heads[k].classList.add("a4h-theme-title-hidden");
    }
  }

  var dates = document.querySelectorAll(".a4h-dates li[data-date]");
  for (var j = 0; j < dates.length; j++) {
    if (Date.now() > Date.parse(dates[j].getAttribute("data-date"))) dates[j].classList.add("past");
  }

  tick();
  setInterval(tick, 1000);
})();
</script>
