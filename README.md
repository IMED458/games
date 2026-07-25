<html lang="ka">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <meta name="theme-color" content="#070816" />
  <title>IMED Games</title>
  <meta name="description" content="IMED Games — ონლაინ თამაშების კოლექცია მეგობრებისთვის." />

  <link rel="preconnect" href="https://fonts.googleapis.com" />
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin />
  <link href="https://fonts.googleapis.com/css2?family=Manrope:wght@500;600;700;800&family=Noto+Sans+Georgian:wght@500;600;700;800&display=swap" rel="stylesheet" />

  <style>
    :root {
      --bg: #070816;
      --surface: rgba(17, 20, 39, .78);
      --text: #f7f8ff;
      --muted: #a8aec7;
      --line: rgba(255,255,255,.10);
      --violet: #8b5cf6;
      --cyan: #22d3ee;
      --radius: 30px;
    }

    * { box-sizing: border-box; }

    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      min-height: 100vh;
      overflow-x: hidden;
      color: var(--text);
      background:
        radial-gradient(circle at 12% 8%, rgba(139,92,246,.18), transparent 30%),
        radial-gradient(circle at 92% 20%, rgba(34,211,238,.13), transparent 28%),
        radial-gradient(circle at 50% 100%, rgba(79,70,229,.16), transparent 38%),
        var(--bg);
      font-family: "Noto Sans Georgian", "Manrope", system-ui, sans-serif;
    }

    body::before {
      content: "";
      position: fixed;
      inset: 0;
      z-index: -3;
      opacity: .35;
      pointer-events: none;
      background-image:
        linear-gradient(rgba(255,255,255,.026) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.026) 1px, transparent 1px);
      background-size: 56px 56px;
      mask-image: linear-gradient(to bottom, #000, transparent 88%);
    }

    a { color: inherit; text-decoration: none; }

    button, a { -webkit-tap-highlight-color: transparent; }

    .orb {
      position: fixed;
      z-index: -2;
      width: 30rem;
      aspect-ratio: 1;
      border-radius: 50%;
      filter: blur(110px);
      opacity: .22;
      pointer-events: none;
      animation: drift 15s ease-in-out infinite;
    }

    .orb.one { top: -15rem; left: -10rem; background: #7c3aed; }
    .orb.two { top: 35%; right: -15rem; background: #0891b2; animation-delay: -6s; }
    .orb.three { bottom: -18rem; left: 38%; background: #4338ca; animation-delay: -10s; }

    @keyframes drift {
      0%,100% { transform: translate3d(0,0,0) scale(1); }
      50% { transform: translate3d(0,35px,0) scale(1.08); }
    }

    .container {
      width: min(1180px, calc(100% - 40px));
      margin-inline: auto;
    }

    .nav-wrap {
      position: sticky;
      top: 0;
      z-index: 100;
      padding-top: 16px;
    }

    nav {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      padding: 12px 14px 12px 18px;
      border: 1px solid var(--line);
      border-radius: 20px;
      background: rgba(8,10,24,.72);
      backdrop-filter: blur(18px);
      -webkit-backdrop-filter: blur(18px);
      box-shadow: 0 12px 42px rgba(0,0,0,.22);
    }

    .brand {
      display: inline-flex;
      align-items: center;
      gap: 12px;
      font-family: "Manrope", sans-serif;
      font-weight: 800;
      letter-spacing: -.035em;
    }

    .brand-mark {
      display: grid;
      place-items: center;
      width: 42px;
      height: 42px;
      border-radius: 14px;
      background: linear-gradient(145deg, #a78bfa, #6366f1 58%, #22d3ee);
      box-shadow: 0 12px 30px rgba(99,102,241,.35), inset 0 1px rgba(255,255,255,.4);
    }

    .brand-mark svg { width: 24px; height: 24px; }

    .brand span span { color: #a8a1ff; }

    .nav-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      min-height: 42px;
      padding: 0 18px;
      border: 1px solid rgba(255,255,255,.10);
      border-radius: 13px;
      background: rgba(255,255,255,.06);
      font-size: .84rem;
      font-weight: 800;
      transition: .2s ease;
    }

    .nav-btn:hover {
      transform: translateY(-2px);
      background: rgba(255,255,255,.11);
    }

    .hero {
      position: relative;
      display: grid;
      place-items: center;
      min-height: 620px;
      padding: 90px 0 74px;
      text-align: center;
    }

    .hero-inner {
      max-width: 900px;
    }

    .eyebrow {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      padding: 8px 13px;
      border: 1px solid rgba(167,139,250,.24);
      border-radius: 999px;
      color: #ddd7ff;
      background: rgba(124,58,237,.10);
      font-size: .78rem;
      font-weight: 800;
    }

    .eyebrow::before {
      content: "";
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: #34d399;
      box-shadow: 0 0 0 5px rgba(52,211,153,.10), 0 0 18px rgba(52,211,153,.7);
    }

    h1 {
      margin: 28px auto 22px;
      font-family: "Manrope", "Noto Sans Georgian", sans-serif;
      font-size: clamp(3rem, 8.2vw, 6.5rem);
      line-height: .97;
      letter-spacing: -.075em;
    }

    .gradient {
      color: transparent;
      background: linear-gradient(110deg, #fff, #c7bbff 42%, #8be8f8 72%, #fff);
      background-size: 200% auto;
      -webkit-background-clip: text;
      background-clip: text;
      animation: shine 8s linear infinite;
    }

    @keyframes shine { to { background-position: 200% center; } }

    .hero p {
      max-width: 650px;
      margin: 0 auto;
      color: var(--muted);
      font-size: clamp(1rem, 2vw, 1.16rem);
      line-height: 1.75;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 12px;
      margin-top: 32px;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      min-height: 54px;
      padding: 0 22px;
      border-radius: 16px;
      font-weight: 800;
      transition: .22s ease;
    }

    .btn.primary {
      background: linear-gradient(135deg, #8b5cf6, #6366f1);
      border: 1px solid rgba(255,255,255,.16);
      box-shadow: 0 18px 42px rgba(99,102,241,.30), inset 0 1px rgba(255,255,255,.25);
    }

    .btn.secondary {
      background: rgba(255,255,255,.055);
      border: 1px solid var(--line);
    }

    .btn:hover { transform: translateY(-3px); }
    .btn svg { width: 18px; height: 18px; }

    .games {
      padding: 26px 0 110px;
    }

    .section-head {
      display: flex;
      align-items: end;
      justify-content: space-between;
      gap: 24px;
      margin-bottom: 30px;
    }

    .kicker {
      color: #9e91ff;
      font-family: "Manrope", sans-serif;
      font-size: .76rem;
      font-weight: 800;
      letter-spacing: .15em;
      text-transform: uppercase;
    }

    .section-head h2 {
      margin: 6px 0 0;
      font-family: "Manrope", "Noto Sans Georgian", sans-serif;
      font-size: clamp(2rem,4vw,3.3rem);
      line-height: 1.05;
      letter-spacing: -.05em;
    }

    .section-head p {
      max-width: 390px;
      margin: 0;
      color: var(--muted);
      font-size: .94rem;
      line-height: 1.7;
    }

    .games-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0,1fr));
      gap: 22px;
    }

    .game-card {
      position: relative;
      min-height: 390px;
      overflow: hidden;
      border: 1px solid var(--line);
      border-radius: var(--radius);
      background: var(--surface);
      box-shadow: 0 28px 80px rgba(0,0,0,.30), inset 0 1px rgba(255,255,255,.06);
      outline: none;
      cursor: pointer;
      transition: transform .28s ease, border-color .28s ease, box-shadow .28s ease;
    }

    .game-card:hover,
    .game-card:focus-visible,
    .game-card.is-active {
      transform: translateY(-8px);
      border-color: rgba(255,255,255,.22);
      box-shadow: 0 36px 100px rgba(0,0,0,.42), 0 0 0 1px rgba(255,255,255,.035) inset;
    }

    .poster {
      position: absolute;
      inset: 0;
      overflow: hidden;
      background: #11152a;
    }

    .poster svg {
      width: 100%;
      height: 100%;
      display: block;
      transition: transform .65s cubic-bezier(.2,.75,.2,1), filter .45s ease;
    }

    .game-card:hover .poster svg,
    .game-card:focus-visible .poster svg,
    .game-card.is-active .poster svg {
      transform: scale(1.07);
      filter: saturate(1.12);
    }

    .poster::after {
      content: "";
      position: absolute;
      inset: 0;
      background:
        linear-gradient(to top, rgba(5,7,18,.96) 0%, rgba(5,7,18,.55) 38%, rgba(5,7,18,.08) 72%),
        linear-gradient(120deg, rgba(255,255,255,.05), transparent 40%);
    }

    .poster-title {
      position: absolute;
      left: 28px;
      right: 28px;
      bottom: 92px;
      z-index: 3;
      margin: 0;
      font-family: "Manrope", "Noto Sans Georgian", sans-serif;
      font-size: clamp(2rem,4.5vw,3.4rem);
      line-height: .98;
      letter-spacing: -.055em;
      text-shadow: 0 10px 30px rgba(0,0,0,.55);
      transform: translateY(18px);
      transition: transform .3s ease;
    }

    .game-card:hover .poster-title,
    .game-card:focus-visible .poster-title,
    .game-card.is-active .poster-title {
      transform: translateY(0);
    }

    .tag {
      position: absolute;
      left: 28px;
      top: 26px;
      z-index: 4;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 8px 12px;
      border: 1px solid rgba(255,255,255,.18);
      border-radius: 999px;
      background: rgba(8,10,24,.40);
      backdrop-filter: blur(12px);
      -webkit-backdrop-filter: blur(12px);
      font-size: .72rem;
      font-weight: 800;
      text-transform: uppercase;
      letter-spacing: .08em;
    }

    .tag::before {
      content: "";
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #fff;
      box-shadow: 0 0 14px rgba(255,255,255,.65);
    }

    .play-overlay {
      position: absolute;
      inset: 0;
      z-index: 5;
      display: grid;
      place-items: center;
      pointer-events: none;
      background: rgba(4,6,16,.20);
      opacity: 0;
      transition: opacity .3s ease;
    }

    .game-card:hover .play-overlay,
    .game-card:focus-visible .play-overlay,
    .game-card.is-active .play-overlay {
      opacity: 1;
      pointer-events: auto;
    }

    .start-btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 11px;
      min-height: 58px;
      padding: 0 24px;
      border: 1px solid rgba(255,255,255,.25);
      border-radius: 18px;
      color: #fff;
      background: rgba(9,11,26,.76);
      box-shadow: 0 18px 46px rgba(0,0,0,.38), inset 0 1px rgba(255,255,255,.17);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      font-family: inherit;
      font-size: .95rem;
      font-weight: 800;
      transform: translateY(18px) scale(.94);
      transition: transform .3s cubic-bezier(.2,.8,.2,1), background .2s ease;
    }

    .game-card:hover .start-btn,
    .game-card:focus-visible .start-btn,
    .game-card.is-active .start-btn {
      transform: translateY(0) scale(1);
    }

    .start-btn:hover {
      background: rgba(109,92,246,.88);
    }

    .start-btn svg { width: 19px; height: 19px; }

    .bottom-info {
      position: absolute;
      left: 28px;
      right: 28px;
      bottom: 25px;
      z-index: 4;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 14px;
      color: #d7dbea;
      font-size: .78rem;
      font-weight: 700;
      transition: opacity .25s ease, transform .25s ease;
    }

    .game-card:hover .bottom-info,
    .game-card:focus-visible .bottom-info,
    .game-card.is-active .bottom-info {
      opacity: 0;
      transform: translateY(10px);
    }

    .status {
      display: inline-flex;
      align-items: center;
      gap: 7px;
      color: #b7bdd2;
    }

    .status::before {
      content: "";
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #34d399;
      box-shadow: 0 0 12px rgba(52,211,153,.8);
    }

    .tap-hint {
      display: none;
      color: #aab0c7;
      font-size: .75rem;
    }

    footer { padding: 0 0 34px; }

    .footer-inner {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 18px;
      padding-top: 22px;
      border-top: 1px solid rgba(255,255,255,.075);
      color: #8c93aa;
      font-size: .82rem;
    }

    .footer-inner strong { color: #c9cce0; }

    .reveal {
      opacity: 0;
      transform: translateY(24px);
      transition: opacity .65s ease, transform .65s ease;
    }

    .reveal.visible {
      opacity: 1;
      transform: none;
    }

    @media (max-width: 920px) {
      .games-grid { grid-template-columns: 1fr; }
      .section-head { align-items: flex-start; flex-direction: column; }
      .game-card { min-height: 430px; }
    }

    @media (max-width: 640px) {
      .container { width: min(100% - 24px, 1180px); }
      .nav-wrap { padding-top: 10px; }
      nav { border-radius: 17px; }
      .nav-btn { padding: 0 13px; font-size: .78rem; }
      .brand { font-size: .92rem; }
      .hero { min-height: auto; padding: 96px 0 82px; }
      .games { padding-bottom: 76px; }
      .game-card { min-height: 390px; }
      .poster-title { left: 22px; right: 22px; bottom: 86px; font-size: 2.35rem; }
      .tag { left: 22px; top: 22px; }
      .bottom-info { left: 22px; right: 22px; bottom: 22px; }
      .tap-hint { display: inline; }
      .footer-inner { align-items: flex-start; flex-direction: column; }
    }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        scroll-behavior: auto !important;
        animation-duration: .01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: .01ms !important;
      }
    }
  </style>
</head>

<body>
  <div class="orb one"></div>
  <div class="orb two"></div>
  <div class="orb three"></div>

  <div class="nav-wrap">
    <div class="container">
      <nav>
        <a class="brand" href="#" aria-label="IMED Games მთავარი">
          <span class="brand-mark" aria-hidden="true">
            <svg viewBox="0 0 24 24" fill="none">
              <path d="M8.4 7.2h7.2a4.9 4.9 0 0 1 4.72 6.23l-.7 2.5a2.05 2.05 0 0 1-3.4.92l-1.28-1.18a2.2 2.2 0 0 0-1.5-.59h-2.88a2.2 2.2 0 0 0-1.5.59l-1.28 1.18a2.05 2.05 0 0 1-3.4-.92l-.7-2.5A4.9 4.9 0 0 1 8.4 7.2Z" fill="white"/>
              <path d="M8.2 10.2v3.1M6.65 11.75h3.1M15.6 10.85h.02M17.35 12.55h.02" stroke="#5B4BE7" stroke-width="1.5" stroke-linecap="round"/>
            </svg>
          </span>
          <span>IMED <span>Games</span></span>
        </a>
        <a class="nav-btn" href="#games">თამაშები</a>
      </nav>
    </div>
  </div>

  <main>
    <section class="hero">
      <div class="container hero-inner">
        <div class="eyebrow reveal">ონლაინ თამაშები მეგობრებისთვის</div>
        <h1 class="reveal">ითამაშე. გაერთე.<br><span class="gradient">შექმენი მოგონებები.</span></h1>
        <p class="reveal">
          აირჩიე თამაში, გახსენი ოთახი და მოიწვიე მეგობრები.
          ყველა თამაში პირდაპირ ბრაუზერში მუშაობს.
        </p>
        <div class="hero-actions reveal">
          <a class="btn primary" href="#games">
            თამაშების ნახვა
            <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
              <path d="m7 10 5 5 5-5" stroke="currentColor" stroke-width="2" stroke-linecap="round"/>
            </svg>
          </a>        </div>
      </div>
    </section>

    <section class="games" id="games">
      <div class="container">
        <div class="section-head reveal">
          <div>
            <div class="kicker">Game Library</div>
            <h2>აირჩიე თამაში</h2>
          </div>
          <p>კურსორი მიიტანე თამაშზე ან ტელეფონზე ერთხელ დააჭირე — გამოჩნდება დაწყების ღილაკი.</p>
        </div>

        <div class="games-grid">
          <!-- DreamClue -->
          <article class="game-card reveal" tabindex="0" aria-label="DreamClue">
            <div class="poster" aria-hidden="true">
              <svg viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice">
                <defs>
                  <linearGradient id="d-bg" x1="0" y1="0" x2="1" y2="1">
                    <stop offset="0" stop-color="#170b35"/>
                    <stop offset=".52" stop-color="#3b1f7a"/>
                    <stop offset="1" stop-color="#0d6a78"/>
                  </linearGradient>
                  <radialGradient id="d-moon">
                    <stop offset="0" stop-color="#fff"/>
                    <stop offset=".52" stop-color="#e9ddff"/>
                    <stop offset="1" stop-color="#a78bfa"/>
                  </radialGradient>
                  <filter id="d-blur"><feGaussianBlur stdDeviation="18"/></filter>
                </defs>
                <rect width="1200" height="800" fill="url(#d-bg)"/>
                <circle cx="930" cy="180" r="170" fill="url(#d-moon)" opacity=".95"/>
                <circle cx="1000" cy="120" r="160" fill="#2c1761"/>
                <g fill="#fff" opacity=".75">
                  <circle cx="130" cy="120" r="4"/><circle cx="240" cy="180" r="3"/><circle cx="520" cy="90" r="4"/>
                  <circle cx="680" cy="170" r="3"/><circle cx="1050" cy="310" r="3"/><circle cx="820" cy="70" r="2"/>
                </g>
                <ellipse cx="310" cy="270" rx="220" ry="75" fill="#5eead4" opacity=".16" filter="url(#d-blur)"/>
                <ellipse cx="620" cy="390" rx="290" ry="110" fill="#c084fc" opacity=".18" filter="url(#d-blur)"/>
                <path d="M0 600C190 510 340 575 500 520s330-120 700-5v285H0Z" fill="#11102e"/>
                <path d="M0 675c210-70 380-25 550-60s420-105 650-30v215H0Z" fill="#090a1c"/>
                <path d="M340 650c55-165 130-250 210-250 105 0 150 95 185 250Z" fill="#1e184d"/>
                <path d="M438 505c25-85 67-126 117-126 56 0 91 48 118 126Z" fill="#30236f"/>
                <g transform="translate(500 355)">
                  <circle cx="58" cy="55" r="28" fill="#f5d0fe"/>
                  <path d="M22 130c12-52 33-78 64-78 32 0 54 26 67 78Z" fill="#ddd6fe"/>
                  <path d="M0 180c26-60 63-90 112-90 45 0 82 30 110 90Z" fill="#7c3aed" opacity=".9"/>
                </g>
              </svg>
            </div>
            <span class="tag">წარმოსახვა</span>
            <h3 class="poster-title">DreamClue</h3>
            <div class="bottom-info">
              <span>ასოციაციებისა და მინიშნებების თამაში</span>
              <span class="status">ონლაინ</span>
            </div>
            <div class="play-overlay">
              <a class="start-btn" href="https://imed458.github.io/dixit/?room=VC824S" target="_blank" rel="noopener noreferrer">
                <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path d="m9 7 8 5-8 5V7Z" fill="currentColor"/>
                </svg>
                თამაშის დაწყება
              </a>
            </div>
          </article>

          <!-- Truth or Dare -->
          <article class="game-card reveal" tabindex="0" aria-label="სიმართლე თუ მოქმედება">
            <div class="poster" aria-hidden="true">
              <svg viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice">
                <defs>
                  <linearGradient id="t-bg" x1="0" y1="0" x2="1" y2="1">
                    <stop offset="0" stop-color="#3a0b23"/>
                    <stop offset=".52" stop-color="#a61d45"/>
                    <stop offset="1" stop-color="#f59e0b"/>
                  </linearGradient>
                  <radialGradient id="t-glow">
                    <stop offset="0" stop-color="#fff1cc"/>
                    <stop offset=".35" stop-color="#fb7185" stop-opacity=".65"/>
                    <stop offset="1" stop-color="#fb7185" stop-opacity="0"/>
                  </radialGradient>
                </defs>
                <rect width="1200" height="800" fill="url(#t-bg)"/>
                <circle cx="890" cy="250" r="330" fill="url(#t-glow)"/>
                <g opacity=".32" fill="none" stroke="#fff" stroke-width="8">
                  <circle cx="160" cy="140" r="55"/><path d="M130 140h60M160 110v60"/>
                  <path d="M1020 115l40 40m0-40-40 40"/>
                </g>
                <path d="M0 690c150-90 320-75 470-20 180 65 320 45 730-50v180H0Z" fill="#240914" opacity=".72"/>
                <g transform="translate(545 145) rotate(-8 70 100)">
                  <circle cx="70" cy="70" r="63" fill="#fff" opacity=".96"/>
                  <path d="M12 69c2-32 27-52 61-52 35 0 61 20 61 52 0 23-12 37-34 50-21 12-28 20-28 38v5H34v-7c0-27 12-42 35-56 18-11 25-18 25-30 0-13-10-22-24-22-15 0-25 9-27 25Z" fill="#e11d48"/>
                  <circle cx="53" cy="179" r="16" fill="#e11d48"/>
                </g>
                <g fill="#fff" opacity=".7">
                  <circle cx="240" cy="360" r="5"/><circle cx="340" cy="230" r="4"/><circle cx="970" cy="480" r="5"/>
                  <circle cx="1090" cy="350" r="3"/><circle cx="410" cy="110" r="3"/>
                </g>
                <path d="M140 540c105-130 210-135 315 0" fill="none" stroke="#fff" stroke-opacity=".15" stroke-width="20" stroke-linecap="round"/>
                <path d="M785 570c85-112 180-118 286 0" fill="none" stroke="#fff" stroke-opacity=".13" stroke-width="18" stroke-linecap="round"/>
              </svg>
            </div>
            <span class="tag">წვეულება</span>
            <h3 class="poster-title">სიმართლე თუ<br>მოქმედება</h3>
            <div class="bottom-info">
              <span>მხიარული კითხვები და დავალებები</span>
              <span class="status">ონლაინ</span>
            </div>
            <div class="play-overlay">
              <a class="start-btn" href="https://imed458.github.io/TruthorDare/" target="_blank" rel="noopener noreferrer">
                <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path d="m9 7 8 5-8 5V7Z" fill="currentColor"/>
                </svg>
                თამაშის დაწყება
              </a>
            </div>
          </article>

          <!-- Secret Hitler -->
          <article class="game-card reveal" tabindex="0" aria-label="Secret Hitler">
            <div class="poster" aria-hidden="true">
              <svg viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice">
                <defs>
                  <linearGradient id="s-bg" x1="0" y1="0" x2="1" y2="1">
                    <stop offset="0" stop-color="#100e13"/>
                    <stop offset=".55" stop-color="#30211f"/>
                    <stop offset="1" stop-color="#7f1d1d"/>
                  </linearGradient>
                  <linearGradient id="s-card" x1="0" y1="0" x2="1" y2="1">
                    <stop stop-color="#fff8e7"/>
                    <stop offset="1" stop-color="#d6c7aa"/>
                  </linearGradient>
                </defs>
                <rect width="1200" height="800" fill="url(#s-bg)"/>
                <circle cx="950" cy="160" r="250" fill="#ef4444" opacity=".16"/>
                <path d="M0 610c190-65 320-60 530-15 250 54 430 20 670-50v255H0Z" fill="#09090b" opacity=".78"/>
                <g opacity=".18" stroke="#fff" fill="none">
                  <path d="M90 110h330v210H90z" stroke-width="8"/>
                  <path d="M790 430h300v170H790z" stroke-width="7"/>
                </g>
                <g transform="translate(475 120) rotate(-4)">
                  <rect x="0" y="0" width="285" height="390" rx="20" fill="url(#s-card)" stroke="#f8ead0" stroke-width="7"/>
                  <rect x="25" y="24" width="235" height="72" rx="10" fill="#991b1b"/>
                  <circle cx="142.5" cy="196" r="74" fill="#201616"/>
                  <path d="M97 285h91M97 316h72" stroke="#7f1d1d" stroke-width="14" stroke-linecap="round"/>
                  <path d="M110 170c18-42 82-42 101 0" fill="none" stroke="#e7d6b8" stroke-width="17" stroke-linecap="round"/>
                  <path d="M117 235c17 23 37 34 61 34 25 0 45-11 60-34" fill="none" stroke="#e7d6b8" stroke-width="16" stroke-linecap="round"/>
                </g>
                <g fill="#fff" opacity=".55">
                  <circle cx="140" cy="500" r="4"/><circle cx="270" cy="180" r="3"/><circle cx="960" cy="330" r="4"/>
                  <circle cx="1060" cy="210" r="3"/><circle cx="820" cy="110" r="2"/>
                </g>
              </svg>
            </div>
            <span class="tag">სოციალური დედუქცია</span>
            <h3 class="poster-title">Secret Hitler</h3>
            <div class="bottom-info">
              <span>ნდობა, ბლეფი და ფარული როლები</span>
              <span class="status">ონლაინ</span>
            </div>
            <div class="play-overlay">
              <a class="start-btn" href="https://imed458.github.io/secrethitleronline.github.io/" target="_blank" rel="noopener noreferrer">
                <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path d="m9 7 8 5-8 5V7Z" fill="currentColor"/>
                </svg>
                თამაშის დაწყება
              </a>
            </div>
          </article>

          <!-- Bura -->
          <article class="game-card reveal" tabindex="0" aria-label="ბურა">
            <div class="poster" aria-hidden="true">
              <svg viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice">
                <defs>
                  <linearGradient id="b-bg" x1="0" y1="0" x2="1" y2="1">
                    <stop offset="0" stop-color="#06261d"/>
                    <stop offset=".55" stop-color="#0f766e"/>
                    <stop offset="1" stop-color="#14532d"/>
                  </linearGradient>
                  <linearGradient id="b-card" x1="0" y1="0" x2="1" y2="1">
                    <stop stop-color="#fff"/>
                    <stop offset="1" stop-color="#d1fae5"/>
                  </linearGradient>
                </defs>
                <rect width="1200" height="800" fill="url(#b-bg)"/>
                <circle cx="920" cy="170" r="270" fill="#22c55e" opacity=".12"/>
                <path d="M0 635c190-90 360-70 540-25 240 60 430 40 660-40v230H0Z" fill="#021b14" opacity=".82"/>
                <g transform="translate(395 120)">
                  <g transform="rotate(-11 150 210)">
                    <rect x="0" y="0" width="260" height="390" rx="22" fill="url(#b-card)" stroke="#f0fff7" stroke-width="7"/>
                    <text x="28" y="55" fill="#15803d" font-family="Manrope, sans-serif" font-size="42" font-weight="800">A</text>
                    <path d="M62 74c-18-27-52-17-52 10 0 28 52 58 52 58s52-30 52-58c0-27-34-37-52-10Z" transform="translate(88 105)" fill="#16a34a"/>
                    <text x="208" y="355" fill="#15803d" font-family="Manrope, sans-serif" font-size="42" font-weight="800">A</text>
                  </g>
                  <g transform="translate(175 25) rotate(10 150 210)">
                    <rect x="0" y="0" width="260" height="390" rx="22" fill="#fff" stroke="#ecfdf5" stroke-width="7"/>
                    <text x="28" y="55" fill="#dc2626" font-family="Manrope, sans-serif" font-size="42" font-weight="800">K</text>
                    <path d="M58 26c-18 0-33 14-33 32 0 25 33 47 33 47s33-22 33-47c0-18-15-32-33-32Z" transform="translate(74 115)" fill="#dc2626"/>
                    <path d="M58 26c-18 0-33 14-33 32 0 25 33 47 33 47s33-22 33-47c0-18-15-32-33-32Z" transform="translate(74 190)" fill="#dc2626"/>
                    <text x="205" y="355" fill="#dc2626" font-family="Manrope, sans-serif" font-size="42" font-weight="800">K</text>
                  </g>
                </g>
                <g fill="#fff" opacity=".55">
                  <circle cx="130" cy="170" r="4"/><circle cx="230" cy="320" r="3"/><circle cx="990" cy="420" r="5"/>
                  <circle cx="1080" cy="300" r="3"/><circle cx="840" cy="90" r="2"/>
                </g>
              </svg>
            </div>
            <span class="tag">კარტის თამაში</span>
            <h3 class="poster-title">ბურა</h3>
            <div class="bottom-info">
              <span>სწრაფი და აზარტული კარტის თამაში</span>
              <span class="status">ონლაინ</span>
            </div>
            <div class="play-overlay">
              <a class="start-btn" href="http://bura.imed.com.ge/" target="_blank" rel="noopener noreferrer">
                <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path d="m9 7 8 5-8 5V7Z" fill="currentColor"/>
                </svg>
                თამაშის დაწყება
              </a>
            </div>
          </article>

          <!-- Spy -->
          <article class="game-card reveal" tabindex="0" aria-label="ჯაშუში">
            <div class="poster" aria-hidden="true">
              <svg viewBox="0 0 1200 800" preserveAspectRatio="xMidYMid slice">
                <defs>
                  <linearGradient id="sp-bg" x1="0" y1="0" x2="1" y2="1">
                    <stop offset="0" stop-color="#080b16"/>
                    <stop offset=".55" stop-color="#241b57"/>
                    <stop offset="1" stop-color="#4338ca"/>
                  </linearGradient>
                  <radialGradient id="sp-glow">
                    <stop offset="0" stop-color="#c7d2fe" stop-opacity=".9"/>
                    <stop offset=".4" stop-color="#818cf8" stop-opacity=".45"/>
                    <stop offset="1" stop-color="#818cf8" stop-opacity="0"/>
                  </radialGradient>
                  <linearGradient id="sp-lens" x1="0" y1="0" x2="1" y2="1">
                    <stop stop-color="#a5b4fc" stop-opacity=".85"/>
                    <stop offset="1" stop-color="#6366f1" stop-opacity=".55"/>
                  </linearGradient>
                </defs>
                <rect width="1200" height="800" fill="url(#sp-bg)"/>
                <circle cx="470" cy="300" r="360" fill="url(#sp-glow)"/>
                <g fill="#fff" opacity=".7">
                  <circle cx="180" cy="130" r="4"/><circle cx="300" cy="220" r="3"/><circle cx="980" cy="180" r="4"/>
                  <circle cx="1080" cy="330" r="3"/><circle cx="860" cy="90" r="2"/><circle cx="150" cy="420" r="3"/>
                </g>
                <path d="M0 660c190-70 360-55 540-15 240 55 430 35 660-40v195H0Z" fill="#070a15" opacity=".8"/>
                <g transform="translate(360 150)" fill="#0b0f1e">
                  <path d="M60 430c0-120 70-190 160-190s160 70 160 190Z"/>
                  <circle cx="220" cy="180" r="72"/>
                  <ellipse cx="220" cy="118" rx="140" ry="30"/>
                  <path d="M150 120c0-52 30-84 70-84s70 32 70 84Z"/>
                  <rect x="150" y="96" width="140" height="18" rx="9" fill="#4338ca"/>
                </g>
                <g transform="translate(690 360) rotate(20)">
                  <circle cx="0" cy="0" r="120" fill="url(#sp-lens)" stroke="#e0e7ff" stroke-width="16"/>
                  <circle cx="0" cy="0" r="120" fill="none" stroke="#312e81" stroke-width="4" opacity=".6"/>
                  <path d="M92 92l120 120" stroke="#e0e7ff" stroke-width="42" stroke-linecap="round"/>
                  <path d="M92 92l120 120" stroke="#c7d2fe" stroke-width="18" stroke-linecap="round"/>
                  <path d="M-55 -30a70 70 0 0 1 40 -40" fill="none" stroke="#fff" stroke-width="10" stroke-linecap="round" opacity=".7"/>
                </g>
              </svg>
            </div>
            <span class="tag">ბლეფი და დედუქცია</span>
            <h3 class="poster-title">ჯაშუში</h3>
            <div class="bottom-info">
              <span>იპოვე ჯაშუში ან გამოიცანი სიტყვა</span>
              <span class="status">ონლაინ</span>
            </div>
            <div class="play-overlay">
              <a class="start-btn" href="https://imed458.github.io/Spy/" target="_blank" rel="noopener noreferrer">
                <svg viewBox="0 0 24 24" fill="none" aria-hidden="true">
                  <path d="m9 7 8 5-8 5V7Z" fill="currentColor"/>
                </svg>
                თამაშის დაწყება
              </a>
            </div>
          </article>
        </div>

        <p class="tap-hint">ტელეფონზე: ჯერ შეეხე ბარათს, შემდეგ დააჭირე ღილაკს.</p>
      </div>
    </section>
  </main>

  <footer>
    <div class="container footer-inner">
      <div><strong>IMED Games</strong> © <span id="year"></span></div>
      <div>შექმნილია მეგობრებთან ერთად გასართობად</div>
    </div>
  </footer>

  <script>
    document.getElementById("year").textContent = new Date().getFullYear();

    const revealItems = document.querySelectorAll(".reveal");
    const revealObserver = new IntersectionObserver(
      entries => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            entry.target.classList.add("visible");
            revealObserver.unobserve(entry.target);
          }
        });
      },
      { threshold: 0.12 }
    );

    revealItems.forEach((item, index) => {
      item.style.transitionDelay = `${Math.min(index * 70, 280)}ms`;
      revealObserver.observe(item);
    });

    const cards = document.querySelectorAll(".game-card");

    cards.forEach(card => {
      card.addEventListener("click", event => {
        const clickedButton = event.target.closest(".start-btn");
        if (clickedButton) return;

        cards.forEach(other => {
          if (other !== card) other.classList.remove("is-active");
        });

        card.classList.toggle("is-active");
      });

      card.addEventListener("keydown", event => {
        if (event.key === "Enter" || event.key === " ") {
          event.preventDefault();
          card.classList.toggle("is-active");
        }
      });
    });

    document.addEventListener("click", event => {
      if (!event.target.closest(".game-card")) {
        cards.forEach(card => card.classList.remove("is-active"));
      }
    });
  </script>
</body>
</html>
