---
layout: post 
title: Portfolio Home 
hide: true
show_reading_time: false
---

<style>
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