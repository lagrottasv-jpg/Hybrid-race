# Hybrid-race

<!DOCTYPE html>

<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>The Hybrid Race — El Salvador</title>
<link href="https://fonts.googleapis.com/css2?family=Barlow+Condensed:ital,wght@0,400;0,600;0,700;0,800;0,900;1,700&family=Barlow:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  :root {
    --black: #0a0a0a;
    --yellow: #F5E642;
    --white: #ffffff;
    --gray: #1a1a1a;
    --gray2: #2a2a2a;
    --text-muted: #888;
  }

- { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
background: var(–black);
color: var(–white);
font-family: ‘Barlow’, sans-serif;
overflow-x: hidden;
}

/* ── HERO ── */
.hero {
min-height: 100vh;
display: flex;
flex-direction: column;
align-items: center;
justify-content: center;
text-align: center;
position: relative;
padding: 40px 20px 60px;
background:
radial-gradient(ellipse 80% 60% at 50% 0%, rgba(245,230,66,0.10) 0%, transparent 70%),
var(–black);
overflow: hidden;
}

.hero::before {
content: ‘’;
position: absolute;
inset: 0;
background: repeating-linear-gradient(
0deg,
transparent,
transparent 59px,
rgba(255,255,255,0.03) 60px
),
repeating-linear-gradient(
90deg,
transparent,
transparent 59px,
rgba(255,255,255,0.03) 60px
);
pointer-events: none;
}

.badge {
display: inline-block;
border: 1px solid var(–yellow);
color: var(–yellow);
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 11px;
font-weight: 700;
letter-spacing: 3px;
text-transform: uppercase;
padding: 6px 16px;
margin-bottom: 32px;
animation: fadeUp 0.6s ease both;
}

.logo-line {
display: flex;
align-items: center;
justify-content: center;
gap: 12px;
margin-bottom: 8px;
animation: fadeUp 0.7s ease both;
}

.logo-dash {
width: 40px;
height: 2px;
background: var(–yellow);
}

h1 {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: clamp(72px, 18vw, 180px);
font-weight: 900;
line-height: 0.88;
letter-spacing: -2px;
text-transform: uppercase;
animation: fadeUp 0.8s ease both;
}

h1 .yellow { color: var(–yellow); }

.hero-sub {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: clamp(16px, 4vw, 26px);
font-weight: 600;
letter-spacing: 6px;
text-transform: uppercase;
color: var(–text-muted);
margin-top: 16px;
animation: fadeUp 0.9s ease both;
}

.hero-meta {
display: flex;
align-items: center;
justify-content: center;
gap: 24px;
margin-top: 36px;
animation: fadeUp 1s ease both;
}

.hero-meta .dot {
width: 6px; height: 6px;
border-radius: 50%;
background: var(–yellow);
}

.hero-meta span {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 18px;
font-weight: 700;
letter-spacing: 2px;
text-transform: uppercase;
}

.hero-cta {
margin-top: 52px;
animation: fadeUp 1.1s ease both;
}

.btn-primary {
display: inline-block;
background: var(–yellow);
color: var(–black);
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 16px;
font-weight: 800;
letter-spacing: 3px;
text-transform: uppercase;
padding: 18px 44px;
text-decoration: none;
transition: transform 0.15s, box-shadow 0.15s;
cursor: pointer;
border: none;
}

.btn-primary:hover {
transform: translateY(-2px);
box-shadow: 0 8px 30px rgba(245,230,66,0.35);
}

.scroll-hint {
position: absolute;
bottom: 28px;
left: 50%;
transform: translateX(-50%);
display: flex;
flex-direction: column;
align-items: center;
gap: 8px;
animation: fadeUp 1.3s ease both;
}

.scroll-hint span {
font-size: 10px;
letter-spacing: 3px;
color: var(–text-muted);
text-transform: uppercase;
}

.scroll-arrow {
width: 1px;
height: 40px;
background: linear-gradient(to bottom, var(–yellow), transparent);
animation: scrollPulse 1.6s ease-in-out infinite;
}

/* ── STATS BAR ── */
.stats-bar {
background: var(–yellow);
display: flex;
justify-content: center;
flex-wrap: wrap;
gap: 0;
}

.stat-item {
flex: 1;
min-width: 140px;
padding: 24px 20px;
text-align: center;
border-right: 1px solid rgba(0,0,0,0.15);
color: var(–black);
}

.stat-item:last-child { border-right: none; }

.stat-num {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 42px;
font-weight: 900;
line-height: 1;
}

.stat-label {
font-size: 11px;
font-weight: 700;
letter-spacing: 2px;
text-transform: uppercase;
margin-top: 4px;
opacity: 0.7;
}

/* ── SECTIONS ── */
section {
padding: 100px 20px;
max-width: 1000px;
margin: 0 auto;
}

.section-tag {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 11px;
font-weight: 700;
letter-spacing: 4px;
text-transform: uppercase;
color: var(–yellow);
margin-bottom: 16px;
}

h2 {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: clamp(40px, 8vw, 72px);
font-weight: 900;
text-transform: uppercase;
line-height: 0.95;
margin-bottom: 32px;
}

/* ── FORMAT ── */
.format-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
gap: 2px;
margin-top: 48px;
}

.format-card {
background: var(–gray);
padding: 36px 24px;
position: relative;
overflow: hidden;
transition: background 0.2s;
}

.format-card:hover { background: var(–gray2); }

.format-card::before {
content: ‘’;
position: absolute;
top: 0; left: 0; right: 0;
height: 3px;
background: var(–yellow);
}

.format-num {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 56px;
font-weight: 900;
color: var(–yellow);
line-height: 1;
}

.format-card h3 {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 20px;
font-weight: 800;
text-transform: uppercase;
letter-spacing: 1px;
margin: 8px 0 6px;
}

.format-card p {
font-size: 13px;
color: var(–text-muted);
line-height: 1.5;
}

/* ── RACE FLOW ── */
.race-flow {
margin-top: 48px;
display: flex;
flex-direction: column;
gap: 2px;
}

.flow-item {
display: flex;
align-items: center;
gap: 20px;
background: var(–gray);
padding: 20px 24px;
}

