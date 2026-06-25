
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0">
<title>For Aveeka ✦</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,500;0,600;0,700;1,500;1,600&family=Poppins:wght@300;400;500;600&display=swap" rel="stylesheet">
<style>
  :root{
    --bg-deep:#0b0a1f;
    --bg-mid:#150f2e;
    --nebula-purple:#8a4fff;
    --nebula-pink:#ff6fb5;
    --star-gold:#ffd580;
    --star-white:#f5f3ff;
    --text-dim:#b9b3d6;
  }

  *{margin:0;padding:0;box-sizing:border-box;}

  html{scroll-behavior:smooth;}

  body{
    background:var(--bg-deep);
    color:var(--star-white);
    font-family:'Poppins', sans-serif;
    overflow-x:hidden;
    cursor:default;
  }

  @media (prefers-reduced-motion: reduce){
    *{animation-duration:0.01ms !important; animation-iteration-count:1 !important; transition-duration:0.01ms !important;}
  }

  #scene-canvas{
    position:fixed;
    top:0; left:0;
    width:100%; height:100%;
    z-index:0;
    display:block;
  }

  .veil{
    position:fixed;
    top:0;left:0;width:100%;height:100%;
    background:radial-gradient(ellipse at 50% 30%, rgba(138,79,255,0.10), transparent 60%),
               radial-gradient(ellipse at 80% 80%, rgba(255,111,181,0.08), transparent 55%);
    pointer-events:none;
    z-index:1;
  }

  .content{
    position:relative;
    z-index:2;
  }

  section{
    min-height:100vh;
    display:flex;
    flex-direction:column;
    align-items:center;
    justify-content:center;
    text-align:center;
    padding:6vh 6vw;
    position:relative;
  }

  .eyebrow{
    font-family:'Poppins', sans-serif;
    font-size:0.72rem;
    letter-spacing:0.28em;
    text-transform:uppercase;
    color:var(--star-gold);
    opacity:0.85;
    margin-bottom:1.4rem;
    font-weight:500;
  }

  h1, h2{
    font-family:'Playfair Display', serif;
    font-weight:600;
    line-height:1.1;
  }

  .reveal{
    opacity:0;
    transform:translateY(28px);
    transition:opacity 1.1s cubic-bezier(.16,1,.3,1), transform 1.1s cubic-bezier(.16,1,.3,1);
  }
  .reveal.in{
    opacity:1;
    transform:translateY(0);
  }
  .reveal.d1{transition-delay:.15s;}
  .reveal.d2{transition-delay:.32s;}
  .reveal.d3{transition-delay:.5s;}

  /* ---------- HERO ---------- */
  #hero{
    gap:0;
  }
  .hero-name{
    font-size:clamp(3rem, 11vw, 7.5rem);
    background:linear-gradient(120deg, var(--star-white) 10%, var(--nebula-pink) 45%, var(--star-gold) 70%, var(--nebula-purple) 100%);
    background-size:200% auto;
    -webkit-background-clip:text;
    background-clip:text;
    -webkit-text-fill-color:transparent;
    animation:shimmer 7s ease-in-out infinite;
    letter-spacing:0.01em;
    margin-bottom:0.5rem;
  }
  @keyframes shimmer{
    0%,100%{background-position:0% 50%;}
    50%{background-position:100% 50%;}
  }
  .hero-sub{
    font-size:clamp(0.95rem, 1.6vw, 1.2rem);
    color:var(--text-dim);
    font-weight:300;
    letter-spacing:0.02em;
    max-width:32ch;
  }
  .scroll-cue{
    position:absolute;
    bottom:6vh;
    display:flex;
    flex-direction:column;
    align-items:center;
    gap:0.6rem;
    color:var(--text-dim);
    font-size:0.7rem;
    letter-spacing:0.2em;
    text-transform:uppercase;
    opacity:0;
    animation:fadeInCue 1.5s ease forwards 2.2s;
  }
  @keyframes fadeInCue{to{opacity:0.75;}}
  .scroll-cue .line{
    width:1px;
    height:34px;
    background:linear-gradient(to bottom, var(--star-gold), transparent);
    animation:pulseLine 2s ease-in-out infinite;
  }
  @keyframes pulseLine{
    0%,100%{opacity:0.3;}
    50%{opacity:1;}
  }

  /* ---------- MESSAGE SECTION ---------- */
  #message{
    max-width:760px;
    margin:0 auto;
  }
  .message-text{
    font-family:'Playfair Display', serif;
    font-style:italic;
    font-weight:500;
    font-size:clamp(1.5rem, 4vw, 2.6rem);
    line-height:1.5;
    color:var(--star-white);
  }
  .message-text .accent{
    background:linear-gradient(120deg, var(--nebula-pink), var(--star-gold));
    -webkit-background-clip:text;
    background-clip:text;
    -webkit-text-fill-color:transparent;
    font-style:normal;
    font-weight:700;
  }
  .signature{
    margin-top:2.5rem;
    font-family:'Poppins', sans-serif;
    font-size:0.85rem;
    color:var(--text-dim);
    letter-spacing:0.05em;
  }

  /* ---------- CONSTELLATION SECTION ---------- */
  #constellation{
    position:relative;
  }
  .const-wrap{
    width:100%;
    max-width:680px;
    aspect-ratio:1/1;
    position:relative;
  }
  #const-svg{
    width:100%;
    height:100%;
    overflow:visible;
  }
  .const-star{
    fill:var(--star-white);
    cursor:pointer;
    filter:drop-shadow(0 0 6px rgba(255,255,255,0.6));
    transition:r 0.25s ease, fill 0.25s ease;
  }
  .const-star:hover{
    fill:var(--star-gold);
  }
  .const-star.lit{
    fill:var(--star-gold);
    filter:drop-shadow(0 0 14px rgba(255,213,128,0.95));
  }
  .const-line{
    stroke:var(--nebula-pink);
    stroke-width:2;
    opacity:0;
    stroke-dasharray:4 6;
    transition:opacity 0.5s ease;
  }
  .const-line.lit{
    opacity:0.85;
  }
  .const-progress{
    margin-top:2rem;
    font-size:0.8rem;
    letter-spacing:0.15em;
    text-transform:uppercase;
    color:var(--text-dim);
  }
  .const-hint{
    margin-top:0.6rem;
    font-size:0.85rem;
    color:var(--text-dim);
    font-style:italic;
    font-family:'Playfair Display', serif;
    opacity:0.85;
  }

  /* ---------- PLANET / QUESTION SECTION ---------- */
  #planet-section{
    position:relative;
    gap:1.2rem;
  }
  .planet-wrap{
    width:min(78vw, 380px);
    height:min(78vw, 380px);
    position:relative;
    margin-bottom:1rem;
  }
  #planet-canvas{
    width:100%;
    height:100%;
    cursor:grab;
  }
  #planet-canvas:active{cursor:grabbing;}
  .planet-instructions{
    font-size:0.78rem;
    letter-spacing:0.1em;
    text-transform:uppercase;
    color:var(--text-dim);
    opacity:0.8;
  }

  .question-card{
    margin-top:2.5rem;
    max-width:560px;
    opacity:0;
    transform:scale(0.92);
    pointer-events:none;
    transition:opacity 0.7s cubic-bezier(.16,1,.3,1), transform 0.7s cubic-bezier(.16,1,.3,1);
  }
  .question-card.shown{
    opacity:1;
    transform:scale(1);
    pointer-events:auto;
  }
  .question-title{
    font-size:clamp(1.8rem, 5vw, 3rem);
    margin-bottom:0.8rem;
  }
  .question-detail{
    color:var(--text-dim);
    font-size:1rem;
    margin-bottom:2.2rem;
    font-weight:300;
  }
  .btn-row{
    display:flex;
    gap:1.2rem;
    justify-content:center;
    flex-wrap:wrap;
    position:relative;
    min-height:60px;
  }
  .btn{
    font-family:'Poppins', sans-serif;
    font-size:0.95rem;
    font-weight:500;
    padding:0.95rem 2.2rem;
    border-radius:100px;
    border:none;
    cursor:pointer;
    transition:transform 0.25s ease, box-shadow 0.25s ease;
  }
  .btn-yes{
    background:linear-gradient(120deg, var(--nebula-pink), var(--star-gold));
    color:#1a0f2e;
    box-shadow:0 8px 30px rgba(255,111,181,0.35);
  }
  .btn-yes:hover{
    transform:translateY(-3px) scale(1.04);
    box-shadow:0 12px 36px rgba(255,111,181,0.5);
  }
  .btn-no{
    background:transparent;
    color:var(--text-dim);
    border:1px solid rgba(185,179,214,0.35);
    position:relative;
  }
  .btn-no:hover{
    color:var(--star-white);
  }

  /* ---------- FINAL SECTION ---------- */
  #finale{
    display:none;
  }
  #finale.shown{
    display:flex;
  }
  .finale-title{
    font-size:clamp(2.2rem, 7vw, 4.5rem);
    margin-bottom:1rem;
    background:linear-gradient(120deg, var(--star-gold), var(--nebula-pink), var(--star-white));
    background-size:200% auto;
    -webkit-background-clip:text;
    background-clip:text;
    -webkit-text-fill-color:transparent;
    animation:shimmer 6s ease-in-out infinite;
  }
  .finale-detail{
    font-size:clamp(1rem, 2vw, 1.25rem);
    color:var(--text-dim);
    max-width:480px;
    line-height:1.7;
    font-weight:300;
  }
  .finale-detail b{
    color:var(--star-gold);
    font-weight:500;
  }
  .coffee-icon{
    font-size:3rem;
    margin:1.5rem 0;
    display:inline-block;
    animation:floatIcon 3s ease-in-out infinite;
  }
  @keyframes floatIcon{
    0%,100%{transform:translateY(0) rotate(-4deg);}
    50%{transform:translateY(-12px) rotate(4deg);}
  }

  #confetti-canvas{
    position:fixed;
    top:0;left:0;
    width:100%;height:100%;
    pointer-events:none;
    z-index:50;
  }

  footer{
    text-align:center;
    padding:3rem 1rem 4rem;
    font-size:0.75rem;
    color:rgba(185,179,214,0.5);
    letter-spacing:0.08em;
    position:relative;
    z-index:2;
  }

  @media (max-width:600px){
    .const-wrap{max-width:90vw;}
  }
