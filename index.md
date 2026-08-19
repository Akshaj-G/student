---
layout: post 
title: Portfolio Home 
hide: true
show_reading_time: false
---

<style>
/* ===== Page-wide background ===== */
body {
  background-color: #0a0d12;
  background-image:
    linear-gradient(rgba(255,255,255,0.035) 1px, transparent 1px),
    linear-gradient(90deg, rgba(255,255,255,0.035) 1px, transparent 1px),
    radial-gradient(ellipse 900px 550px at 12% -5%, rgba(63,185,80,0.09), transparent 60%),
    radial-gradient(ellipse 1000px 650px at 105% 20%, rgba(88,166,255,0.08), transparent 60%),
    radial-gradient(ellipse 800px 550px at 50% 115%, rgba(57,197,207,0.07), transparent 60%);
  background-size: 42px 42px, 42px 42px, auto, auto, auto;
  background-attachment: fixed, fixed, fixed, fixed, fixed;
}

/* ===== 🦄 Unicorn Mascot (my unicorn feature) ===== */
.uni-widget {
  position: fixed;
  right: 18px;
  bottom: 18px;
  width: 120px;
  height: 140px;
  z-index: 999;
  cursor: pointer;
  -webkit-tap-highlight-color: transparent;
}
.uni-hint {
  position: absolute;
  top: -4px;
  right: 4px;
  font-family: ui-monospace, monospace;
  font-size: 11px;
  color: #e6edf3;
  background: #161b22;
  border: 1px solid #30363d;
  padding: 3px 8px;
  border-radius: 999px;
  white-space: nowrap;
  animation: uni-hint-bob 1.8s ease-in-out infinite, uni-hint-fade 1s ease 6s forwards;
  pointer-events: none;
}
@keyframes uni-hint-bob { 0%,100% { transform: translateY(0); } 50% { transform: translateY(-4px); } }
@keyframes uni-hint-fade { to { opacity: 0; visibility: hidden; } }

.uni-character {
  position: absolute;
  bottom: 6px;
  right: 20px;
  width: 90px;
  height: 100px;
  animation: uni-float 3.2s ease-in-out infinite;
}
@keyframes uni-float {
  0%, 100% { transform: translateY(0) rotate(-1deg); }
  50% { transform: translateY(-9px) rotate(1.5deg); }
}

