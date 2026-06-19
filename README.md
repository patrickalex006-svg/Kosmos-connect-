<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Kosmos Connect | Visual Storytelling Studio</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Inter:wght@300;400;500;600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
<style>
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

  :root {
    --black: #0a0a0a;
    --dark: #111214;
    --card: #161819;
    --cyan: #00d4e8;
    --orange: #ff6b1a;
    --gold: #f5c842;
    --white: #f0f0f0;
    --muted: #888;
  }

  html { scroll-behavior: smooth; }

  body {
    background: var(--black);
    color: var(--white);
    font-family: 'Inter', sans-serif;
    font-size: 16px;
    line-height: 1.6;
    overflow-x: hidden;
  }

  /* NAV */
  nav {
    position: fixed; top: 0; left: 0; right: 0; z-index: 100;
    display: flex; align-items: center; justify-content: space-between;
    padding: 16px 40px;
    background: rgba(10,10,10,0.92);
    backdrop-filter: blur(12px);
    border-bottom: 1px solid rgba(0,212,232,0.12);
  }
  .nav-logo {
    display: flex; align-items: center; gap: 10px;
  }
  .nav-logo img {
    width: 44px; height: 44px; border-radius: 50%; object-fit: cover;
  }
  .nav-logo span {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px;
    letter-spacing: 2px;
    color: var(--cyan);
  }
  .nav-logo span em {
    color: var(--gold);
    font-style: normal;
  }
  .nav-links {
    display: flex; gap: 32px; list-style: none;
  }
  .nav-links a {
    text-decoration: none;
    color: var(--muted);
    font-size: 13px;
    letter-spacing: 1.5px;
    text-transform: uppercase;
    transition: color 0.2s;
  }
  .nav-links a:hover { color: var(--cyan); }
  .nav-cta {
    background: var(--cyan);
    color: var(--black) !important;
    padding: 8px 20px;
    border-radius: 4px;
    font-weight: 600 !important;
    font-size: 13px !important;
    transition: background 0.2s !important;
  }
  .nav-cta:hover { background: var(--orange) !important; color: var(--white) !important; }

  /* HERO */
  .hero {
    min-height: 100vh;
    display: flex; flex-direction: column; align-items: center; justify-content: center;
    text-align: center;
    padding: 120px 24px 80px;
    position: relative;
    overflow: hidden;
  }
  .hero::before {
    content: '';
    position: absolute; inset: 0;
    background: radial-gradient(ellipse 70% 60% at 50% 40%, rgba(0,212,232,0.08) 0%, transparent 70%),
                radial-gradient(ellipse 40% 40% at 80% 80%, rgba(255,107,26,0.06) 0%, transparent 60%);
    pointer-events: none;
  }
  .hero-logo {
    width: 120px; height: 120px;
    border-radius: 50%;
    object-fit: cover;
    border: 3px solid var(--cyan);
    box-shadow: 0 0 40px rgba(0,212,232,0.3);
    margin-bottom: 32px;
    animation: floatLogo 4s ease-in-out infinite;
  }
  @keyframes floatLogo {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-10px); }
  }
  .hero-eyebrow {
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--cyan);
    margin-bottom: 16px;
  }
  .hero-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(56px, 10vw, 110px);
    line-height: 0.95;
    letter-spacing: 2px;
    color: var(--white);
    margin-bottom: 8px;
  }
  .hero-title span {
    color: var(--gold);
    font-family: 'Dancing Script', cursive;
    font-size: clamp(40px, 7vw, 80px);
  }
  .hero-subtitle {
    font-size: 15px;
    color: var(--muted);
    max-width: 540px;
    margin: 20px auto 40px;
    line-height: 1.8;
  }
  .hero-motto {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(18px, 3vw, 28px);
    letter-spacing: 3px;
    color: var(--orange);
    margin-bottom: 40px;
    text-transform: uppercase;
  }
  .hero-btns {
    display: flex; gap: 16px; flex-wrap: wrap; justify-content: center;
  }
  .btn-primary {
    background: var(--cyan);
    color: var(--black);
    padding: 14px 32px;
    border-radius: 4px;
    font-weight: 700;
    font-size: 14px;
    letter-spacing: 1px;
    text-decoration: none;
    text-transform: uppercase;
    transition: transform 0.2s, background 0.2s;
  }
  .btn-primary:hover { background: var(--orange); color: var(--white); transform: translateY(-2px); }
  .btn-outline {
    border: 1px solid var(--cyan);
    color: var(--cyan);
    padding: 14px 32px;
    border-radius: 4px;
    font-size: 14px;
    letter-spacing: 1px;
    text-decoration: none;
    text-transform: uppercase;
    transition: transform 0.2s, background 0.2s;
  }
  .btn-outline:hover { background: rgba(0,212,232,0.1); transform: translateY(-2px); }

  /* SECTION */
  section { padding: 100px 24px; max-width: 1100px; margin: 0 auto; }
  .section-label {
    font-size: 11px;
    letter-spacing: 4px;
    text-transform: uppercase;
    color: var(--cyan);
    margin-bottom: 12px;
  }
  .section-title {
    font-family: 'Bebas Neue', sans-serif;
    font-size: clamp(36px, 6vw, 64px);
    letter-spacing: 2px;
    line-height: 1;
    margin-bottom: 48px;
  }
  .divider {
    width: 60px; height: 3px;
    background: linear-gradient(90deg, var(--cyan), var(--orange));
    margin: 16px 0 48px;
    border-radius: 2px;
  }

  /* SERVICES */
  .services-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 24px;
  }
  .service-card {
    background: var(--card);
    border: 1px solid rgba(255,255,255,0.06);
    border-radius: 8px;
    padding: 36px 24px;
    text-align: center;
    transition: transform 0.25s, border-color 0.25s;
    position: relative;
    overflow: hidden;
  }
  .service-card::after {
    content: '';
    position: absolute; bottom: 0; left: 0; right: 0;
    height: 3px;
    background: linear-gradient(90deg, var(--cyan), var(--orange));
    transform: scaleX(0);
    transition: transform 0.3s;
  }
  .service-card:hover { transform: translateY(-6px); border-color: rgba(0,212,232,0.3); }
  .service-card:hover::after { transform: scaleX(1); }
  .service-icon {
    font-size: 36px;
    margin-bottom: 16px;
    display: block;
  }
  .service-name {
    font-family: 'Bebas Neue', sans-serif;
    font-size: 22px;
    letter-spacing: 2px;
    color: var(--white);
    margin-bottom: 10px;
  }
  .service-desc {
    font-size: 13px;
    color: var(--muted);
    line-height: 1.7;
  }

  /* GALLERY */
  .gallery {
    background: var(--dark);
    padding: 100px 0;
  }
  .gallery-inner { max-width: 1100px; margin: 0 auto; padding: 0 24px; }
  .gallery-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 16px;
    margin-top: 48px;
  }
  .gallery-grid img {
    width: 100%; height: 320px;
    object-fit: cover;
    border-radius: 8px;
    filter: grayscale(20%);
    transition: filter 0.3s, transform 0.3s;
  }
  .gallery-grid img:first-child {
    grid-column: 1 / -1;
    height: 400px;
  }
  .gallery-grid img:hover { filter: grayscale(0%); transform: scale(1.01); }

  /* CONTACT */
  .contact-section { background: var(--black); }
  .contact-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 64px;
    align-items: start;
  }
  .contact-item {
    display: flex; align-items: flex-start; gap: 16px;
    margin-bottom: 28px;
  }
  .contact-icon {
    font-size: 22px;
    min-width: 36px;
    margin-top: 2px;
  }
  .contact-label {
    font-size: 11px;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--cyan);
    margin-bottom: 4px;
  }
  .contact-value {
    font-size: 15px;
    color: var(--white);
  }
  .contact-value a {
    color: var(--white);
    text-decoration: none;
    transition: color 0.2s;
  }
  .contact-value a:hover { color: var(--cyan); }
  .social-links {
    display: flex; gap: 12px; flex-wrap: wrap; margin-top: 32px;
  }
  .social-btn {
    display: inline-flex; align-items: center; gap: 8px;
    background: var(--card);
    border: 1px solid rgba(255,255,255,0.08);
    color: var(--white);
    text-decoration: none;
    padding: 10px 18px;
    border-radius: 4px;
    font-size: 13px;
    transition: border-color 0.2s, color 0.2s;
  }
  .social-btn:hover { border-color: var(--cyan); color: var(--cyan); }
  .whatsapp-btn {
    display: inline-flex; align-items: center; gap: 10px;
    background: #25D366;
    color: #fff;
    text-decoration: none;
    padding: 16px 32px;
    border-radius: 4px;
    font-size: 15px;
    font-weight: 700;
    margin-top: 32px;
    transition: opacity 0.2s, transform 0.2s;
  }
  .whatsapp-btn:hover { opacity: 0.88; transform: translateY(-2px); }

  /* FOOTER */
  footer {
    background: var(--dark);
    border-top: 1px solid rgba(255,255,255,0.06);
    text-align: center;
    padding: 40px 24px;
    font-size: 13px;
    color: var(--muted);
  }
  footer span { color: var(--cyan); }

  @media (max-width: 700px) {
    nav { padding: 12px 20px; }
    .nav-links { display: none; }
    .gallery-grid { grid-template-columns: 1fr; }
    .gallery-grid img:first-child { height: 240px; }
    .contact-grid { grid-template-columns: 1fr; gap: 32px; }
    section { padding: 70px 20px; }
  }
</style>
</head>
<body>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <img 