</style>
</head>
<body>

<canvas id="scene-canvas"></canvas>
<div class="veil"></div>
<canvas id="confetti-canvas"></canvas>

<div class="content">

  <!-- HERO -->
  <section id="hero">
    <div class="eyebrow reveal">a message from across the galaxy</div>
    <h1 class="hero-name reveal d1">Aveeka</h1>
    <p class="hero-sub reveal d2">there's something I've been meaning to ask you...</p>
    <div class="scroll-cue">
      <span>scroll</span>
      <span class="line"></span>
    </div>
  </section>

  <!-- MESSAGE -->
  <section id="message">
    <p class="message-text reveal">
      I made this whole thing <span class="accent">cosmic</span> because honestly —
      you're like a <span class="accent">space</span> filled with stars,
      and you <span class="accent">shine</span> brighter than all of them.
    </p>
    <p class="signature reveal d2">— from someone who noticed</p>
  </section>

  <!-- CONSTELLATION -->
  <section id="constellation">
    <div class="eyebrow reveal">connect the stars</div>
    <div class="const-wrap reveal d1">
      <svg id="const-svg" viewBox="0 0 600 600"></svg>
    </div>
    <div class="const-progress reveal d2" id="const-progress">0 / 0 stars lit</div>
    <div class="const-hint reveal d2">tap each star, in order, to light up the sky</div>
  </section>

  <!-- PLANET / QUESTION -->
  <section id="planet-section">
    <div class="eyebrow reveal">one more thing</div>
    <h2 class="reveal d1" style="font-size:clamp(1.6rem,4vw,2.3rem); margin-bottom:0.5rem;">Spin the planet to find out</h2>
    <div class="planet-wrap reveal d2">
      <canvas id="planet-canvas"></canvas>
    </div>
    <p class="planet-instructions reveal d3">drag to rotate · keep spinning</p>

    <div class="question-card" id="question-card">
      <h2 class="question-title">Will you go on a date with me? ☕</h2>
      <p class="question-detail">A coffee date — just us, good coffee, and however much talking (or comfortable silence) we want.</p>
      <div class="btn-row">
        <button class="btn btn-yes" id="btn-yes">Yes, let's get coffee</button>
        <button class="btn btn-no" id="btn-no">Let me think about it</button>
      </div>
    </div>
  </section>

  <!-- FINALE -->
  <section id="finale">
    <div class="coffee-icon">☕✦</div>
    <h2 class="finale-title">It's a date.</h2>
    <p class="finale-detail">
      <b>Aveeka</b> just said yes. Somewhere out there, a star just got a little brighter.
      I'll find the time and place — you just bring yourself.
    </p>
  </section>

  <footer>made with stars, nerves, and way too much css ✦</footer>

