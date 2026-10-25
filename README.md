
<!DOCTYPE html>
<html lang="es" data-theme="system">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="theme-color" content="#f5f6fb">
  <meta name="description" content="Portafolio de SebasDev, desarrollador de software. Proyectos web, aplicaciones móviles y tecnología.">
  <title>SebasDev — Software Developer</title>

  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=DM+Sans:wght@400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">

  <style>
    :root {
      color-scheme: light;
      --bg: #f5f6fb;
      --text: #191a25;
      --muted: #696b7c;
      --surface: rgba(255,255,255,.64);
      --surface-solid: rgba(255,255,255,.88);
      --border: rgba(255,255,255,.85);
      --line: rgba(80,80,120,.13);
      --accent: #6757e8;
      --accent2: #a06de8;
      --shadow: 0 16px 50px rgba(39,40,80,.09);
      --content: 1120px;
    }

    :root[data-theme="dark"] {
      color-scheme: dark;
      --bg: #101116;
      --text: #f4f3fc;
      --muted: #a4a5b7;
      --surface: rgba(30,31,44,.69);
      --surface-solid: rgba(25,26,37,.92);
      --border: rgba(255,255,255,.13);
      --line: rgba(255,255,255,.12);
      --accent: #a79aff;
      --accent2: #7eb7ff;
      --shadow: 0 16px 50px rgba(0,0,0,.24);
    }

    @media (prefers-color-scheme: dark) {
      :root:not([data-theme="light"]) {
        color-scheme: dark;
      }
    }

    * { box-sizing: border-box; }

    html {
      scroll-behavior: smooth;
      scroll-padding-top: 100px;
    }

    body {
      margin: 0;
      overflow-x: hidden;
      background:
        radial-gradient(ellipse at 10% 5%, rgba(151,130,255,.14), transparent 35rem),
        radial-gradient(ellipse at 95% 40%, rgba(91,170,255,.12), transparent 30rem),
        var(--bg);
      color: var(--text);
      font-family: "DM Sans", sans-serif;
      line-height: 1.7;
      transition: background .25s, color .25s;
    }

    a { color: inherit; text-decoration: none; }
    button { font: inherit; }
    a:focus-visible, button:focus-visible {
      outline: 3px solid var(--accent);
      outline-offset: 4px;
    }

    .container {
      width: min(var(--content), calc(100% - 40px));
      margin-inline: auto;
    }

    .glass {
      background: var(--surface);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      -webkit-backdrop-filter: blur(22px) saturate(145%);
      backdrop-filter: blur(22px) saturate(145%);
    }

    /* Navegación */

    .navbar {
      position: sticky;
      top: 12px;
      z-index: 100;
      width: min(1160px, calc(100% - 24px));
      margin: 12px auto 0;
      min-height: 66px;
      padding: 9px 14px 9px 19px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 16px;
      border-radius: 22px;
      background: var(--surface-solid);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      -webkit-backdrop-filter: blur(28px) saturate(160%);
      backdrop-filter: blur(28px) saturate(160%);
    }

    .brand {
      display: flex;
      align-items: center;
      gap: 10px;
      font-family: "Space Grotesk", sans-serif;
      font-weight: 700;
      letter-spacing: -.04em;
      white-space: nowrap;
    }

    .brand-icon {
      width: 35px;
      height: 35px;
      display: grid;
      place-items: center;
      color: white;
      border-radius: 12px;
      background: linear-gradient(135deg, #9282ff, #5745d6);
      box-shadow: 0 6px 18px rgba(103,87,232,.3);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 23px;
    }

    .nav-links a {
      font-size: 12px;
      font-weight: 600;
      color: var(--muted);
      transition: color .2s;
    }

    .nav-links a:hover,
    .nav-links a.active { color: var(--accent); }

    .nav-actions { display: flex; gap: 9px; align-items: center; }

    .theme-button {
      width: 40px;
      height: 40px;
      display: grid;
      place-items: center;
      border-radius: 14px;
      border: 1px solid var(--line);
      background: var(--surface);
      color: var(--text);
      cursor: pointer;
    }

    .theme-button svg {
      width: 19px;
      fill: none;
      stroke: currentColor;
      stroke-width: 1.7;
      stroke-linecap: round;
    }

    .button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 9px;
      min-height: 46px;
      padding: 0 18px;
      border-radius: 14px;
      font-size: 12px;
      font-weight: 700;
      border: 1px solid transparent;
      transition: transform .2s, box-shadow .2s, background .2s;
      cursor: pointer;
    }

    .button:hover { transform: translateY(-2px); }

    .primary {
      color: white;
      background: linear-gradient(135deg, #7969f3, #5947d6);
      box-shadow: 0 8px 22px rgba(103,87,232,.24);
    }

    .secondary {
      color: var(--text);
      border-color: var(--line);
      background: var(--surface);
    }

    /* Presentación */

    .hero {
      min-height: 620px;
      display: grid;
      grid-template-columns: 1.1fr .9fr;
      align-items: center;
      gap: 45px;
      padding-top: 65px;
      padding-bottom: 65px;
    }

    .availability {
      display: inline-flex;
      align-items: center;
      gap: 9px;
      padding: 7px 12px;
      border: 1px solid var(--line);
      border-radius: 99px;
      background: var(--surface);
      color: var(--muted);
      font-size: 11px;
    }

    .dot {
      width: 7px;
      height: 7px;
      border-radius: 50%;
      background: #36c994;
      box-shadow: 0 0 0 4px rgba(54,201,148,.12);
    }

    .eyebrow {
      margin: 27px 0 12px;
      color: var(--accent);
      font-size: 10px;
      font-weight: 700;
      letter-spacing: .19em;
    }

    h1, h2, h3 {
      font-family: "Space Grotesk", sans-serif;
      letter-spacing: -.055em;
      line-height: 1.15;
    }

    h1 {
      max-width: 650px;
      margin: 0 0 20px;
      font-size: clamp(43px, 5.7vw, 70px);
      font-weight: 600;
    }

    .gradient {
      color: var(--accent);
      background: linear-gradient(100deg, #8371f5, #aa6de9, #4c9ee8);
      -webkit-background-clip: text;
      background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero-description {
      max-width: 520px;
      color: var(--muted);
      font-size: 15px;
      line-height: 1.9;
    }

    .role-line {
      min-height: 34px;
      display: flex;
      align-items: center;
      flex-wrap: wrap;
      gap: 7px;
      margin: 20px 0 24px;
      font-size: 11px;
    }

    .role-label { color: var(--muted); }
    #roleText { font-weight: 700; }

    .hero-actions { display: flex; flex-wrap: wrap; gap: 11px; }

    .social-links {
      display: flex;
      gap: 22px;
      margin-top: 27px;
    }

    .social-links a {
      font-size: 11px;
      color: var(--muted);
      font-weight: 700;
    }

    .social-links a:hover { color: var(--accent); }

    /* Tarjeta de perfil */

    .visual {
      min-height: 440px;
      display: grid;
      place-items: center;
      position: relative;
    }

    .orbit {
      position: absolute;
      width: 340px;
      height: 410px;
      border: 1px solid var(--line);
      border-radius: 50%;
      transform: rotate(35deg);
    }

    .orbit-two {
      width: 390px;
      height: 290px;
      transform: rotate(-25deg);
      border-style: dashed;
    }

    .profile-card {
      position: relative;
      z-index: 2;
      width: min(330px, 85%);
      padding: 23px;
      border-radius: 30px;
      transform: rotate(2deg);
      transition: transform .35s;
    }

    .profile-card:hover { transform: rotate(0) translateY(-5px); }

    .window-dots { display: flex; gap: 5px; }
    .window-dots span { width: 6px; height: 6px; border-radius: 50%; background: #ff777b; }
    .window-dots span:nth-child(2) { background: #ffc65b; }
    .window-dots span:nth-child(3) { background: #54c995; }

    .profile-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }

    .mini-label { color: var(--muted); font-size: 8px; letter-spacing: .12em; }

    .avatar {
      width: 83px;
      height: 83px;
      display: grid;
      place-items: center;
      margin: 27px auto 15px;
      border-radius: 27px;
      background: linear-gradient(145deg, #aa9cff, #6855dd 65%, #4c90e8);
      color: white;
      box-shadow: 0 15px 35px rgba(104,84,221,.28);
      font: 700 24px "Space Grotesk", sans-serif;
      transform: rotate(-5deg);
    }

    .profile-kicker {
      margin: 0;
      text-align: center;
      font-size: 8px;
      font-weight: 700;
      color: var(--muted);
      letter-spacing: .15em;
    }

    .profile-card h2 {
      text-align: center;
      font-size: 34px;
      margin: 5px 0 0;
    }

    .profile-card h2 span { color: var(--accent); }

    .profile-subtitle {
      text-align: center;
      color: var(--muted);
      font-size: 11px;
      margin: 0;
    }

    .profile-divider { height: 1px; background: var(--line); margin: 21px 0 14px; }

    .profile-row {
      display: flex;
      justify-content: space-between;
      gap: 10px;
      margin-top: 10px;
      font-size: 9px;
    }

    .profile-row span { color: var(--muted); }
    .profile-row strong { text-align: right; }

    .floating-chip {
      position: absolute;
      z-index: 3;
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 10px 13px;
      border-radius: 14px;
      background: var(--surface-solid);
      border: 1px solid var(--border);
      box-shadow: var(--shadow);
      font-size: 10px;
      font-weight: 700;
    }

    .chip-one { top: 75px; right: -3px; transform: rotate(5deg); }
    .chip-two { bottom: 52px; left: -3px; transform: rotate(-5deg); }
    .chip-icon {
      width: 24px;
      height: 24px;
      display: grid;
      place-items: center;
      border-radius: 8px;
      background: var(--accent);
      color: white;
    }

    /* Bloques */

    .quick-strip {
      display: flex;
      justify-content: space-around;
      gap: 15px;
      padding: 21px;
      border-radius: 21px;
    }

    .quick-strip div {
      display: flex;
      gap: 10px;
      align-items: center;
      font-size: 11px;
      color: var(--muted);
      font-weight: 600;
    }

    .quick-strip b { color: var(--accent); }

    .section { padding-top: 115px; }

    .section-heading { margin-bottom: 30px; }

    .section-heading .eyebrow { margin-top: 0; }

    .section-heading h2 {
      font-size: clamp(32px, 4vw, 47px);
      margin: 0;
    }

    .muted-heading { color: var(--muted); }

    .section-description {
      max-width: 570px;
      margin: 14px 0 0;
      color: var(--muted);
      font-size: 13px;
    }

    .about-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 15px;
    }

    .about-card {
      padding: 24px;
      border-radius: 22px;
      transition: transform .25s, box-shadow .25s;
    }

    .about-card:hover, .tech-card:hover, .project-card:hover {
      transform: translateY(-4px);
      box-shadow: 0 23px 55px rgba(50,50,90,.14);
    }

    .about-icon {
      width: 43px;
      height: 43px;
      display: grid;
      place-items: center;
      margin-bottom: 20px;
      border-radius: 15px;
      background: var(--accent);
      color: white;
      font-size: 18px;
    }

    .about-card h3 { font-size: 18px; margin: 0 0 10px; }
    .about-card p { font-size: 12px; color: var(--muted); margin: 0; }

    /* Tecnologías */

    .tech-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 12px;
    }

    .tech-card {
      display: flex;
      align-items: center;
      gap: 11px;
      min-width: 0;
      padding: 15px 12px;
      border-radius: 17px;
      transition: transform .25s, box-shadow .25s;
    }

    .tech-symbol {
      flex: 0 0 38px;
      height: 38px;
      display: grid;
      place-items: center;
      border-radius: 12px;
      color: var(--accent);
      background: rgba(115,99,230,.12);
      font-size: 12px;
      font-weight: 700;
    }

    .tech-info { min-width: 0; }
    .tech-info strong { display: block; font-size: 11px; }
    .tech-info small { display: block; color: var(--muted); font-size: 9px; }

    .footnote { margin-top: 15px; font-size: 10px; color: var(--muted); }

    /* Proyectos */

    .section-title-row {
      display: flex;
      justify-content: space-between;
      align-items: end;
      gap: 20px;
    }

    .text-link { color: var(--accent); font-size: 11px; font-weight: 700; }

    .project-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 17px;
    }

    .project-card {
      overflow: hidden;
      border-radius: 25px;
      transition: transform .25s, box-shadow .25s;
    }

    .project-art {
      height: 190px;
      position: relative;
      display: grid;
      place-items: center;
      overflow: hidden;
      background: linear-gradient(135deg, #d9d1ff, #a99bf9 48%, #7a70d9);
    }

    .project-art.blue {
      background: linear-gradient(135deg, #c6e6ff, #83b7ed 50%, #6888df);
    }

    :root[data-theme="dark"] .project-art {
      background: linear-gradient(135deg, #3a315f, #5144a0 55%, #292c5b);
    }

    :root[data-theme="dark"] .project-art.blue {
      background: linear-gradient(135deg, #203e5c, #315f91 55%, #343d80);
    }

    .orb {
      position: absolute;
      width: 200px;
      height: 200px;
      border: 1px solid rgba(255,255,255,.45);
      border-radius: 50%;
      box-shadow: inset 0 0 40px rgba(255,255,255,.18);
    }

    .orb::before, .orb::after {
      content: "";
      position: absolute;
      inset: 20px -15px;
      border: 1px solid rgba(255,255,255,.4);
      border-radius: 50%;
      transform: rotate(55deg);
    }

    .orb::after { transform: rotate(-55deg); }

    .project-art-label {
      position: absolute;
      top: 17px;
      left: 18px;
      color: rgba(35,35,70,.65);
      font-size: 9px;
      font-weight: 700;
      letter-spacing: .15em;
    }

    .project-glyph {
      position: relative;
      color: white;
      font: 600 60px "Space Grotesk", sans-serif;
      text-shadow: 0 8px 25px rgba(40,30,100,.2);
    }

    .project-body { padding: 22px; }
    .project-meta { display: flex; justify-content: space-between; gap: 10px; color: var(--muted); font-size: 9px; }
    .project-body h3 { margin: 13px 0 8px; font-size: 24px; }
    .project-body p { min-height: 60px; color: var(--muted); font-size: 12px; }
    .tags { display: flex; flex-wrap: wrap; gap: 7px; }

    .tags span {
      padding: 5px 9px;
      border: 1px solid var(--line);
      border-radius: 8px;
      color: var(--muted);
      font-size: 9px;
    }

    .project-link {
      display: flex;
      justify-content: space-between;
      margin-top: 18px;
      padding-top: 15px;
      border-top: 1px solid var(--line);
      font-size: 11px;
      font-weight: 700;
    }

    .project-link span { color: var(--accent); }

    /* GitHub */

    .stats-grid {
      display: grid;
      grid-template-columns: repeat(2, minmax(0, 1fr));
      gap: 15px;
    }

    .stats-card {
      min-width: 0;
      overflow: hidden;
      padding: 17px;
      border-radius: 20px;
    }

    .stats-card h3 {
      color: var(--muted);
      font: 700 9px "DM Sans", sans-serif;
      letter-spacing: .12em;
    }

    .stats-card img { display: block; width: 100%; height: auto; }
    .stats-wide { grid-column: 1 / -1; }
    .stats-wide img { width: auto; max-width: 100%; margin: auto; }

    .center-button { display: flex; width: fit-content; margin: 22px auto 0; }

    /* Contacto */

    .contact-card {
      position: relative;
      overflow: hidden;
      isolation: isolate;
      padding: clamp(35px, 6vw, 65px);
      border-radius: 30px;
      text-align: center;
    }

    .contact-card::before {
      content: "";
      position: absolute;
      z-index: -1;
      width: 430px;
      height: 300px;
      top: -180px;
      left: 50%;
      transform: translateX(-50%);
      border-radius: 50%;
      background: rgba(135,113,255,.18);
      filter: blur(70px);
    }

    .contact-card h2 { margin: 0; font-size: clamp(36px, 5vw, 57px); }
    .contact-card p { max-width: 450px; margin: 18px auto 25px; color: var(--muted); font-size: 13px; }
    .contact-actions { display: flex; flex-wrap: wrap; justify-content: center; gap: 11px; }

    /* Footer y menú de temas */

    footer {
      display: flex;
      justify-content: space-between;
      align-items: center;
      gap: 20px;
      margin-top: 45px;
      padding-top: 28px;
      padding-bottom: 30px;
      border-top: 1px solid var(--line);
    }

    footer p, footer a { color: var(--muted); font-size: 10px; margin: 0; }

    .theme-menu {
      position: fixed;
      z-index: 200;
      top: 82px;
      right: max(22px, calc((100vw - 1160px) / 2 + 115px));
      width: 180px;
      padding: 7px;
      border-radius: 17px;
    }

    .theme-menu[hidden] { display: none; }

    .theme-menu button {
      width: 100%;
      display: flex;
      justify-content: space-between;
      padding: 10px;
      border: 0;
      border-radius: 10px;
      background: transparent;
      color: var(--text);
      text-align: left;
      cursor: pointer;
      font-size: 12px;
    }

    .theme-menu button:hover { background: var(--surface); }
    .check { color: var(--accent); }

    @media (max-width: 850px) {
      .nav-links { gap: 12px; }
      .nav-links a { font-size: 10px; }
      .hero { gap: 20px; }
      .tech-grid { grid-template-columns: repeat(2, 1fr); }
    }

    @media (max-width: 650px) {
      html { scroll-padding-top: 85px; }
      .container { width: calc(100% - 32px); }
      .navbar { top: 7px; width: calc(100% - 16px); margin-top: 8px; min-height: 58px; padding: 8px 9px 8px 12px; }
      .brand { gap: 7px; font-size: 13px; }
      .brand-icon { width: 30px; height: 30px; }
      .nav-links { display: none; }
      .nav-actions { margin-left: auto; }
      .nav-actions .button { min-height: 38px; padding: 0 11px; font-size: 10px; }
      .theme-button { width: 37px; height: 37px; }
      .theme-menu { top: 72px; right: 75px; }
      .hero { display: flex; flex-direction: column; align-items: stretch; gap: 15px; min-height: auto; padding-top: 75px; padding-bottom: 45px; }
      h1 { font-size: clamp(42px, 12vw, 59px); }
      .hero-description { font-size: 14px; }
      .visual { min-height: 400px; }
      .profile-card { width: min(320px, 83%); }
      .orbit { width: 290px; height: 350px; }
      .orbit-two { width: 330px; height: 260px; }
      .chip-one { right: 0; }
      .chip-two { left: 0; }
      .quick-strip { flex-direction: column; gap: 13px; padding: 19px; }
      .section { padding-top: 80px; }
      .section-title-row { align-items: flex-start; flex-direction: column; }
      .about-grid, .project-grid, .stats-grid { grid-template-columns: 1fr; }
      .stats-wide { grid-column: auto; }
      .project-body p { min-height: 0; }
      .contact-card { padding: 37px 20px; }
      footer { display: grid; grid-template-columns: 1fr auto; gap: 12px; }
      footer p { grid-column: 1 / -1; grid-row: 2; }
    }

    @media (max-width: 370px) {
      .hero-actions .button { width: 100%; }
      .tech-card { gap: 7px; padding: 11px 8px; }
      .tech-symbol { flex-basis: 31px; height: 31px; }
    }

    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after {
        scroll-behavior: auto !important;
        animation-duration: .01ms !important;
        animation-iteration-count: 1 !important;
        transition-duration: .01ms !important;
      }
    }

    @supports not ((backdrop-filter: blur(1px)) or (-webkit-backdrop-filter: blur(1px))) {
      .glass, .navbar, .floating-chip, .theme-menu { background: var(--surface-solid); }
    }
  </style>
</head>

<body>
  <header class="navbar">
    <a class="brand" href="#inicio" aria-label="SebasDev inicio">
      <span class="brand-icon">S.</span>
      <span>SebasDev</span>
    </a>

    <nav class="nav-links" aria-label="Navegación principal">
      <a href="#sobre-mi">Sobre mí</a>
      <a href="#tecnologias">Tecnologías</a>
      <a href="#proyectos">Proyectos</a>
      <a href="#contacto">Contacto</a>
    </nav>

    <div class="nav-actions">
      <button class="theme-button" id="themeButton" aria-label="Preferencias de tema" aria-expanded="false" aria-haspopup="true" title="Cambiar tema">
        <svg viewBox="0 0 24 24" aria-hidden="true">
          <circle cx="12" cy="12" r="4"></circle>
          <path d="M12 2v2m0 16v2M4.93 4.93l1.42 1.42m11.3 11.3 1.42 1.42M2 12h2m16 0h2M4.93 19.07l1.42-1.42m11.3-11.3 1.42-1.42"></path>
        </svg>
      </button>
      <a class="button primary" href="#contacto">Hablemos ↗</a>
    </div>
  </header>

  <main>
    <section class="hero container" id="inicio">
      <div>
        <div class="availability"><span class="dot"></span> Siempre aprendiendo y construyendo</div>
        <p class="eyebrow">HOLA, SOY SEBASDEV</p>
        <h1>Ideas que se convierten en <span class="gradient">software.</span></h1>
        <p class="hero-description">
          Soy desarrollador de software y estudiante de Sistemas.
          Me gusta resolver problemas, construir experiencias digitales
          y aprender algo nuevo con cada proyecto.
        </p>

        <div class="role-line" aria-live="polite">
          <span class="role-label">Explorando:</span>
          <span id="roleText">Java y programación orientada a objetos</span>
        </div>

        <div class="hero-actions">
          <a class="button primary" href="#proyectos">Explorar proyectos ↘</a>
          <a class="button secondary glass" href="#sobre-mi">Conóceme mejor</a>
        </div>

        <div class="social-links">
          <a href="https://github.com/SebasDevs01" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
          <a href="https://linkedin.com/in/sebasdevs" target="_blank" rel="noopener noreferrer">LinkedIn ↗</a>
        </div>
      </div>

      <div class="visual" aria-label="Tarjeta de perfil SebasDev">
        <div class="orbit"></div>
        <div class="orbit orbit-two"></div>

        <div class="profile-card glass">
          <div class="profile-top">
            <div class="window-dots"><span></span><span></span><span></span></div>
            <span class="mini-label">DEV PROFILE / 001</span>
          </div>
          <div class="avatar">&lt;/&gt;</div>
          <p class="profile-kicker">CREANDO CON CURIOSIDAD</p>
          <h2>Sebas<span>Dev</span></h2>
          <p class="profile-subtitle">Software developer in progress.</p>
          <div class="profile-divider"></div>
          <div class="profile-row"><span>Enfoque</span><strong>Web · Móvil · Backend</strong></div>
          <div class="profile-row"><span>Mindset</span><strong>Learn. Build. Repeat.</strong></div>
        </div>

        <div class="floating-chip chip-one"><span class="chip-icon">J</span> Java</div>
        <div class="floating-chip chip-two"><span class="chip-icon">&lt;/&gt;</span> Build mode</div>
      </div>
    </section>

    <section class="container quick-strip glass" aria-label="Mi filosofía">
      <div><b>01</b> Curiosidad constante</div>
      <div><b>02</b> Soluciones prácticas</div>
      <div><b>03</b> Aprendizaje continuo</div>
    </section>

    <section class="container section" id="sobre-mi">
      <div class="section-heading">
        <p class="eyebrow">UN POCO SOBRE MÍ</p>
        <h2>La tecnología me gusta.<br><span class="muted-heading">Crear con ella, aún más.</span></h2>
      </div>

      <div class="about-grid">
        <article class="about-card glass">
          <div class="about-icon">✳</div>
          <h3>Resolver problemas</h3>
          <p>Me interesa entender cómo funcionan las cosas y transformar ideas en soluciones claras, útiles y mantenibles.</p>
        </article>
        <article class="about-card glass">
          <div class="about-icon">⌘</div>
          <h3>Construir proyectos</h3>
          <p>Exploro desarrollo web, aplicaciones móviles y backend, aprendiendo a conectar las piezas de un producto.</p>
        </article>
        <article class="about-card glass">
          <div class="about-icon">↗</div>
          <h3>Seguir creciendo</h3>
          <p>Valoro la práctica, la colaboración y la mejora continua. Cada proyecto es una oportunidad para aprender.</p>
        </article>
      </div>
    </section>

    <section class="container section" id="tecnologias">
      <div class="section-heading">
        <p class="eyebrow">MI CAJA DE HERRAMIENTAS</p>
        <h2>Tecnologías que <span class="gradient">exploro.</span></h2>
        <p class="section-description">Una selección de herramientas con las que he trabajado o que forman parte de mi aprendizaje.</p>
      </div>

      <div class="tech-grid">
        <div class="tech-card glass"><span class="tech-symbol">J</span><span class="tech-info"><strong>Java</strong><small>POO · Backend</small></span></div>
        <div class="tech-card glass"><span class="tech-symbol">S</span><span class="tech-info"><strong>Spring Boot</strong><small>Aplicaciones web</small></span></div>
        <div class="tech-card glass"><span class="tech-symbol">&lt;/&gt;</span><span class="tech-info"><strong>HTML & CSS</strong><small>Interfaces web</small></span></div>
        <div class="tech-card glass"><span class="tech-symbol">PHP</span><span class="tech-info"><strong>PHP</strong><small>Desarrollo web</small></span></div>
        <div class="tech-card glass"><span class="tech-symbol">F</span><span class="tech-info"><strong>Flutter</strong><small>Apps móviles</small></span></div>
        <div class="tech-card glass"><span class="tech-symbol">⌘</span><span class="tech-info"><strong>Git & GitHub</strong><small>Control de versiones</small></span></div>
        <div class="tech-card glass"><span class="tech-symbol">▰</span><span class="tech-info"><strong>Linux</strong><small>Entorno y terminal</small></span></div>
        <div class="tech-card glass"><span class="tech-symbol">Py</span><span class="tech-info"><strong>Python</strong><small>Fundamentos</small></span></div>
      </div>
      <p class="footnote">Personaliza esta lista para mostrar únicamente tus tecnologías y nivel de experiencia reales.</p>
    </section>

    <section class="container section" id="proyectos">
      <div class="section-title-row section-heading">
        <div>
          <p class="eyebrow">COSAS QUE HE CONSTRUIDO</p>
          <h2>Proyectos con <span class="gradient">intención.</span></h2>
        </div>
        <a class="text-link" href="https://github.com/SebasDevs01" target="_blank" rel="noopener noreferrer">Ver GitHub completo ↗</a>
      </div>

      <div class="project-grid">
        <article class="project-card glass">
          <div class="project-art">
            <div class="orb"></div>
            <span class="project-art-label">APP / 01</span>
            <span class="project-glyph">✳</span>
          </div>
          <div class="project-body">
            <div class="project-meta"><span>Aplicación</span><span>Proyecto personal</span></div>
            <h3>La Diabla App</h3>
            <p>Una experiencia digital en desarrollo. Presenta aquí el propósito de la app, sus funciones principales y los aprendizajes técnicos.</p>
            <div class="tags"><span>Flutter</span><span>Web</span><span>UI/UX</span></div>
            <a class="project-link" href="https://ladiabla-11718.web.app/index.html" target="_blank" rel="noopener noreferrer">Explorar proyecto <span>↗</span></a>
          </div>
        </article>

        <article class="project-card glass">
          <div class="project-art blue">
            <div class="orb"></div>
            <span class="project-art-label">DEV / 02</span>
            <span class="project-glyph">&lt;/&gt;</span>
          </div>
          <div class="project-body">
            <div class="project-meta"><span>Portafolio</span><span>Personal</span></div>
            <h3>Mi espacio en GitHub</h3>
            <p>Un lugar para documentar proyectos, experimentar con tecnologías y compartir mi evolución como desarrollador.</p>
            <div class="tags"><span>GitHub</span><span>Desarrollo</span><span>Aprendizaje</span></div>
            <a class="project-link" href="https://github.com/SebasDevs01" target="_blank" rel="noopener noreferrer">Visitar repositorios <span>↗</span></a>
          </div>
        </article>
      </div>
    </section>

    <section class="container section" id="github">
      <div class="section-heading">
        <p class="eyebrow">EN MOVIMIENTO</p>
        <h2>Mi actividad en <span class="gradient">GitHub.</span></h2>
        <p class="section-description">Estadísticas cargadas desde servicios externos. Su disponibilidad depende de esos servicios.</p>
      </div>

      <div class="stats-grid">
        <div class="stats-card glass">
          <h3>RESUMEN DEL PERFIL</h3>
          <img loading="lazy" src="https://github-readme-stats.vercel.app/api?username=SebasDevs01&show_icons=true&hide_border=true&border_radius=16&theme=transparent" alt="Estadísticas GitHub de SebasDevs01">
        </div>
        <div class="stats-card glass">
          <h3>RACHA DE CONTRIBUCIONES</h3>
          <img loading="lazy" src="https://github-readme-streak-stats.herokuapp.com?user=SebasDevs01&hide_border=true&border_radius=16&theme=transparent" alt="Racha de contribuciones">
        </div>
        <div class="stats-card stats-wide glass">
          <h3>LENGUAJES MÁS UTILIZADOS</h3>
          <img loading="lazy" src="https://github-readme-stats.vercel.app/api/top-langs/?username=SebasDevs01&layout=compact&langs_count=8&hide_border=true&border_radius=16&theme=transparent" alt="Lenguajes más utilizados en GitHub">
        </div>
      </div>

      <a class="button secondary glass center-button" href="https://github.com/SebasDevs01" target="_blank" rel="noopener noreferrer">Ver perfil de GitHub ↗</a>
    </section>

    <section class="container section" id="contacto">
      <div class="contact-card glass">
        <p class="eyebrow">¿CONSTRUIMOS ALGO?</p>
        <h2>Las buenas ideas<br>empiezan con un <span class="gradient">hola.</span></h2>
        <p>Estoy abierto a conectar, aprender y conversar sobre proyectos de software.</p>
        <div class="contact-actions">
          <a class="button primary" href="https://linkedin.com/in/sebasdevs" target="_blank" rel="noopener noreferrer">Conectar en LinkedIn ↗</a>
          <a class="button secondary glass" href="https://github.com/SebasDevs01" target="_blank" rel="noopener noreferrer">GitHub ↗</a>
        </div>
      </div>
    </section>
  </main>

  <footer class="container">
    <a class="brand" href="#inicio"><span class="brand-icon">S.</span><span>SebasDev</span></a>
    <p>Diseñado con curiosidad y un poco de cristal. ✳</p>
    <a href="#inicio">Volver arriba ↑</a>
  </footer>

  <div class="theme-menu glass" id="themeMenu" hidden>
    <button type="button" data-theme="system">◐ Automático <span class="check"></span></button>
    <button type="button" data-theme="light">☀ Claro <span class="check"></span></button>
    <button type="button" data-theme="dark">☾ Oscuro <span class="check"></span></button>
  </div>

  <script>
    (() => {
      const root = document.documentElement;
      const themeButton = document.getElementById("themeButton");
      const themeMenu = document.getElementById("themeMenu");
      const themeOptions = [...themeMenu.querySelectorAll("[data-theme]")];
      const systemTheme = window.matchMedia("(prefers-color-scheme: dark)");
      const themeMeta = document.querySelector('meta[name="theme-color"]');
      const validThemes = ["system", "light", "dark"];
      let currentTheme = "system";

      try {
        const stored = localStorage.getItem("sebasdev-theme");
        if (validThemes.includes(stored)) currentTheme = stored;
      } catch (_) {}

      function applyTheme(theme) {
        currentTheme = theme;

        if (theme === "system") {
          root.removeAttribute("data-theme");
        } else {
          root.setAttribute("data-theme", theme);
        }

        const dark = theme === "dark" ||
          (theme === "system" && systemTheme.matches);

        themeMeta.setAttribute("content", dark ? "#101116" : "#f5f6fb");

        themeOptions.forEach(option => {
          const selected = option.dataset.theme === theme;
          option.setAttribute("aria-pressed", String(selected));
          option.querySelector(".check").textContent = selected ? "✓" : "";
        });

        try {
          localStorage.setItem("sebasdev-theme", theme);
        } catch (_) {}
      }

      function closeMenu() {
        themeMenu.hidden = true;
        themeButton.setAttribute("aria-expanded", "false");
      }

      themeButton.addEventListener("click", event => {
        event.stopPropagation();
        themeMenu.hidden = !themeMenu.hidden;
        themeButton.setAttribute("aria-expanded", String(!themeMenu.hidden));
      });

      themeOptions.forEach(option => {
        option.addEventListener("click", () => {
          applyTheme(option.dataset.theme);
          closeMenu();
          themeButton.focus();
        });
      });

      document.addEventListener("click", event => {
        if (!themeMenu.contains(event.target) && !themeButton.contains(event.target)) {
          closeMenu();
        }
      });

      document.addEventListener("keydown", event => {
        if (event.key === "Escape") closeMenu();
      });

      systemTheme.addEventListener("change", () => {
        if (currentTheme === "system") applyTheme("system");
      });

      applyTheme(currentTheme);

      // Texto rotativo de especialidades.
      const roleText = document.getElementById("roleText");
      const roles = [
        "Java y programación orientada a objetos",
        "Desarrollo web con HTML, CSS y PHP",
        "Aplicaciones móviles con Flutter",
        "Backend con Spring Boot",
        "Aprender, construir y mejorar"
      ];

      const reduceMotion = window.matchMedia(
        "(prefers-reduced-motion: reduce)"
      ).matches;

      if (!reduceMotion) {
        let index = 0;
        window.setInterval(() => {
          index = (index + 1) % roles.length;
          roleText.animate(
            [
              { opacity: 0, transform: "translateY(5px)" },
              { opacity: 1, transform: "translateY(0)" }
            ],
            { duration: 280, easing: "ease-out" }
          );
          roleText.textContent = roles[index];
        }, 3200);
      }

      // Resalta la sección visible en el menú.
      const navLinks = [...document.querySelectorAll(".nav-links a")];

      if ("IntersectionObserver" in window) {
        const observer = new IntersectionObserver(entries => {
          entries.forEach(entry => {
            if (!entry.isIntersecting) return;

            navLinks.forEach(link => {
              const active = link.getAttribute("href") === "#" + entry.target.id;
              link.classList.toggle("active", active);
            });
          });
        }, { rootMargin: "-25% 0px -65% 0px" });

        navLinks.forEach(link => {
          const section = document.querySelector(link.getAttribute("href"));
          if (section) observer.observe(section);
        });
      }
    })();
  </script>
</body>
</html>