.uni-mane {
  position: absolute;
  border-radius: 60% 40% 55% 45% / 55% 45% 55% 45%;
  opacity: 0.92;
  transform-origin: 80% 20%;
}
.uni-mane.m1 { width: 34px; height: 30px; top: 14px; left: 6px; background: linear-gradient(135deg,#ff5f7e,#ffd166); animation: uni-sway 2.4s ease-in-out infinite; z-index: 1; }
.uni-mane.m2 { width: 30px; height: 28px; top: 26px; left: 2px; background: linear-gradient(135deg,#ffd166,#06d6a0); animation: uni-sway 2.6s ease-in-out infinite 0.25s; z-index: 1; }
.uni-mane.m3 { width: 26px; height: 24px; top: 40px; left: 4px; background: linear-gradient(135deg,#06d6a0,#4cc9f0); animation: uni-sway 2.2s ease-in-out infinite 0.5s; z-index: 1; }
@keyframes uni-sway { 0%,100% { transform: rotate(-6deg); } 50% { transform: rotate(6deg); } }

.uni-tail {
  position: absolute;
  width: 22px; height: 20px;
  bottom: 10px; left: 2px;
  border-radius: 50% 50% 60% 40%;
  background: linear-gradient(135deg,#4cc9f0,#b28dff);
  transform-origin: 70% 30%;
  animation: uni-sway 2.1s ease-in-out infinite 0.15s;
  z-index: 0;
}

.uni-body {
  position: absolute;
  width: 46px; height: 40px;
  bottom: 6px; right: 12px;
  border-radius: 55% 45% 50% 50% / 60% 60% 40% 40%;
  background: #fdfcff;
  box-shadow: 0 3px 10px rgba(0,0,0,0.35);
  z-index: 2;
}
.uni-neck {
  position: absolute;
  width: 26px; height: 40px;
  bottom: 30px; right: 22px;
  border-radius: 50% 50% 40% 40%;
  background: #fdfcff;
  transform: rotate(-10deg);
  z-index: 2;
}
.uni-head {
  position: absolute;
  width: 40px; height: 34px;
  top: 6px; right: 14px;
  border-radius: 58% 42% 50% 50% / 55% 55% 45% 45%;
  background: #fdfcff;
  box-shadow: 0 3px 10px rgba(0,0,0,0.3);
  z-index: 3;
}
.uni-ear {
  position: absolute;
  top: -6px; right: 2px;
  width: 0; height: 0;
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-bottom: 10px solid #fdfcff;
  transform: rotate(18deg);
  z-index: 3;
}
.uni-horn {
  position: absolute;
  top: -16px; right: 10px;
  width: 0; height: 0;
  border-left: 5px solid transparent;
  border-right: 5px solid transparent;
  border-bottom: 18px solid #ffd166;
  filter: drop-shadow(0 0 4px rgba(255,209,102,0.85));
  transform: rotate(12deg);
  z-index: 4;
  animation: uni-glow 2s ease-in-out infinite;
}
@keyframes uni-glow {
  0%,100% { filter: drop-shadow(0 0 3px rgba(255,209,102,0.6)); }
  50% { filter: drop-shadow(0 0 8px rgba(255,209,102,1)); }
}
.uni-eye {
  position: absolute;
  top: 14px; right: 10px;
  width: 4px; height: 5px;
  background: #1b1f27;
  border-radius: 50%;
  z-index: 4;
}
.uni-eye::after {
  content: '';
  position: absolute;
  top: 0; left: 0.5px;
  width: 1.4px; height: 1.4px;
  background: #fff;
  border-radius: 50%;
}
.uni-blush {
  position: absolute;
  top: 20px; right: 20px;
  width: 6px; height: 4px;
  background: #ff9eb5;
  border-radius: 50%;
  opacity: 0.7;
  filter: blur(0.5px);
  z-index: 4;
}

.uni-sparks { position: absolute; top: -20px; right: 6px; width: 30px; height: 30px; pointer-events: none; z-index: 5; }
.uni-spark {
  position: absolute;
  font-size: 10px;
  opacity: 0;
  top: 10px; left: 12px;
}
.uni-widget:hover .uni-spark, .uni-widget.uni-active .uni-spark {
  animation: uni-spark-fly 0.9s ease-out forwards;
}
.uni-spark:nth-child(1) { animation-delay: 0s; }
.uni-spark:nth-child(2) { animation-delay: 0.12s; }
.uni-spark:nth-child(3) { animation-delay: 0.24s; }
.uni-spark:nth-child(4) { animation-delay: 0.36s; }
@keyframes uni-spark-fly {
  0% { opacity: 0; transform: translate(0,0) scale(0.4) rotate(0deg); }
  30% { opacity: 1; }
  100% { opacity: 0; transform: translate(var(--sx,10px), var(--sy,-24px)) scale(1) rotate(90deg); }
}
.uni-spark:nth-child(1) { --sx: -16px; --sy: -20px; }
.uni-spark:nth-child(2) { --sx: 4px;  --sy: -26px; }
.uni-spark:nth-child(3) { --sx: 18px; --sy: -14px; }
.uni-spark:nth-child(4) { --sx: -6px; --sy: -30px; }

.uni-bubble {
  position: absolute;
  bottom: 108px;
  right: 0;
  min-width: 140px;
  max-width: 200px;
  background: #161b22;
  color: #e6edf3;
  border: 1px solid #30363d;
  border-radius: 10px;
  padding: 8px 10px;
  font-family: ui-monospace, monospace;
  font-size: 11.5px;
  line-height: 1.4;
  opacity: 0;
  transform: translateY(6px) scale(0.92);
  transform-origin: bottom right;
  transition: opacity 0.18s ease, transform 0.18s ease;
  pointer-events: none;
  box-shadow: 0 8px 20px rgba(0,0,0,0.4);
}
.uni-bubble::after {
  content: '';
  position: absolute;
  bottom: -6px;
  right: 24px;
  width: 12px; height: 12px;
  background: #161b22;
  border-right: 1px solid #30363d;
  border-bottom: 1px solid #30363d;
  transform: rotate(45deg);
}
.uni-bubble.uni-show { opacity: 1; transform: translateY(0) scale(1); }

@media (prefers-reduced-motion: reduce) {
  .uni-character, .uni-mane, .uni-tail, .uni-horn, .uni-hint { animation: none !important; }
}
@media (max-width: 480px) {
  .uni-widget { width: 92px; height: 110px; transform: scale(0.85); transform-origin: bottom right; }
}

/* ===== Hero / Boot Sequence ===== */
.boot-hero {
  position: relative;
  border-radius: 10px;
  overflow: hidden;
  border: 1px solid #30363d;
  background: #0d1117;
  margin-bottom: 22px;
}
#boot-matrix {
  position: absolute;
  inset: 0;
  width: 100%;
  height: 100%;
  display: block;
}
.boot-content {
  position: relative;
  z-index: 2;
  padding: 26px 22px;
  font-family: 'JetBrains Mono', 'Fira Code', ui-monospace, SFMono-Regular, Menlo, monospace;
}
.boot-line { color: #7ee787; font-size: 13px; margin-bottom: 4px; }
.boot-line .boot-prompt { color: #58a6ff; margin-right: 8px; }
.boot-name { color: #e6edf3; font-size: 26px; font-weight: 700; margin: 6px 0 2px 0; }
.boot-sub { color: #8b949e; font-size: 13.5px; }
.boot-cursor {
  display: inline-block;
  width: 8px;
  height: 15px;
  background: #7ee787;
  margin-left: 3px;
  vertical-align: text-bottom;
  animation: ghp-blink 1.1s steps(1) infinite;
}
@keyframes ghp-blink { 50% { opacity: 0; } }
@media (prefers-reduced-motion: reduce) {
  .boot-cursor { animation: none; }
}

/* ===== Dev Environment: install manifest ===== */
.de-panel {
  font-family: 'JetBrains Mono', 'Fira Code', ui-monospace, SFMono-Regular, Menlo, monospace;
  background: #0d1117; border: 1px solid #30363d; border-radius: 10px; overflow: hidden;
}
.de-titlebar { padding: 10px 16px; background: #161b22; border-bottom: 1px solid #30363d; color: #7ee787; font-size: 13px; }
.de-list { padding: 6px; }
.de-pkg {
  display: flex; align-items: center; gap: 10px;
  text-decoration: none; padding: 9px 12px; margin: 3px 4px;
  border-radius: 6px; transition: background 0.18s ease, transform 0.18s ease;
  opacity: 0; animation: de-fade-in 0.4s ease forwards;
}
.de-pkg:nth-child(1) { animation-delay: 0.15s; }
.de-pkg:nth-child(2) { animation-delay: 0.35s; }
.de-pkg:nth-child(3) { animation-delay: 0.55s; }
@keyframes de-fade-in { from { opacity: 0; transform: translateX(-6px); } to { opacity: 1; transform: translateX(0); } }
@media (prefers-reduced-motion: reduce) {
  .de-pkg { animation: none; opacity: 1; }
}
.de-pkg:hover { background: #161b22; transform: translateX(4px); }
.de-check { color: #3fb950; font-weight: 700; }
.de-name { color: #e6edf3; font-weight: 600; font-size: 14px; }
.de-ver { color: #8b949e; font-size: 12px; }
.de-desc { color: #8b949e; font-size: 12px; margin-left: auto; text-align: right; }
.de-summary { padding: 10px 16px; color: #3fb950; font-size: 12px; border-top: 1px solid #30363d; }

/* ===== My Lessons: test suite ===== */
.ml-panel {
  font-family: 'JetBrains Mono', 'Fira Code', ui-monospace, SFMono-Regular, Menlo, monospace;
  background: #0d1117; border: 1px solid #30363d; border-radius: 10px; overflow: hidden;
}
.ml-titlebar { padding: 10px 16px; background: #161b22; border-bottom: 1px solid #30363d; color: #7ee787; font-size: 13px; }
.ml-tests { padding: 6px; }
.ml-test {
  display: block; text-decoration: none; padding: 9px 14px; margin: 3px 4px;
  border-radius: 6px; transition: background 0.18s ease;
}
.ml-test:hover { background: #161b22; }
.ml-row { display: flex; align-items: center; gap: 10px; }
.ml-status {
  font-size: 10px; font-weight: 700; padding: 2px 7px; border-radius: 4px;
  background: rgba(63,185,80,0.15); color: #3fb950; letter-spacing: 0.5px;
}
.ml-name { color: #e6edf3; font-size: 13.5px; font-weight: 600; }
.ml-time { color: #8b949e; font-size: 11.5px; margin-left: auto; }
.ml-bar-track { height: 4px; background: #21262d; border-radius: 2px; margin-top: 7px; overflow: hidden; }
.ml-bar-fill { height: 100%; width: 0%; background: #3fb950; border-radius: 2px; transition: width 0.6s ease; }
.ml-test:hover .ml-bar-fill { width: var(--cov); }
.ml-cov-label { font-size: 10px; color: #8b949e; margin-top: 3px; }
.ml-summary { padding: 10px 16px; color: #3fb950; font-size: 12px; border-top: 1px solid #30363d; white-space: pre-line; }

/* ===== Class Progress: arcade select ===== */
.cp-arcade {
  font-family: 'Press Start 2P', 'JetBrains Mono', monospace;
  background:
    repeating-linear-gradient(0deg, rgba(255,255,255,0.025) 0px, rgba(255,255,255,0.025) 1px, transparent 1px, transparent 3px),
    #0a0a12;
  border: 2px solid #2a2a3d;
  border-radius: 10px;
  padding: 20px 16px;
  text-align: center;
}
.cp-title { color: #f0f0f0; font-size: 13px; letter-spacing: 2px; margin-bottom: 4px; }
.cp-blink { color: #ff6ec7; font-size: 10px; letter-spacing: 1.5px; animation: cp-flicker 1.2s steps(1) infinite; margin-bottom: 18px; }
@keyframes cp-flicker { 50% { opacity: 0.15; } }
@media (prefers-reduced-motion: reduce) {
  .cp-blink { animation: none; }
}
.cp-grid { display: flex; flex-wrap: wrap; gap: 14px; justify-content: center; }
.cp-cabinet {
  text-decoration: none;
  width: 130px;
  padding: 16px 10px 12px 10px;
  border-radius: 8px;
  background: #14141f;
  border: 2px solid var(--cp-accent);
  box-shadow: 0 0 0 rgba(0,0,0,0);
  transition: transform 0.18s ease, box-shadow 0.18s ease;
}
.cp-cabinet:hover {
  transform: translateY(-4px) scale(1.03);
  box-shadow: 0 0 16px var(--cp-accent);
}
.cp-icon { font-size: 22px; margin-bottom: 10px; }
.cp-name { color: var(--cp-accent); font-size: 9.5px; line-height: 1.6; margin-bottom: 8px; }
.cp-mode { color: #8b8b9e; font-size: 6.5px; letter-spacing: 0.5px; }
</style>

<div class="boot-hero">
  <canvas id="boot-matrix"></canvas>
  <div class="boot-content">
    <div class="boot-line"><span class="boot-prompt">$</span>whoami</div>
    <div class="boot-name" id="boot-line1"></div>
    <div class="boot-line" style="margin-top:8px;"><span class="boot-prompt">$</span>status</div>
    <div class="boot-sub" id="boot-line2"><span class="boot-cursor"></span></div>
  </div>
</div>

<script>
(function(){
  var canvas = document.getElementById('boot-matrix');
  var reduceMotion = window.matchMedia && window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  if (canvas) {
    var ctx = canvas.getContext('2d');
    function resize(){
      canvas.width = canvas.offsetWidth;
      canvas.height = canvas.offsetHeight;
    }
    resize();
    window.addEventListener('resize', resize);
    if (reduceMotion) {
      ctx.fillStyle = '#0d1117';
      ctx.fillRect(0,0,canvas.width,canvas.height);
    } else {
      var chars = '01{}<>/;=+-*[]()xyzABCDEF'.split('');
      var fontSize = 14;
      var columns = Math.max(1, Math.floor(canvas.width / fontSize));
      var drops = new Array(columns).fill(1);
      (function draw(){
        ctx.fillStyle = 'rgba(13,17,23,0.12)';
        ctx.fillRect(0,0,canvas.width,canvas.height);
        ctx.fillStyle = 'rgba(63,185,80,0.55)';
        ctx.font = fontSize + 'px monospace';
        for (var i=0;i<drops.length;i++){
          var text = chars[Math.floor(Math.random()*chars.length)];
          ctx.fillText(text, i*fontSize, drops[i]*fontSize);
          if (drops[i]*fontSize > canvas.height && Math.random() > 0.975) drops[i] = 0;
          drops[i]++;
        }
        requestAnimationFrame(draw);
      })();
    }
  }

  var el1 = document.getElementById('boot-line1');
  var el2 = document.getElementById('boot-line2');
  var text1 = 'Akshaj Gurugubelli';
  var text2 = 'building, learning, shipping code.';
  if (reduceMotion) {
    if (el1) el1.textContent = text1;
    if (el2) el2.innerHTML = text2 + '<span class="boot-cursor"></span>';
    return;
  }
  var i = 0;
  function type1(){
    if (i <= text1.length) {
      el1.textContent = text1.slice(0, i);
      i++;
      setTimeout(type1, 55);
    } else {
      setTimeout(type2, 300);
    }
  }
  var j = 0;
  function type2(){
    if (j <= text2.length) {
      el2.innerHTML = text2.slice(0, j) + '<span class="boot-cursor"></span>';
      j++;
      setTimeout(type2, 35);
    }
  }
  if (el1) type1();
})();
</script>

> 🦄 **This is my unicorn.** Nobody asked for a living mascot on a portfolio homepage — I built one anyway. Bottom-right corner, always with you. Click it.

<div class="uni-widget" id="uniWidget" title="click me">
  <span class="uni-hint">psst 👋</span>
  <div class="uni-bubble" id="uniBubble"></div>
  <div class="uni-character">
    <div class="uni-tail"></div>
    <div class="uni-mane m1"></div>
    <div class="uni-mane m2"></div>
    <div class="uni-mane m3"></div>
    <div class="uni-body"></div>
    <div class="uni-neck"></div>
    <div class="uni-head">
      <div class="uni-ear"></div>
      <div class="uni-horn"></div>
      <div class="uni-eye"></div>
      <div class="uni-blush"></div>
      <div class="uni-sparks">
        <span class="uni-spark">✦</span>
        <span class="uni-spark">✧</span>
        <span class="uni-spark">✦</span>
        <span class="uni-spark">✧</span>
      </div>
    </div>
  </div>
</div>

<script>
(function(){
  var widget = document.getElementById('uniWidget');
  var bubble = document.getElementById('uniBubble');
  if (!widget || !bubble) return;
  var lines = [
    "console.log('magic');",
    "I debug with sparkles ✨",
    "404: ordinary portfolio not found",
    "git commit -m 'added a unicorn, no regrets'",
    "powered by caffeine and CSS",
    "not all heroes wear capes, some wear horns",
    "O(1) magic, O(n) homework",
    "this.horn.glow = true;"
  ];
  var hideTimer = null;
  widget.addEventListener('click', function(){
    var msg = lines[Math.floor(Math.random() * lines.length)];
    bubble.textContent = msg;
    bubble.classList.add('uni-show');
    widget.classList.add('uni-active');
    clearTimeout(hideTimer);
    hideTimer = setTimeout(function(){
      bubble.classList.remove('uni-show');
      widget.classList.remove('uni-active');
    }, 3200);
  });
})();
</script>

<br>

### Development Environment

> Coding starts with tools, explore these tools and procedures with a click.

<div class="de-panel">
  <div class="de-titlebar">$ npm install --save-dev ocs github vscode-dev</div>
  <div class="de-list">
    <a class="de-pkg" href="https://opencodingsociety.com">
      <span class="de-check">✓</span>
      <span class="de-name">ocs</span>
      <span class="de-ver">v4.0.0</span>
      <span class="de-desc">Open Coding Society hub</span>
    </a>
    <a class="de-pkg" href="https://github.com/Open-Coding-Society/portfolio">
      <span class="de-check">✓</span>
      <span class="de-name">portfolio</span>
      <span class="de-ver">v1.0.0</span>
      <span class="de-desc">Source for this site, deployed via GitHub Actions</span>
    </a>
    <a class="de-pkg" href="https://vscode.dev/">
      <span class="de-check">✓</span>
      <span class="de-name">vscode-dev</span>
      <span class="de-ver">v1.0.0</span>
      <span class="de-desc">Browser-based editor</span>
    </a>
  </div>
  <div class="de-summary">added 3 packages in 0.6s</div>
</div>

<br>

### My Lessons

> Foundations in Tech are essential, click to see some of my lesson creations.

<div class="ml-panel">
  <div class="ml-titlebar">$ npm test -- lessons</div>
  <div class="ml-tests">
    <a class="ml-test" href="{{site.baseurl}}/code/javascript" style="--cov: 92%;">
      <div class="ml-row">
        <span class="ml-status">PASS</span>
        <span class="ml-name">js-basics.test.js</span>
        <span class="ml-time">8ms</span>
      </div>
      <div class="ml-bar-track"><div class="ml-bar-fill"></div></div>
      <div class="ml-cov-label">92% coverage</div>
    </a>
    <a class="ml-test" href="{{site.baseurl}}/game/essentials/variables" style="--cov: 88%;">
      <div class="ml-row">
        <span class="ml-status">PASS</span>
        <span class="ml-name">js-variables.test.js</span>
        <span class="ml-time">6ms</span>
      </div>
      <div class="ml-bar-track"><div class="ml-bar-fill"></div></div>
      <div class="ml-cov-label">88% coverage</div>
    </a>
    <a class="ml-test" href="{{site.baseurl}}/gamerunner" style="--cov: 95%;">
      <div class="ml-row">
        <span class="ml-status">PASS</span>
        <span class="ml-name">gamerunner.test.js</span>
        <span class="ml-time">14ms</span>
      </div>
      <div class="ml-bar-track"><div class="ml-bar-fill"></div></div>
      <div class="ml-cov-label">95% coverage</div>
    </a>
    <a class="ml-test" href="{{site.baseurl}}/network/stack" style="--cov: 90%;">
      <div class="ml-row">
        <span class="ml-status">PASS</span>
        <span class="ml-name">network-stack.test.js</span>
        <span class="ml-time">10ms</span>
      </div>
      <div class="ml-bar-track"><div class="ml-bar-fill"></div></div>
      <div class="ml-cov-label">90% coverage</div>
    </a>
  </div>
  <div class="ml-summary">Test Suites: 4 passed, 4 total
Tests:       4 passed, 4 total
Time:        0.38s</div>
</div>

<br>

### Class Progress

> Here is my game progress through coding, click to see these in the browser

<div class="cp-arcade">
  <div class="cp-title">SELECT YOUR GAME</div>
  <div class="cp-blink">◆ PRESS START ◆</div>
  <div class="cp-grid">
    <a class="cp-cabinet" style="--cp-accent:#3fb950;" href="{{site.baseurl}}/snake">
      <div class="cp-icon">🐍</div>
      <div class="cp-name">SNAKE</div>
      <div class="cp-mode">CLASSIC MODE</div>
    </a>
    <a class="cp-cabinet" style="--cp-accent:#58a6ff;" href="{{site.baseurl}}/gamify/parallax">
      <div class="cp-icon">🐟</div>
      <div class="cp-name">FISH</div>
      <div class="cp-mode">PARALLAX DEMO</div>
    </a>
    <a class="cp-cabinet" style="--cp-accent:#39c5cf;" href="{{site.baseurl}}/gamify">
      <div class="cp-icon">🎮</div>
      <div class="cp-name">GAMIFY</div>
      <div class="cp-mode">LEVEL HUB</div>
    </a>
    <a class="cp-cabinet" style="--cp-accent:#ffa657;" href="{{site.baseurl}}/cs-pathway">
      <div class="cp-icon">🗺️</div>
      <div class="cp-name">CS PATHWAY</div>
      <div class="cp-mode">SKILL TREE</div>
    </a>
  </div>
</div>

<br>

### GitHub Pages Fundamentals

> Learning the building blocks behind this site, six commits deep into how it works.

<style>
.ghp-terminal {
  font-family: 'JetBrains Mono', 'Fira Code', ui-monospace, SFMono-Regular, Menlo, monospace;
  background: #0d1117;
  border: 1px solid #30363d;
  border-radius: 10px;
  overflow: hidden;
  box-shadow: 0 8px 24px rgba(0,0,0,0.35);
  margin: 8px 0 18px 0;
}
.ghp-titlebar {
  display: flex;
  align-items: center;
  gap: 8px;
  padding: 10px 14px;
  background: #161b22;
  border-bottom: 1px solid #30363d;
}
.ghp-dot { width: 11px; height: 11px; border-radius: 50%; display: inline-block; }
.ghp-titlebar span.ghp-path {
  margin-left: 10px;
  color: #8b949e;
  font-size: 12.5px;
}
.ghp-prompt {
  padding: 12px 16px 4px 16px;
  color: #7ee787;
  font-size: 13px;
}
.ghp-prompt .ghp-cursor {
  display: inline-block;
  width: 7px;
  height: 14px;
  background: #7ee787;
  margin-left: 4px;
  vertical-align: text-bottom;
  animation: ghp-blink 1.1s steps(1) infinite;
}
.ghp-log { padding: 6px 6px 14px 6px; }
.ghp-commit {
  display: block;
  text-decoration: none;
  position: relative;
  padding: 10px 14px 10px 22px;
  margin: 2px 6px;
  border-radius: 6px;
  border-left: 3px solid var(--ghp-accent);
  transition: background 0.18s ease, transform 0.18s ease, padding-bottom 0.18s ease;
}
.ghp-commit:hover {
  background: #161b22;
  transform: translateX(4px);
}
.ghp-hash {
  color: var(--ghp-accent);
  font-weight: 700;
  font-size: 13px;
}
.ghp-msg {
  color: #e6edf3;
  font-size: 14.5px;
  font-weight: 600;
  margin-left: 10px;
}
.ghp-desc {
  color: #8b949e;
  font-size: 12.5px;
  max-height: 0;
  opacity: 0;
  overflow: hidden;
  transition: max-height 0.25s ease, opacity 0.2s ease, margin-top 0.2s ease;
}
.ghp-commit:hover .ghp-desc {
  max-height: 40px;
  opacity: 1;
  margin-top: 4px;
}
.ghp-tag {
  float: right;
  font-size: 10.5px;
  color: #0d1117;
  background: var(--ghp-accent);
  padding: 1px 8px;
  border-radius: 999px;
  font-weight: 700;
}
.ghp-readme {
  font-family: 'JetBrains Mono', 'Fira Code', ui-monospace, SFMono-Regular, Menlo, monospace;
  background: #0d1117;
  border: 1px solid #30363d;
  border-radius: 10px;
  overflow: hidden;
}
.ghp-tabbar {
  display: flex;
  background: #161b22;
  border-bottom: 1px solid #30363d;
}
.ghp-tab {
  padding: 9px 16px;
  font-size: 12.5px;
  color: #8b949e;
  border-right: 1px solid #30363d;
}
.ghp-tab.active {
  color: #e6edf3;
  background: #0d1117;
  border-top: 2px solid #58a6ff;
}
.ghp-readme-body {
  padding: 16px 18px;
  color: #c9d1d9;
  font-size: 13.5px;
  line-height: 1.7;
}
.ghp-readme-body .ghp-comment { color: #7ee787; display: block; margin-bottom: 10px; }
.ghp-readme-body code {
  background: #161b22;
  color: #ffa657;
  padding: 1px 5px;
  border-radius: 4px;
  font-size: 12.5px;
}
</style>

<div class="ghp-terminal">
  <div class="ghp-titlebar">
    <span class="ghp-dot" style="background:#ff5f56;"></span>
    <span class="ghp-dot" style="background:#ffbd2e;"></span>
    <span class="ghp-dot" style="background:#27c93f;"></span>
    <span class="ghp-path">akshaj@portfolio: ~/github-pages-fundamentals</span>
  </div>
  <div class="ghp-prompt">$ git log --oneline --graph<span class="ghp-cursor"></span></div>
  <div class="ghp-log">
    <a class="ghp-commit" style="--ghp-accent:#3fb950;" href="{{site.baseurl}}/github/pages/jokes">
      <span class="ghp-tag">01</span>
      <span class="ghp-hash">a1e4f2c</span><span class="ghp-msg">Notebooks &amp; Jokes</span>
      <div class="ghp-desc">Fun with JavaScript and Jupyter Notebooks</div>
    </a>
    <a class="ghp-commit" style="--ghp-accent:#58a6ff;" href="{{site.baseurl}}/github/pages/anatomy">
      <span class="ghp-tag">02</span>
      <span class="ghp-hash">b7c91da</span><span class="ghp-msg">Anatomy</span>
      <div class="ghp-desc">Explore the structure of a GitHub Pages site</div>
    </a>
    <a class="ghp-commit" style="--ghp-accent:#e3b341;" href="{{site.baseurl}}/github/pages/theme">
      <span class="ghp-tag">03</span>
      <span class="ghp-hash">c3f0e8b</span><span class="ghp-msg">Theme</span>
      <div class="ghp-desc">Theme templates and SASS layout for advanced styling</div>
    </a>
    <a class="ghp-commit" style="--ghp-accent:#ffa657;" href="{{site.baseurl}}/github/pages/markdown">
      <span class="ghp-tag">04</span>
      <span class="ghp-hash">d92a1f4</span><span class="ghp-msg">Markdown</span>
      <div class="ghp-desc">Master Markdown for content creation</div>
    </a>
    <a class="ghp-commit" style="--ghp-accent:#39c5cf;" href="{{site.baseurl}}/github/pages/jekyll">
      <span class="ghp-tag">05</span>
      <span class="ghp-hash">e58b3c7</span><span class="ghp-msg">Jekyll</span>
      <div class="ghp-desc">Understand Jekyll static site generation</div>
    </a>
    <a class="ghp-commit" style="--ghp-accent:#3fb950;" href="{{site.baseurl}}/github/pages/hacks">
      <span class="ghp-tag">06</span>
      <span class="ghp-hash">f14d6a9</span><span class="ghp-msg">Hacks</span>
      <div class="ghp-desc">Apply your knowledge with hands-on challenges</div>
    </a>
  </div>
</div>

<div class="ghp-readme">
  <div class="ghp-tabbar">
    <div class="ghp-tab active">README.md</div>
  </div>
  <div class="ghp-readme-body">
    <span class="ghp-comment"># why i linked these</span>
    Notebooks &amp; Jokes introduces JavaScript basics inside Jupyter Notebooks, using a set of programmer and accountant jokes as a low-stakes way to test code output in the console. Anatomy breaks down the structure of a GitHub Pages repository, showing how folders like <code>_notebooks</code>, <code>_posts</code>, <code>_layouts</code>, and <code>_sass</code> fit together to generate a site. Theme covers how SASS files and layout templates control the look of the site, and how to swap or customize the Minima theme. Markdown explains the syntax used to write nearly every page on this site, including this one, from headers to links to embedded HTML. Jekyll ties it together by explaining how the static site generator turns Markdown, front matter, and layouts into the deployed website. Hacks is where all of it gets applied through hands-on challenges. I linked these here so I have a fast reference back to the fundamentals as I keep building out this site.
  </div>
</div>

<br>