</div>

<script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
<script>
/* ============== BACKGROUND STARFIELD + NEBULA SCENE ============== */
(function(){
  const canvas = document.getElementById('scene-canvas');
  const renderer = new THREE.WebGLRenderer({ canvas, antialias:true, alpha:true });
  renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
  renderer.setSize(window.innerWidth, window.innerHeight);

  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(65, window.innerWidth/window.innerHeight, 0.1, 2000);
  camera.position.z = 60;

  // Starfield - multiple layers for depth
  function makeStarLayer(count, spread, size, color, opacity){
    const geo = new THREE.BufferGeometry();
    const positions = new Float32Array(count*3);
    for(let i=0;i<count;i++){
      positions[i*3] = (Math.random()-0.5)*spread;
      positions[i*3+1] = (Math.random()-0.5)*spread;
      positions[i*3+2] = (Math.random()-0.5)*spread;
    }
    geo.setAttribute('position', new THREE.BufferAttribute(positions,3));
    const mat = new THREE.PointsMaterial({
      color, size, transparent:true, opacity,
      sizeAttenuation:true, depthWrite:false
    });
    const pts = new THREE.Points(geo, mat);
    scene.add(pts);
    return pts;
  }

  const starsFar = makeStarLayer(1800, 800, 0.9, 0xffffff, 0.55);
  const starsMid = makeStarLayer(900, 500, 1.4, 0xc9b6ff, 0.7);
  const starsNear = makeStarLayer(350, 300, 2.2, 0xffd580, 0.85);

  // Nebula glow sprites
  function makeGlow(x,y,z,scale,color,opacity){
    const spriteMat = new THREE.SpriteMaterial({
      map: makeRadialTexture(color),
      transparent:true,
      opacity,
      depthWrite:false
    });
    const sprite = new THREE.Sprite(spriteMat);
    sprite.position.set(x,y,z);
    sprite.scale.set(scale,scale,1);
    scene.add(sprite);
    return sprite;
  }

  function makeRadialTexture(hexColor){
    const size = 256;
    const c = document.createElement('canvas');
    c.width = c.height = size;
    const ctx = c.getContext('2d');
    const grad = ctx.createRadialGradient(size/2,size/2,0,size/2,size/2,size/2);
    const col = new THREE.Color(hexColor);
    const r = Math.floor(col.r*255), g = Math.floor(col.g*255), b = Math.floor(col.b*255);
    grad.addColorStop(0, `rgba(${r},${g},${b},0.9)`);
    grad.addColorStop(0.4, `rgba(${r},${g},${b},0.35)`);
    grad.addColorStop(1, `rgba(${r},${g},${b},0)`);
    ctx.fillStyle = grad;
    ctx.fillRect(0,0,size,size);
    const tex = new THREE.CanvasTexture(c);
    return tex;
  }

  const glows = [
    makeGlow(-40, 20, -100, 140, 0x8a4fff, 0.5),
    makeGlow(50, -30, -160, 180, 0xff6fb5, 0.4),
    makeGlow(0, 60, -200, 160, 0x6f4fff, 0.35),
  ];

  let mouseX = 0, mouseY = 0;
  window.addEventListener('mousemove', (e)=>{
    mouseX = (e.clientX/window.innerWidth - 0.5);
    mouseY = (e.clientY/window.innerHeight - 0.5);
  });

  let scrollFrac = 0;
  function updateScroll(){
    const max = document.body.scrollHeight - window.innerHeight;
    scrollFrac = max > 0 ? window.scrollY / max : 0;
  }
  window.addEventListener('scroll', updateScroll, {passive:true});
  updateScroll();

  function animate(){
    requestAnimationFrame(animate);
    const t = performance.now()*0.0001;

    starsFar.rotation.y = t*0.5 + scrollFrac*0.6;
    starsMid.rotation.y = t*0.8 + scrollFrac*1.0;
    starsNear.rotation.y = t*1.2 + scrollFrac*1.6;
    starsFar.rotation.x = scrollFrac*0.3;
    starsMid.rotation.x = scrollFrac*0.45;

    camera.position.x += (mouseX*8 - camera.position.x)*0.02;
    camera.position.y += (-mouseY*8 - camera.position.y)*0.02;
    camera.position.z = 60 - scrollFrac*20;
    camera.lookAt(0,0,0);

    glows.forEach((g,i)=>{
      g.material.rotation = t*(0.2+i*0.1);
    });

    renderer.render(scene, camera);
  }
  animate();

  window.addEventListener('resize', ()=>{
    camera.aspect = window.innerWidth/window.innerHeight;
    camera.updateProjectionMatrix();
    renderer.setSize(window.innerWidth, window.innerHeight);
  });
})();

