<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Nihal Pandey | Fullstack MERN & DevOps & Android Developer</title>
  <meta name="description" content="Portfolio of Nihal Pandey - Fullstack MERN Developer, DevOps Engineer, Android App Developer, and Git/GitHub Specialist." />
  
  <!-- Google Fonts & Font Awesome Icons -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;700&family=Outfit:wght@300;400;500;600;700;800;900&family=Space+Grotesk:wght@400;600;700&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" />

  <style>
    /* =====================================================================
       CSS VARIABLES & RESET
       ===================================================================== */
    :root {
      --bg-dark: #07090e;
      --bg-card: rgba(14, 20, 36, 0.75);
      --bg-card-hover: rgba(22, 32, 56, 0.85);
      --border-color: rgba(255, 255, 255, 0.08);
      --border-glow: rgba(0, 245, 212, 0.35);
      
      --cyan: #00f5d4;
      --cyan-glow: rgba(0, 245, 212, 0.4);
      --purple: #9d4edd;
      --purple-glow: rgba(157, 78, 221, 0.4);
      --blue: #3a86ff;
      --android-green: #3ddc84;
      --devops-orange: #ff7b00;
      --git-red: #f34f29;
      --mern-green: #00ed64;
      
      --text-main: #f0f4fc;
      --text-muted: #8b9bb4;
      --text-dim: #54647f;
      
      --font-body: 'Outfit', sans-serif;
      --font-heading: 'Space Grotesk', sans-serif;
      --font-mono: 'JetBrains Mono', monospace;
      
      --radius-sm: 8px;
      --radius-md: 14px;
      --radius-lg: 22px;
      --radius-full: 9999px;
      
      --transition: all 0.3s cubic-bezier(0.16, 1, 0.3, 1);
    }

    *, *::before, *::after {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    html {
      scroll-behavior: smooth;
    }

    body {
      background-color: var(--bg-dark);
      color: var(--text-main);
      font-family: var(--font-body);
      line-height: 1.6;
      overflow-x: hidden;
      position: relative;
      selection-background-color: var(--cyan);
      selection-color: #000;
    }

    ::selection {
      background: var(--cyan);
      color: #000;
    }

    /* Custom Scrollbar */
    ::-webkit-scrollbar {
      width: 8px;
    }
    ::-webkit-scrollbar-track {
      background: #090c14;
    }
    ::-webkit-scrollbar-thumb {
      background: #1c263c;
      border-radius: 4px;
    }
    ::-webkit-scrollbar-thumb:hover {
      background: var(--cyan);
    }

    /* =====================================================================
       BACKGROUND CANVAS & GLOW ORBS
       ===================================================================== */
    #particle-canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
      pointer-events: none;
    }

    .ambient-glow {
      position: fixed;
      border-radius: 50%;
      filter: blur(120px);
      z-index: -1;
      pointer-events: none;
      opacity: 0.35;
      animation: floatOrbs 20s ease-in-out infinite alternate;
    }
    .glow-1 {
      top: -10%;
      left: -5%;
      width: 500px;
      height: 500px;
      background: radial-gradient(circle, var(--cyan-glow), transparent 70%);
    }
    .glow-2 {
      top: 40%;
      right: -10%;
      width: 600px;
      height: 600px;
      background: radial-gradient(circle, var(--purple-glow), transparent 70%);
      animation-delay: -7s;
    }
    .glow-3 {
      bottom: -10%;
      left: 30%;
      width: 550px;
      height: 550px;
      background: radial-gradient(circle, rgba(58, 134, 255, 0.3), transparent 70%);
      animation-delay: -14s;
    }

    @keyframes floatOrbs {
      0% { transform: translate(0, 0) scale(1); }
      50% { transform: translate(40px, -30px) scale(1.1); }
      100% { transform: translate(-30px, 40px) scale(0.95); }
    }

    /* Custom Cursor Aura */
    .cursor-dot, .cursor-outline {
      position: fixed;
      top: 0;
      left: 0;
      transform: translate(-50%, -50%);
      border-radius: 50%;
      z-index: 9999;
      pointer-events: none;
      transition: transform 0.15s ease-out, opacity 0.2s ease;
    }
    .cursor-dot {
      width: 8px;
      height: 8px;
      background: var(--cyan);
      box-shadow: 0 0 10px var(--cyan);
    }
    .cursor-outline {
      width: 38px;
      height: 38px;
      border: 1.5px solid var(--cyan-glow);
      transition: all 0.2s cubic-bezier(0.16, 1, 0.3, 1);
    }

    /* =====================================================================
       LAYOUT & UTILITY CLASSES
       ===================================================================== */
    .container {
      max-width: 1200px;
      margin: 0 auto;
      padding: 0 24px;
    }

    section {
      padding: 90px 0;
      position: relative;
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 16px;
      background: rgba(0, 245, 212, 0.08);
      border: 1px solid rgba(0, 245, 212, 0.3);
      color: var(--cyan);
      border-radius: var(--radius-full);
      font-size: 0.85rem;
      font-family: var(--font-mono);
      font-weight: 600;
      letter-spacing: 0.5px;
      text-transform: uppercase;
      box-shadow: 0 0 20px rgba(0, 245, 212, 0.15);
    }

    .section-header {
      text-align: center;
      margin-bottom: 60px;
    }
    .section-header .badge {
      margin-bottom: 16px;
    }
    .section-title {
      font-family: var(--font-heading);
      font-size: clamp(2rem, 4vw, 2.8rem);
      font-weight: 800;
      letter-spacing: -0.5px;
      margin-bottom: 14px;
    }
    .section-subtitle {
      color: var(--text-muted);
      font-size: 1.05rem;
      max-width: 650px;
      margin: 0 auto;
    }

    .gradient-text {
      background: linear-gradient(135deg, #fff 15%, var(--cyan) 60%, var(--purple) 100%);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .btn {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      gap: 10px;
      padding: 13px 28px;
      border-radius: var(--radius-full);
      font-size: 0.95rem;
      font-weight: 600;
      text-decoration: none;
      transition: var(--transition);
      cursor: pointer;
      font-family: var(--font-heading);
      border: none;
    }
    .btn-primary {
      background: linear-gradient(135deg, var(--cyan), #00c4a7);
      color: #07090e;
      box-shadow: 0 4px 20px rgba(0, 245, 212, 0.35);
    }
    .btn-primary:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 30px rgba(0, 245, 212, 0.55);
    }
    .btn-outline {
      background: rgba(255, 255, 255, 0.03);
      color: var(--text-main);
      border: 1px solid var(--border-color);
      backdrop-filter: blur(10px);
    }
    .btn-outline:hover {
      background: rgba(255, 255, 255, 0.08);
      border-color: var(--cyan);
      color: var(--cyan);
      transform: translateY(-3px);
      box-shadow: 0 4px 20px rgba(0, 245, 212, 0.15);
    }
    .btn-git {
      background: linear-gradient(135deg, #24292e, #161b22);
      color: #fff;
      border: 1px solid rgba(255, 255, 255, 0.15);
    }
    .btn-git:hover {
      border-color: var(--git-red);
      transform: translateY(-3px);
      box-shadow: 0 6px 25px rgba(243, 79, 41, 0.3);
    }

    .glass-card {
      background: var(--bg-card);
      backdrop-filter: blur(16px);
      -webkit-backdrop-filter: blur(16px);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 30px;
      transition: var(--transition);
      position: relative;
      overflow: hidden;
    }
    .glass-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      right: 0;
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
    }
    .glass-card:hover {
      border-color: var(--border-glow);
      transform: translateY(-6px);
      box-shadow: 0 15px 40px rgba(0, 0, 0, 0.45);
    }

    /* =====================================================================
       NAVIGATION BAR
       ===================================================================== */
    .navbar {
      position: fixed;
      top: 18px;
      left: 50%;
      transform: translateX(-50%);
      width: calc(100% - 48px);
      max-width: 1140px;
      padding: 12px 24px;
      background: rgba(9, 12, 20, 0.85);
      backdrop-filter: blur(20px);
      -webkit-backdrop-filter: blur(20px);
      border: 1px solid rgba(255, 255, 255, 0.08);
      border-radius: var(--radius-full);
      display: flex;
      align-items: center;
      justify-content: space-between;
      z-index: 1000;
      transition: var(--transition);
      box-shadow: 0 10px 30px rgba(0,0,0,0.5);
    }
    .navbar.scrolled {
      top: 10px;
      background: rgba(7, 9, 14, 0.95);
      border-color: rgba(0, 245, 212, 0.25);
      box-shadow: 0 10px 35px rgba(0, 245, 212, 0.1);
    }

    .nav-logo {
      display: flex;
      align-items: center;
      gap: 10px;
      text-decoration: none;
      color: var(--text-main);
      font-family: var(--font-heading);
      font-weight: 800;
      font-size: 1.25rem;
    }
    .nav-logo-icon {
      width: 38px;
      height: 38px;
      border-radius: 10px;
      background: linear-gradient(135deg, var(--cyan), var(--purple));
      display: flex;
      align-items: center;
      justify-content: center;
      color: #07090e;
      font-weight: 900;
      font-size: 1.1rem;
      box-shadow: 0 0 15px var(--cyan-glow);
    }
    .nav-logo span {
      color: var(--cyan);
    }

    .nav-links {
      display: flex;
      align-items: center;
      gap: 28px;
      list-style: none;
    }
    .nav-links a {
      text-decoration: none;
      color: var(--text-muted);
      font-size: 0.9rem;
      font-weight: 500;
      transition: var(--transition);
      position: relative;
    }
    .nav-links a:hover,
    .nav-links a.active {
      color: var(--cyan);
    }
    .nav-links a::after {
      content: '';
      position: absolute;
      bottom: -6px;
      left: 0;
      width: 0%;
      height: 2px;
      background: var(--cyan);
      transition: width 0.3s ease;
      border-radius: 2px;
    }
    .nav-links a:hover::after,
    .nav-links a.active::after {
      width: 100%;
    }

    .nav-right {
      display: flex;
      align-items: center;
      gap: 14px;
    }

    .status-indicator {
      display: flex;
      align-items: center;
      gap: 8px;
      padding: 6px 14px;
      background: rgba(61, 220, 132, 0.08);
      border: 1px solid rgba(61, 220, 132, 0.3);
      border-radius: var(--radius-full);
      font-size: 0.8rem;
      font-family: var(--font-mono);
      color: var(--android-green);
    }
    .pulse-dot {
      width: 8px;
      height: 8px;
      background: var(--android-green);
      border-radius: 50%;
      box-shadow: 0 0 10px var(--android-green);
      animation: pulse 1.8s infinite;
    }

    @keyframes pulse {
      0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(61, 220, 132, 0.7); }
      70% { transform: scale(1.1); box-shadow: 0 0 0 9px rgba(61, 220, 132, 0); }
      100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(61, 220, 132, 0); }
    }

    .mobile-toggle {
      display: none;
      background: transparent;
      border: none;
      color: var(--text-main);
      font-size: 1.4rem;
      cursor: pointer;
    }

    /* =====================================================================
       HERO SECTION
       ===================================================================== */
    .hero {
      min-height: 100vh;
      display: flex;
      align-items: center;
      padding-top: 130px;
      padding-bottom: 70px;
    }
    .hero-grid {
      display: grid;
      grid-template-columns: 1.2fr 0.8fr;
      gap: 50px;
      align-items: center;
    }

    .hero-text {
      display: flex;
      flex-direction: column;
      gap: 22px;
    }

    .hero-greeting {
      font-family: var(--font-mono);
      color: var(--cyan);
      font-size: 1.05rem;
      letter-spacing: 1px;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .hero-greeting i {
      animation: waveHand 2s infinite;
      transform-origin: 70% 70%;
      display: inline-block;
    }
    @keyframes waveHand {
      0%, 100% { transform: rotate(0deg); }
      20%, 60% { transform: rotate(14deg); }
      40%, 80% { transform: rotate(-14deg); }
    }

    .hero-title {
      font-family: var(--font-heading);
      font-size: clamp(2.6rem, 5.5vw, 4.2rem);
      font-weight: 900;
      line-height: 1.1;
      letter-spacing: -1.5px;
    }

    .typewriter-box {
      display: flex;
      align-items: center;
      font-family: var(--font-mono);
      font-size: clamp(1.1rem, 2.2vw, 1.55rem);
      font-weight: 600;
      color: #b5c7e4;
      min-height: 40px;
    }
    .typewriter-box .role-prefix {
      color: var(--text-dim);
      margin-right: 8px;
    }
    .typed-text {
      color: var(--cyan);
      font-weight: 700;
      text-shadow: 0 0 15px rgba(0, 245, 212, 0.4);
    }
    .cursor-blink {
      display: inline-block;
      width: 2px;
      height: 1.2em;
      background: var(--cyan);
      margin-left: 4px;
      animation: blink 0.9s infinite;
      vertical-align: middle;
    }
    @keyframes blink {
      0%, 50% { opacity: 1; }
      51%, 100% { opacity: 0; }
    }

    .hero-description {
      font-size: 1.12rem;
      color: var(--text-muted);
      line-height: 1.7;
      max-width: 580px;
    }
    .hero-description strong {
      color: var(--text-main);
      font-weight: 600;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 16px;
      margin-top: 10px;
    }

    .hero-stats {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
      margin-top: 25px;
      padding-top: 25px;
      border-top: 1px solid var(--border-color);
    }
    .stat-item {
      display: flex;
      flex-direction: column;
    }
    .stat-number {
      font-family: var(--font-heading);
      font-size: 1.9rem;
      font-weight: 800;
      color: var(--text-main);
      background: linear-gradient(135deg, #fff, var(--cyan));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }
    .stat-label {
      font-size: 0.78rem;
      color: var(--text-dim);
      text-transform: uppercase;
      font-family: var(--font-mono);
      letter-spacing: 0.5px;
    }

    /* 3D Visual Sphere & Orbit in Hero */
    .hero-visual {
      position: relative;
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      padding: 20px 0;
    }
    .avatar-wrapper {
      position: relative;
      width: min(320px, 72vw);
      height: min(320px, 72vw);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      background: radial-gradient(circle at 30% 30%, #151d33, #090c14);
      border: 2px solid rgba(0, 245, 212, 0.3);
      box-shadow: 0 0 50px rgba(0, 245, 212, 0.25), inset 0 0 30px rgba(157, 78, 221, 0.3);
    }
    .avatar-inner {
      width: min(250px, 56vw);
      height: min(250px, 56vw);
      border-radius: 50%;
      background: linear-gradient(145deg, #101728, #0a0d16);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      border: 1px solid rgba(255, 255, 255, 0.1);
      position: relative;
      overflow: hidden;
    }
    .avatar-inner .avatar-symbol {
      font-family: var(--font-heading);
      font-size: clamp(2.8rem, 11vw, 4.8rem);
      font-weight: 900;
      background: linear-gradient(135deg, var(--cyan), var(--purple));
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      filter: drop-shadow(0 0 20px var(--cyan-glow));
    }
    .avatar-inner .avatar-name {
      font-family: var(--font-mono);
      font-size: clamp(0.72rem, 2.5vw, 0.85rem);
      color: var(--text-muted);
      letter-spacing: 2px;
      text-transform: uppercase;
      margin-top: 4px;
    }

    /* Orbiting Badges */
    .orbit-ring {
      position: absolute;
      width: min(380px, 86vw);
      height: min(380px, 86vw);
      border: 1px dashed rgba(255, 255, 255, 0.12);
      border-radius: 50%;
      animation: rotateOrbit 30s linear infinite;
    }
    @keyframes rotateOrbit {
      from { transform: rotate(0deg); }
      to { transform: rotate(360deg); }
    }

    .orbit-badge {
      position: absolute;
      width: clamp(38px, 10vw, 48px);
      height: clamp(38px, 10vw, 48px);
      border-radius: 50%;
      background: rgba(14, 20, 36, 0.95);
      border: 1.5px solid var(--border-color);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: clamp(1rem, 3vw, 1.25rem);
      box-shadow: 0 4px 15px rgba(0,0,0,0.5);
      backdrop-filter: blur(10px);
      transition: var(--transition);
      animation: counterRotate 30s linear infinite;
    }
    @keyframes counterRotate {
      from { transform: rotate(0deg); }
      to { transform: rotate(-360deg); }
    }
    .orbit-badge:hover {
      transform: scale(1.15);
    }
    .badge-git { top: -20px; left: calc(50% - clamp(19px, 5vw, 24px)); color: var(--git-red); border-color: rgba(243, 79, 41, 0.4); }
    .badge-mern { bottom: -20px; left: calc(50% - clamp(19px, 5vw, 24px)); color: var(--mern-green); border-color: rgba(0, 237, 100, 0.4); }
    .badge-devops { top: calc(50% - clamp(19px, 5vw, 24px)); right: -20px; color: var(--devops-orange); border-color: rgba(255, 123, 0, 0.4); }
    .badge-android { top: calc(50% - clamp(19px, 5vw, 24px)); left: -20px; color: var(--android-green); border-color: rgba(61, 220, 132, 0.4); }

    /* =====================================================================
       INTERACTIVE TERMINAL / WHOAMI SECTION
       ===================================================================== */
    .terminal-container {
      margin-top: 50px;
      background: #090d16;
      border-radius: var(--radius-lg);
      border: 1px solid var(--border-color);
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.6);
      overflow: hidden;
      font-family: var(--font-mono);
    }
    .terminal-header {
      background: #111726;
      padding: 12px 20px;
      display: flex;
      align-items: center;
      justify-content: space-between;
      border-bottom: 1px solid var(--border-color);
    }
    .terminal-dots {
      display: flex;
      gap: 8px;
    }
    .terminal-dot {
      width: 12px;
      height: 12px;
      border-radius: 50%;
    }
    .dot-red { background: #ff5f56; }
    .dot-yellow { background: #ffbd2e; }
    .dot-green { background: #27c93f; }
    .terminal-title {
      color: var(--text-dim);
      font-size: 0.8rem;
    }
    .terminal-body {
      padding: 24px;
      color: #cfd8ea;
      font-size: 0.92rem;
      line-height: 1.7;
      max-height: 380px;
      overflow-y: auto;
    }
    .term-prompt {
      color: var(--cyan);
      font-weight: 600;
    }
    .term-path {
      color: var(--purple);
    }
    .term-cmd {
      color: #fff;
    }
    .term-output {
      margin: 8px 0 18px 0;
      color: var(--text-muted);
    }
    .term-key {
      color: #4facfe;
    }
    .term-val {
      color: var(--android-green);
    }
    .term-input-row {
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .terminal-cli-input {
      background: transparent;
      border: none;
      outline: none;
      color: #fff;
      font-family: var(--font-mono);
      font-size: 0.92rem;
      flex: 1;
    }

    /* =====================================================================
       EXPERTISE FOUR PILLARS
       ===================================================================== */
    .pillars-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(min(100%, 250px), 1fr));
      gap: 20px;
    }
    .pillar-card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 30px;
      transition: var(--transition);
      position: relative;
      overflow: hidden;
    }
    .pillar-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 3px;
      background: linear-gradient(90deg, transparent, var(--card-color, var(--cyan)), transparent);
      opacity: 0;
      transition: opacity 0.3s ease;
    }
    .pillar-card:hover {
      border-color: rgba(255, 255, 255, 0.18);
      transform: translateY(-8px);
      box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4);
    }
    .pillar-card:hover::before {
      opacity: 1;
    }
    .pillar-icon-box {
      width: 56px;
      height: 56px;
      border-radius: var(--radius-md);
      background: rgba(255, 255, 255, 0.04);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.6rem;
      color: var(--card-color, var(--cyan));
      margin-bottom: 20px;
      box-shadow: 0 0 20px rgba(0,0,0,0.3);
      border: 1px solid rgba(255, 255, 255, 0.08);
    }
    .pillar-card h3 {
      font-family: var(--font-heading);
      font-size: 1.3rem;
      font-weight: 700;
      margin-bottom: 12px;
      color: #fff;
    }
    .pillar-card p {
      color: var(--text-muted);
      font-size: 0.92rem;
      line-height: 1.6;
      margin-bottom: 18px;
    }
    .pillar-tags {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }
    .pillar-tag {
      font-size: 0.75rem;
      font-family: var(--font-mono);
      background: rgba(255, 255, 255, 0.05);
      padding: 4px 10px;
      border-radius: var(--radius-sm);
      color: #c0cde3;
      border: 1px solid rgba(255, 255, 255, 0.06);
    }

    /* Pillar specific colors */
    .pillar-mern { --card-color: #00ed64; }
    .pillar-devops { --card-color: #ff7b00; }
    .pillar-android { --card-color: #3ddc84; }
    .pillar-git { --card-color: #f34f29; }

    /* =====================================================================
       INTERACTIVE CI/CD DEVOPS PIPELINE VISUALIZER
       ===================================================================== */
    .pipeline-section {
      background: linear-gradient(180deg, transparent, rgba(14, 20, 36, 0.4), transparent);
    }
    .pipeline-board {
      background: #090d16;
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 35px 25px;
      box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
    }
    .pipeline-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 30px;
      flex-wrap: wrap;
      gap: 15px;
    }
    .pipeline-branch {
      display: flex;
      align-items: center;
      gap: 10px;
      font-family: var(--font-mono);
      font-size: 0.88rem;
      color: var(--cyan);
    }
    .pipeline-status {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      font-family: var(--font-mono);
      font-size: 0.82rem;
      padding: 6px 14px;
      background: rgba(61, 220, 132, 0.1);
      border: 1px solid rgba(61, 220, 132, 0.3);
      color: var(--android-green);
      border-radius: var(--radius-full);
    }

    .pipeline-nodes-wrapper {
      display: grid;
      grid-template-columns: repeat(6, 1fr);
      gap: 14px;
      position: relative;
    }
    .pipeline-nodes-wrapper::before {
      content: '';
      position: absolute;
      top: 50%;
      left: 30px;
      right: 30px;
      height: 2px;
      background: linear-gradient(90deg, var(--git-red), var(--devops-orange), var(--cyan), var(--android-green));
      z-index: 1;
      transform: translateY(-50%);
      opacity: 0.35;
    }

    .pipe-node {
      position: relative;
      z-index: 2;
      background: #0e1526;
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 20px 14px;
      text-align: center;
      cursor: pointer;
      transition: var(--transition);
    }
    .pipe-node:hover,
    .pipe-node.active {
      border-color: var(--cyan);
      transform: translateY(-5px);
      box-shadow: 0 10px 25px rgba(0, 245, 212, 0.25);
      background: #141e35;
    }
    .pipe-icon {
      width: 44px;
      height: 44px;
      margin: 0 auto 12px;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.05);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.15rem;
      color: var(--cyan);
      transition: var(--transition);
    }
    .pipe-node:hover .pipe-icon,
    .pipe-node.active .pipe-icon {
      background: var(--cyan);
      color: #07090e;
      box-shadow: 0 0 15px var(--cyan-glow);
    }
    .pipe-title {
      font-family: var(--font-heading);
      font-size: 0.95rem;
      font-weight: 700;
      color: #fff;
      margin-bottom: 4px;
    }
    .pipe-meta {
      font-size: 0.72rem;
      font-family: var(--font-mono);
      color: var(--text-dim);
    }

    .pipeline-detail-box {
      margin-top: 25px;
      padding: 20px;
      background: rgba(14, 20, 36, 0.7);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      font-family: var(--font-mono);
      font-size: 0.88rem;
      color: #c9d6ea;
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 15px;
    }
    .pipeline-detail-content {
      display: flex;
      align-items: center;
      gap: 15px;
    }
    .pipeline-detail-content i {
      font-size: 1.5rem;
      color: var(--cyan);
    }

    /* =====================================================================
       SKILLS DIRECTORY & TECH STACK
       ===================================================================== */
    .skills-filter-nav {
      display: flex;
      justify-content: center;
      gap: 12px;
      flex-wrap: wrap;
      margin-bottom: 40px;
    }
    .skill-filter-btn {
      padding: 10px 22px;
      border-radius: var(--radius-full);
      background: rgba(255, 255, 255, 0.03);
      border: 1px solid var(--border-color);
      color: var(--text-muted);
      font-size: 0.88rem;
      font-weight: 600;
      font-family: var(--font-heading);
      cursor: pointer;
      transition: var(--transition);
    }
    .skill-filter-btn:hover,
    .skill-filter-btn.active {
      background: rgba(0, 245, 212, 0.12);
      border-color: var(--cyan);
      color: var(--cyan);
      box-shadow: 0 0 20px rgba(0, 245, 212, 0.2);
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(min(100%, 250px), 1fr));
      gap: 16px;
    }
    .skill-card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 22px;
      display: flex;
      flex-direction: column;
      gap: 14px;
      transition: var(--transition);
    }
    .skill-card:hover {
      border-color: var(--cyan-glow);
      transform: translateY(-5px);
      box-shadow: 0 10px 30px rgba(0,0,0,0.3);
    }
    .skill-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    .skill-info {
      display: flex;
      align-items: center;
      gap: 12px;
    }
    .skill-icon {
      width: 42px;
      height: 42px;
      border-radius: 10px;
      background: rgba(255, 255, 255, 0.05);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.3rem;
    }
    .skill-name {
      font-family: var(--font-heading);
      font-weight: 700;
      font-size: 1.05rem;
      color: #fff;
    }
    .skill-category-tag {
      font-size: 0.72rem;
      color: var(--text-dim);
      font-family: var(--font-mono);
    }
    .skill-percentage {
      font-family: var(--font-mono);
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--cyan);
    }
    .progress-bar-bg {
      width: 100%;
      height: 6px;
      background: rgba(255, 255, 255, 0.08);
      border-radius: 10px;
      overflow: hidden;
    }
    .progress-fill {
      height: 100%;
      border-radius: 10px;
      background: linear-gradient(90deg, var(--cyan), var(--purple));
      width: 0%;
      transition: width 1.2s cubic-bezier(0.16, 1, 0.3, 1);
    }

    /* =====================================================================
       FEATURED PROJECTS
       ===================================================================== */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(min(100%, 300px), 1fr));
      gap: 24px;
    }
    .project-card {
      background: var(--bg-card);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 28px;
      display: flex;
      flex-direction: column;
      justify-content: space-between;
      transition: var(--transition);
      position: relative;
    }
    .project-card:hover {
      border-color: rgba(0, 245, 212, 0.4);
      transform: translateY(-8px);
      box-shadow: 0 20px 45px rgba(0, 0, 0, 0.5);
    }
    .project-top {
      display: flex;
      align-items: center;
      justify-content: space-between;
      margin-bottom: 20px;
    }
    .project-folder-icon {
      font-size: 2.2rem;
      color: var(--cyan);
    }
    .project-links {
      display: flex;
      gap: 14px;
    }
    .project-link-btn {
      color: var(--text-muted);
      font-size: 1.15rem;
      transition: var(--transition);
      text-decoration: none;
    }
    .project-link-btn:hover {
      color: var(--cyan);
      transform: translateY(-2px);
    }
    .project-title {
      font-family: var(--font-heading);
      font-size: 1.35rem;
      font-weight: 700;
      color: #fff;
      margin-bottom: 12px;
      line-height: 1.3;
    }
    .project-desc {
      color: var(--text-muted);
      font-size: 0.94rem;
      line-height: 1.6;
      margin-bottom: 20px;
    }
    .project-features {
      list-style: none;
      margin-bottom: 22px;
      display: flex;
      flex-direction: column;
      gap: 8px;
    }
    .project-features li {
      font-size: 0.85rem;
      color: #b1c1dc;
      display: flex;
      align-items: center;
      gap: 8px;
    }
    .project-features li i {
      color: var(--cyan);
      font-size: 0.75rem;
    }
    .project-techs {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
      border-top: 1px solid var(--border-color);
      padding-top: 18px;
    }
    .project-tech-pill {
      font-size: 0.75rem;
      font-family: var(--font-mono);
      color: var(--cyan);
      background: rgba(0, 245, 212, 0.08);
      padding: 4px 10px;
      border-radius: var(--radius-sm);
      border: 1px solid rgba(0, 245, 212, 0.2);
    }

    /* =====================================================================
       GITHUB METRICS & CONTRIBUTION SHOWCASE
       ===================================================================== */
    .github-overview-card {
      background: #090d16;
      border: 1px solid var(--border-color);
      border-radius: var(--radius-lg);
      padding: 35px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.5);
    }
    .git-header-bar {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      gap: 20px;
      margin-bottom: 30px;
    }
    .git-user-profile {
      display: flex;
      align-items: center;
      gap: 16px;
    }
    .git-avatar {
      width: 60px;
      height: 60px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--git-red), var(--purple));
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.8rem;
      color: #fff;
      box-shadow: 0 0 20px rgba(243, 79, 41, 0.35);
    }
    .git-user-text h3 {
      font-family: var(--font-heading);
      font-size: 1.35rem;
      font-weight: 700;
      color: #fff;
    }
    .git-user-text p {
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--text-muted);
    }

    /* GitHub heatmap grid simulation */
    .heatmap-section {
      margin: 25px 0;
    }
    .heatmap-title {
      font-family: var(--font-mono);
      font-size: 0.85rem;
      color: var(--text-dim);
      margin-bottom: 12px;
      display: flex;
      justify-content: space-between;
      align-items: center;
    }
    .heatmap-grid {
      display: grid;
      grid-template-columns: repeat(45, 1fr);
      gap: 4px;
      overflow-x: auto;
      padding: 6px 0;
    }
    .heat-cell {
      aspect-ratio: 1;
      border-radius: 2px;
      background: #161b22;
      transition: transform 0.15s ease, background 0.15s ease;
      cursor: pointer;
      position: relative;
    }
    .heat-cell:hover {
      transform: scale(1.3);
      z-index: 5;
    }
    .lvl-1 { background: #0e4429; }
    .lvl-2 { background: #006d32; }
    .lvl-3 { background: #26a641; }
    .lvl-4 { background: #39d353; box-shadow: 0 0 6px #39d353; }

    .git-stats-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(min(100%, 180px), 1fr));
      gap: 16px;
      margin-top: 25px;
    }
    .git-stat-box {
      background: rgba(255, 255, 255, 0.02);
      border: 1px solid var(--border-color);
      border-radius: var(--radius-md);
      padding: 18px;
      display: flex;
      align-items: center;
      gap: 16px;
    }
    .git-stat-icon {
      font-size: 1.6rem;
      color: var(--cyan);
    }
    .git-stat-val {
      font-family: var(--font-heading);
      font-size: 1.4rem;
      font-weight: 800;
      color: #fff;
    }
    .git-stat-desc {
      font-size: 0.78rem;
      font-family: var(--font-mono);
      color: var(--text-dim);
    }

    /* =====================================================================
       CONTACT & GET IN TOUCH
       ===================================================================== */
    .contact-grid {
      display: grid;
      grid-template-columns: 1fr 1.2fr;
      gap: 40px;
    }
    .contact-info-card {
      display: flex;
      flex-direction: column;
      gap: 25px;
    }
    .contact-point {
      display: flex;
      align-items: flex-start;
      gap: 16px;
    }
    .contact-point-icon {
      width: 48px;
      height: 48px;
      border-radius: 12px;
      background: rgba(0, 245, 212, 0.08);
      border: 1px solid rgba(0, 245, 212, 0.3);
      display: flex;
      align-items: center;
      justify-content: center;
      color: var(--cyan);
      font-size: 1.2rem;
      flex-shrink: 0;
    }
    .contact-point-text h4 {
      font-family: var(--font-heading);
      font-size: 1.05rem;
      color: #fff;
      margin-bottom: 2px;
    }
    .contact-point-text p, .contact-point-text a {
      color: var(--text-muted);
      font-size: 0.92rem;
      text-decoration: none;
      transition: var(--transition);
    }
    .contact-point-text a:hover {
      color: var(--cyan);
    }

    .social-links-row {
      display: flex;
      gap: 12px;
      margin-top: 15px;
    }
    .social-btn {
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid var(--border-color);
      display: flex;
      align-items: center;
      justify-content: center;
      color: #fff;
      font-size: 1.1rem;
      text-decoration: none;
      transition: var(--transition);
    }
    .social-btn:hover {
      background: var(--cyan);
      color: #07090e;
      border-color: var(--cyan);
      transform: translateY(-4px);
      box-shadow: 0 6px 20px var(--cyan-glow);
    }

    /* Form styling */
    .form-group {
      margin-bottom: 20px;
    }
    .form-label {
      display: block;
      margin-bottom: 8px;
      font-family: var(--font-mono);
      font-size: 0.82rem;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.5px;
    }
    .form-input, .form-textarea {
      width: 100%;
      padding: 14px 18px;
      border-radius: var(--radius-md);
      background: rgba(10, 14, 24, 0.85);
      border: 1px solid var(--border-color);
      color: #fff;
      font-family: var(--font-body);
      font-size: 16px; /* Prevents auto zoom in iOS */
      outline: none;
      transition: var(--transition);
    }
    .form-input:focus, .form-textarea:focus {
      border-color: var(--cyan);
      box-shadow: 0 0 15px rgba(0, 245, 212, 0.2);
    }
    .form-textarea {
      min-height: 130px;
      resize: vertical;
    }

    /* Toast Notification */
    .toast-msg {
      position: fixed;
      bottom: 30px;
      right: 30px;
      background: #0f172a;
      border: 1px solid var(--cyan);
      padding: 16px 24px;
      border-radius: var(--radius-md);
      color: #fff;
      box-shadow: 0 10px 30px rgba(0, 245, 212, 0.3);
      display: flex;
      align-items: center;
      gap: 12px;
      z-index: 99999;
      transform: translateY(120px);
      opacity: 0;
      transition: var(--transition);
    }
    .toast-msg.show {
      transform: translateY(0);
      opacity: 1;
    }

    /* =====================================================================
       FOOTER
       ===================================================================== */
    footer {
      border-top: 1px solid var(--border-color);
      padding: 40px 0;
      background: #05070a;
      text-align: center;
    }
    .footer-content {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 16px;
    }
    .footer-logo {
      font-family: var(--font-heading);
      font-size: 1.4rem;
      font-weight: 800;
      color: #fff;
    }
    .footer-logo span {
      color: var(--cyan);
    }
    .footer-copy {
      font-size: 0.88rem;
      color: var(--text-dim);
    }

    /* =====================================================================
       RESPONSIVE BREAKPOINTS (Mobile & Tablet Optimization)
       ===================================================================== */
    /* Hide custom cursor on touch & mobile screens to eliminate tap lag */
    @media (hover: none), (pointer: coarse), (max-width: 992px) {
      .cursor-dot, .cursor-outline {
        display: none !important;
      }
    }

    /* Tablet & Medium Screens (<= 992px) */
    @media (max-width: 992px) {
      section {
        padding: 75px 0;
      }
      .hero {
        padding-top: 120px;
        padding-bottom: 50px;
        min-height: auto;
      }
      .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
        gap: 40px;
      }
      .hero-greeting {
        justify-content: center;
      }
      .hero-description {
        margin: 0 auto;
      }
      .hero-actions {
        justify-content: center;
      }
      .hero-stats {
        grid-template-columns: repeat(4, 1fr);
        max-width: 650px;
        margin: 25px auto 0;
      }
      .typewriter-box {      color: var(--cyan);
    }
    .footer-copy {
      font-size: 0.88rem;
      color: var(--text-dim);
    }

    /* =====================================================================
       RESPONSIVE BREAKPOINTS (Mobile & Tablet Optimization)
       ===================================================================== */
    /* Hide custom cursor on touch & mobile screens to eliminate tap lag */
    @media (hover: none), (pointer: coarse), (max-width: 992px) {
      .cursor-dot, .cursor-outline {
        display: none !important;
      }
    }

    /* Tablet & Medium Screens (<= 992px) */
    @media (max-width: 992px) {
      section {
        padding: 75px 0;
      }
      .hero {
        padding-top: 120px;
        padding-bottom: 50px;
        min-height: auto;
      }
      .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
        gap: 40px;
      }
      .hero-greeting {
        justify-content: center;
      }
      .hero-description {
        margin: 0 auto;
      }
      .hero-actions {
        justify-content: center;
      }
      .hero-stats {
        grid-template-columns: repeat(4, 1fr);
        max-width: 650px;
        margin: 25px auto 0;
      }
      .typewriter-box {
        justify-content: center;
      }
      .hero-visual {
        margin: 15px auto 0;
      }
      .pipeline-nodes-wrapper {
        grid-template-columns: repeat(3, 1fr);
      }
      .pipeline-nodes-wrapper::before {
        display: none;
      }
      .contact-grid {
        grid-template-columns: 1fr;
        gap: 30px;
      }
    }

    /* Small Tablet & Mobile Devices (<= 768px) */
    @media (max-width: 768px) {
      .container {
        padding: 0 16px;
      }
      section {
        padding: 55px 0;
      }
      .section-header {
        margin-bottom: 35px;
      }
      .section-title {
        font-size: clamp(1.75rem, 5vw, 2.2rem);
      }
      .section-subtitle {
        font-size: 0.92rem;
      }

      /* Compact Navbar */
      .navbar {
        top: 10px;
        width: calc(100% - 20px);
        padding: 8px 16px;
      }
      .nav-links, .nav-right .status-indicator {
        display: none;
      }
        justify-content: center;
      }
      .hero-visual {
        margin: 15px auto 0;
      }
      .pipeline-nodes-wrapper {
        grid-template-columns: repeat(3, 1fr);
      }
      .pipeline-nodes-wrapper::before {
        display: none;
      }
      .contact-grid {
        grid-template-columns: 1fr;
        gap: 30px;
      }
    }

    /* Small Tablet & Mobile Devices (<= 768px) */
    @media (max-width: 768px) {
      .container {
        padding: 0 16px;
      }
      section {
        padding: 55px 0;
      }
      .section-header {
        margin-bottom: 35px;
      }
      .section-title {
        font-size: clamp(1.75rem, 5vw, 2.2rem);
      }
      .section-subtitle {
        font-size: 0.92rem;
      }

      /* Compact Navbar */
      .navbar {
        top: 10px;
        width: calc(100% - 20px);
        padding: 8px 16px;
      }
      .nav-links, .nav-right .status-indicator {
        display: none;
      }
      .mobile-toggle {
        display: flex;
        align-items: center;
        justify-content: center;
        width: 38px;
        height: 38px;
        border-radius: 10px;
        background: rgba(255, 255, 255, 0.05);
        border: 1px solid var(--border-color);
      }

      /* Ultra-Sleek Mobile App Dropdown */
      .mobile-menu {
        position: fixed;
        top: 68px;
        left: 10px;
        right: 10px;
        background: rgba(9, 13, 22, 0.97);
        backdrop-filter: blur(24px);
        -webkit-backdrop-filter: blur(24px);
        border: 1px solid rgba(0, 245, 212, 0.3);
        border-radius: var(--radius-lg);
        padding: 16px 18px;
        display: flex;
        flex-direction: column;
        gap: 8px;
        z-index: 9999;
        transform: translateY(-15px) scale(0.97);
        opacity: 0;
        pointer-events: none;
        transition: var(--transition);
        box-shadow: 0 20px 50px rgba(0, 0, 0, 0.8), 0 0 30px rgba(0, 245, 212, 0.15);
      }
      .mobile-menu.open {
        transform: translateY(0) scale(1);
        opacity: 1;
        pointer-events: auto;
      }
      .mobile-menu a {
        color: var(--text-main);
        text-decoration: none;
        font-weight: 600;
        font-size: 0.98rem;
        display: flex;
        align-items: center;
        gap: 12px;
        padding: 12px 14px;
        border-radius: var(--radius-sm);
        transition: var(--transition);
        border: 1px solid transparent;
      }
      .mobile-menu a i:first-child {
        color: var(--cyan);
        width: 20px;
        text-align: center;
      }
      .mobile-menu a .mob-arrow {
        margin-left: auto;
        font-size: 0.75rem;
        color: var(--text-dim);
      }
      .mobile-menu a:hover, .mobile-menu a:active {
        background: rgba(0, 245, 212, 0.1);
        border-color: rgba(0, 245, 212, 0.3);
        color: var(--cyan);
      }

      /* Hero Mobile */
      .hero {
        padding-top: 105px;
        padding-bottom: 45px;
      }
      .hero-title {
        font-size: clamp(2.1rem, 7.5vw, 2.9rem);
      }
      .hero-stats {
        grid-template-columns: repeat(2, 1fr);
        gap: 14px;
      }
      .stat-number {
        font-size: 1.6rem;
      }

      /* Terminal Mobile */
      .terminal-header {
        padding: 10px 14px;
      }
      .terminal-title {
        font-size: 0.72rem;
        max-width: 170px;
        overflow: hidden;
        text-overflow: ellipsis;
        white-space: nowrap;
      }
      .terminal-body {
        padding: 16px 14px;
        font-size: 0.82rem;
        max-height: 320px;
      }

      /* Pipeline Mobile */
      .pipeline-board {
        padding: 20px 14px;
      }
      .pipeline-header {
        flex-direction: column;
        align-items: flex-start;
        gap: 10px;
      }
      .pipeline-nodes-wrapper {
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
      }
      .pipe-node {
        padding: 14px 10px;
      }
      .pipe-icon {
        width: 38px;
        height: 38px;
        font-size: 1rem;
        margin-bottom: 8px;
      }
      .pipe-title {
        font-size: 0.86rem;
      }
      .pipe-meta {
        font-size: 0.68rem;
      }
      .pipeline-detail-box {
        flex-direction: column;
        align-items: flex-start;
        padding: 14px;
        gap: 10px;
      }

      /* Skills Mobile Filter Nav */
      .skills-filter-nav {
        display: flex;
        overflow-x: auto;
        flex-wrap: nowrap;
        justify-content: flex-start;
        padding-bottom: 10px;
        margin-bottom: 24px;
        -webkit-overflow-scrolling: touch;
        scrollbar-width: none;
      }
      .skills-filter-nav::-webkit-scrollbar {
        display: none;
      }
      .skill-filter-btn {
        flex-shrink: 0;
        white-space: nowrap;
        padding: 8px 16px;
        font-size: 0.82rem;
      }

      /* GitHub Overview Mobile */
      .github-overview-card {
        padding: 20px 14px;
      }
      .git-header-bar {
        flex-direction: column;
        align-items: stretch;
        gap: 16px;
        text-align: center;
      }
      .git-user-profile {
        justify-content: center;
      }
      .git-header-bar .btn {
        width: 100%;
      }
      .heatmap-title {
        flex-direction: column;
        align-items: flex-start;
        gap: 8px;
      }
      .heatmap-grid {
        -webkit-overflow-scrolling: touch;
        padding: 8px 0;
      }
      .git-stats-grid {
        grid-template-columns: repeat(2, 1fr);
        gap: 12px;
      }

      /* Cards Padding Mobile */
      .glass-card, .pillar-card, .project-card {
        padding: 22px 18px;
      }

      /* Toast Notification Mobile */
      .toast-msg {
        left: 14px;
        right: 14px;
        bottom: 20px;
        padding: 14px 18px;
        font-size: 0.88rem;
        justify-content: center;
      }
    }

    /* Small Phones & Ultra-Compact Screens (<= 480px) */
    @media (max-width: 480px) {
      .hero-title {
        font-size: 2.15rem;
      }
      .hero-greeting {
        font-size: 0.88rem;
      }
      .typewriter-box {
        font-size: 0.95rem;
        flex-wrap: wrap;
        min-height: 48px;
      }
      .hero-actions {
        flex-direction: column;
        width: 100%;
        gap: 12px;
      }
      .hero-actions .btn {
        width: 100%;
        padding: 14px 20px;
      }
      .hero-stats {
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
        padding-top: 18px;
      }
      .stat-number {
        font-size: 1.45rem;
      }
      .stat-label {
        font-size: 0.68rem;
      }
      .pipeline-nodes-wrapper {
        grid-template-columns: repeat(2, 1fr);
        gap: 8px;
      }
      .git-stats-grid {
        grid-template-columns: 1fr;
      }
      .contact-point {
        gap: 12px;
      }
      .contact-point-icon {
        width: 40px;
        height: 40px;
        font-size: 1rem;
      }
    }
  </style>