.flow-item.run-item { background: rgba(245,230,66,0.07); border-left: 3px solid var(–yellow); }
.flow-item.station-item { background: var(–gray); border-left: 3px solid #333; }

.flow-icon {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 13px;
font-weight: 800;
letter-spacing: 2px;
text-transform: uppercase;
min-width: 80px;
color: var(–yellow);
}

.flow-item.station-item .flow-icon { color: var(–text-muted); }

.flow-desc {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 18px;
font-weight: 700;
text-transform: uppercase;
letter-spacing: 1px;
}

/* ── CATEGORIES ── */
.cats-grid {
display: grid;
grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
gap: 2px;
margin-top: 48px;
}

.cat-card {
background: var(–gray);
padding: 40px 32px;
position: relative;
overflow: hidden;
transition: transform 0.2s;
}

.cat-card:hover { transform: translateY(-4px); }

.cat-icon {
font-size: 32px;
margin-bottom: 16px;
}

.cat-card h3 {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 28px;
font-weight: 900;
text-transform: uppercase;
letter-spacing: 1px;
margin-bottom: 8px;
}

.cat-card .price {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 42px;
font-weight: 900;
color: var(–yellow);
line-height: 1;
}

.cat-card .price-sub {
font-size: 12px;
color: var(–text-muted);
letter-spacing: 2px;
text-transform: uppercase;
margin-top: 4px;
}

.cat-tag {
display: inline-block;
background: var(–yellow);
color: var(–black);
font-size: 10px;
font-weight: 800;
letter-spacing: 2px;
text-transform: uppercase;
padding: 4px 10px;
margin-bottom: 20px;
}

/* ── REGISTER ── */
.register-section {
background: var(–gray);
padding: 80px 40px;
text-align: center;
position: relative;
overflow: hidden;
}

.register-section::before {
content: ‘’;
position: absolute;
inset: 0;
background: radial-gradient(ellipse 60% 80% at 50% 0%, rgba(245,230,66,0.08) 0%, transparent 70%);
}

.register-section > * { position: relative; }

.register-section h2 {
margin-bottom: 16px;
}

.register-section p {
color: var(–text-muted);
font-size: 16px;
max-width: 500px;
margin: 0 auto 40px;
line-height: 1.6;
}

/* ── MODAL ── */
.modal-overlay {
display: none;
position: fixed;
inset: 0;
background: rgba(0,0,0,0.85);
z-index: 1000;
align-items: center;
justify-content: center;
padding: 20px;
backdrop-filter: blur(4px);
}

.modal-overlay.active { display: flex; }

.modal {
background: var(–gray);
max-width: 480px;
width: 100%;
padding: 48px 40px;
position: relative;
border-top: 3px solid var(–yellow);
animation: modalIn 0.3s ease both;
}

.modal-close {
position: absolute;
top: 16px; right: 20px;
background: none;
border: none;
color: var(–text-muted);
font-size: 28px;
cursor: pointer;
line-height: 1;
}

.modal h3 {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 32px;
font-weight: 900;
text-transform: uppercase;
margin-bottom: 8px;
}

.modal .step {
display: flex;
gap: 16px;
margin-top: 24px;
align-items: flex-start;
}

.step-num {
width: 32px;
height: 32px;
background: var(–yellow);
color: var(–black);
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 18px;
font-weight: 900;
display: flex;
align-items: center;
justify-content: center;
flex-shrink: 0;
}

.step-content strong {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 16px;
font-weight: 800;
letter-spacing: 1px;
text-transform: uppercase;
display: block;
margin-bottom: 4px;
}

.step-content p {
font-size: 14px;
color: var(–text-muted);
line-height: 1.5;
}

.step-content .highlight {
color: var(–yellow);
font-weight: 600;
}

.modal-divider {
border: none;
border-top: 1px solid #333;
margin: 28px 0;
}

.modal-note {
font-size: 12px;
color: var(–text-muted);
text-align: center;
letter-spacing: 1px;
}

/* ── ORGANIZERS ── */
.org-row {
display: flex;
align-items: center;
justify-content: center;
gap: 32px;
flex-wrap: wrap;
margin-top: 48px;
}

.org-badge {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 24px;
font-weight: 900;
text-transform: uppercase;
letter-spacing: 2px;
border: 2px solid #333;
padding: 16px 32px;
transition: border-color 0.2s;
}

.org-badge:hover { border-color: var(–yellow); }

.org-x {
font-family: ‘Barlow Condensed’, sans-serif;
font-size: 28px;
font-weight: 900;
color: var(–yellow);
}

/* ── FOOTER ── */
footer {
background: #060606;
border-top: 1px solid #1a1a1a;
text-align: center;
padding: 40px 20px;
}

footer p {
font-size: 12px;
color: var(–text-muted);
letter-spacing: 2px;
text-transform: uppercase;
}

footer .ig {
color: var(–yellow);
text-decoration: none;
font-weight: 700;
}

/* ── ANIMATIONS ── */
@keyframes fadeUp {
from { opacity: 0; transform: translateY(24px); }
to { opacity: 1; transform: translateY(0); }
}

@keyframes scrollPulse {
0%, 100% { opacity: 1; transform: scaleY(1); }
50% { opacity: 0.3; transform: scaleY(0.6); }
}

@keyframes modalIn {
from { opacity: 0; transform: translateY(20px); }
to { opacity: 1; transform: translateY(0); }
}

/* ── RESPONSIVE ── */
@media (max-width: 600px) {
section { padding: 70px 16px; }
.modal { padding: 36px 24px; }
.hero-meta { flex-direction: column; gap: 12px; }
.hero-meta .dot { display: none; }
}
</style>

</head>
<body>

<!-- HERO -->

<div class="hero">
  <div class="badge">El Salvador's First Hybrid Race</div>
  <div class="logo-line">
    <div class="logo-dash"></div>
    <span style="font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:700;letter-spacing:4px;color:var(--text-muted);text-transform:uppercase;">The</span>
    <div class="logo-dash"></div>
  </div>
  <h1>HYBRID<br><span class="yellow">RACE</span></h1>
  <p class="hero-sub">Strength × Endurance × Competition</p>
  <div class="hero-meta">
    <span>20 · Junio · 2026</span>
    <div class="dot"></div>
    <span>Centro Deportivo BeSport</span>
    <div class="dot"></div>
    <span>El Salvador</span>
  </div>
  <div class="hero-cta">
    <button class="btn-primary" onclick="openModal()">INSCRIBIRME AHORA</button>
  </div>
  <div class="scroll-hint">
    <span>Scroll</span>
    <div class="scroll-arrow"></div>
  </div>
</div>

<!-- STATS BAR -->

<div class="stats-bar">
  <div class="stat-item">
    <div class="stat-num">5</div>
    <div class="stat-label">Estaciones</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">5</div>
    <div class="stat-label">Corridas</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">1km</div>
    <div class="stat-label">Por Run</div>
  </div>
  <div class="stat-item">
    <div class="stat-num">1</div>
    <div class="stat-label">Solo Final</div>
  </div>
</div>

<!-- FORMAT -->

<section>
  <p class="section-tag">El Reto</p>
  <h2>El Formato</h2>
  <p style="color:var(--text-muted);font-size:16px;line-height:1.7;max-width:600px;">
    Inspirado en el formato Hyrox, The Hybrid Race combina resistencia cardiovascular con fuerza funcional. Cada kilómetro te pone a prueba. Cada estación te define.
  </p>

  <div class="race-flow">
    <div class="flow-item run-item">
      <span class="flow-icon">RUN 1</span>
      <span class="flow-desc">1 Kilómetro</span>
    </div>
    <div class="flow-item station-item">
      <span class="flow-icon">ESTACIÓN 1</span>
      <span class="flow-desc">1,000 mts — Row</span>
    </div>
    <div class="flow-item run-item">
      <span class="flow-icon">RUN 2</span>
      <span class="flow-desc">1 Kilómetro</span>
    </div>
    <div class="flow-item station-item">
      <span class="flow-icon">ESTACIÓN 2</span>
      <span class="flow-desc">200 mts — Farmer Carry</span>
    </div>
    <div class="flow-item run-item">
      <span class="flow-icon">RUN 3</span>
      <span class="flow-desc">1 Kilómetro</span>
    </div>
    <div class="flow-item station-item">
      <span class="flow-icon">ESTACIÓN 3</span>
      <span class="flow-desc">80 mts — Burpee Broad Jump</span>
    </div>
    <div class="flow-item run-item">
      <span class="flow-icon">RUN 4</span>
      <span class="flow-desc">1 Kilómetro</span>
    </div>
    <div class="flow-item station-item">
      <span class="flow-icon">ESTACIÓN 4</span>
      <span class="flow-desc">100 mts — Sandbag Lunges</span>
    </div>
    <div class="flow-item run-item">
      <span class="flow-icon">RUN 5</span>
      <span class="flow-desc">1 Kilómetro</span>
    </div>
    <div class="flow-item station-item">
      <span class="flow-icon">ESTACIÓN 5</span>
      <span class="flow-desc">100 — Wall Ball Shots</span>
    </div>
    <div class="flow-item run-item" style="background:rgba(245,230,66,0.15);">
      <span class="flow-icon" style="font-size:15px;">🏁 FINISH</span>
      <span class="flow-desc" style="color:var(--yellow);">¡Cruzar la Meta!</span>
    </div>
  </div>
</section>

<!-- CATEGORIES -->

<section style="background:var(--gray);max-width:100%;padding:80px 20px;">
  <div style="max-width:1000px;margin:0 auto;">
    <p class="section-tag">Categorías</p>
    <h2>Elige Tu Dupla</h2>
    <p style="color:var(--text-muted);font-size:16px;line-height:1.7;max-width:600px;margin-bottom:0;">
      Compites en pareja. Una sola categoría de competencia para todos.
    </p>

```
<div class="cats-grid">
  <div class="cat-card">
    <div class="cat-tag">Pareja</div>
    <div class="cat-icon">👨‍👨</div>
    <h3>Dupla Masculina</h3>
    <div class="price">$120</div>
    <div class="price-sub">por pareja</div>
  </div>
  <div class="cat-card">
    <div class="cat-tag">Pareja</div>
    <div class="cat-icon">👩‍👩</div>
    <h3>Dupla Femenina</h3>
    <div class="price">$120</div>
    <div class="price-sub">por pareja</div>
  </div>
  <div class="cat-card">
    <div class="cat-tag">Pareja</div>
    <div class="cat-icon">👫</div>
    <h3>Mixta</h3>
    <div class="price">$120</div>
    <div class="price-sub">por pareja</div>
  </div>
</div>
```

  </div>
</section>

<!-- REGISTER CTA -->

<div class="register-section">
  <p class="section-tag">Inscripciones Abiertas</p>
  <h2>¿Listo para<br><span style="color:var(--yellow);">el reto?</span></h2>
  <p>Los cupos son limitados. Asegura tu lugar con tu pareja y sé parte de la primera Hybrid Race de El Salvador.</p>
  <button class="btn-primary" onclick="openModal()">INSCRIBIRME AHORA — $120</button>
</div>

<!-- ORGANIZERS -->

<section style="text-align:center;">
  <p class="section-tag">Organizadores</p>
  <h2>By</h2>
  <div class="org-row">
    <div style="display:flex;flex-direction:column;align-items:center;gap:12px;">
      <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAkACQAAD/4QECRXhpZgAATU0AKgAAAAgABwEOAAIAAAALAAAAYgESAAMAAAABAAEAAAEaAAUAAAABAAAAbgEbAAUAAAABAAAAdgEoAAMAAAABAAIAAAEyAAIAAAAUAAAAfodpAAQAAAABAAAAkgAAAABTY3JlZW5zaG90AAAAAACQAAAAAQAAAJAAAAABMjAyNjowNDowNiAxNzoxNTo1MQAABZADAAIAAAAUAAAA1JKGAAcAAAASAAAA6KABAAMAAAAB//8AAKACAAQAAAABAAABaqADAAQAAAABAAABaQAAAAAyMDI2OjA0OjA2IDE3OjE1OjUxAEFTQ0lJAAAAU2NyZWVuc2hvdP/tAG5QaG90b3Nob3AgMy4wADhCSU0EBAAAAAAANhwBWgADGyVHHAIAAAIAAhwCeAAKU2NyZWVuc2hvdBwCPAAGMTcxNTUxHAI3AAgyMDI2MDQwNjhCSU0EJQAAAAAAEAN3iJ2Wi8wdVLmE4wOG8sr/4gIoSUNDX1BST0ZJTEUAAQEAAAIYYXBwbAQAAABtbnRyUkdCIFhZWiAH5gABAAEAAAAAAABhY3NwQVBQTAAAAABBUFBMAAAAAAAAAAAAAAAAAAAAAAAA9tYAAQAAAADTLWFwcGwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAApkZXNjAAAA/AAAADBjcHJ0AAABLAAAAFB3dHB0AAABfAAAABRyWFlaAAABkAAAABRnWFlaAAABpAAAABRiWFlaAAABuAAAABRyVFJDAAABzAAAACBjaGFkAAAB7AAAACxiVFJDAAABzAAAACBnVFJDAAABzAAAACBtbHVjAAAAAAAAAAEAAAAMZW5VUwAAABQAAAAcAEQAaQBzAHAAbABhAHkAIABQADNtbHVjAAAAAAAAAAEAAAAMZW5VUwAAADQAAAAcAEMAbwBwAHkAcgBpAGcAaAB0ACAAQQBwAHAAbABlACAASQBuAGMALgAsACAAMgAwADIAMlhZWiAAAAAAAAD21QABAAAAANMsWFlaIAAAAAAAAIPfAAA9v////7tYWVogAAAAAAAASr8AALE3AAAKuVhZWiAAAAAAAAAoOAAAEQsAAMi5cGFyYQAAAAAAAwAAAAJmZgAA8qcAAA1ZAAAT0AAACltzZjMyAAAAAAABDEIAAAXe///zJgAAB5MAAP2Q///7ov///aMAAAPcAADAbv/AABEIAWkBagMBIgACEQEDEQH/xAAfAAABBQEBAQEBAQAAAAAAAAAAAQIDBAUGBwgJCgv/xAC1EAACAQMDAgQDBQUEBAAAAX0BAgMABBEFEiExQQYTUWEHInEUMoGRoQgjQrHBFVLR8CQzYnKCCQoWFxgZGiUmJygpKjQ1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4eLj5OXm5+jp6vHy8/T19vf4+fr/xAAfAQADAQEBAQEBAQEBAAAAAAAAAQIDBAUGBwgJCgv/xAC1EQACAQIEBAMEBwUEBAABAncAAQIDEQQFITEGEkFRB2FxEyIygQgUQpGhscEJIzNS8BVictEKFiQ04SXxFxgZGiYnKCkqNTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqCg4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2dri4+Tl5ufo6ery8/T19vf4+fr/2wBDAAICAgICAgMCAgMFAwMDBQYFBQUFBggGBgYGBggKCAgICAgICgoKCgoKCgoMDAwMDAwODg4ODg8PDw8PDw8PDw//2wBDAQIDAwQEBAcEBAcQCwkLEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBD/3QAEABf/2gAMAwEAAhEDEQA/APw7ooorsOcKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAP//Q/Duiiiuw5wooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooA//9H8O6KKK7DnCiiigAooooAKKKKACiiigAooooAKKKKACiipIopZ5FhhQySOQFVRkknoAB1NA0m3ZEdFe0eGvgF8SvEYSZtPGlW75/eXreUeP+mYDSD2ygHvXuWifspaREFfxFrk1wSOUtY1hAP++/mZH/ARW0aUpbH6RlnAmfY5KdPDuMX1lZfg7NnxLRX6X6V8AvhXpYRv7H+2SL/HcSySZ+q7gn/jtekaX4V8L6KwbSNHs7Jh0MNvHGfzVQa9CGCct5H6VhPB7MJ/7ziIw9E3+dj8k4NPv7n/AI9raWXP9xGb+QrZg8G+L7rH2bQ76XP9y2lb+S1+uh560wjFenDK4S3kfRx8HaC+PFN+kUv1PyVm8B+ObcZn8O6jGP8AatJh/NayZtB1y2/4+NOuYsf34XX+Yr9fSO9NrvjkdOX239xnU8IcP9jEy+5P9T8cCCDgjBFJX696jomjauuzVrC3vR0xNEkg/wDHga4DVPgt8L9WJa58PwRMe9uXt8fhEyj9Kb4cqP8AhzT9VY+ZxXhLi4f7viIy9U1+Vz8w6K+7tZ/Zb8H3QZtF1K70+QngPsnjH/AcI35vXiviT9mzx9o26XSDDrUIz/qm8uXA7lJMD8FZjXl18hxtJX5eZeWv4b/gfnuYcCZ3g05OjzJdYu/4bnz3RV/UdL1PR7prLVrSWyuF6xzI0bj8GANUK+dlFxdpKzPzmcJQk4TVmujCiiioMwooooAKKKKACiiigAooooAKKKKACiiigAooooA//9L8O6KKK7DnCiiigAooooAKKKKACiiigAooqWGGa5mjt7eNpZZWCoigszMxwAAOSSegoGk27Iirc0Dw1r3im+GneHrGW+uDjKxrkKCcZdjhVHuxA96+iPh9+zhqWotBqvjmQ2FrlWFnHzPIuDxI3SP+HgbmIyDsPNfYmgeHtD8L2C6XoFlFY2q4O2NcbmAC7mPVmIAyzEk45NcMsVBO0dT+guGPCzH49Rr5i3Sp9vtNenT5/cfKvg79l6SQJd+ONQ8sHn7LaYLfRpWGPYhVPs1fT/hnwN4S8HReX4c0uGzbGDIBulYHs0jZcj2JxWF4y+KngrwMGj1m/D3ajItYMSznp1UHC5ByN5UHtXyt4t/aa8V6qXtvC1tHo1ueBI2Jrgj6sNi5HbaSOzVtTnKWp+zzxXCPCK5KaTqrt70/m3t+B9zalqumaPaNf6tdxWVsmN0kzrGgJ6DcxAya8U139pL4b6QTFYy3GrSDI/0eLCAj1aUpx7qDX5/6rrOra5dG+1m9mvrhuPMnkaRsemWJ49qz0R5G2opYnsBk13Kq1sflmbeMGNqtxy+jGC7vV/crJfifW2rftX6u+V0HQYLfHRrmVps/8BQR4/76Necan+0V8VNQZvJ1GKxRv4YLePH4GQOw/OvHf7NulUPOFgU85lYJ/PmqryaTEP3+ox59I1aT+QxQ8RP+Y/LMZxxn+Kv7TFSXpaP5Hb3fxR+I965ebxNqAJ7R3MkY/JCBWTL408Yz/wCu12/k/wB66lP82rl21Tw9GMGS4lP+yiqP1aojrehDpDcn/gSD+hrN15fzM+UqZljqjvUrSb822dRH4u8Vw8xa1ep/u3Mg/k1aMHxF8f27BofEmpLjt9rlI/ItiuGGtaH/AM8Lkf8AAkP9KkXVvDz8E3MfuVRh+hFOOIktpMiGPxkHeFVr0b/zPZNP+PfxU0/ao1o3CL/DPDFJn6sV3frXoWl/tU+LYGA1jSbO8QdfKMkDn8SZB/47Xy+lxok3EeoBT6SRsv6jIq2lhJOAbSSK5B/55uGP5ZBr0KWaYmn8FR/PX8z6HDcW55hvgxMvm7/nc+5dD/ai8F3xSPW7G60t26sAs8S/Urtf8kr3Lw94w8LeK4RN4d1SC+GMlUceYo/2ozh1/ECvyflgmhO2ZGQ/7QIohmmt5Unt5GiljOVZSVZSO4I5Br6bC8T4im/3sVJfc/8AL8D9By/xRzGk0sbCM15aP8Lr8D9btY0LRtftTY65Yw38B/gmQOAT3Geh9xzXzn4v/Zj8O6gHuvCF2+lTnJEMpM0BPoCfnX65b6V4R4U/aB+IPhspDeXQ1m0XrHd5Z8d8SjD5/wB4sB6V9R+Df2gvA3igpa6jIdEvX42XJHlE/wCzMML/AN9bfYV9jSzDK8ySp10ubz0fyf8AwT9IhnnDPEcVSxUVGb6SVn8pI+JvGHw28YeBpSNesGW3JwtzH+8gb0w46E9g2D7Vwtfr/NDbXlu0MyJPBMuGVgGR1bsQcggivmP4hfs4aRqwk1PwOy6beHLG1cn7PIevynkxn25XoAF614mY8JTgnVwUuZfyvf5PqfAZ94a1aKdbLJc0f5Xv8nsz4corY13QNZ8NajJpWvWclldR9UkGMj1U9GU9iCQexrHr80nCUJOM1ZrofglSlOlNwqRakt09GvVBRRRWZiFFFFABRRRQAUUUUAFFFFABRRRQB//T/Duiiiuw5wooooAKKKKACiiigAoor1j4YfCnVviHemdibTR7dgJrkjlj/wA84s8F8dT0UcnnAOFatTowdSo7JHrZblmKzLEwwmDg5zlsl+b7JHL+DPA3iLx3qX9naFBuCYMsz/LFCp7u2D+AGSewr71+Hfwn8NfD+FZrdPtuqMMPeSqN/IwRGOdi/Tk9yeK7Dw94d0fwrpcWj6FbLbW0XOB1Zj1Zj1Zj3Jryj4nfG/SPBQk0jRQmo60MhkzmGA/9NCOrf7AOfUjjPxEsfWxtT2dFe7/W5/a2ScJ5PwhhP7SzWalVX2nsn2it2/lc9Y8TeL/D/g3TjqfiG8W1i5CKeZJGH8KIOWP06dTgc18ZePv2hvEniIyaf4W36Lp5yN6n/SpBnglx/q+3CHI5+YivEdf8R634p1F9W167e8uX43OeFHXaqjhVHYAAVnQ2ryIZnYRQr96RzhR/ia+pw2DjSV56v8D8O4q8TsfmblQwF6VLy+Jrza2+RXZmdi7kszHJJ5JJq0tlJ5fn3LLbw/35DtH4Dqay7nX7SzzHpUfmyD/ltIOP+Ar/AFNctdXl1eyGa7laVz3Y5/L0rvc+x+EWb1Z1s+s6PacW8b3sg/ib5I/y6msifxNqsqmKGQWsfPywgJ19+v61z1FZNt7lpIleSSVt8rF2Pdjk/rUVFFIYUUUUAFFFFABTgSDkHBFNooA2rbxBq9p8iXDOn9yT51/Js1sweINPuMLqFr5LHHzwHj8UP9DXGUU02hNHo8drHdp5mmzLdKOSF4cfVTzVUgqSrDBHY1w0cjxuHiYow6EHBH411Fr4ldwIdXj+0r0Eg4lX8eh/GtVPuQ49j2PwF8X/ABf4BkSCzn+26aD81nOS0eM8+WesZ+nGeSDX3F8P/i14U+IMSxWEv2TUguXs5iBIMdSh6OvuOcdQK/Nb7NFPCbrT5Rcwjrjh1/3l6ioIJ57WaO5tpGimiYMjoSrKw5BBHII9a+1yviHEYNqLfNDs/wBH0P0rh/jbMMqapTfPT/lb29H09D9VfFvgvw743006Z4htFnTny5BxLEx/ijfqD+h7gjivgn4m/BrX/h9K9/DnUNFZsLcqOY89FlUfdPYN908dCcV618Lv2inVodC+IL7lOFj1ADkegmA6/wC+P+BDq1fXhFlqdngiO6tLpPaSOSNx+IZSD9CK/SquGwGe0PaUnaa69V5NdUfuuJwGTcXYX29CXLUXW2q8muqPyFor6h+MnwKfw+k/irwbG0mmjLXFqMs9uOpdOpaMdx1Xryudvy9X41jsBXwdZ0qy16Po13R/LucZNisrxDw2KjZ9H0a7p9goooryz54KKKKACiiigAooooAKKKKAP//U/Duiiiuw5wooooAKKKKACiivSPhh8ONT+JHiFdNtt0Njb4e7uAOI4yeg7F2xhR9T0BrCvXp0Kcq1V2itz0cFgq+MrxwuGjzTk7JL+tupsfCb4UX/AMQ9RNzc7rbRLRgJ5hwXbr5Uef4iOp6KOTyQD+g+m6Vp+i6fBpWlwLbWlsoSONBgKB/XuSeSeTzVrSNC03w7pdtoujwLbWlogSNF7DuSe5J5JPJPJr5J+OfxlJe48E+Ep8KMx3t0h6noYoyO3ZyP90d8/j0sXiM6xXs6atBfgu78z+4cuwWV8C5TLE4l81WW7W8n/KuyRN8X/jmLYzeGPA9xmYEpcXqdE7FYW9fVx0/h55HyASztk5ZmP1JJoRHkYIg3M3AAov8AUotFBgtiJb49W6rF7D1b+VfquEwlLC0vZ0/m+rP5B4j4kx2e4p4nFy0XwxWyXZL82TXMtnpKCTUP3k5GUgB59i57D261x+o6rd6m4a4bCL92NeEUewqhJJJNI0krFnY5JPJJqKulybPkkrBRRRUjCiiigAooooAKKKKACiiigAooooAKKKKACiiigC3a3dzZTCe1cxuvcf1rs7LU7PWMRT7bW8PfpHIf/ZT+lcDRTi2hNXPQJYpIJDFKpRl6g17l8I/jPf8AgKddI1gveaDIfuA5e3Ynl489v7yfiOc5+fNM1uOZF0/Vm+UcRzdWT2b1X+ValxbyWz7JO/II5BHqDXsYLG1cLVVWjK0l/Vn3R6eXZlicuxEcThZ8sl9zXZrqj9btN1PT9a0+DVNLnS6tLlQ8ciHKsp/zgg8g8Hmvjj44fBMaV5/jPwdB/oXL3dog/wBT3MkYH8H95f4eo+XO3zf4R/Fq/wDh5qQs70tcaHdN++h6mNjx5sfuO46MPfBH6I2N9Y6vYw6hp8q3NrdIHjdTlXVhwa/baNbC59hHTqK0196fdH9V4bE5dxhlrpVVy1I7rrF913TPyIor6P8Ajr8I/wDhE7tvFXh2HGjXT/vY1HFtKx9O0bH7vYH5eMrXzhX4vjsFVwdeVGqtV+K7o/lfNsqxGWYqeExKtJdejXRryYUUUV5p4QUUUUAFFFFABRRRQB//1fw7ooorsOcKKKKACiiigDY0DQtT8T61Z6Bo8RmvL6QRxr2yepJ7KoyWPYAmv1R8AfD7S/h34Zg0DTv3kg+e4nIw00xHzOfQdlHYADk5J8j/AGX/AIU/2FoX/CwNahxqGrJi0VhzFan+P6y9R/sYwfmIr1v4t/EGy+GfhWbWpQst9MfKs4GP+smI6kDB2KOW6ccZBIr8K4izSePxccvwusU7adX/AJI/sHgHJMPkmXzzrH+7OUb3fSP+bPDv2gvi2fC9s3g3w5Nt1a7TNxKp5tonHAB7SOOndV56lSPgkBnYKoyScAe9XNS1G91fULjVNSma4uruRpZZG6s7HJNQXd4NEtRKP+P2cfux/wA81/vH3Pav1fKstp5fh1SjrLq+7/yP534p4kxGe46WJqaQWkY9l/m+pDqeoLo0bWdqQbxxiRx/yzB/hH+16+lcKSSSSck0rMzsWY5JOST3NMr027nxqVgooopDCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACur0bV49g0zUW/0c/wCrkPWIn/2X1rlKKadgPQriCS2lMUg5HQjoQehB9DX0B8DPiy/g/UU8Na9N/wASS9f5XY8WsrfxA9kY/eHb73rn5x0TUFvoV0i7bEi/8e7n1/uH2ParTKyMUcYZTgivawGOq4StGvReq/Fdn5M9XK8zr5bioYvDu0o/c11T8mfrtf2Flq1hPp2oRLcWt0hjkRuVZGGCK/M/4pfD+6+HnieXS/nksJ/3tpMw+/Ef4SRxuQ/K3TscAEV9Qfs8/E469pw8Fa1KDf6dGPsrngy268bfdox+a/QmvU/ip4BtviF4Vm0wBVv7fMtnIeNsoH3Sf7rj5W/A4yBX7PmOGo5zgI16HxrVd/NM/qHPMDh+KcnjjcGv3kVePe/WLPzEoqWeCe1nktbmNoZoWKOjgqyspwVYHkEHgg1FX4U1bRn8hNNOzCiiikIKKKKACiiigD//1vw7ooorsOcKKKKACvYfgd8NpPid49tNHmQnTLT/AEm+YcfuEI+TPrIxCjuASe1ePV+tf7Lfw0/4Qj4awavfRbNU8SbbyXI+ZYMfuE/75Jf1Bcg9K+L4ozb+z8DKUH78tI/Pd/JH6BwfkyzLMoQqK8I6y80tl82e0SxW1lbfwQW9unsqIiD8AAAPwFfkZ8bfiVL8SvGtxf27n+ybHMFih4Hlg8yEf3pD8x74wD0r7f8A2t/iKfCfg6PwfpsuzUfEQZZNp+aOzXiQ+3mH5B6rv9K/MOON5ZFjjGWY4A+tfHcD5Vam8wqrV3UfTq/n+h+k+JPELqSjlNF+7Gzl5vovkieHyYIZNQuxmC37f33P3V/HvXDXt5Pf3T3c5y8hz7AdgPYVt+I71HmTTLdsw2nBI/ik/iP9BXL1+uSd2fz4lYKKKKgoKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigB4JQhlOCOQRXf292NYsftn/L1BhZh/eHZ/6GvPa1NJ1FtMvUuMboz8si/3kPUVSdmJq53mi6xqHh/VrTWtLlMN1ZyLJGw9R2PqCOCO44r9R/BXiux8a+GbLxHYYVblP3kecmKVeHQ/Q9PUYPevytu4Vhl/dHdE4Do3qrcivov9m7x0dD8Sv4SvpMWWsn91k8JcqPl/7+D5fcha/RuGM0eGxHsZv3Jfg+n3n674fZ88Fj/qdR+5UdvR9H8zQ/aV8BHTNYh8b6bFi11IiO62jhLhR8rHn/loo7DGVJJywr5br9Y/F3hqz8W+HNQ8O33EV7EUDYzscco491YA/hX5V6ppt5o2pXWk6gnl3NnK8Mq9cOh2nnvyOvenxTlyoYj6xTXuz/B9fvK8Q8iWBx/1ykvcq3b8n1+8oUUUV8EfjIUUUUAFFFFAH//X/Duiiiuw5wooooA9R+DHgRviR8StE8Kupa1mmEt0R2tofnl57blG0H1Ir9wpUjijO7CIg+gAH8sV8GfsJeBwtn4h+Il1H80rLptsx7KuJZ/wJMYB9iK+gP2ofGx8C/CDVpreTZe6xjTrcjrm4B8wj0IiDkHscV/NfFmInmWcwwFJ6RtFer3fyP6d4OpU8ryaePrLWV5P0Wy+e5+W/wAbvH5+JPxJ1bxHCxNiH+z2YJzi2h+VCPTecyEdixry83A02wn1I8Sf6uH/AH2HJ/AVAAScDkmszxPcYuItLjPyWa4b3kblv8K/oejQhhqEaNJWjFJL5H844nEVMVXliKrvKTbfqzlySxyeSabRRTMAoopcGgBKKUgjrSUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQB3GjXP27S3s3OZbL5094z94fgeat21zPZ3MV5ayGKaB1kR1OCrKcgg+oNcho99/Z2oQ3J+4DtceqNww/Kuxu4Ps9y8IOVB+U+qnkH8q6KcmtiG3FqSP1U8D+KLfxn4U03xHAAv2yIGRB0SVflkX6BgQPUc18b/ALTPhL+yfFlt4ntkxBrMeJMdBPCAp+m5Np9yCa7H9ljxTkat4NuH6YvbcenRJR/6AQPqa9j+OnhgeJfhxqSou6400C9i/wC2IO/84y3Hriv22vJZnlPN9pK/zW/36n9eY5LiThX261mlf/t6O/3n5rUUUV+LH8fBRRRQAUUUUAf/0Pw7ooorsOcKKK7D4feGz4w8d+HvCvO3Vr+2tnI7JLIqu34KSfwrKrVjSpyqz2SbfyNaVOVScYR3bt95+1PwB8HDwV8HPC+iumyd7RbqcEYbzrr984b3Uvt+gr4W/bs8XfbfGOh+Cbd8xaTatdTAH/ltdNgBh6qiAj2ev1ZaFY1CIAqqMAAcACvwU+PniN/FXxk8Xau7bl/tCW3jPrFanyIz+KoDX808EU5Y7OJ42rvFOXzbt+TP6M4yrrCZPDBU9m0vklf8zy6w2Cc3Ev8Aq7dWlb6IM/zrz2aZ55pJ5Dl5GLH6k5rtr6X7NoVw4OGuXWEfQfM39K4Kv6Tm9T+c4rQKKKKzLNPSLRL/AFSzspG2JPKiFvQMQCa/RyH4VeA4tEXRm0eB02YMjKPNJx97f1z+NfmmjNG4dDhl5Br2KL46fEaHRxo6XyFAmwSmMGYL0+9/XGa8bH4etW5fZStY/VuDs9yvLFXWYUeZySs7J+q12uec+J9Nh0jxDqOl27+ZFaTyRq3qFOBWBX0f8N/ghJ470c+Jdc1CS0juWbygih3fB5ZiegzXnHxK+H138PNaXTZZvtFvOnmQy4wWXOCCOxB612U8VTlP2SleSPm8dw7j6OFWaTpctGbutVontpul6nm9FFFdp8aFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABXoMM323SLO7Jy8YMD890+7/AOOmvPq7Dw3L5tpf2JIyFWZfqhw36Gri7MlrQ9N+FXiI+FviBourM2yHz1hmJ6eVN+7cn/dDbvqK/UaaKOaJ4JlDxyAqynkEHgg/Wvx46c1+s3gvWG8QeENG1qRg8l5aQySEc/vGQbx+DZFfqfC+JajOi/X9Gf034U45zp4jAy6NNfPR/kflx4q0V/DniXVNBfJ+wXMsIJ/iVGIVvxGDWBXv/wC0po6aZ8SXvY+mqWsNweOAy5hIH4Rgn614BXw2OoexxM6S2Tf3dPwP5/zzA/Usyr4VbQbS9L6BRRRXnHzwUUUUAf/R/Duiiiuw5wr6j/Y20L+2/j9oMjpvj0yK6u3H+5CyIfwd1NfLlffn/BPbSxcfE3xFqzDItNIMI9jPPEf5RmvkuKK/sMoxE12a+/Q+lyCkqmZ0Iv8AmT+7X9D9PPGGrr4a8K614jfG3S7K4ujnpiCNpOfyr+cqSR5ZGllYu7ksxPJJPJJr97f2oNRbRfgL40vFO3zLL7Pn/r6kSA/+h1+B9fm/hnRSw1ev3kl92v6n3vH1dyr0aPaLf3u36FPxI5js9OtfVXlI/wB44H6CuPrpvFRxqSQf88IYk/8AHc/1rma/anufkiCiiikMcAWIVRkmvSYPhN4/uNHGtxaRIbcrvAyN5XrkJnOPwrh9IuIbTVbO7uU8yKGZHdfVVYEj8q/Ta38a+EpdGTWk1SAWnl7s71BHHTb1z2xivGx+Lq4fl9nG9z9Y4N4awGbqs8ZX5OVKyTS3vr6I+Wvhb8cNM8IaAvhvxHaylbQt5TxAE4Y5KsCRznvXFeOvE2qfGTxVbw6Bp8jLEhjgiGC5GcsznoP5CvMvFF3b6p4j1PUbFNlvc3EkkY9FZiRXtP7PHiLQ9B8R3cGsypbvexKkMshAUMGyVyemf6UTowoqWJpw9+xeEzfFZnOjkGLxCWHUrc1km0r21foeWeKPh94r8HpHLrtg1vHMcK4IdCfTKkgH2NcQRg4r7w+PPijw3H4Kn0YXMNxe3bJ5SIwcrtYEucZwMV8HnrXRgcROvS56kbM8Di3JsLlWYfVsJU542T6Np9nbQSiiivRPgwooooAKKKKACiphBOyeYsbFPUA4/OoaACiiigAooooAKKKKACiiigAooooAKKKKACui8Lyqmswxt92cNEf+BqR/PFc7V7T5TBf204OPLkRvyIoA68gqSp4I4r9E/wBm/VP7R+GFtank6dcz2/5sJh+klfnvqCeXfXC+kjfzr7P/AGT75pNG8Q6YT8sFxBMB7zIyn/0XX2WRVeTFLzTX6n694ZYh0s9jT/mi192v6Gd+1fpg8vw7q6ryDcQO312Mg/Rq+Na/QH9qCzNx8O7e4A5tb+FyfZkkT+bCvz+oz2NsW5d0n+n6HN4k4ZUc+nJfaSf4W/QKKKK+ZPyIKKKKAP/S/Duiiiuw5wr9Nv8AgnDaLLeeP7s/eij0yMfSQ3JP/oFfmTX6j/8ABNhdw+I3t/ZH/t5X55x07ZFXa8v/AEpH2HCz/wCFSl8/yZ7/APttXBtf2edeiH/LzPYxn8LmN/8A2Svw5r9v/wBuxEH7P9+zNtP26ywMZyfM6e3GT+FfiBXg+GyX9kyf99/kj2eNZXzCP+FfmzD8UHOv3nswH5KBXP1ueJP+Q7fZ/wCeprDr9VPz4KKKKACpllfI+aprG0lv7yCyh5kndUXPTLHAr7Ji/Zl0E6MFl1Kf+0yuS4C+UGx024zjPvmuHEYulQt7R2ufX5Lw3mGbqbwULqO92lv016s3/gT4U8NL4Jt9Za2iu7y9L+a8ihyu1iAoznAAGa8Q/aC8OaN4f8S2k2jRpbm9hLyxIAFVg2AQB0zXE6d4y8ZfDS/vtC0i/MHkyskiFQ8ZdTjIDdPrXF65r2reI9Qk1TWLlrq5l6s3p2AHQD2FcVDCVY4iVZyvFn2ma8R4CrkVPKo4flqxsm7Kya3ae7bMcuzdTmv6Lv8AgjT8LfDWqfB/xv4z8R6NZ6k2oaxFaQtdW8cxVbSEO20upwCZucelfznV/Xd/wS48JHwp+xn4PmdQsuuTX2otxjPmTtGpP/AI1r2z8cPre78M/BSx1m18OXuleHrfVr5We3s5ILRLiZV+80cRAdgO5AOK+I/27/2I/g18Tfgv4o8ZeHfDVj4f8ZeHLGfUbW+sIEtTP9lQyNDOsQCyK6ggFgSpwQeoNH44fstfGX4uft4/Df4x2q2+n+AfAlvaSPdm5UTyzQTSTvEkK5f5yUUkgLjPPau+/wCCh37Tngn4D/AnxD4bu7+OXxd4v0+4sNM09GDTEXCmJ7h1zlYowxO48FgFHJoA/kHAJOBya9w0H9mn9ofxTpi614c+GniPUbCRdyTwaVdPGy+qsI8MPpmv1x/4JH/sheGfFlte/tIfETTY9SisrlrPQba4QPEJogDNdFGyGKEhI85AbceoBr9YvHf7YPw38A/tHeEf2Y7yzvbzxJ4qjRxNAqG2tPN3CESlmDEuUP3VO0YJ60Afxq65oGu+GdTm0XxHp9xpWoW5xLb3cLwTIfRkkCsPxFf0R/8ABMf9hP4Zn4WaX8f/AIraHb+I9c8RF5tMtr6MTW1naRuUSTyXyjSyFSwZgdq7duCSa9S/4K9fB/wr4o/Zyl+KsllFH4i8IXdr5V2FAle2upVgkhZhyyZcOAehHHU5+qv2CfFmh+Lv2Rfhpe6FKrpY6XHYTqpGY7i0JilVh2ORu+hB70AfTM1l4M0a2j0+4g0+xgcbY4mWKJCB2VTgfgK/l0/4Kz6j4bu/2p4/C/hLTbSzTRtItIphZQRx+dc3DPMS3lgbm2MgBOTX2j/wWK/Zv8Z+Ik0f9orw082oaZoNoNO1S1UlvskXmF47pVHRCzlZT2+U9AcfmN/wTz8MSeOv2yfhvZ3ga5SyvWvn3/P8tjE865z2ygFAHhPh/wDZy/aA8VwLdeG/ht4j1KBukkGlXTofowjx+tZfjT4HfGX4c2ov/H3gbW/DtqTjzr/T7i3iz6b3QL+tf21fEv4ieGvhN4C1z4j+MJJItG8PWsl3dNEnmSeXGMkIuRuY9AM8mq/hDxT4L+NXw403xZpUa6p4Z8VWSzxx3UIxLbzLyskTgj1DKc0AfwkV6D4J+FPxO+JMkkXw98J6r4laI4f+zrKa6CH/AGjErAfjX3n4x/Y10/Xf+Cieofs1eEYzZeHJ9Tju2EfP2XTJIVu5lXPTYhZEz/siv6XNQu/hJ+yx8HLnURaw+GfBPg6z3tHbRZ2xpgcKvzSSOcDJyzMeTk0Afxh+Nvgf8ZPhvai+8f8AgfWvDtsxwJr/AE+4t4ifTfIgXP415rbW1zeTpa2sTTTSkKiIpZmY8AADkk1/dV4b1zwR8cPhnp/iG1t01bwt4vsEnSK7hG2a2uFztkicEdDgg1/N9+zp8BtP8Gf8FUF+GWkJ/wASnwhrF9fQK3zbLeG3a5t1yepXci59qAPgfQ/2W/2kvE1ut5oPwu8S3sDjKyJpN1sYezGMA/hVnSP2bfjTD8TdB+HniPwLrWm6nqc0Dm2nsJ1kFq8yxtMVKZESk4Ln5R3Nf2heP/H/AIR+FvhDUvHnjzUV0nQdHj826uXV3EaZCg7UDMckgAAE5r84fgN+018FPjN+3J4x1nw14phvzd+HdN0Tw8ixzq14qNNfXxRXjG3yyFDb9uccZoA++Yvgl8G9P05LeLwLoTLbQhFzplqSQi4H/LPk8V/Fx8b7DW7T4reKbvXNDn8OvqWpXl5DZ3Fq9mUt5p3MeyJ1TCY4XAxxxX9vXjDxf4b8A+GNS8ZeMb+PS9F0iFri7upc7IokGWY7QTx7Amv5C/8AgoZ8ZPC3xy/ai8Q+M/A+prq/h2K3s7OxuUVlSSOGIFyocK2PNZ+oFAHw/RRRQAUoJBzSUUAem6sd2oSt/e2n81Br6o/ZOnK6p4jtc8SQ27/98M4/9mr5V1LP2ts/3Y//AEAV9Q/sn7f+Ei13IO77LHg9seZzX0OWStiIv+tj9F4AbXEWGt3f/pLPdf2hoBL8J9XkPWF7Zx9TOi/+zV+bVfpd+0CP+LRa8f8Ar1/9Koq/NGvQzuV68X5L82fW+LMUs5p2/wCfa/8ASpBRRRXzR+ChRRRQB//T/Duiiiuw5wr9RP8AgmpOgu/iFaH70kelyD6IboH/ANCFfl3X6Kf8E3tUEXxS8TaKTgXmjmce5guIl/lKa/P+N4OeRYhLsn9zTPquHZ8mZUpPu/xTR9ifty2JuP2dNdnxxaXNjIfbNykf/s9fhPX9Df7WGitrX7PPji0Vd3l2P2nHtaSJOT+Hl1/PJXyXhjVUssqU+qm/xS/yZ7vGUf8AbIT7pfg2YfigY1+892B/NQa5+um8VDOpJP8A894Yn/8AHcf0rma/YmfABRRRSAt2d3LY3UN5AcSQOrqfQqcivrSH9p6JNHCzaMzakExuDgQlsY3evvjH418gUVx1sLSrW51ex9VlHEOYZUpLA1OXn30T+evU0dU1GfVtQudTujma6kaRz/tMcms6iiutaKyPmZSlOTnJ3b1JI0Mjqg6sQPzr+4f9mrwkPAn7Pvw68JkBX07QdPSTAx+8aBXk4/32NfxafCrwzJ40+JnhTwjECz6zqtnZgAZ5nmVOn41/dnb20NrbRWsC7YoUVFA7KowB+VMzPzw+Bn7cOrfF79rXx9+zfL4at4NN8J/bfs2p28zu8hspUiYSoRtG5mOCp4Ixg1x//BWP4S+D/GX7L+rfETULKJfEHg2a1msrzaBMI5p0hlhLdSjB87TxuANfc3gH4EfB34T67r3i3wD4Ws9E1fxHK8+pXsYZp7h5HMjl5JGYhS5LFQQuecV+Pf8AwVn/AGv/AALqfgVf2cfh3q8Os6le3UU+tS2sglhtobZt6W5kUlTK0gUsoJ2qvzYJAoA/Tn9h/wALWXg79kz4X6RYoEWTRbe8fHeS9zcOT/wKQ15b8SdW/YB8HfHv/hbfxM8S6DY/FDQjHGZbjU5Dc2xSPCBrVJCgIRsjMeeQeuDWX/wTb/aJ8GfF79nTwv4QtdRhTxV4Ns49MvtPZwJxHb/JDOqH5mjeML8w4DAg4ruvjB/wT6/Zc+OXjm6+I3jzw1O+u34T7VNaXtxarcGNQitIkbhdwUAZABIAzQB+an/BTP8Abu+B/wAV/gwvwb+Dmvf8JLd6re2899cQQyx20NvbN5gXfKqb3aQLgKCAAST0z8yf8Es/2r9c+EPxfsfgzrUjXPhDx7dx26xdTaajJhIZk9nOEkHcYbqvPtfxn/ZQ+DvhT/goX8Gfgh8LPDkenaDNBaalqVu0st154hnmllMhneQnMUOCOmO1fuVpn7OfwC0XxNB4z0b4c+H7DXbZ/NivbfTLaKeOT++jogKt7jmgD03xJoWl+KPD2peHNct0u9P1O3lt7iGQZSSKVSrKQexBr+cz/glX8MYdK/bU8fxxAyW3gS11W0ikIz8/2sWqkn1Kbq/cj9pL9oz4d/s2fDjUvG3jfUYorhYZBYWG8fab642nZFFHnccnG5sYUckgV+X3/BGbTL3X1+MHxc1Zc3ev6nbRM46eYxmuZsf8CkWgD6z/AOCpvixvDP7HPim0hfbN4gubHTU9SJbhGcD/AIAjV9P/ALMfhKXwJ+zx8OPCdwuyfTtB09ZVPBErQq8gP0ZjVv41fAT4e/H/AErRNC+JVvPe6ZoepQ6pHbRTGKOaeAMqLMAMvHhzlcjPrXlX7W37Wvw1/Zc+HOo6jq2o28viiW3dNJ0eN1NxPOVxGWjHKQqcF3IAAGBk4BAPjv8AZffTfiH/AMFLv2gPH8TLOvh6zh0qBsA7XXyYJMH2MLiuv/4K/wDiO70j9lSHQ7Ryn/CRa7Y2cgB+8ib7jH/fUQr81v8AglD8f9G8J/tI+JrD4i6rHaTfEa2cJd3DhEk1Lz/PVWZuAZdzhc9WIHU1/RV8U/gx8NfjVp2laV8TNGTWrPRb+HU7WJ5JEVbqDOxiI2XcMMQVbKkHkUAUv2fvC0vgX4FeAPCVyuybSNC0+CUdMSJbpvH/AH1mvyd/YsitfiR/wUk+PvxOgxLbaMt1ZwuORvM8VqCPqkD1+hf7Yn7UPg79mL4Sat4i1K+g/wCEku7eSHRtOLjzrm6ddqME6+WhO52xgAYzkgH8/wD/AIIseHbqXwJ8TPiVqWZbrXtWt7YzvyztbxvNKc98tOCfegD6B/4K2eLG8N/sfatpcb7H8RalYWI55IEv2hh/3zEa/KX/AII4+FDrX7Ul94idcx+HtDu5gcZxJO0duPp8sjV9a/8ABbrxZ5HhT4aeBUc/6Ze3uoOue1vGsSk/9/jXA/8ABESTQU8S/E6KadBrMlpp/kxEje1sskvmso6kB/Lz6ZFAH6Hf8FR/F3/CK/saeMo0OJdakstOTnGRPcJv/wDHFav5EK/sf/4KHaN4G1H9knx7qXjrTE1SLRrJ7qxWRnURagR5VtKCjKcq8g4OQe4NfxwUAFFFFABSgEnFJV7T4TPf20AGfMkRfzIoA7/Vht1CVf7u0fkoFfVf7JduX1TxHc44jht0/wC+2c/+y18n6g/mX1w3rI386+0v2TLJo9I8RakR8txPBCD7xKzH/wBGV7uA0rRfb/I/UfDei6nEeHfbmf8A5K/1Z6V+0RMIfhNrEZ/5bPbIPwnRv/Za/Nev0I/aju/s/wAObe3B5utQhQj2VJH/AJqK/PeunMp81Zeh7vizUUs8jFfZgl+Lf6hRRRXin4SFFFFAH//U/Duiiiuw5wr67/YZ18aH+0h4egkbZFq0N5ZOT/twNIg/GSNRXyJXe/CvxTH4I+JfhXxfOWWDRtUs7qXb1MUUytIPxQEfjXiZxhfrWX18OlrKLS9Wnb8T0MFW9jiKdTs0/wAT+knxx4dXxT4O17ww2NusWF1ZnPT/AEiJo/8A2av5fJI3idopFKuhIIPBBHUGv6tmVWUOhDKwyCOciv5sf2jvCr+C/jr430AxCGNNTnuIUUYVYLs/aIgB6CORRX4B4V4y1XEYV9Umvk2n+h+lcYUuanSq9m19+q/I8I8SIZLPTrr0V4if905H6GuPrvb6L7ToVwgGWtnWYfQ/K39K4Kv6QktT8rjsFFFFSUFFFFABRRRQBfsb+90u9h1HTLmS0u7Z1kimhcxyRupyrIykFSDyCDkV6Ofjt8bf+ig+Iv8AwbXf/wAcrymigD0fU/i98WdatHsNZ8aa3f20gw0VxqVzLGwPqryEGvOKKKANTStY1fQb+LVNDvZ9OvYDmOe3laGVD6q6EMPwNevn9pz9o5rT7A3xS8Tm3xjZ/bF5jHp/ra8MooA6KbxZ4ouNZHiW41i8l1YHcLxriRrkN6+aW359816la/tO/tH2Vt9jtPil4oigxjYusXgGP+/teF0UAb/iDxP4k8Wag2r+KNWu9Zvn4M95PJcSke7yMzfrX9Tv/BIzwmPD37IVjq7Jtk8Ratf3uT3VCtuP/RRr+UOvdfC37TP7Qvgbw/aeFfB3xG17RdHsAy29naahNDBEHYuwREYAZYkn3NAH6wf8Fi/jL400D4veDvA3hDxHqGjR2mjyXdzHY3c1sJGupii+YImUNgQnGemTX4cX9/fandvfalcyXlzKcvLM5kdj6lmJJ/Gum8b/ABB8cfEvW/8AhJPiDr174i1by1h+1X873E3lpkqm9yTtGTge9cYTmgBQSpyOCK9o0n9oz9oHQtNTSNE+JXiSxsY12pBDq12kaqOyqJMAewrxWigDc13xH4h8VajJq/ifU7rV7+X79xeTvcTNj1eQsx/Ot/w98S/iN4SsW0zwn4q1XRbNnMhhsb6e2iLkAFikTqCxAAzjPFcJRQB1XiPxp4w8Zyw3HjDXb/XJbcFYnv7qW6aNTyQplZiAT1Aqr4c8U+JfB+rQ674T1W70XUrfPl3NlO9vMmeu2SMqw/OufooA9R8YfGr4wfEKyGl+O/G+t+IbMEN5F/qNxcxZXkHZI7LkdjivLqKKACiiigArovC8SvrMMjfdgDSn/gCk/wA8Vztdh4bi8q0v74gZKrCv1c5b9BTSuxNl0ksSx5J5r9Fv2a9LOn/DCC6P/MSup7j8iIf/AGnX50V+tPgjSH8PeENF0WVdstnaQxyD/poEG/8A8ezXt4R2nc/obwgwLq5nWxTWkI2+ben4I+Zv2s9Sxb+HNHVvvtcTuvptCKh/Vq+L6+g/2l9ZXU/iS1gn3dKtYYDzwWfMxP5SAH6V8+VliZ81Vs/PuPsYsTxBiZp6RaX3JJ/iFFFFch+ZhRRRQB//1fw7ooorsOcKKKKAP6Uf2Z/Gy/ET4D+DfErSeZcGxS1uSTljcWebeQt6FmTd9CK/NP8A4KS+ATpHxD8P/EG2jxb6/ZNazMB/y8WTcFj6tHIoH+4a9V/4JmfEVbnTPFXwovJf3lq66tZqTkmOTbDcAegVhEcerk19P/tr/DJviP8AATWxZxebqPh0jVrYAcn7MD5yjucwtJgd2Ar+QMLL+wOLXTlpBya+U9vuufslV/2hlF1rJK/zW/3n8+dhsM5t5f8AV3CtE30cY/nXns0LwTSQSDDxsVP1BxXbAkHI4IrM8T2+biLVIx8l4uW9pF4b/Gv65qLqfj8WcrRRRWJoFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABXoMMP2LSLO0Iw8gM78d3+7/wCOiuS0ex/tHUIbY/cJ3OfRF5Y/lXY3c/2i5eYDCk/KPRRwB+VawWtyJPQ7f4WeHf8AhKfiBomksoeEzrLMCODFD+8cH/eC7fqa/UxpUjRpJWCKgJJJwAB1Jr42/ZY8Lndq3jKdOABZQH8pJTj/AL4AP1Fe2/HDxMPDPw31SWNttxqCiyh92nBD/QiMOR7iu+nPlP7U8PMNDJ+GqmaV1bnvN+iVkvnv8z88PFuuN4l8T6rr7ZAv7mWZQeqozEqv4LgVz1FFYN3dz+L69adarOtUd5Sbb9W7sKKKKRzBRRRQB//W/Duiiiuw5wooooA9w/Zw+KDfB/4y+G/G00hSwhuBb34HQ2dx+7mJHfYp3gf3lFf0wyxQXUBBCzQzL04ZXVh+RBFfyXV/Ql+wx8Zh8Wfgva6Pqc/ma/4N8vTbsMQXkgC/6LMe/wA0alCTyzxuT1r+cfFLJ3KnTzSkvh92Xo9n95+icMY3llLDSe+q/U/F/wDaP+FUnwa+MPiDwTGhGnpL9p09jnDWdx88QBPUpkxse7I1eKm3GpWE+mnmT/WQ/wC+o5H4iv3A/wCCh/wSfxr8PLf4o6Hb79W8IBvtIUZaXTpDl89z5DfOOwUyGvw6jkeKRZIzhlOQfpX6jwhnSzbK6dWTvOOkvVdfmj5rNsH9UxUope69V6P/AC2OCIKnB4IptdR4jskSZNTt1xDd8kD+GT+If1FcvX2TR5AUUUUgCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKK1NJ05tTvUt87Yx80jf3UHU0AdJo1t9h0t7xxiW9+RPaMfeP4nirVtbz3lxFaWsZlmndURFGSzMcAAepNPu5lml/dDbEgCIvoq8Cvof9nHwMdc8TP4rvo82Oin93kcPdMPlxkYPlj5j3B21vdQjdnv5DlFXN8xpYGlvJ6vst2/kj7L8C+F7fwX4U07w3AQ5tI/3jj+OVjukb6FicZ6DA7V8g/tO+K/7S8T2nhS3Y+VpEfmSjkZnnAYA9jtj24P+0RX2T4o8Q2XhTw9f+ItQP7ixiMhGcF26IgPq7EKPc1+VWrape63ql3rGov5l1eyvNI3qznJwOw9B2FRSk5an9S+KeaUcvyulkuG05raLpCOy+bX4GdRRRXQfxmFFFFABRRRQB//X/Duiiiuw5wooooAK+lP2VPjnP8Bfi1p/iO6cnQNS22OrR5bAtJXXMwVQxLwECRQFJYBkBG8mvmuivPx2DpY3DzwtdXhJNP8Arub0a06NSNWD1R/Wzc21hq9g8Mqx3llexFWU4kjlikXBHcMrKfoRX8237UvwKvPgN8U73w9DG7aBqO670mZskNbO3+qLd3hb5G7kbWwAwr9L/wDgnX8f08YeDH+Cvie6L614ZQvprSuzPcaaT/qwXYktbMdoAwBEUVVwjGvp39qD4Bab8fvhrc+HPkg12w3XOlXTD/V3IH3GI58uUfK/pw2CVFfyNkePrcKZ5PBYt/u27SfddJL06n6njKUM0wUatP4lqvXqj+a2HyZ4ZNPuziC47/3HH3W/DvXDXtnPYXT2k4w8Zx7EdiPY16Hrei6r4b1i+8P67bPZajps0lvcQSDDxyxMVdT7gjFUbuzGt2oiH/H7AP3Z/wCei/3T7jtX9h3U4qcXdM/KldPlZ57RT2VkYqwwQcEHsaZWJYUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFADwC5CqMk8ACu/t7QaPY/Y/8Al6nw0x/ujsn9TVHRNPWxhXV7tcyN/wAe6H1/vn2HarTMzsXc5ZjkmtoR6mcpdDQ0jSb/AF3VLXRtLiM11eSLHGo7sx7nsB1J6Acmv1B8EeFbHwT4asvDtjhhbrmSTGDLK3LufqemTwMDtXhH7Pnw0/sawXxvrMY+3X8eLRGHMUDfx89GkHTHRO/zED1/4k+OrXwB4WuNYkKvdv8AurWI/wDLSZhxkD+FfvNyOBjqRXz+IxftaqpU+n5n9qeHnD1LIssnneY+7Oavr0hv973+4+cf2lfHovb6DwJp0mYbIie8IPWYj5I/+AqcnqMkd1r5SqzeXdzqF3Nf3sjTXFy7SSOxyzO5yxPuSarV9DThyRUT+VOJM8q5zmVTH1NOZ+6uyWy+4KKKK1PkgooooAKKKKAP/9D8O6KKK7DnCiiigAooooA6vwP408Q/DrxdpXjfwpcm01XR51ngk6jI4ZWHdHUlXXupIPWv6aPgh8Y/DHx3+Hlh488MnyzMPKvLRmDSWl2gHmQueM4zlWwNykNgZwP5bK+k/wBmH9orXv2dvHya3AHvPD+pbIdWsVP+uhB4kQHgSxZJQnGclSQGJr8n444VWcYVVaC/fQXu+a6p/ofTZPmbwlXln8Et/LzP0h/bz/ZRk8b2M/xn+Htn5niDT4h/alpEvzXttEMCZAOs0SjBHV0HHzKA34mKxVgynBHINf1oeFfFPh3x34a0/wAX+E72PUdI1WITW88Z4ZT1BHVWU5VlOCrAggEEV+Rn7bv7GcmlS3/xm+E1jusHLT6vpkC8wHq91Ao/5ZnrIg+5yw+TIT854C4x9g1k+ZO1naLfT+6+3zPoM6yv2ieLw6v1aXXzR+UOp6eusxteWoAvEGZEH/LQD+If7Xr61wpBBIIwRXeI7xsHQ7WXkEUX+mxa0DPbARXw6r0WX3Ho386/peUOqPz2L7nA0VLJHJDI0cqlXU4IPBBqKsjQKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAK6vRtIj2DU9RX/Rx/q4z1lI/9l9ak0zRI4UXUNWX5TzHD0Z/dvRf51qXFxJcvvk7cADgAegFaRjfVkNiXE8lzKZZDyegHQAdAB6Cvd/gn8Kn8YagviHXIsaLZPwrD/j5lX+Af7C/xHv90d8YPwo+FWofELUftNyGttEtWHnzjguRz5UeerEdT0UcnnAP6DafptlpFjBpumwrb2tsoSONBgKo7f8A1+/evls3zeNG9Ck/e6+X/BP6N8N+A5ZhVjmuYQ/cxd4xf2muvovxJbu8tNOs5r68kWC3tkZ5HY4VUUZJPsBX5xfFT4h3HxD8SNeoGi020BitImPITPLsOgZzycdBhcnGa9F+OfxYHiK4fwh4dn3aXbt/pEqH5biRT90EdY1P4MeegBPzbXTlGCdOHtaq957eS/zZXidxtHH1XlOAlelF+81tJrovJBRRRX1B/NYUUUUAFFFFABRRRQB//9H8O6KKK7DnCiiigAooooAKKKKAPs39kb9rLWf2fPEH9ia6ZdQ8D6rKDeWq/M9rIcD7Tbg/xAY3p0cD+8FNf0GaDr2g+L9CsvEvhm9i1PStSiE1vcQtujkRu4/kQeQcggEEV/JNX2D+yt+1t4n/AGeNa/srUFk1jwVfyZu9P3fPCzcG4tS3CyAfeU4WQcHB2sv4VxvwMswUsdgFast10l/kz7HKM4eHapVX7nR9v+AfWP7YX7C7I178UvgjYFgxabUNEgXp3eazUdu7Qge6cfIPyPIZGwcqyn6EEV/WF4I8c+EfiX4Ys/GPgfUotV0m+XKSxH7rD7yOpwyOvRlYAg9RXxN+1D+wz4Y+LrXfjT4emHw/4wfMkq422d+/U+aFH7uU/wDPRQcn76kncPkOEuPp4VrLs5ulHRSd7q2lpLfQ9fMskjWXt8Ju9bdH5o/By5is9WQR6h+7nAwk4HPsHHce/WuP1HSrvTHC3C5RvuyLyjD2Neq+N/Ani/4b+Ibjwr430qbSNUtT80My4yvQOjDKuhxwykqexrnIbp40MLqJYW+9G4yp/wADX9NwlTqwU6ck09U1qn6M/PXzQbjJWaPOaK7S50C0vMyaVJ5Uh/5YyHj/AIC39DXLXVndWUhhu4micdmGPy9alprcaZUooopDCiiigAooooAKKKKACiiigAooooAKKkjjeRwkSl2PQAZJ/CuotfDToBNq8n2ZeojHMrfh0H400rgc9a2lzezCC1QyO3Yf1rs7LTLPR8Sz7bq8HbrHGf8A2Y/pVr7TFBCbXT4hbQnrjl2/3m6moIYZrmZLe3jaWWVgqIgLMzHgAAckn0rVRS1kRdt2iJLLJPIZZWLs3UmvbfhN8GdU8fTpquph7PQY2+aXo85HVYs9s8Fug6DJ4HrHwq/Zonl8nxB8RozFHw8Wng4Zu4M5H3R/sDn+8Ryp+wmgtNPtAkapbW1smABhI40QdhwAoA+gFfmmdcU04XoYJ3l1l0Xp3Z/SnBfhrPESjjs5jywWqg9G/XsvIwNN0jT9E0+DSdJt1tbS1UJHGgwFA/mSeSTyTyea+SPjb8Z1mFx4M8IT5jOY7y6Q/e7GKMjt2Zh16DjOYvjL8eBqYn8K+B5itocpc3q8GUdCkR7J6t1boPl5b5PrfIcknpisWtd0n+bPV498RIeyllGTStG1pSjtba0bdOlwooor9KP5RCiiigAooooAKKKKACiiigD/0vw7ooorsOcKKKKACiiigAooooAKKKKAPb/gd+0D8RfgD4j/ALb8FXm60uCv23T58taXaL2dARhh/C64ZfXBIP72/AH9qX4Z/tCaaqaDcf2Z4iiTdc6RcuPtCY+80R4E0Y/vKMgY3KpIFfzR1e0zU9S0XULfVtHupbG+tHEkM8DtHLG68hkdSCpHYg1+ZcTcF4LOYur8FXpJdfJrqfQ5dm1bCPl3h2/y7H9RXxX+DPw8+Mugnw94/wBJj1CJQxgmHyXNs5/jhlHzIemR91sYYEcV+Lnx7/YJ+JPwvNxr/gISeMPDiZY+Sn/Ewt0HP72Ff9YB/fjz0JKIK9p/Z8/4KOX+nC18K/HuFr62G2NNbto/36Dpm5hX/WAd3jAbA5R2Oa/WTwx4r8L+OtEg8SeDtUt9Y0y6GY7i2kEiE91OPusO6nBB4IBr+fqWKz/hCt7Kor029ndwfo+jPvfZ4HNYcy0l9zXr3R/J8ysjFHBVlOCDwQRVtb2Ty/IuVW4h/uSDcPwPUV/R38Y/2Tvgz8Z/OvvEOjjTtalyf7T0/FvclvWTAKS/WRGOOARX5ffFP/gnb8WvCDTX/wAP7qDxhp65IjXFreqvXmKRvLbA/uSFj2UdK/dMm8QcqzBKFaXsp9nt8nsfHYvh/FUPeprmj5b/AHb/AHXPz1n0bR7vm3keykP8LfPH+fUVkT+GdViUywxi6j5+aEh+nt1/Su28QeGfEXhPUpNH8UaXdaRfRfegu4XgkHvtcA496xkd423IxUjuDg1+pR5JxU4O6fbVHzDcou0lqcM8ckTbJVKMOzDB/Woq9L/tK6ZQk5WdRxiVQ/8APmqrx6TKP3+nR59Y2aP+RxQ4MOZHn1Fd02l+HpBkx3ER/wBl1YfqtRHRNCPSa5H/AAFD/UUuVhdHFUV2o0XQ/wDnvcn/AICg/rUi6T4eTki5k9iyKP0Bo5WF0cNTgCTgDJNd6lvokPMenhj6ySM36DAq2l/JAALSOK2A/wCeaBT+eCaagw5kcfbeH9Xu/nS3ZE/vyfIv5titmDw/p9vhtQuvOYY+SAcfi5/oKvSzzTHdM7Of9ok0kUUs8qQwI0kkhCqqglmJ6AAck1fIlqyeZvRE8d1HaJ5emwraqeCV5c/VjzVUksSzHJPc19HeBP2WPi341Mdzc6d/YFg/Pn6hmJiP9mHBlJx0yqg/3q+1vAP7Jfw48FmO91tG8S6imDvulC26kf3YASv/AH2X9q+KzLizLsFePPzy7LX73svvPvsq4NzPMGpcnLD+Z6fct2fnz8N/gj46+JcqTaVafY9Lz899cApDgddnGZD2wvGepHWv0F+HHwM8H/DOFbizj/tDVyMPfTqN/IwRGvIjXr0ySOCxr6Fnit7O3JO2CCBfZURVH4AACvjb4n/tWeFtA8/SvASLruooShuTlbKNgWU4PDTEEAjbhGBBDnpX5bWzjNM+qOhhoNR6pbfNn9A5dkuQ8L01i8bJSqdJPe/91antvjHxZ4c8EaU+seJb1LOAZCgnLyN/djQcs3sOnU8ZNfnT8V/jprnxCeTStNDaZoOeIAf3k4HQzMPz2D5R33EA15V4n8W+JPGeptrHifUJNQumGA0hACj+6iKAqDvhQBnmudr9NyThelgrVqz55/gvT/Nn5NxV4hYzNYywuFvTovddX6tbLyQUUUV9+fioUUUUAFFFFABRRRQAUUUUAFFFFAH/0/w7ooorsOcKKKKACiiigAooooAKKKKACiiigAr0L4dfFb4h/CfWP7c+Huu3OjXJx5gibMUwXossTZjkHs6nHavPaKxrUKVem6daKlF7pq6fqmaQnKElKDs0fr98Jv8AgphY3Cw6V8aNBNvJwp1LShvjPbdJbO25fUlHbPZB0r9FfAfxX+GvxTsft/w/8RWetIF3PHDJieMH/npC2JU/4Eor+Wyrmn6jqGk3kWo6Xcy2d3A26OaF2jkRh3VlIIPuDX4vm/hnluJbqYKTpS7br7nqvkfZYPiTEUrRqrmX3P7z+prxV4M8KeM7A6V4v0ez1qzPPlXkCToD6gODg+hHNfFPjj/gnp8DfEckl14ba/8AC87ZIW2m8+3ye5juA7Y9lkUCvz9+HP7eHx+8CCO01TU4vFmnxgL5WqoZJgO5FwhSUsfWRnA9K+zfCP8AwUs+HWoqkXjfwtqOjTHAL2jx3sOe5O7yXA9grH+dfmf+q/FOTSbwUnKP916fNO1/uPrY5rlWMVsQkn/eX6o8R8T/APBNXxxZlm8I+L9P1JRyFvYZbNsemY/tAJ/L8K8F1/8AYi/aN0Ms0fhyPVIk/wCWlndwPn6I7pIf++a/XDw9+1/+zh4o2LZ+NLWzkbql8ktntPoWnRE/JiPevZNG8X+D/FCh/DOu2GrqRkG0uopxj/tmzVtHjfiTA6Yynf8AxQa/KxssgyrE/wAGdvRp/nc/nQv/AID/ABs0yVorzwHrilOrLp1xIn4OiFT+Brmrn4c/EKyz9s8L6pBjr5llOv8ANBX9NckdUZI69in4o4m3v4dP0bQv9S6D+Gq18kfzNW/gTxvdf8evh7UZv9y0mb+S1t2/wf8Ai1dkC18E63Ln+7p1yR+fl1/R5JHVF4+xrZ+J9d/Dh197/wAjohwLRfxVn9y/zPwR0X9lP4+65taDwlPaxnq13JDbY+qyurfkpr2HQv2CvibeFH8Q6zpulxN1EZluZV+qhUT8nr9ctUv9N0mA3WqXcNnCOrzSLGv5sQK8X8RftC/A/wANhv7S8Z6c5XqttL9rYexW3Ehz+Fcn+vOeYx8uFppekW3+Nz1ocI5NhlzYmbf+JpL8P8z5p8NfsH/DzTCkvijWr7WpF6pGEtIW+qjzH/KQV9NeEfhZ4A+H0PleDtCttNJG1pUTdOw9GmfdIw9ixr578Uft0/CfTA8fh2x1DW5R91hGttC31aQ7x/37NfMPjT9uH4m66Hg8J2Vp4bgY8OB9ruAPTfKBH/5Cz71X9k8T5rpiXJRf8zsvuX+R6MM44byrXDqLkuyu/vf+Z+nmt6xo3h+xk1PXr6DTrOP701xIsUY+rMQM18e/EP8AbL8AaAJbLwVbyeI7wZAl5gtFPruYb3weyrg9mr80/Eni3xP4wvjqfinVbnVbk5w9xK0hUHsoJwo9hgVz1fd5ZwBhqVp42bk+y0X+bPlMy8RcVUThgaagu71f+SPV/iL8a/iH8T5XTxHqRSwLZWxt8xWq4IIygJLkEZBkLEdiK8ooor9bw+GpYemqVGCjFdErH4/isXXxVV1sRJyk+rd2FFFFdJxhRRRQAUUUUAFFFFABRRRQAUUUUAFFFFAH/9T8O6KKK7DnCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKVWZWDKcEcgjqKSigDtrD4l/EbSkSPS/FWq2aRjCiG+njCj0AVxit3/hefxs6f8LB8Q/+Da7/APjteWUVwywOGk7ypp/JHWsTWSspP72eo/8AC8fjUf8AmoHiD/wa3f8A8crHvvif8S9Tz/aXi3V7vPXzb+4kz/305rhqKFgcNF3jTS+S/wAgeKrtWdR/eWbu9vL+Y3F9PJcynq8jF2P4nJqtRRXakkrI5W23dhRRRTEFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAFFFFABRRRQAUUUUAf/9X8O6KKK7DnCiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigD//2Q==" alt="BeSport" style="width:120px;height:120px;object-fit:cover;border-radius:50%;">
      <span style="font-family:'Barlow Condensed',sans-serif;font-size:18px;font-weight:800;letter-spacing:2px;text-transform:uppercase;">BeSport</span>
    </div>
    <div class="org-x">×</div>
    <div style="display:flex;flex-direction:column;align-items:center;gap:12px;">
      <img src="data:image/jpeg;base64,/9j/4AAQSkZJRgABAQAAkACQAAD/4QECRXhpZgAATU0AKgAAAAgABwEOAAIAAAALAAAAYgESAAMAAAABAAEAAAEaAAUAAAABAAAAbgEbAAUAAAABAAAAdgEoAAMAAAABAAIAAAEyAAIAAAAUAAAAfodpAAQAAAABAAAAkgAAAABTY3JlZW5zaG90AAAAAACQAAAAAQAAAJAAAAABMjAyNjowNDowNiAxNzoxNjoyMAAABZADAAIAAAAUAAAA1JKGAAcAAAASAAAA6KABAAMAAAAB//8AAKACAAQAAAABAAABT6ADAAQAAAABAAABUgAAAAAyMDI2OjA0OjA2IDE3OjE2OjIwAEFTQ0lJAAAAU2NyZWVuc2hvdP/tAG5QaG90b3Nob3AgMy4wADhCSU0EBAAAAAAANhwBWgADGyVHHAIAAAIAAhwCeAAKU2NyZWVuc2hvdBwCPAAGMTcxNjIwHAI3AAgyMDI2MDQwNjhCSU0EJQAAAAAAEIdw6oIuUY6odqszUiM1LJX/4gIoSUNDX1BST0ZJTEUAAQEAAAIYYXBwbAQAAABtbnRyUkdCIFhZWiAH5gABAAEAAAAAAABhY3NwQVBQTAAAAABBUFBMAAAAAAAAAAAAAAAAAAAAAAAA9tYAAQAAAADTLWFwcGwAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAApkZXNjAAAA/AAAADBjcHJ0AAABLAAAAFB3dHB0AAABfAAAABRyWFlaAAABkAAAABRnWFlaAAABpAAAABRiWFlaAAABuAAAABRyVFJDAAABzAAAACBjaGFkAAAB7AAAACxiVFJDAAABzAAAACBnVFJDAAABzAAAACBtbHVjAAAAAAAAAAEAAAAMZW5VUwAAABQAAAAcAEQAaQBzAHAAbABhAHkAIABQADNtbHVjAAAAAAAAAAEAAAAMZW5VUwAAADQAAAAcAEMAbwBwAHkAcgBpAGcAaAB0ACAAQQBwAHAAbABlACAASQBuAGMALgAsACAAMgAwADIAMlhZWiAAAAAAAAD21QABAAAAANMsWFlaIAAAAAAAAIPfAAA9v////7tYWVogAAAAAAAASr8AALE3AAAKuVhZWiAAAAAAAAAoOAAAEQsAAMi5cGFyYQAAAAAAAwAAAAJmZgAA8qcAAA1ZAAAT0AAACltzZjMyAAAAAAABDEIAAAXe///zJgAAB5MAAP2Q///7ov///aMAAAPcAADAbv/AABEIAVIBTwMBIgACEQEDEQH/xAAfAAABBQEBAQEBAQAAAAAAAAAAAQIDBAUGBwgJCgv/xAC1EAACAQMDAgQDBQUEBAAAAX0BAgMABBEFEiExQQYTUWEHInEUMoGRoQgjQrHBFVLR8CQzYnKCCQoWFxgZGiUmJygpKjQ1Njc4OTpDREVGR0hJSlNUVVZXWFlaY2RlZmdoaWpzdHV2d3h5eoOEhYaHiImKkpOUlZaXmJmaoqOkpaanqKmqsrO0tba3uLm6wsPExcbHyMnK0tPU1dbX2Nna4eLj5OXm5+jp6vHy8/T19vf4+fr/xAAfAQADAQEBAQEBAQEBAAAAAAAAAQIDBAUGBwgJCgv/xAC1EQACAQIEBAMEBwUEBAABAncAAQIDEQQFITEGEkFRB2FxEyIygQgUQpGhscEJIzNS8BVictEKFiQ04SXxFxgZGiYnKCkqNTY3ODk6Q0RFRkdISUpTVFVWV1hZWmNkZWZnaGlqc3R1dnd4eXqCg4SFhoeIiYqSk5SVlpeYmZqio6Slpqeoqaqys7S1tre4ubrCw8TFxsfIycrS09TV1tfY2dri4+Tl5ufo6ery8/T19vf4+fr/2wBDAAICAgICAgMCAgMFAwMDBQYFBQUFBggGBgYGBggKCAgICAgICgoKCgoKCgoMDAwMDAwODg4ODg8PDw8PDw8PDw//2wBDAQIDAwQEBAcEBAcQCwkLEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBAQEBD/3QAEABX/2gAMAwEAAhEDEQA/APw7ooorsOcKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigD//0Pw7ooorsOcKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigD//0fw7ooorsOcKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAopyoznagLH0HNXE0y/dd/ksq+rfKP1xQBR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jj6tET/NfeueUbao1jK5ytFFFZlhRRRQAUUUUAFdj4U8V6l4We9k084N7bvA3tu6MPcHkVx1Lk1E4RnHlkro6sPiKuHqKrSlaS2aNbVdX1LWZ/tWqXDXMwULvc5O0dBWRRRVJJKyMp1J1JOc3dvqzvLHxvdWHhWfwtBYWhjudwknaINOQ3o56Y7VwdFFRGEY3cVudFfFVqyhGrK6irLyXYKKKK0OIKKKKACiiigAooooAK2dI0qTU5juPlW0XMknoPQepPYU/SdHl1FjLI3k20f35D/JfUmuqlniESWdmnlW0f3V7k/3mPcmrjG5LdhLiaNlS3tk8u3hGEX+p9Se9VqKK6UjEKKKKACiiigAooooA//Q/Duiiiuw5wooooAKKKKACiiigAooooAKmgnlt5BLEcMPyI9D7VDRQBHfaNb6lm40wCG56tDnCv7ofX2rjZYpIZGilUo6nBBGCDXbgkHI4IqzM1pqSCHVELMBhZl/1i/X+8PrWModjRS7nnNFdDf+Hru0Q3FuRdW/99OSP95eornqxNAooooAKKKKACiiigAooooAKKKKACiiigAoorVsNHvdRJaBMRL96RvlQfiaAMqur07w+Ai3mrkxQnlYx/rH/wAB71rWtpp2k/NABdXI/wCWrD5FP+yv9TSSyyTOZJWLs3UmtVDuQ5diWe5MwWJFEUMfCRr91R/U+9VqKK3MgooooAKKKKACiiigAooooA//0fw7ooorsOcKKKKACiiigAooooAKKKKACiiigAooooAlhnmt38yFyje1LcRaXqPN7B5Up/5aw8H8V6GoaKTSe407GZP4YucF9OkS8X0U7ZB9VP8ASudnt57d/LuI2iYdmBB/Wu2BIORwRVwahclPKmInj/uygOP1rJ0+xakebUV6BJbaLc/66y8pu7QuV/8AHTkVSfw/pEgzDeyQn0kj3fqp/pUODKujjKK6xvC5YZgv7dh/tFkP6ioj4XvR0uLY/wDbUf1qbMdzmKK6YeFr49Z7Yf8AbZakXwrLnMl9bIPZ2Y/otFmFzlaK7FPDumpzPqBfHaOI/wA2Iq3Hp+gW+CtvJcEd5X2j8lH9aaixXRw6ozsFQFmPQDk1vW3hvUp1Ek6i0iOPmmO38h1P5V06XzwLssoo7Uf9M1AP59aqu7yNvkYsx7k5NaKn3JchkGm6PY4JU30o7v8ALGD/ALvU/jVme7nuMLI2EXoqjCj6AcVWorRJIhtsKKKKoQUUUUAFFFFABRRRQAUUUUAFFFFAH//S/Duiiiuw5wooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAP//T/Duiiiuw5wooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAP//U/Duiiiuw5wooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKACiiigAooooAKKKKAP//Z" alt="La Grotta" style="width:120px;height:120px;object-fit:cover;border-radius:50%;">
      <span style="font-family:'Barlow Condensed',sans-serif;font-size:18px;font-weight:800;letter-spacing:2px;text-transform:uppercase;">La Grotta CrossFit</span>
      <span style="font-family:'Barlow Condensed',sans-serif;font-size:13px;font-weight:700;letter-spacing:3px;color:var(--yellow);text-transform:uppercase;">Hyrox Training Club</span>
    </div>
  </div>
  <p style="color:var(--text-muted);margin-top:32px;font-size:14px;">
    Síguenos en Instagram para más detalles y actualizaciones
    <br><a href="https://instagram.com/hybridrace503" target="_blank" style="color:var(--yellow);text-decoration:none;font-weight:700;">@hybridrace503</a>
  </p>
</section>

<!-- FOOTER -->

<footer>
  <p>© 2026 The Hybrid Race · El Salvador · <a href="https://instagram.com/hybridrace503" class="ig">@hybridrace503</a></p>
</footer>

<!-- PAYMENT MODAL -->

<style>
  .form-group {
    margin-bottom: 14px;
  }
  .form-group label {
    display: block;
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 11px;
    font-weight: 700;
    letter-spacing: 2px;
    text-transform: uppercase;
    color: var(--text-muted);
    margin-bottom: 6px;
  }
  .form-group input, .form-group select {
    width: 100%;
    background: #111;
    border: 1px solid #333;
    color: var(--white);
    font-family: 'Barlow', sans-serif;
    font-size: 15px;
    padding: 12px 14px;
    outline: none;
    transition: border-color 0.2s;
    -webkit-appearance: none;
    border-radius: 0;
  }
  .form-group input:focus, .form-group select:focus {
    border-color: var(--yellow);
  }
  .form-group input::placeholder {
    color: #555;
  }
  .section-divider {
    font-family: 'Barlow Condensed', sans-serif;
    font-size: 12px;
    font-weight: 800;
    letter-spacing: 3px;
    text-transform: uppercase;
    color: var(--yellow);
    margin: 20px 0 14px;
    display: flex;
    align-items: center;
    gap: 10px;
  }
  .section-divider::after {
    content: '';
    flex: 1;
    height: 1px;
    background: #333;
  }
  .error-msg {
    color: #ff4444;
    font-size: 12px;
    margin-top: 4px;
    display: none;
  }
  .modal { max-height: 90vh; overflow-y: auto; }
</style>

<div class="modal-overlay" id="modal" onclick="handleOverlayClick(event)">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">×</button>
    <p style="font-family:'Barlow Condensed',sans-serif;font-size:11px;font-weight:700;letter-spacing:3px;color:var(--yellow);text-transform:uppercase;margin-bottom:8px;">Inscripción</p>
    <h3>Registra tu<br>Pareja</h3>
    <p style="color:var(--text-muted);font-size:13px;margin:8px 0 20px;line-height:1.5;">Completa los datos y serás redirigido al pago seguro con tarjeta.</p>

```
<!-- CATEGORIA -->
<div class="form-group">
  <label>Categoría</label>
  <select id="categoria">
    <option value="">Selecciona una categoría</option>
    <option value="Dupla Masculina">Dupla Masculina</option>
    <option value="Dupla Femenina">Dupla Femenina</option>
    <option value="Mixta">Mixta (Hombre + Mujer)</option>
  </select>
</div>

<!-- COMPETIDOR 1 -->
<div class="section-divider">Competidor 1</div>
<div class="form-group">
  <label>Nombre completo</label>
  <input type="text" id="nombre1" placeholder="Tu nombre completo">
</div>
<div class="form-group">
  <label>Correo electrónico</label>
  <input type="email" id="email1" placeholder="correo@ejemplo.com">
</div>
<div class="form-group">
  <label>Teléfono</label>
  <input type="tel" id="telefono1" placeholder="+503 0000-0000">
</div>

<!-- COMPETIDOR 2 -->
<div class="section-divider">Competidor 2</div>
<div class="form-group">
  <label>Nombre completo</label>
  <input type="text" id="nombre2" placeholder="Nombre de tu pareja">
</div>
<div class="form-group">
  <label>Correo electrónico</label>
  <input type="email" id="email2" placeholder="correo@ejemplo.com">
</div>
<div class="form-group">
  <label>Teléfono</label>
  <input type="tel" id="telefono2" placeholder="+503 0000-0000">
</div>

<p id="form-error" class="error-msg">Por favor completa todos los campos.</p>

<hr class="modal-divider" style="margin-top:24px;">

<div style="background:#111;padding:14px;border-left:3px solid var(--yellow);margin-bottom:20px;">
  <p style="font-size:13px;color:var(--text-muted);margin-bottom:4px;">Total a pagar</p>
  <p style="font-family:'Barlow Condensed',sans-serif;font-size:28px;font-weight:900;color:var(--yellow);">$120.00</p>
  <p style="font-size:11px;color:var(--text-muted);">Pago seguro con tarjeta vía Wompi</p>
</div>

<button class="btn-primary" onclick="handlePago()" style="width:100%;border:none;cursor:pointer;font-size:15px;">
  PAGAR CON TARJETA →
</button>

<p class="modal-note" style="margin-top:14px;">Cupos limitados · @hybridrace503</p>
```

  </div>
</div>

<script>
  const WOMPI_URL = 'https://s.wompi.sv/1262514npk';

  function openModal() {
    document.getElementById('modal').classList.add('active');
    document.body.style.overflow = 'hidden';
  }

  function closeModal() {
    document.getElementById('modal').classList.remove('active');
    document.body.style.overflow = '';
  }

  function handleOverlayClick(e) {
    if (e.target === document.getElementById('modal')) closeModal();
  }

  document.addEventListener('keydown', e => { if (e.key === 'Escape') closeModal(); });

  function handlePago() {
    const campos = ['categoria','nombre1','email1','telefono1','nombre2','email2','telefono2'];
    const error = document.getElementById('form-error');
    let valido = true;

    campos.forEach(id => {
      const el = document.getElementById(id);
      if (!el.value.trim()) {
        valido = false;
        el.style.borderColor = '#ff4444';
      } else {
        el.style.borderColor = '#333';
      }
    });

    if (!valido) {
      error.style.display = 'block';
      return;
    }

    error.style.display = 'none';

    // Guardar datos en localStorage para referencia
    const registro = {
      categoria: document.getElementById('categoria').value,
      competidor1: {
        nombre: document.getElementById('nombre1').value,
        email: document.getElementById('email1').value,
        telefono: document.getElementById('telefono1').value,
      },
      competidor2: {
        nombre: document.getElementById('nombre2').value,
        email: document.getElementById('email2').value,
        telefono: document.getElementById('telefono2').value,
      },
      fecha: new Date().toISOString()
    };

    // Enviar datos por WhatsApp a La Grotta automáticamente
    const msg = encodeURIComponent(
      `🏁 *INSCRIPCIÓN HYBRID RACE*\n\n` +
      `📋 Categoría: ${registro.categoria}\n\n` +
      `👤 *Competidor 1*\n` +
      `Nombre: ${registro.competidor1.nombre}\n` +
      `Email: ${registro.competidor1.email}\n` +
      `Tel: ${registro.competidor1.telefono}\n\n` +
      `👤 *Competidor 2*\n` +
      `Nombre: ${registro.competidor2.nombre}\n` +
      `Email: ${registro.competidor2.email}\n` +
      `Tel: ${registro.competidor2.telefono}\n\n` +
      `💳 Procediendo al pago de $120.00 vía Wompi`
    );

    // Abrir WhatsApp con los datos y luego redirigir a Wompi
    window.open(`https://wa.me/50322526186?text=${msg}`, '_blank');

    setTimeout(() => {
      window.open(WOMPI_URL, '_blank');
    }, 800);
  }
</script>

</body>
</html>