/* ============== SCROLL REVEAL ============== */
(function(){
  const els = document.querySelectorAll('.reveal');
  const obs = new IntersectionObserver((entries)=>{
    entries.forEach(entry=>{
      if(entry.isIntersecting){
        entry.target.classList.add('in');
      }
    });
  }, { threshold:0.25 });
  els.forEach(el=>obs.observe(el));
})();

/* ============== CONSTELLATION PUZZLE (spells small heart pattern via stars) ============== */
(function(){
  const svg = document.getElementById('const-svg');
  const progressEl = document.getElementById('const-progress');

  // Star points forming a heart-ish constellation, connect in this order
  const points = [
    {x:300, y:160}, // 1 top dip left-of-center start
    {x:230, y:100}, // 2 left upper lobe
    {x:140, y:140}, // 3 left side
    {x:110, y:230}, // 4 left lower
    {x:160, y:330}, // 5 left bottom curve
    {x:300, y:460}, // 6 bottom point
    {x:440, y:330}, // 7 right bottom curve
    {x:490, y:230}, // 8 right lower
    {x:460, y:140}, // 9 right side
    {x:370, y:100}, // 10 right upper lobe
    {x:300, y:160}, // 11 close back to start
  ];

  let litCount = 0;
  const total = points.length - 1; // number of connections needed (last point repeats first)
  let nextIndex = 0;

  // background faint stars scattered for atmosphere
  for(let i=0;i<40;i++){
    const x = Math.random()*600;
    const y = Math.random()*600;
    const r = Math.random()*1.2+0.4;
    const c = document.createElementNS('http://www.w3.org/2000/svg','circle');
    c.setAttribute('cx', x);
    c.setAttribute('cy', y);
    c.setAttribute('r', r);
    c.setAttribute('fill', '#ffffff');
    c.setAttribute('opacity', (Math.random()*0.35+0.1).toFixed(2));
    svg.appendChild(c);
  }

  // draw lines (hidden initially) between consecutive points
  const lineEls = [];
  for(let i=0;i<points.length-1;i++){
    const line = document.createElementNS('http://www.w3.org/2000/svg','line');
    line.setAttribute('x1', points[i].x);
    line.setAttribute('y1', points[i].y);
    line.setAttribute('x2', points[i+1].x);
    line.setAttribute('y2', points[i+1].y);
    line.classList.add('const-line');
    svg.appendChild(line);
    lineEls.push(line);
  }

  // draw star nodes (skip duplicate last point which equals first)
  const starEls = [];
  const uniquePoints = points.slice(0, points.length-1);
  uniquePoints.forEach((p, i)=>{
    const star = document.createElementNS('http://www.w3.org/2000/svg','circle');
    star.setAttribute('cx', p.x);
    star.setAttribute('cy', p.y);
    star.setAttribute('r', 7);
    star.classList.add('const-star');
    star.dataset.index = i;
    svg.appendChild(star);
    starEls.push(star);

    star.addEventListener('click', ()=>{
      if(i !== nextIndex) return; // must click in order
      star.classList.add('lit');
      star.setAttribute('r', 9);
      // light the line leading INTO this star (except first star)
      if(i > 0){
        lineEls[i-1].classList.add('lit');
      }
      nextIndex++;
      litCount++;
      progressEl.textContent = `${litCount} / ${uniquePoints.length} stars lit`;

      if(nextIndex === uniquePoints.length){
        // light final closing line back to start
        lineEls[lineEls.length-1].classList.add('lit');
        starEls[0].classList.add('lit'); // ensure start glows too
        progressEl.textContent = `✦ constellation complete ✦`;
      }
    });
  });

  progressEl.textContent = `0 / ${uniquePoints.length} stars lit`;
})();