</head>
<body>

  <!-- Ambient Glowing Background Orbs -->
  <div class="ambient-glow glow-1"></div>
  <div class="ambient-glow glow-2"></div>
  <div class="ambient-glow glow-3"></div>

  <!-- Interactive Dynamic Background Canvas -->
  <canvas id="particle-canvas"></canvas>

  <!-- Interactive Custom Cursor -->
  <div class="cursor-dot" id="cursor-dot"></div>
  <div class="cursor-outline" id="cursor-outline"></div>

  <!-- =====================================================================
       NAVBAR
       ===================================================================== -->
  <header>
    <nav class="navbar" id="navbar">
      <a href="#hero" class="nav-logo">
        <div class="nav-logo-icon">N</div>
        <span>Nihal</span>.dev
      </a>

      <ul class="nav-links">
        <li><a href="#about">About</a></li>
        <li><a href="#pillars">Specializations</a></li>
        <li><a href="#pipeline">CI/CD Flow</a></li>
        <li><a href="#skills">Tech Stack</a></li>
        <li><a href="#projects">Projects</a></li>
        <li><a href="#github-stats">GitHub</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>

      <div class="nav-right">
        <div class="status-indicator">
          <span class="pulse-dot"></span>
          <span>Ready to Deploy</span>
        </div>
        <button class="mobile-toggle" id="mobile-toggle" aria-label="Toggle Menu">
          <i class="fa-solid fa-bars"></i>
        </button>
      </div>
    </nav>

    <!-- Mobile Dropdown Menu -->
    <div class="mobile-menu" id="mobile-menu">
      <a href="#about" class="mob-link"><i class="fa-solid fa-user-astronaut"></i> About Me <i class="fa-solid fa-chevron-right mob-arrow"></i></a>
      <a href="#pillars" class="mob-link"><i class="fa-solid fa-cubes"></i> Specializations <i class="fa-solid fa-chevron-right mob-arrow"></i></a>
      <a href="#pipeline" class="mob-link"><i class="fa-solid fa-diagram-project"></i> CI/CD Pipeline <i class="fa-solid fa-chevron-right mob-arrow"></i></a>
      <a href="#skills" class="mob-link"><i class="fa-solid fa-layer-group"></i> Tech Stack <i class="fa-solid fa-chevron-right mob-arrow"></i></a>
      <a href="#projects" class="mob-link"><i class="fa-solid fa-code"></i> Projects <i class="fa-solid fa-chevron-right mob-arrow"></i></a>
      <a href="#github-stats" class="mob-link"><i class="fa-brands fa-github"></i> GitHub Stats <i class="fa-solid fa-chevron-right mob-arrow"></i></a>
      <a href="#contact" class="mob-link"><i class="fa-regular fa-paper-plane"></i> Contact Nihal <i class="fa-solid fa-chevron-right mob-arrow"></i></a>
    </div>
  </header>

  <!-- =====================================================================
       HERO SECTION
       ===================================================================== -->
  <section class="hero" id="hero">
    <div class="container">
      <div class="hero-grid">
        
        <div class="hero-text">
          <div class="hero-greeting">
            <i class="fa-solid fa-hand"></i>
            <span>NAMASTE WORLD, I'M</span>
          </div>

          <h1 class="hero-title">
            Nihal Pandey
          </h1>

          <div class="typewriter-box">
            <span class="role-prefix">I build & automate as a</span>
            <span class="typed-text" id="typed-text"></span>
            <span class="cursor-blink"></span>
          </div>

          <p class="hero-description">
            Passionate multi-stack software engineer specialized in building scalable 
            <strong>MERN Web Applications</strong>, orchestrating robust <strong>DevOps & Cloud Pipelines</strong>, 
            crafting high-performance <strong>Android Apps</strong>, and managing production grade <strong>Git & GitHub</strong> workflows.
          </p>

          <div class="hero-actions">
            <a href="#projects" class="btn btn-primary">
              <i class="fa-solid fa-rocket"></i> Explore Projects
            </a>
            <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="btn btn-git">
              <i class="fa-brands fa-github"></i> GitHub Profile
            </a>
            <a href="#contact" class="btn btn-outline">
              <i class="fa-regular fa-paper-plane"></i> Let's Connect
            </a>
          </div>

          <div class="hero-stats">
            <div class="stat-item">
              <span class="stat-number" data-target="25">0</span><span class="stat-number">+</span>
              <span class="stat-label">Projects Built</span>
            </div>
            <div class="stat-item">
              <span class="stat-number" data-target="99">0</span><span class="stat-number">.9%</span>
              <span class="stat-label">Pipeline Uptime</span>
            </div>
            <div class="stat-item">
              <span class="stat-number" data-target="500">0</span><span class="stat-number">+</span>
              <span class="stat-label">Git Commits</span>
            </div>
            <div class="stat-item">
              <span class="stat-number" data-target="100">0</span><span class="stat-number">%</span>
              <span class="stat-label">Clean Code</span>
            </div>
          </div>
        </div>

        <!-- 3D Profile Hologram Sphere with Orbiting Badges -->
        <div class="hero-visual">
          <div class="orbit-ring">
            <div class="orbit-badge badge-git" title="Git & GitHub Master">
              <i class="fa-brands fa-git-alt"></i>
            </div>
            <div class="orbit-badge badge-devops" title="DevOps Engineer (Docker/K8s/CI)">
              <i class="fa-solid fa-gears"></i>
            </div>
            <div class="orbit-badge badge-mern" title="MERN Stack Developer">
              <i class="fa-brands fa-react"></i>
            </div>
            <div class="orbit-badge badge-android" title="Android Developer">
              <i class="fa-brands fa-android"></i>
            </div>
          </div>

          <div class="avatar-wrapper">
            <div class="avatar-inner">
              <div class="avatar-symbol">&lt;NP/&gt;</div>
              <div class="avatar-name">Nihal Pandey</div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- =====================================================================
       ABOUT & INTERACTIVE CLI TERMINAL
       ===================================================================== */ -->
  <section id="about">
    <div class="container">
      <div class="section-header">
        <span class="badge"><i class="fa-solid fa-terminal"></i> System Bio</span>
        <h2 class="section-title">Under The Hood</h2>
        <p class="section-subtitle">
          An engineering mindset combining robust backend architecture, scalable cloud infrastructure, and intuitive mobile & web experiences.
        </p>
      </div>

      <!-- Interactive Linux/Git CLI Terminal -->
      <div class="terminal-container">
        <div class="terminal-header">
          <div class="terminal-dots">
            <span class="terminal-dot dot-red"></span>
            <span class="terminal-dot dot-yellow"></span>
            <span class="terminal-dot dot-green"></span>
          </div>
          <div class="terminal-title">nihal@production-node: ~/portfolio (bash)</div>
          <div style="font-size: 0.75rem; color: var(--cyan);"><i class="fa-solid fa-lock"></i> SSL Secured</div>
        </div>
        <div class="terminal-body" id="terminal-body">
          <p><span class="term-prompt">nihal@devops-core</span>:<span class="term-path">~</span>$ <span class="term-cmd">whoami</span></p>
          <div class="term-output">
            Nihal Pandey &mdash; Fullstack MERN Architect, Cloud/DevOps Engineer & Native Android Developer.
          </div>

          <p><span class="term-prompt">nihal@devops-core</span>:<span class="term-path">~</span>$ <span class="term-cmd">cat profile.json</span></p>
          <div class="term-output">
            {<br/>
            &nbsp;&nbsp;<span class="term-key">"name"</span>: <span class="term-val">"Nihal Pandey"</span>,<br/>
            &nbsp;&nbsp;<span class="term-key">"role"</span>: <span class="term-val">"MERN + DevOps + Android Engineer"</span>,<br/>
            &nbsp;&nbsp;<span class="term-key">"location"</span>: <span class="term-val">"India"</span>,<br/>
            &nbsp;&nbsp;<span class="term-key">"core_philosophies"</span>: [<span class="term-val">"High Availability"</span>, <span class="term-val">"Automate Everything"</span>, <span class="term-val">"Pixel Perfect UX"</span>],<br/>
            &nbsp;&nbsp;<span class="term-key">"version_control"</span>: <span class="term-val">"Git & GitHub Workflow Specialist"</span><br/>
            }
          </div>

          <p><span class="term-prompt">nihal@devops-core</span>:<span class="term-path">~</span>$ <span class="term-cmd">git status</span></p>
          <div class="term-output" style="color: var(--android-green);">
            On branch main<br/>
            Your branch is up to date with 'origin/main'.<br/>
            nothing to commit, working tree clean. Ready for high-impact engineering!
          </div>

          <!-- Dynamic interaction input row -->
          <div class="term-input-row" id="terminal-input-container">
            <span class="term-prompt">guest@nihal-sys</span>:<span class="term-path">~</span>$&nbsp;
            <input type="text" class="terminal-cli-input" id="terminal-cli-input" placeholder="Type 'help', 'skills', 'contact', 'clear' and press Enter..." autocomplete="off" />
          </div>
        </div>
      </div>
    </div>
  </section>

  <!-- =====================================================================
       FOUR CORE PILLARS (MERN, DEVOPS, ANDROID, GIT)
       ===================================================================== -->
  <section id="pillars">
    <div class="container">
      <div class="section-header">
        <span class="badge"><i class="fa-solid fa-cubes"></i> Core Mastery</span>
        <h2 class="section-title">Four Pillars of My Expertise</h2>
        <p class="section-subtitle">
          Versatile full-lifecycle engineering from system design to cloud automation and user interface.
        </p>
      </div>

      <div class="pillars-grid">
        
        <!-- Pillar 1: Fullstack MERN -->
        <div class="pillar-card pillar-mern">
          <div class="pillar-icon-box">
            <i class="fa-brands fa-node-js"></i>
          </div>
          <h3>Fullstack MERN Stack</h3>
          <p>
            Architecting end-to-end web platforms using MongoDB, Express, React, and Node.js. Proficient with Redux, Next.js, WebSockets, RESTful architecture, and JWT authentication.
          </p>
          <div class="pillar-tags">
            <span class="pillar-tag">React.js</span>
            <span class="pillar-tag">Node.js</span>
            <span class="pillar-tag">Express.js</span>
            <span class="pillar-tag">MongoDB</span>
            <span class="pillar-tag">Next.js</span>
            <span class="pillar-tag">REST APIs</span>
          </div>
        </div>

        <!-- Pillar 2: DevOps & Cloud -->
        <div class="pillar-card pillar-devops">
          <div class="pillar-icon-box">
            <i class="fa-solid fa-server"></i>
          </div>
          <h3>DevOps & Cloud Infra</h3>
          <p>
            Automating deployments and managing microservices. Experienced in containerizing with Docker, orchestrating with Kubernetes, setting up CI/CD pipelines, and cloud monitoring.
          </p>
          <div class="pillar-tags">
            <span class="pillar-tag">Docker</span>
            <span class="pillar-tag">Kubernetes</span>
            <span class="pillar-tag">CI/CD</span>
            <span class="pillar-tag">GitHub Actions</span>
            <span class="pillar-tag">Linux</span>
            <span class="pillar-tag">AWS Cloud</span>
          </div>
        </div>

        <!-- Pillar 3: Android Development -->
        <div class="pillar-card pillar-android">
          <div class="pillar-icon-box">
            <i class="fa-brands fa-android"></i>
          </div>
          <h3>Android Development</h3>
          <p>
            Building native Android applications with Kotlin, Java, and modern Jetpack libraries. Strong focus on MVVM architecture, Room DB, Retrofit networking, and responsive Material Design.
          </p>
          <div class="pillar-tags">
            <span class="pillar-tag">Kotlin</span>
            <span class="pillar-tag">Java</span>
            <span class="pillar-tag">Jetpack Compose</span>
            <span class="pillar-tag">MVVM</span>
            <span class="pillar-tag">Retrofit</span>
            <span class="pillar-tag">Firebase</span>
          </div>
        </div>

        <!-- Pillar 4: Git & GitHub Mastery -->
        <div class="pillar-card pillar-git">
          <div class="pillar-icon-box">
            <i class="fa-brands fa-git-alt"></i>
          </div>
          <h3>Git & GitHub Mastery</h3>
          <p>
            Advanced source control management, git rebasing, cherry-picking, interactive workflows, automated PR testing, release versioning, and open-source collaboration.
          </p>
          <div class="pillar-tags">
            <span class="pillar-tag">Git CLI</span>
            <span class="pillar-tag">GitHub Actions</span>
            <span class="pillar-tag">Git Flow</span>
            <span class="pillar-tag">Merge & Rebase</span>
            <span class="pillar-tag">Release Mgmt</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- =====================================================================
       INTERACTIVE DEVOPS CI/CD PIPELINE
       ===================================================================== -->
  <section class="pipeline-section" id="pipeline">
    <div class="container">
      <div class="section-header">
        <span class="badge"><i class="fa-solid fa-diagram-project"></i> Automation Architecture</span>
        <h2 class="section-title">Interactive CI/CD Pipeline</h2>
        <p class="section-subtitle">
          How code transforms from local development to production with zero-downtime automation. Click any stage to inspect!
        </p>
      </div>

      <div class="pipeline-board">
        <div class="pipeline-header">
          <div class="pipeline-branch">
            <i class="fa-solid fa-code-branch"></i>
            <span>branch: <strong>production/main</strong></span>
          </div>
          <div class="pipeline-status">
            <i class="fa-solid fa-circle-check"></i>
            <span>Pipeline: Passed (All 6 Stages Healthy)</span>
          </div>
        </div>

        <div class="pipeline-nodes-wrapper">
          
          <div class="pipe-node active" data-stage="source" onclick="showPipelineStage('source')">
            <div class="pipe-icon"><i class="fa-brands fa-git-alt"></i></div>
            <div class="pipe-title">1. Git Commit</div>
            <div class="pipe-meta">Trigger Webhook</div>
          </div>

          <div class="pipe-node" data-stage="lint" onclick="showPipelineStage('lint')">
            <div class="pipe-icon"><i class="fa-solid fa-spell-check"></i></div>
            <div class="pipe-title">2. Lint & Test</div>
            <div class="pipe-meta">Jest / SonarQube</div>
          </div>

          <div class="pipe-node" data-stage="docker" onclick="showPipelineStage('docker')">
            <div class="pipe-icon"><i class="fa-brands fa-docker"></i></div>
            <div class="pipe-title">3. Docker Build</div>
            <div class="pipe-meta">Multi-stage Image</div>
          </div>

          <div class="pipe-node" data-stage="registry" onclick="showPipelineStage('registry')">
            <div class="pipe-icon"><i class="fa-solid fa-cloud-arrow-up"></i></div>
            <div class="pipe-title">4. Push Registry</div>
            <div class="pipe-meta">Docker Hub / ECR</div>
          </div>

          <div class="pipe-node" data-stage="k8s" onclick="showPipelineStage('k8s')">
            <div class="pipe-icon"><i class="fa-solid fa-dharmachakra"></i></div>
            <div class="pipe-title">5. K8s Deploy</div>
            <div class="pipe-meta">Rolling Updates</div>
          </div>

          <div class="pipe-node" data-stage="monitor" onclick="showPipelineStage('monitor')">
            <div class="pipe-icon"><i class="fa-solid fa-chart-line"></i></div>
            <div class="pipe-title">6. Monitor</div>
            <div class="pipe-meta">Prometheus/Grafana</div>
          </div>

        </div>

        <div class="pipeline-detail-box" id="pipeline-detail-box">
          <div class="pipeline-detail-content">
            <i class="fa-brands fa-git-alt" id="pipe-detail-icon"></i>
            <div>
              <strong id="pipe-detail-title" style="color:#fff; font-size: 1rem;">Stage 1: Source Control & Versioning</strong>
              <div id="pipe-detail-desc" style="color: var(--text-muted); font-size: 0.85rem; margin-top: 3px;">
                Feature branch merged to main triggers GitHub Actions automated workflow via Webhook.
              </div>
            </div>
          </div>
          <div style="color: var(--android-green); font-size: 0.82rem;">
            <i class="fa-solid fa-bolt"></i> Execution Time: 42s
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- =====================================================================
       TECH STACK & SKILLS DIRECTORY
       ===================================================================== -->
  <section id="skills">
    <div class="container">
      <div class="section-header">
        <span class="badge"><i class="fa-solid fa-layer-group"></i> Arsenal</span>
        <h2 class="section-title">Technologies & Tools</h2>
        <p class="section-subtitle">
          Curated selection of frameworks, libraries, cloud providers, and databases I leverage every day.
        </p>
      </div>

      <div class="skills-filter-nav">
        <button class="skill-filter-btn active" onclick="filterSkills('all', this)">All Technologies</button>
        <button class="skill-filter-btn" onclick="filterSkills('mern', this)">MERN Stack</button>
        <button class="skill-filter-btn" onclick="filterSkills('devops', this)">DevOps & Cloud</button>
        <button class="skill-filter-btn" onclick="filterSkills('android', this)">Android Mobile</button>
        <button class="skill-filter-btn" onclick="filterSkills('git', this)">Git & VCS</button>
      </div>

      <div class="skills-grid" id="skills-grid">
        
        <!-- React.js -->
        <div class="skill-card" data-category="mern">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#61dafb;"><i class="fa-brands fa-react"></i></div>
              <div>
                <div class="skill-name">React.js</div>
                <div class="skill-category-tag">Frontend Library</div>
              </div>
            </div>
            <div class="skill-percentage">92%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 92%;"></div>
          </div>
        </div>

        <!-- Node.js -->
        <div class="skill-card" data-category="mern">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#68a063;"><i class="fa-brands fa-node-js"></i></div>
              <div>
                <div class="skill-name">Node.js</div>
                <div class="skill-category-tag">Runtime Engine</div>
              </div>
            </div>
            <div class="skill-percentage">90%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 90%;"></div>
          </div>
        </div>

        <!-- MongoDB -->
        <div class="skill-card" data-category="mern">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#00ed64;"><i class="fa-solid fa-database"></i></div>
              <div>
                <div class="skill-name">MongoDB</div>
                <div class="skill-category-tag">NoSQL Database</div>
              </div>
            </div>
            <div class="skill-percentage">88%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 88%;"></div>
          </div>
        </div>

        <!-- Express.js -->
        <div class="skill-card" data-category="mern">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#fff;"><i class="fa-solid fa-network-wired"></i></div>
              <div>
                <div class="skill-name">Express.js</div>
                <div class="skill-category-tag">API Backend</div>
              </div>
            </div>
            <div class="skill-percentage">92%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 92%;"></div>
          </div>
        </div>

        <!-- Docker -->
        <div class="skill-card" data-category="devops">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#2496ed;"><i class="fa-brands fa-docker"></i></div>
              <div>
                <div class="skill-name">Docker</div>
                <div class="skill-category-tag">Containerization</div>
              </div>
            </div>
            <div class="skill-percentage">89%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 89%;"></div>
          </div>
        </div>

        <!-- Kubernetes -->
        <div class="skill-card" data-category="devops">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#326ce5;"><i class="fa-solid fa-dharmachakra"></i></div>
              <div>
                <div class="skill-name">Kubernetes</div>
                <div class="skill-category-tag">Orchestration</div>
              </div>
            </div>
            <div class="skill-percentage">82%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 82%;"></div>
          </div>
        </div>

        <!-- CI/CD GitHub Actions -->
        <div class="skill-card" data-category="devops">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#2088ff;"><i class="fa-solid fa-gears"></i></div>
              <div>
                <div class="skill-name">CI/CD & Actions</div>
                <div class="skill-category-tag">Pipeline Automation</div>
              </div>
            </div>
            <div class="skill-percentage">94%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 94%;"></div>
          </div>
        </div>

        <!-- Linux / Bash -->
        <div class="skill-card" data-category="devops">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#fcc624;"><i class="fa-brands fa-linux"></i></div>
              <div>
                <div class="skill-name">Linux & Bash</div>
                <div class="skill-category-tag">System Administration</div>
              </div>
            </div>
            <div class="skill-percentage">90%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 90%;"></div>
          </div>
        </div>

        <!-- Kotlin Android -->
        <div class="skill-card" data-category="android">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#7f52ff;"><i class="fa-brands fa-android"></i></div>
              <div>
                <div class="skill-name">Kotlin</div>
                <div class="skill-category-tag">Modern Android</div>
              </div>
            </div>
            <div class="skill-percentage">87%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 87%;"></div>
          </div>
        </div>

        <!-- Java Android -->
        <div class="skill-card" data-category="android">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#f89820;"><i class="fa-brands fa-java"></i></div>
              <div>
                <div class="skill-name">Java SDK</div>
                <div class="skill-category-tag">Native Development</div>
              </div>
            </div>
            <div class="skill-percentage">85%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 85%;"></div>
          </div>
        </div>

        <!-- Git Core -->
        <div class="skill-card" data-category="git">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#f34f29;"><i class="fa-brands fa-git-alt"></i></div>
              <div>
                <div class="skill-name">Git VCS</div>
                <div class="skill-category-tag">Branching, Rebasing</div>
              </div>
            </div>
            <div class="skill-percentage">96%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 96%;"></div>
          </div>
        </div>

        <!-- GitHub Pro -->
        <div class="skill-card" data-category="git">
          <div class="skill-header">
            <div class="skill-info">
              <div class="skill-icon" style="color:#fff;"><i class="fa-brands fa-github"></i></div>
              <div>
                <div class="skill-name">GitHub Ecosystem</div>
                <div class="skill-category-tag">PRs, Secrets, Packages</div>
              </div>
            </div>
            <div class="skill-percentage">95%</div>
          </div>
          <div class="progress-bar-bg">
            <div class="progress-fill" style="width: 95%;"></div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- =====================================================================
       FEATURED PROJECTS
       ===================================================================== -->
  <section id="projects">
    <div class="container">
      <div class="section-header">
        <span class="badge"><i class="fa-solid fa-code"></i> Portfolio</span>
        <h2 class="section-title">Featured Production Builds</h2>
        <p class="section-subtitle">
          Real-world applications spanning fullstack platforms, automated cloud infrastructures, and mobile applications.
        </p>
      </div>

      <div class="projects-grid">
        
        <!-- Project 1: Cloud-Native MERN Platform -->
        <div class="project-card">
          <div>
            <div class="project-top">
              <i class="fa-regular fa-folder project-folder-icon"></i>
              <div class="project-links">
                <a href="https://github.com" target="_blank" class="project-link-btn" title="GitHub Repo"><i class="fa-brands fa-github"></i></a>
                <a href="#contact" class="project-link-btn" title="Live Preview"><i class="fa-solid fa-arrow-up-right-from-square"></i></a>
              </div>
            </div>
            <h3 class="project-title">Cloud-Native MERN Microservices</h3>
            <p class="project-desc">
              High-throughput enterprise web platform architected with React, Node.js microservices, MongoDB replica sets, and Redis caching.
            </p>
            <ul class="project-features">
              <li><i class="fa-solid fa-check"></i> Dockerized container architecture</li>
              <li><i class="fa-solid fa-check"></i> JWT authentication & role-based RBAC</li>
              <li><i class="fa-solid fa-check"></i> Real-time updates via Socket.io</li>
            </ul>
          </div>
          <div class="project-techs">
            <span class="project-tech-pill">React</span>
            <span class="project-tech-pill">Node.js</span>
            <span class="project-tech-pill">MongoDB</span>
            <span class="project-tech-pill">Redis</span>
            <span class="project-tech-pill">Docker</span>
          </div>
        </div>

        <!-- Project 2: Automated DevOps Pipeline -->
        <div class="project-card">
          <div>
            <div class="project-top">
              <i class="fa-regular fa-folder project-folder-icon" style="color: var(--devops-orange);"></i>
              <div class="project-links">
                <a href="https://github.com" target="_blank" class="project-link-btn" title="GitHub Repo"><i class="fa-brands fa-github"></i></a>
                <a href="#contact" class="project-link-btn" title="Live Preview"><i class="fa-solid fa-arrow-up-right-from-square"></i></a>
              </div>
            </div>
            <h3 class="project-title">DevOps Auto-Deployment & Infra</h3>
            <p class="project-desc">
              Zero-downtime CI/CD pipeline using GitHub Actions, Kubernetes manifests, and Prometheus/Grafana monitoring dashboard.
            </p>
            <ul class="project-features">
              <li><i class="fa-solid fa-check"></i> Automated build, test & security scan</li>
              <li><i class="fa-solid fa-check"></i> Blue/Green deployment strategy</li>
              <li><i class="fa-solid fa-check"></i> Automated Slack alert notifications</li>
            </ul>
          </div>
          <div class="project-techs">
            <span class="project-tech-pill">GitHub Actions</span>
            <span class="project-tech-pill">Kubernetes</span>
            <span class="project-tech-pill">Docker</span>
            <span class="project-tech-pill">AWS</span>
            <span class="project-tech-pill">Grafana</span>
          </div>
        </div>

        <!-- Project 3: Android Kotlin App -->
        <div class="project-card">
          <div>
            <div class="project-top">
              <i class="fa-regular fa-folder project-folder-icon" style="color: var(--android-green);"></i>
              <div class="project-links">
                <a href="https://github.com" target="_blank" class="project-link-btn" title="GitHub Repo"><i class="fa-brands fa-github"></i></a>
                <a href="#contact" class="project-link-btn" title="Live Preview"><i class="fa-solid fa-arrow-up-right-from-square"></i></a>
              </div>
            </div>
            <h3 class="project-title">Android Smart Task & Productivity</h3>
            <p class="project-desc">
              Native Android application built using Kotlin and Jetpack Compose. Utilizes MVVM clean architecture with Room offline sync.
            </p>
            <ul class="project-features">
              <li><i class="fa-solid fa-check"></i> 100% Kotlin & Jetpack Compose UI</li>
              <li><i class="fa-solid fa-check"></i> Offline-first local database caching</li>
              <li><i class="fa-solid fa-check"></i> Coroutines & Flow async processing</li>
            </ul>
          </div>
          <div class="project-techs">
            <span class="project-tech-pill">Kotlin</span>
            <span class="project-tech-pill">Jetpack Compose</span>
            <span class="project-tech-pill">Room DB</span>
            <span class="project-tech-pill">Coroutines</span>
            <span class="project-tech-pill">Firebase</span>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- =====================================================================
       GITHUB METRICS & CONTRIBUTION SHOWCASE
       ===================================================================== -->
  <section id="github-stats">
    <div class="container">
      <div class="section-header">
        <span class="badge"><i class="fa-brands fa-github"></i> Open Source & Code</span>
        <h2 class="section-title">GitHub Activity & Impact</h2>
        <p class="section-subtitle">
          Continuous integration, regular commits, pull request reviews, and open source contributions.
        </p>
      </div>

      <div class="github-overview-card">
        <div class="git-header-bar">
          <div class="git-user-profile">
            <div class="git-avatar">
              <i class="fa-brands fa-github"></i>
            </div>
            <div class="git-user-text">
              <h3>Nihal Pandey</h3>
              <p>@NihalPandey &bull; Fullstack &bull; DevOps &bull; Android</p>
            </div>
          </div>

          <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="btn btn-git">
            <i class="fa-brands fa-github"></i> Follow on GitHub
          </a>
        </div>

        <!-- Simulated Heatmap Grid -->
        <div class="heatmap-section">
          <div class="heatmap-title">
            <span>Contributions Heatmap &bull; 650+ Commits in Last Year</span>
            <span style="display:flex; align-items:center; gap:4px; font-size:0.75rem;">
              Less 
              <span style="display:inline-block; width:10px; height:10px; background:#161b22; border-radius:2px;"></span>
              <span style="display:inline-block; width:10px; height:10px; background:#0e4429; border-radius:2px;"></span>
              <span style="display:inline-block; width:10px; height:10px; background:#006d32; border-radius:2px;"></span>
              <span style="display:inline-block; width:10px; height:10px; background:#26a641; border-radius:2px;"></span>
              <span style="display:inline-block; width:10px; height:10px; background:#39d353; border-radius:2px;"></span>
              More
            </span>
          </div>
          <div class="heatmap-grid" id="heatmap-grid">
            <!-- Populated via JavaScript dynamically -->
          </div>
        </div>

        <!-- Stat Counter Grid -->
        <div class="git-stats-grid">
          <div class="git-stat-box">
            <div class="git-stat-icon"><i class="fa-solid fa-code-commit"></i></div>
            <div>
              <div class="git-stat-val">650+</div>
              <div class="git-stat-desc">Total Commits</div>
            </div>
          </div>
          <div class="git-stat-box">
            <div class="git-stat-icon"><i class="fa-solid fa-code-pull-request"></i></div>
            <div>
              <div class="git-stat-val">85+</div>
              <div class="git-stat-desc">Pull Requests Merged</div>
            </div>
          </div>
          <div class="git-stat-box">
            <div class="git-stat-icon"><i class="fa-solid fa-book-bookmark"></i></div>
            <div>
              <div class="git-stat-val">30+</div>
              <div class="git-stat-desc">Public Repositories</div>
            </div>
          </div>
          <div class="git-stat-box">
            <div class="git-stat-icon"><i class="fa-solid fa-fire"></i></div>
            <div>
              <div class="git-stat-val">120 Days</div>
              <div class="git-stat-desc">Longest Streak</div>
            </div>
          </div>
        </div>

      </div>
    </div>
  </section>

  <!-- =====================================================================
       CONTACT & SOCIALS
       ===================================================================== -->
  <section id="contact">
    <div class="container">
      <div class="section-header">
        <span class="badge"><i class="fa-regular fa-envelope"></i> Let's Collaborate</span>
        <h2 class="section-title">Get In Touch</h2>
        <p class="section-subtitle">
          Have a project in mind, an exciting role to discuss, or want to build robust DevOps pipelines together? Say hello!
        </p>
      </div>

      <div class="contact-grid">
        
        <div class="contact-info-card">
          <div class="contact-point">
            <div class="contact-point-icon"><i class="fa-solid fa-user-astronaut"></i></div>
            <div class="contact-point-text">
              <h4>Nihal Pandey</h4>
              <p>Fullstack MERN, DevOps & Android Engineer</p>
            </div>
          </div>

          <div class="contact-point">
            <div class="contact-point-icon"><i class="fa-regular fa-envelope"></i></div>
            <div class="contact-point-text">
              <h4>Email</h4>
              <a href="mailto:nihalpandey.dev@gmail.com">nihalpandey.dev@gmail.com</a>
            </div>
          </div>

          <div class="contact-point">
            <div class="contact-point-icon"><i class="fa-solid fa-location-dot"></i></div>
            <div class="contact-point-text">
              <h4>Location</h4>
              <p>India (Open to Worldwide Remote & Hybrid Roles)</p>
            </div>
          </div>

          <div class="contact-point">
            <div class="contact-point-icon"><i class="fa-brands fa-git-alt"></i></div>
            <div class="contact-point-text">
              <h4>Source Control</h4>
              <p>GitHub & GitLab CI Specialist</p>
            </div>
          </div>

          <div style="margin-top: 10px;">
            <h4 style="font-family: var(--font-heading); color: #fff; margin-bottom: 10px;">Connect on Socials</h4>
            <div class="social-links-row">
              <a href="https://github.com" target="_blank" rel="noopener noreferrer" class="social-btn" title="GitHub"><i class="fa-brands fa-github"></i></a>
              <a href="https://linkedin.com" target="_blank" rel="noopener noreferrer" class="social-btn" title="LinkedIn"><i class="fa-brands fa-linkedin-in"></i></a>
              <a href="https://twitter.com" target="_blank" rel="noopener noreferrer" class="social-btn" title="Twitter/X"><i class="fa-brands fa-x-twitter"></i></a>
              <a href="https://discord.com" target="_blank" rel="noopener noreferrer" class="social-btn" title="Discord"><i class="fa-brands fa-discord"></i></a>
            </div>
          </div>
        </div>

        <!-- Interactive Contact Form -->
        <div class="glass-card">
          <form id="contact-form" onsubmit="handleFormSubmit(event)">
            <div class="form-group">
              <label class="form-label" for="user-name">Your Name</label>
              <input type="text" id="user-name" class="form-input" placeholder="e.g. Alex Sharma" required />
            </div>

            <div class="form-group">
              <label class="form-label" for="user-email">Email Address</label>
              <input type="email" id="user-email" class="form-input" placeholder="e.g. alex@company.com" required />
            </div>

            <div class="form-group">
              <label class="form-label" for="user-subject">Project Category</label>
              <select id="user-subject" class="form-input" style="background:#0a0e18;">
                <option value="Fullstack MERN Project">Fullstack MERN Web App</option>
                <option value="DevOps & Cloud Setup">DevOps & CI/CD Pipeline Setup</option>
                <option value="Android Mobile App">Native Android App Development</option>
                <option value="Job Opportunity">Full-time / Contract Hiring</option>
                <option value="Other">General Discussion</option>
              </select>
            </div>

            <div class="form-group">
              <label class="form-label" for="user-message">Your Message</label>
              <textarea id="user-message" class="form-textarea" placeholder="Tell me about your goals, timelines, or tech stack requirements..." required></textarea>
            </div>

            <button type="submit" class="btn btn-primary" style="width: 100%;">
              <i class="fa-regular fa-paper-plane"></i> Send Message
            </button>
          </form>
        </div>

      </div>
    </div>
  </section>

  <!-- =====================================================================
       FOOTER
       ===================================================================== -->
  <footer>
    <div class="container footer-content">
      <div class="footer-logo">
        &lt;<span>Nihal Pandey</span> /&gt;
      </div>
      <p class="footer-copy">
        Crafted with precision &bull; Fullstack MERN &bull; DevOps &bull; Android &bull; Git &bull; &copy; 2026 Nihal Pandey.
      </p>
      <a href="#hero" class="btn btn-outline" style="padding: 8px 18px; font-size: 0.82rem; margin-top: 5px;">
        <i class="fa-solid fa-arrow-up"></i> Back To Top
      </a>
    </div>
  </footer>

  <!-- Toast Notification Message -->
  <div class="toast-msg" id="toast-msg">
    <i class="fa-solid fa-circle-check" style="color: var(--cyan); font-size: 1.3rem;"></i>
    <span id="toast-text">Thank you! Your message has been received.</span>
  </div>

  <!-- =====================================================================
       ALL-IN-ONE JAVASCRIPT LOGIC
       ===================================================================== -->
  <script>
    // -------------------------------------------------------------
    // 1. PARTICLES INTERACTIVE BACKGROUND CANVAS
    // -------------------------------------------------------------
    const canvas = document.getElementById('particle-canvas');
    const ctx = canvas.getContext('2d');
    let particlesArray = [];
    let mouse = { x: null, y: null, radius: 140 };

    function initCanvas() {
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;
    }
    initCanvas();
    window.addEventListener('resize', initCanvas);

    window.addEventListener('mousemove', (e) => {
      mouse.x = e.x;
      mouse.y = e.y;
    });

    class Particle {
      constructor() {
        this.x = Math.random() * canvas.width;
        this.y = Math.random() * canvas.height;
        this.size = Math.random() * 2 + 1;
        this.speedX = (Math.random() - 0.5) * 0.8;
        this.speedY = (Math.random() - 0.5) * 0.8;
        this.color = Math.random() > 0.5 ? '#00f5d4' : '#9d4edd';
      }
      update() {
        this.x += this.speedX;
        this.y += this.speedY;

        if (this.x > canvas.width || this.x < 0) this.speedX = -this.speedX;
        if (this.y > canvas.height || this.y < 0) this.speedY = -this.speedY;

        // Mouse interaction repel/attract
        if (mouse.x != null) {
          let dx = mouse.x - this.x;
          let dy = mouse.y - this.y;
          let distance = Math.sqrt(dx * dx + dy * dy);
          if (distance < mouse.radius) {
            this.x -= (dx / distance) * 2;
            this.y -= (dy / distance) * 2;
          }
        }
      }
      draw() {
        ctx.fillStyle = this.color;
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
        ctx.fill();
      }
    }

    function createParticles() {
      particlesArray = [];
      const numberOfParticles = Math.floor((canvas.width * canvas.height) / 16000);
      for (let i = 0; i < numberOfParticles; i++) {
        particlesArray.push(new Particle());
      }
    }
    createParticles();

    function connectParticles() {
      for (let a = 0; a < particlesArray.length; a++) {
        for (let b = a; b < particlesArray.length; b++) {
          let dx = particlesArray[a].x - particlesArray[b].x;
          let dy = particlesArray[a].y - particlesArray[b].y;
          let distance = Math.sqrt(dx * dx + dy * dy);

          if (distance < 110) {
            let opacity = 1 - (distance / 110);
            ctx.strokeStyle = `rgba(0, 245, 212, ${opacity * 0.15})`;
            ctx.lineWidth = 1;
            ctx.beginPath();
            ctx.moveTo(particlesArray[a].x, particlesArray[a].y);
            ctx.lineTo(particlesArray[b].x, particlesArray[b].y);
            ctx.stroke();
          }
        }
      }
    }

    function animateParticles() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
      for (let i = 0; i < particlesArray.length; i++) {
        particlesArray[i].update();
        particlesArray[i].draw();
      }
      connectParticles();
      requestAnimationFrame(animateParticles);
    }
    animateParticles();

    // -------------------------------------------------------------
    // 2. SMOOTH CURSOR AURA EFFECT
    // -------------------------------------------------------------
    const cursorDot = document.getElementById('cursor-dot');
    const cursorOutline = document.getElementById('cursor-outline');

    window.addEventListener('mousemove', (e) => {
      const posX = e.clientX;
      const posY = e.clientY;

      cursorDot.style.left = `${posX}px`;
      cursorDot.style.top = `${posY}px`;

      cursorOutline.animate({
        left: `${posX}px`,
        top: `${posY}px`
      }, { duration: 400, fill: "forwards" });
    });

    // -------------------------------------------------------------
    // 3. DYNAMIC TYPEWRITER EFFECT
    // -------------------------------------------------------------
    const roles = [
      "Fullstack MERN Developer",
      "DevOps & Cloud Engineer",
      "Native Android Developer",
      "Git & GitHub Specialist",
      "Microservices Architect"
    ];
    let roleIndex = 0;
    let charIndex = 0;
    let isDeleting = false;
    const typedTextEl = document.getElementById('typed-text');

    function typeLoop() {
      const currentRole = roles[roleIndex];
      
      if (isDeleting) {
        typedTextEl.textContent = currentRole.substring(0, charIndex - 1);
        charIndex--;
      } else {
        typedTextEl.textContent = currentRole.substring(0, charIndex + 1);
        charIndex++;
      }

      let speed = isDeleting ? 35 : 80;

      if (!isDeleting && charIndex === currentRole.length) {
        speed = 2000; // pause at peak
        isDeleting = true;
      } else if (isDeleting && charIndex === 0) {
        isDeleting = false;
        roleIndex = (roleIndex + 1) % roles.length;
        speed = 400;
      }

      setTimeout(typeLoop, speed);
    }
    typeLoop();

    // -------------------------------------------------------------
    // 4. ANIMATED STAT COUNTER OBSERVER
    // -------------------------------------------------------------
    const statCounters = document.querySelectorAll('.stat-number[data-target]');
    let hasAnimatedStats = false;

    const statsObserver = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting && !hasAnimatedStats) {
          hasAnimatedStats = true;
          statCounters.forEach(counter => {
            const target = +counter.getAttribute('data-target');
            let current = 0;
            const increment = target / 50;

            const updateCount = () => {
              current += increment;
              if (current < target) {
                counter.innerText = Math.ceil(current);
                setTimeout(updateCount, 30);
              } else {
                counter.innerText = target;
              }
            };
            updateCount();
          });
        }
      });
    }, { threshold: 0.5 });

    const heroStatsEl = document.querySelector('.hero-stats');
    if (heroStatsEl) statsObserver.observe(heroStatsEl);

    // -------------------------------------------------------------
    // 5. NAVBAR SCROLL EFFECT & MOBILE MENU
    // -------------------------------------------------------------
    const navbar = document.getElementById('navbar');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 50) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });

    const mobileToggle = document.getElementById('mobile-toggle');
    const mobileMenu = document.getElementById('mobile-menu');
    mobileToggle.addEventListener('click', () => {
      mobileMenu.classList.toggle('open');
      const icon = mobileToggle.querySelector('i');
      if (mobileMenu.classList.contains('open')) {
        icon.classList.remove('fa-bars');
        icon.classList.add('fa-xmark');
      } else {
        icon.classList.remove('fa-xmark');
        icon.classList.add('fa-bars');
      }
    });

    document.querySelectorAll('.mob-link').forEach(link => {
      link.addEventListener('click', () => {
        mobileMenu.classList.remove('open');
        mobileToggle.querySelector('i').classList.replace('fa-xmark', 'fa-bars');
      });
    });

    // -------------------------------------------------------------
    // 6. INTERACTIVE CI/CD PIPELINE LOGIC
    // -------------------------------------------------------------
    const stageDetails = {
      source: {
        title: "Stage 1: Source Control & Versioning (Git/GitHub)",
        icon: "fa-brands fa-git-alt",
        desc: "Developer commits code to feature branch. Pull Request triggers automated GitHub Action matrix build and checks for merge conflicts.",
        exec: "Execution Time: 32s"
      },
      lint: {
        title: "Stage 2: Code Quality, Linting & Unit Testing",
        icon: "fa-solid fa-spell-check",
        desc: "ESLint, Prettier & Jest suites execute across Node.js/React & Kotlin test suites. Quality gate guarantees 0 vulnerabilities.",
        exec: "Execution Time: 54s"
      },
      docker: {
        title: "Stage 3: Multi-Stage Docker Container Build",
        icon: "fa-brands fa-docker",
        desc: "Creates lean, production-ready Alpine Docker image using caching layers and minimal attack surface footprint.",
        exec: "Execution Time: 1m 12s"
      },
      registry: {
        title: "Stage 4: Automated Push to Secure Container Registry",
        icon: "fa-solid fa-cloud-arrow-up",
        desc: "Image tagged with commit SHA and pushed directly to Docker Hub / Amazon ECR with Trivy vulnerability scanning.",
        exec: "Execution Time: 28s"
      },
      k8s: {
        title: "Stage 5: Kubernetes Cluster Rolling Deployment",
        icon: "fa-solid fa-dharmachakra",
        desc: "Kubernetes manifests applied with zero downtime. Pods update gradually with automated health probes (Liveness & Readiness).",
        exec: "Execution Time: 45s"
      },
      monitor: {
        title: "Stage 6: Real-time Metrics & Observability",
        icon: "fa-solid fa-chart-line",
        desc: "Prometheus scrapes endpoint metrics, Grafana visualizes traffic and error rates, while Alertmanager triggers alerts on anomalies.",
        exec: "Status: 99.98% Uptime"
      }
    };

    function showPipelineStage(stageKey) {
      document.querySelectorAll('.pipe-node').forEach(node => {
        node.classList.remove('active');
        if (node.getAttribute('data-stage') === stageKey) {
          node.classList.add('active');
        }
      });

      const detail = stageDetails[stageKey];
      const detailBox = document.getElementById('pipeline-detail-box');
      const iconEl = document.getElementById('pipe-detail-icon');
      const titleEl = document.getElementById('pipe-detail-title');
      const descEl = document.getElementById('pipe-detail-desc');

      iconEl.className = detail.icon;
      titleEl.innerText = detail.title;
      descEl.innerText = detail.desc;
    }

    // -------------------------------------------------------------
    // 7. TECH STACK FILTERING
    // -------------------------------------------------------------
    function filterSkills(category, btnElement) {
      document.querySelectorAll('.skill-filter-btn').forEach(b => b.classList.remove('active'));
      btnElement.classList.add('active');

      const cards = document.querySelectorAll('.skill-card');
      cards.forEach(card => {
        const cardCat = card.getAttribute('data-category');
        if (category === 'all' || cardCat === category) {
          card.style.display = 'flex';
          setTimeout(() => {
            card.style.opacity = '1';
            card.style.transform = 'translateY(0)';
          }, 50);
        } else {
          card.style.display = 'none';
        }
      });
    }

    // -------------------------------------------------------------
    // 8. DYNAMIC GITHUB HEATMAP GENERATOR
    // -------------------------------------------------------------
    const heatmapGrid = document.getElementById('heatmap-grid');
    if (heatmapGrid) {
      const levels = ['lvl-0', 'lvl-1', 'lvl-2', 'lvl-3', 'lvl-4'];
      const totalCells = 180; // ~6 months visual
      for (let i = 0; i < totalCells; i++) {
        const cell = document.createElement('div');
        cell.classList.add('heat-cell');
        
        // Randomly simulate commit density
        const rand = Math.random();
        if (rand > 0.8) cell.classList.add('lvl-4');
        else if (rand > 0.6) cell.classList.add('lvl-3');
        else if (rand > 0.4) cell.classList.add('lvl-2');
        else if (rand > 0.2) cell.classList.add('lvl-1');

        cell.title = `Contributions: ${Math.floor(rand * 12)} commits on Day #${i + 1}`;
        heatmapGrid.appendChild(cell);
      }
    }

    // -------------------------------------------------------------
    // 9. INTERACTIVE BASH TERMINAL EMULATOR
    // -------------------------------------------------------------
    const termInput = document.getElementById('terminal-cli-input');
    const termBody = document.getElementById('terminal-body');

    if (termInput) {
      termInput.addEventListener('keydown', (e) => {
        if (e.key === 'Enter') {
          const rawCommand = termInput.value.trim().toLowerCase();
          termInput.value = '';

          if (!rawCommand) return;

          // Append User Command line
          const cmdLine = document.createElement('p');
          cmdLine.innerHTML = `<span class="term-prompt">guest@nihal-sys</span>:<span class="term-path">~</span>$ <span class="term-cmd">${rawCommand}</span>`;
          termBody.insertBefore(cmdLine, document.getElementById('terminal-input-container'));

          // Output responses
          let responseHTML = '';
          switch (rawCommand) {
            case 'help':
              responseHTML = `Available commands:<br/>
              &bull; <strong style="color:var(--cyan)">whoami</strong>: Display bio info<br/>
              &bull; <strong style="color:var(--cyan)">skills</strong>: View core tech competencies<br/>
              &bull; <strong style="color:var(--cyan)">git log</strong>: Recent git commits & activity<br/>
              &bull; <strong style="color:var(--cyan)">contact</strong>: Quick contact information<br/>
              &bull; <strong style="color:var(--cyan)">sudo hire nihal</strong>: Execute instant hire request<br/>
              &bull; <strong style="color:var(--cyan)">clear</strong>: Clear terminal screen`;
              break;
            case 'whoami':
              responseHTML = `Nihal Pandey &mdash; Fullstack MERN Architect, DevOps Automation Engineer & Android Specialist.`;
              break;
            case 'skills':
              responseHTML = `Frontend: React.js, Next.js, Redux, Tailwind, CSS3<br/>
              Backend: Node.js, Express.js, REST APIs, GraphQL, MongoDB<br/>
              DevOps: Docker, Kubernetes, CI/CD Actions, Linux, AWS, Nginx<br/>
              Mobile: Kotlin, Java, Jetpack Compose, MVVM Architecture`;
              break;
            case 'git log':
              responseHTML = `commit b4927f8 (HEAD -> main)<br/>
              Author: Nihal Pandey &lt;nihalpandey.dev@gmail.com&gt;<br/>
              Date:   Today<br/>
              &nbsp;&nbsp;&nbsp;&nbsp;feat: deploy high-performance fullstack portfolio and automated CI/CD pipeline`;
              break;
            case 'contact':
              responseHTML = `Email: <a href="mailto:nihalpandey.dev@gmail.com" style="color:var(--cyan);">nihalpandey.dev@gmail.com</a><br/>GitHub: <a href="https://github.com" target="_blank" style="color:var(--cyan);">github.com</a>`;
              break;
            case 'sudo hire nihal':
              responseHTML = `<span style="color:var(--android-green); font-weight:700;">[SUCCESS] Authentication granted! Nihal is ready to join your engineering team and build groundbreaking software.</span>`;
              break;
            case 'clear':
              termBody.innerHTML = '';
              const newRow = document.createElement('div');
              newRow.className = 'term-input-row';
              newRow.id = 'terminal-input-container';
              newRow.innerHTML = `<span class="term-prompt">guest@nihal-sys</span>:<span class="term-path">~</span>$&nbsp;
              <input type="text" class="terminal-cli-input" id="terminal-cli-input" placeholder="Type 'help'..." autocomplete="off"/>`;
              termBody.appendChild(newRow);
              // Re-bind listener
              location.hash = "#about";
              return;
            default:
              responseHTML = `command not found: "${rawCommand}". Type <strong style="color:var(--cyan)">help</strong> to see available commands.`;
          }

          const outDiv = document.createElement('div');
          outDiv.className = 'term-output';
          outDiv.innerHTML = responseHTML;
          termBody.insertBefore(outDiv, document.getElementById('terminal-input-container'));

          termBody.scrollTop = termBody.scrollHeight;
        }
      });
    }

    // -------------------------------------------------------------
    // 10. CONTACT FORM SUBMISSION & TOAST NOTIFICATION
    // -------------------------------------------------------------
    function handleFormSubmit(e) {
      e.preventDefault();
      const name = document.getElementById('user-name').value;
      const toast = document.getElementById('toast-msg');
      const toastText = document.getElementById('toast-text');

      toastText.innerText = `Thank you ${name}! Your message was successfully sent.`;
      toast.classList.add('show');

      e.target.reset();

      setTimeout(() => {
        toast.classList.remove('show');
      }, 4500);
    }
  </script>
</body>
</html>