/* ============== ROTATING 3D PLANET ============== */
(function(){
  const canvas = document.getElementById('planet-canvas');
  const renderer = new THREE.WebGLRenderer({ canvas, antialias:true, alpha:true });
  renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));

  const scene = new THREE.Scene();
  const camera = new THREE.PerspectiveCamera(45, 1, 0.1, 100);
  camera.position.z = 5.2;

  function resize(){
    const w = canvas.clientWidth, h = canvas.clientHeight;
    renderer.setSize(w, h, false);
    camera.aspect = w/h;
    camera.updateProjectionMatrix();
  }

  // Planet sphere with procedural-ish gradient texture
  function makePlanetTexture(){
    const size = 512;
    const c = document.createElement('canvas');
    c.width = size; c.height = size/2;
    const ctx = c.getContext('2d');
    const grad = ctx.createLinearGradient(0,0,0,size/2);
    grad.addColorStop(0, '#ff8fc7');
    grad.addColorStop(0.45, '#a86bff');
    grad.addColorStop(0.75, '#6f3fd8');
    grad.addColorStop(1, '#3a1f7a');
    ctx.fillStyle = grad;
    ctx.fillRect(0,0,size,size/2);

    // swirl bands
    ctx.globalAlpha = 0.25;
    for(let i=0;i<6;i++){
      ctx.beginPath();
      const y = (size/2/6)*i + Math.random()*20;
      ctx.moveTo(0, y);
      for(let x=0;x<=size;x+=32){
        ctx.lineTo(x, y + Math.sin(x*0.02+i)*14);
      }
      ctx.strokeStyle = i%2===0 ? '#ffd580' : '#ffffff';
      ctx.lineWidth = 6;
      ctx.stroke();
    }
    ctx.globalAlpha = 1;

    // speckle stars/craters
    for(let i=0;i<140;i++){
      ctx.beginPath();
      ctx.arc(Math.random()*size, Math.random()*size/2, Math.random()*2+0.5, 0, Math.PI*2);
      ctx.fillStyle = `rgba(255,255,255,${Math.random()*0.5+0.2})`;
      ctx.fill();
    }

    const tex = new THREE.CanvasTexture(c);
    tex.wrapS = THREE.RepeatWrapping;
    return tex;
  }

  const geo = new THREE.SphereGeometry(2, 48, 48);
  const mat = new THREE.MeshStandardMaterial({
    map: makePlanetTexture(),
    roughness:0.65,
    metalness:0.15,
    emissive: new THREE.Color(0x4a1f8a),
    emissiveIntensity:0.15
  });
  const planet = new THREE.Mesh(geo, mat);
  scene.add(planet);

  // glow ring
  const ringGeo = new THREE.RingGeometry(2.6, 2.85, 64);
  const ringMat = new THREE.MeshBasicMaterial({ color:0xffd580, transparent:true, opacity:0.25, side:THREE.DoubleSide });
  const ring = new THREE.Mesh(ringGeo, ringMat);
  ring.rotation.x = Math.PI/2.4;
  scene.add(ring);

  // small orbiting moon/heart particle
  const moonGeo = new THREE.SphereGeometry(0.18, 16, 16);
  const moonMat = new THREE.MeshStandardMaterial({ color:0xffd580, emissive:0xffd580, emissiveIntensity:0.6 });
  const moon = new THREE.Mesh(moonGeo, moonMat);
  scene.add(moon);

  const ambient = new THREE.AmbientLight(0xffffff, 0.55);
  scene.add(ambient);
  const point = new THREE.PointLight(0xffffff, 1.1);
  point.position.set(5,3,5);
  scene.add(point);
  const point2 = new THREE.PointLight(0xff6fb5, 0.6);
  point2.position.set(-5,-2,3);
  scene.add(point2);

  // sparkle particles around planet
  const sparkleCount = 60;
  const sparkleGeo = new THREE.BufferGeometry();
  const sparklePos = new Float32Array(sparkleCount*3);
  for(let i=0;i<sparkleCount;i++){
    const r = 3 + Math.random()*1.5;
    const theta = Math.random()*Math.PI*2;
    const phi = Math.random()*Math.PI;
    sparklePos[i*3] = r*Math.sin(phi)*Math.cos(theta);
    sparklePos[i*3+1] = r*Math.sin(phi)*Math.sin(theta);
    sparklePos[i*3+2] = r*Math.cos(phi);
  }
  sparkleGeo.setAttribute('position', new THREE.BufferAttribute(sparklePos,3));
  const sparkleMat = new THREE.PointsMaterial({ color:0xffffff, size:0.06, transparent:true, opacity:0.8 });
  const sparkles = new THREE.Points(sparkleGeo, sparkleMat);
  scene.add(sparkles);

  // interaction: drag to rotate, track total rotation for "spin enough" trigger
  let isDragging = false;
  let prevX = 0, prevY = 0;
  let velocityX = 0.004, velocityY = 0;
  let totalSpin = 0;
  let questionRevealed = false;

  function pointerDown(x,y){
    isDragging = true;
    prevX = x; prevY = y;
  }
  function pointerMove(x,y){
    if(!isDragging) return;
    const dx = x - prevX;
    const dy = y - prevY;
    velocityX = dx*0.005;
    velocityY = dy*0.005;
    planet.rotation.y += velocityX;
    planet.rotation.x += velocityY;
    totalSpin += Math.abs(dx);
    prevX = x; prevY = y;
    checkSpinThreshold();
  }
  function pointerUp(){ isDragging = false; }

  canvas.addEventListener('mousedown', e=>pointerDown(e.clientX, e.clientY));
  window.addEventListener('mousemove', e=>pointerMove(e.clientX, e.clientY));
  window.addEventListener('mouseup', pointerUp);

  canvas.addEventListener('touchstart', e=>{
    const t = e.touches[0];
    pointerDown(t.clientX, t.clientY);
  }, {passive:true});
  canvas.addEventListener('touchmove', e=>{
    const t = e.touches[0];
    pointerMove(t.clientX, t.clientY);
  }, {passive:true});
  canvas.addEventListener('touchend', pointerUp);

  const questionCard = document.getElementById('question-card');
  function checkSpinThreshold(){
    if(questionRevealed) return;
    if(totalSpin > 260){
      questionRevealed = true;
      questionCard.classList.add('shown');
    }
  }

  let moonAngle = 0;
  function animate(){
    requestAnimationFrame(animate);
    resize();

    if(!isDragging){
      planet.rotation.y += velocityX;
      planet.rotation.x += velocityY*0.3;
      velocityX *= 0.985;
      velocityY *= 0.985;
      if(Math.abs(velocityX) < 0.0015) velocityX = 0.0018; // gentle idle spin never fully stops
      totalSpin += Math.abs(velocityX)*30;
      checkSpinThreshold();
    }

    ring.rotation.z += 0.002;
    moonAngle += 0.018;
    moon.position.set(Math.cos(moonAngle)*3.1, Math.sin(moonAngle*0.6)*0.6, Math.sin(moonAngle)*3.1);
    sparkles.rotation.y += 0.0015;
    sparkles.rotation.x += 0.0008;

    renderer.render(scene, camera);
  }
  resize();
  animate();
  window.addEventListener('resize', resize);
})();

/* ============== QUESTION BUTTONS + PLAYFUL "NO" + CONFETTI ============== */
(function(){
  const btnYes = document.getElementById('btn-yes');
  const btnNo = document.getElementById('btn-no');
  const btnRow = document.querySelector('.btn-row');
  const finale = document.getElementById('finale');

  const noTexts = [
    "Let me think about it",
    "Catch me if you can",
    "Still thinking...",
    "Nope, try again",
    "You'll have to be quicker",
    "So close!"
  ];
  let noIndex = 0;
  let dodgeCount = 0;

  function dodge(){
    dodgeCount++;
    noIndex = (noIndex+1) % noTexts.length;
    btnNo.textContent = noTexts[noIndex];

    const rowRect = btnRow.getBoundingClientRect();
    const btnRect = btnNo.getBoundingClientRect();
    const maxX = rowRect.width - btnRect.width - 10;
    const maxY = 70;

    const randX = (Math.random()*2-1)*Math.min(maxX/2, 140);
    const randY = (Math.random()*2-1)*maxY*0.5;

    btnNo.style.position = 'relative';
    btnNo.style.left = randX + 'px';
    btnNo.style.top = randY + 'px';

    if(dodgeCount >= 5){
      btnNo.style.opacity = '0.4';
      btnNo.textContent = "ok, you win 🤍";
      btnNo.style.pointerEvents = 'none';
    }
  }

  btnNo.addEventListener('mouseenter', dodge);
  btnNo.addEventListener('click', (e)=>{ e.preventDefault(); dodge(); });
  btnNo.addEventListener('touchstart', (e)=>{ e.preventDefault(); dodge(); }, {passive:false});

  btnYes.addEventListener('click', ()=>{
    finale.classList.add('shown');
    finale.scrollIntoView({ behavior:'smooth' });
    launchConfetti();
  });

  /* Confetti / star-burst celebration */
  function launchConfetti(){
    const canvas = document.getElementById('confetti-canvas');
    const ctx = canvas.getContext('2d');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;

    const colors = ['#ff6fb5','#ffd580','#8a4fff','#ffffff','#c9b6ff'];
    const particles = [];
    const count = 160;

    for(let i=0;i<count;i++){
      particles.push({
        x: canvas.width/2,
        y: canvas.height*0.4,
        vx: (Math.random()-0.5)*14,
        vy: (Math.random()-1.2)*14,
        size: Math.random()*5+3,
        color: colors[Math.floor(Math.random()*colors.length)],
        rotation: Math.random()*360,
        rotSpeed: (Math.random()-0.5)*10,
        shape: Math.random()>0.5 ? 'star' : 'circle',
        life: 1
      });
    }

    function drawStar(ctx, size){
      ctx.beginPath();
      for(let i=0;i<5;i++){
        const angle = (i*4*Math.PI)/5 - Math.PI/2;
        const x = Math.cos(angle)*size;
        const y = Math.sin(angle)*size;
        if(i===0) ctx.moveTo(x,y); else ctx.lineTo(x,y);
      }
      ctx.closePath();
    }

    let frame = 0;
    const maxFrames = 220;

    function tick(){
      frame++;
      ctx.clearRect(0,0,canvas.width,canvas.height);
      particles.forEach(p=>{
        p.vy += 0.22; // gravity
        p.x += p.vx;
        p.y += p.vy;
        p.rotation += p.rotSpeed;
        p.life -= 0.0045;

        ctx.save();
        ctx.translate(p.x, p.y);
        ctx.rotate(p.rotation*Math.PI/180);
        ctx.globalAlpha = Math.max(p.life, 0);
        ctx.fillStyle = p.color;
        if(p.shape==='star'){
          drawStar(ctx, p.size);
          ctx.fill();
        } else {
          ctx.beginPath();
          ctx.arc(0,0,p.size*0.6,0,Math.PI*2);
          ctx.fill();
        }
        ctx.restore();
      });

      if(frame < maxFrames){
        requestAnimationFrame(tick);
      } else {
        ctx.clearRect(0,0,canvas.width,canvas.height);
      }
    }
    tick();
  }

  window.addEventListener('resize', ()=>{
    const canvas = document.getElementById('confetti-canvas');
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
  });
})();
</script>
</body>
</html>
