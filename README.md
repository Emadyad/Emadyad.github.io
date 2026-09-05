<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<meta name="description" content="Emad Yad — technology learner and builder. Cloud, DevOps, cybersecurity, networking, AI infrastructure and Python.">
<meta name="theme-color" content="#0a0b0f">
<title>Emad Yad — Technology Portfolio</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:ital,wght@0,100..800;1,100..800&display=swap" rel="stylesheet">
<style>
  :root{
    --ink:#0a0b0f;
    --panel:#12141a;
    --panel-2:#0e0f14;
    --line:rgba(255,255,255,.11);
    --line-soft:rgba(255,255,255,.06);
    --text:#e8eaee;
    --muted:#8b93a3;
    --dim:#575f6c;
    --amber:#f2a93c;
    --amber-soft:rgba(242,169,60,.13);
    --amber-line:rgba(242,169,60,.35);
    --max:960px;
    --radius:5px;
  }
  *{box-sizing:border-box}
  html{scroll-behavior:smooth}
  body{
    margin:0;background:var(--ink);color:var(--text);
    font-family:"JetBrains Mono",ui-monospace,SFMono-Regular,Menlo,Consolas,monospace;
    line-height:1.7;font-size:16px;-webkit-font-smoothing:antialiased;
  }
  body::before{
    content:"";position:fixed;inset:0;pointer-events:none;z-index:-1;
    background-image:
      linear-gradient(var(--line-soft) 1px,transparent 1px),
      linear-gradient(90deg,var(--line-soft) 1px,transparent 1px);
    background-size:64px 64px;
    -webkit-mask-image:radial-gradient(ellipse 70% 55% at 50% 0%,#000 0%,transparent 72%);
            mask-image:radial-gradient(ellipse 70% 55% at 50% 0%,#000 0%,transparent 72%);
    opacity:.5;
  }
  a{color:inherit;text-decoration:none}
  ::selection{background:var(--amber-soft);color:var(--text)}
  :focus-visible{outline:1.5px solid var(--amber);outline-offset:3px}

  .wrap{max-width:var(--max);margin:0 auto;padding:0 24px}
  .section{max-width:var(--max);margin:0 auto;padding:96px 24px}
  .section + .section{border-top:1px solid var(--line-soft)}

  /* ---------- nav ---------- */
  .nav{
    position:sticky;top:0;z-index:30;
    background:rgba(10,11,15,.82);backdrop-filter:blur(10px);
    border-bottom:1px solid var(--line-soft);
  }
  .nav-inner{max-width:var(--max);margin:0 auto;padding:0 24px;height:60px;display:flex;align-items:center;justify-content:space-between}
  .brand{font-size:14px;font-weight:600;color:var(--text)}
  .brand .prompt{color:var(--amber)}
  .nav-links{display:flex;align-items:center;gap:26px;font-size:13px;color:var(--muted)}
  .nav-links a{position:relative;padding:4px 0}
  .nav-links a:hover{color:var(--text)}
  .nav-links a::after{content:"";position:absolute;left:0;right:0;bottom:-2px;height:1px;background:var(--amber);transform:scaleX(0);transform-origin:left;transition:transform .2s ease}
  .nav-links a:hover::after{transform:scaleX(1)}
  .connect-btn{font-size:13px;border:1px solid var(--line);padding:8px 14px;border-radius:var(--radius);color:var(--text)}
  .connect-btn:hover{border-color:var(--amber-line);color:var(--amber)}
  .nav-toggle{display:none;background:none;border:1px solid var(--line);border-radius:var(--radius);color:var(--text);width:36px;height:36px;font-size:16px;cursor:pointer}
  .nav-mobile{display:none;flex-direction:column;gap:2px;padding:10px 24px 18px;border-top:1px solid var(--line-soft)}
  .nav-mobile a{padding:10px 0;font-size:14px;color:var(--muted);border-bottom:1px solid var(--line-soft)}
  .nav-mobile.open{display:flex}

  /* ---------- hero ---------- */
  .hero{padding-top:64px;padding-bottom:96px;display:grid;grid-template-columns:1.05fr .95fr;gap:56px;align-items:center}
  .prompt-line{font-size:13px;color:var(--dim);margin-bottom:18px}
  .prompt-line .amber{color:var(--amber)}
  h1{
    font-family:inherit;font-weight:700;letter-spacing:-.01em;
    font-size:clamp(34px,4.6vw,50px);line-height:1.12;margin:0 0 20px;color:var(--text);
  }
  .hero-lede{color:var(--muted);font-size:15.5px;max-width:52ch;margin:0 0 34px}
  .hero-lede strong{color:var(--text);font-weight:600}
  .hero-actions{display:flex;flex-wrap:wrap;gap:12px;margin-bottom:44px}
  .btn{
    font-size:13px;padding:12px 18px;border-radius:var(--radius);border:1px solid var(--line);
    display:inline-flex;align-items:center;gap:8px;
  }
  .btn.primary{background:var(--amber);color:#151005;border-color:var(--amber);font-weight:600}
  .btn.primary:hover{background:#ffb852}
  .btn.ghost:hover{border-color:var(--amber-line);color:var(--amber)}
  .stat-row{display:flex;gap:0}
  .stat{padding:0 24px;border-left:1px solid var(--line-soft)}
  .stat:first-child{padding-left:0;border-left:none}
  .stat b{display:block;font-size:18px;color:var(--text);font-weight:600}
  .stat span{font-size:11.5px;color:var(--dim)}

  /* ---------- terminal ---------- */
  .terminal{
    background:var(--panel);border:1px solid var(--line);border-radius:8px;
    overflow:hidden;box-shadow:0 24px 60px -20px rgba(0,0,0,.6);
  }
  .terminal-bar{
    display:flex;align-items:center;gap:8px;padding:11px 14px;
    border-bottom:1px solid var(--line-soft);background:var(--panel-2);
  }
  .terminal-bar .dot{width:9px;height:9px;border-radius:50%;background:var(--dim);opacity:.55}
  .terminal-bar .title{margin-left:6px;font-size:11.5px;color:var(--dim)}
  .terminal-body{padding:22px 20px 26px;font-size:13.5px;min-height:236px}
  .terminal-body .row{display:flex;gap:10px;margin-bottom:4px;color:var(--text)}
  .terminal-body .row .sym{color:var(--amber);flex-shrink:0}
  .terminal-body .out{color:var(--muted);margin:0 0 16px;padding-left:20px}
  .caret{display:inline-block;width:7px;height:14px;background:var(--amber);vertical-align:-2px;animation:blink 1s step-end infinite}
  @keyframes blink{50%{opacity:0}}
  .typed-hide{visibility:hidden}

  /* ---------- section head ---------- */
  .head{margin-bottom:48px}
  .head .tag{font-size:12.5px;color:var(--dim);display:block;margin-bottom:10px}
  .head .tag .amber{color:var(--amber)}
  .head h2{font-size:clamp(24px,3vw,32px);font-weight:700;letter-spacing:-.01em;margin:0;color:var(--text)}

  /* ---------- about ---------- */
  .about-grid{display:grid;grid-template-columns:1.35fr .65fr;gap:64px}
  .about-main p{color:var(--muted);font-size:15px;max-width:60ch}
  .about-main p.lead{color:var(--text);font-size:16.5px;line-height:1.8}
  .about-main strong{color:var(--text);font-weight:600}
  .whois{border:1px solid var(--line);border-radius:var(--radius);background:var(--panel);align-self:start}
  .whois-head{font-size:12px;color:var(--dim);padding:12px 16px;border-bottom:1px solid var(--line-soft)}
  .whois-head span{color:var(--amber)}
  .whois-row{display:flex;justify-content:space-between;gap:16px;padding:12px 16px;font-size:12.5px;border-bottom:1px solid var(--line-soft)}
  .whois-row:last-child{border-bottom:none}
  .whois-row .k{color:var(--dim)}
  .whois-row .v{color:var(--text);text-align:right}

  /* ---------- skills table ---------- */
  .skill-table{border-top:1px solid var(--line)}
  .skill-row{
    display:grid;grid-template-columns:26px 1fr auto;gap:18px;align-items:start;
    padding:22px 0;border-bottom:1px solid var(--line-soft);
  }
  .skill-row .idx{color:var(--dim);font-size:12.5px;padding-top:3px}
  .skill-row h3{margin:0 0 6px;font-size:16px;font-weight:600;color:var(--text)}
  .skill-row p{margin:0 0 10px;color:var(--muted);font-size:13.5px;max-width:60ch}
  .stack{display:flex;flex-wrap:wrap;gap:6px}
  .stack span{font-size:11px;color:var(--dim);border:1px solid var(--line);border-radius:3px;padding:3px 7px}
  .status{
    font-size:11.5px;white-space:nowrap;padding-top:3px;text-align:right;
    display:flex;align-items:center;gap:7px;justify-content:flex-end;color:var(--muted);
  }
  .status i{width:6px;height:6px;border-radius:50%;background:var(--dim);flex-shrink:0}
  .status.on i{background:var(--amber);box-shadow:0 0 0 3px var(--amber-soft)}
  .status.on{color:var(--amber)}

  /* ---------- journey / traceroute ---------- */
  .trace-cmd{font-size:13px;color:var(--dim);margin-bottom:8px}
  .trace-cmd .amber{color:var(--amber)}
  .trace{position:relative;margin-top:28px}
  .trace::before{content:"";position:absolute;left:15px;top:6px;bottom:6px;width:1px;background:var(--line)}
  .hop{position:relative;display:grid;grid-template-columns:32px 1fr auto;gap:18px;align-items:start;padding:18px 0}
  .hop .n{width:32px;height:32px;border-radius:50%;background:var(--panel-2);border:1px solid var(--line);display:grid;place-items:center;font-size:11.5px;color:var(--dim);position:relative;z-index:1}
  .hop.done .n{border-color:var(--amber-line);color:var(--amber)}
  .hop h3{margin:0 0 4px;font-size:15px;font-weight:600;color:var(--text)}
  .hop p{margin:0;color:var(--muted);font-size:13px}
  .hop .flag{font-size:11px;color:var(--dim);padding-top:2px;white-space:nowrap}
  .hop.done .flag{color:var(--amber)}

  /* ---------- projects ---------- */
  .repo-list{display:flex;flex-direction:column;gap:1px;background:var(--line-soft);border:1px solid var(--line-soft);border-radius:var(--radius);overflow:hidden}
  .repo{background:var(--panel);padding:22px 22px;display:grid;grid-template-columns:1fr auto;gap:16px;align-items:start}
  .repo-name{font-size:15px;font-weight:600;color:var(--text);margin:0 0 6px;display:flex;align-items:center;gap:8px}
  .repo-name .lang{width:8px;height:8px;border-radius:50%;background:var(--amber)}
  .repo-tag{font-size:11px;color:var(--dim)}
  .repo p.desc{margin:8px 0 0;color:var(--muted);font-size:13.5px;max-width:62ch}
  .repo-status{font-size:11.5px;color:var(--muted);white-space:nowrap;border:1px solid var(--line);padding:5px 10px;border-radius:3px}

  /* ---------- now / status ---------- */
  .status-panel{border:1px solid var(--line);border-radius:8px;background:var(--panel);padding:36px;display:grid;grid-template-columns:1fr 1fr;gap:40px;align-items:center}
  .status-panel h2{font-size:clamp(20px,2.6vw,28px);margin:0 0 8px;font-weight:700}
  .status-panel .tag{font-size:12.5px;color:var(--dim);display:block;margin-bottom:10px}
  .now-list{border-top:1px solid var(--line-soft)}
  .now-item{display:flex;justify-content:space-between;align-items:center;padding:12px 0;border-bottom:1px solid var(--line-soft);font-size:13px}
  .now-item .name{color:var(--text)}
  .now-item .flag{font-size:11px;color:var(--dim)}
  .now-item.active .flag{color:var(--amber)}

  /* ---------- vision ---------- */
  .vision{text-align:left;padding-top:80px;padding-bottom:80px}
  .vision blockquote{margin:0;font-size:clamp(21px,2.8vw,30px);font-weight:600;line-height:1.5;color:var(--text);letter-spacing:-.01em;max-width:26ch}
  .vision cite{display:block;margin-top:20px;font-style:normal;font-size:13px;color:var(--dim)}

  /* ---------- contact ---------- */
  .contact-card{border:1px solid var(--line);border-radius:8px;background:var(--panel);padding:52px;display:flex;justify-content:space-between;align-items:flex-end;gap:40px;flex-wrap:wrap}
  .contact-card h2{font-size:clamp(26px,3.6vw,38px);margin:0 0 14px;font-weight:700}
  .contact-card p{color:var(--muted);font-size:14px;max-width:44ch;margin:0}
  .contact-actions{display:flex;flex-direction:column;gap:8px;min-width:200px}
  .contact-btn{border:1px solid var(--line);border-radius:var(--radius);padding:13px 16px;font-size:13px;display:flex;justify-content:space-between}
  .contact-btn:first-child{background:var(--amber);color:#151005;border-color:var(--amber);font-weight:600}
  .contact-btn:not(:first-child):hover{border-color:var(--amber-line);color:var(--amber)}

  footer{border-top:1px solid var(--line-soft);max-width:var(--max);margin:0 auto;padding:28px 24px;display:flex;justify-content:space-between;gap:14px;flex-wrap:wrap;font-size:12px;color:var(--dim)}

  @media(prefers-reduced-motion:reduce){html{scroll-behavior:auto}.caret{animation:none;opacity:1}}

  @media(max-width:820px){
    .nav-links{display:none}
    .nav-toggle{display:inline-block}
    .hero{grid-template-columns:1fr;padding-top:44px}
    .terminal{order:-1}
    .about-grid,.status-panel{grid-template-columns:1fr}
    .contact-card{flex-direction:column;align-items:flex-start}
  }
  @media(max-width:560px){
    .section{padding:72px 20px}
    .stat-row{flex-wrap:wrap;row-gap:16px}
    .skill-row{grid-template-columns:22px 1fr}
    .status{grid-column:1 / -1;justify-content:flex-start;padding-left:40px}
    .hop{grid-template-columns:28px 1fr}
    .hop .flag{grid-column:1 / -1;padding-left:44px}
    .repo{grid-template-columns:1fr}
  }
</style>
</head>
<body>

  <header class="nav">
    <div class="nav-inner">
      <a class="brand" href="#top"><span class="prompt">~/</span>emad-yad</a>
      <nav class="nav-links">
        <a href="#about">./about</a>
        <a href="#skills">./skills</a>
        <a href="#journey">./journey</a>
        <a href="#projects">./projects</a>
        <a href="#contact" class="connect-btn">connect</a>
      </nav>
      <button class="nav-toggle" id="navToggle" aria-label="Toggle menu" aria-expanded="false">≡</button>
    </div>
    <nav class="nav-mobile" id="navMobile">
      <a href="#about">./about</a>
      <a href="#skills">./skills</a>
      <a href="#journey">./journey</a>
      <a href="#projects">./projects</a>
      <a href="#contact">./connect</a>
    </nav>
  </header>

  <main id="top">
    <section class="section hero">
      <div>
        <div class="prompt-line"><span class="amber">$</span> whoami --intro</div>
        <h1>I learn systems by taking them apart, then building them back better.</h1>
        <p class="hero-lede">
          I'm <strong>Emad Yad</strong>, 17, working toward a career across
          <strong>cloud, DevOps, cybersecurity and AI infrastructure</strong> —
          starting from the fundamentals: Linux, networking and Python.
        </p>
        <div class="hero-actions">
          <a class="btn primary" href="#projects">See what I'm building</a>
          <a class="btn ghost" href="#about">About me</a>
        </div>
        <div class="stat-row">
          <div class="stat"><b>17</b><span>years old</span></div>
          <div class="stat"><b>Network+</b><span>certified</span></div>
          <div class="stat"><b>CCNA</b><span>in progress</span></div>
        </div>
      </div>

      <div class="terminal" aria-hidden="true">
        <div class="terminal-bar">
          <span class="dot"></span><span class="dot"></span><span class="dot"></span>
          <span class="title">emad@yad — zsh</span>
        </div>
        <div class="terminal-body" id="termBody"></div>
      </div>
    </section>

    <section id="about" class="section">
      <div class="head">
        <span class="tag"><span class="amber">$</span> cat about.md</span>
        <h2>More than a résumé</h2>
      </div>
      <div class="about-grid">
        <div class="about-main">
          <p class="lead">
            I enjoy understanding how systems actually work — from packets moving
            across a network to the pipelines that ship code into production.
          </p>
          <p>
            My process is the same every time: learn the fundamentals, build
            something small, break it on purpose, understand why it broke, fix it,
            and move on to the next layer. Right now that means Linux, Python and
            networking. Next comes cloud and automation.
          </p>
          <p>
            I'm especially interested in where infrastructure, security and AI
            meet — and I want to build skills that hold up internationally, not
            just in one market.
          </p>
        </div>
        <aside class="whois">
          <div class="whois-head"><span>$</span> whois emad-yad</div>
          <div class="whois-row"><span class="k">name</span><span class="v">Emad Yad</span></div>
          <div class="whois-row"><span class="k">role</span><span class="v">Technology learner &amp; builder</span></div>
          <div class="whois-row"><span class="k">language</span><span class="v">Python</span></div>
          <div class="whois-row"><span class="k">also writes</span><span class="v">C#</span></div>
          <div class="whois-row"><span class="k">networking</span><span class="v">Network+, CCNA</span></div>
          <div class="whois-row"><span class="k">design</span><span class="v">Illustrator</span></div>
          <div class="whois-row"><span class="k">status</span><span class="v">available to connect</span></div>
        </aside>
      </div>
    </section>

    <section id="skills" class="section">
      <div class="head">
        <span class="tag"><span class="amber">$</span> ls -l ./skills</span>
        <h2>Skills &amp; direction</h2>
      </div>
      <div class="skill-table">
        <div class="skill-row">
          <span class="idx">01</span>
          <div>
            <h3>Cloud &amp; infrastructure</h3>
            <p>Learning how modern infrastructure is designed, deployed, automated and operated.</p>
            <div class="stack"><span>Linux</span><span>Cloud</span><span>Docker</span><span>Terraform</span></div>
          </div>
          <div class="status on"><i></i>building</div>
        </div>
        <div class="skill-row">
          <span class="idx">02</span>
          <div>
            <h3>Cybersecurity</h3>
            <p>Developing a systems-first security mindset around networks, Linux and identity.</p>
            <div class="stack"><span>Networking</span><span>Linux</span><span>Security</span></div>
          </div>
          <div class="status on"><i></i>building</div>
        </div>
        <div class="skill-row">
          <span class="idx">03</span>
          <div>
            <h3>Programming</h3>
            <p>Python is my main language for automation, tooling and future infrastructure work.</p>
            <div class="stack"><span>Python</span><span>C#</span><span>Automation</span></div>
          </div>
          <div class="status on"><i></i>active</div>
        </div>
        <div class="skill-row">
          <span class="idx">04</span>
          <div>
            <h3>Networking</h3>
            <p>Building strong fundamentals, working through CCNA concepts after Network+.</p>
            <div class="stack"><span>Network+</span><span>CCNA</span><span>DNS</span><span>ICMP</span></div>
          </div>
          <div class="status"><i></i>foundation</div>
        </div>
        <div class="skill-row">
          <span class="idx">05</span>
          <div>
            <h3>Visual design</h3>
            <p>Practical experience with Adobe Illustrator and an eye for polished visual systems.</p>
            <div class="stack"><span>Illustrator</span><span>Branding</span><span>UI</span></div>
          </div>
          <div class="status"><i></i>experienced</div>
        </div>
        <div class="skill-row">
          <span class="idx">06</span>
          <div>
            <h3>AI infrastructure</h3>
            <p>Long-term direction: connecting cloud, automation and infrastructure with ML systems.</p>
            <div class="stack"><span>AI</span><span>ML</span><span>MLOps</span></div>
          </div>
          <div class="status"><i></i>exploring</div>
        </div>
      </div>
    </section>

    <section id="journey" class="section">
      <div class="head">
        <span class="tag"><span class="amber">$</span> traceroute career</span>
        <h2>From fundamentals to systems</h2>
      </div>
      <div class="trace">
        <div class="hop done">
          <span class="n">1</span>
          <div><h3>Programming</h3><p>Python, C#, automation</p></div>
          <span class="flag">active</span>
        </div>
        <div class="hop done">
          <span class="n">2</span>
          <div><h3>Networking</h3><p>Network+, CCNA, protocols</p></div>
          <span class="flag">active</span>
        </div>
        <div class="hop done">
          <span class="n">3</span>
          <div><h3>Linux</h3><p>Systems, CLI, administration</p></div>
          <span class="flag">active</span>
        </div>
        <div class="hop">
          <span class="n">4</span>
          <div><h3>Cloud &amp; DevOps</h3><p>Docker, CI/CD, Terraform, Kubernetes</p></div>
          <span class="flag">next</span>
        </div>
        <div class="hop">
          <span class="n">5</span>
          <div><h3>Security</h3><p>Cloud security, IAM, DevSecOps</p></div>
          <span class="flag">queued</span>
        </div>
        <div class="hop">
          <span class="n">6</span>
          <div><h3>AI infrastructure</h3><p>MLOps, AI systems, scalable infrastructure</p></div>
          <span class="flag">queued</span>
        </div>
      </div>
    </section>

    <section id="projects" class="section">
      <div class="head">
        <span class="tag"><span class="amber">$</span> ls -l ./projects</span>
        <h2>Things I'm building</h2>
      </div>
      <div class="repo-list">
        <div class="repo">
          <div>
            <p class="repo-name"><span class="lang"></span>file-manager <span class="repo-tag">python · cli</span></p>
            <p class="desc">A practical terminal tool for creating, reading, writing, listing and deleting files — built to strengthen Python fundamentals.</p>
          </div>
          <span class="repo-status">in progress</span>
        </div>
        <div class="repo">
          <div>
            <p class="repo-name"><span class="lang"></span>network-lab <span class="repo-tag">networking</span></p>
            <p class="desc">Hands-on experiments with IP addressing, DNS, ICMP, TTL and core network concepts.</p>
          </div>
          <span class="repo-status">learning</span>
        </div>
        <div class="repo">
          <div>
            <p class="repo-name"><span class="lang"></span>linux-lab <span class="repo-tag">linux · systems</span></p>
            <p class="desc">A personal lab for the command line, system administration, permissions, processes and services.</p>
          </div>
          <span class="repo-status">building</span>
        </div>
      </div>
    </section>

    <section class="section">
      <div class="status-panel">
        <div>
          <span class="tag"><span class="amber">$</span> uptime --learning</span>
          <h2>One skill at a time.</h2>
        </div>
        <div class="now-list">
          <div class="now-item active"><span class="name">Linux</span><span class="flag">active</span></div>
          <div class="now-item active"><span class="name">Python</span><span class="flag">active</span></div>
          <div class="now-item active"><span class="name">CCNA</span><span class="flag">active</span></div>
          <div class="now-item"><span class="name">Cloud / DevOps</span><span class="flag">next</span></div>
        </div>
      </div>
    </section>

    <section class="section vision">
      <blockquote>
        “Build skills that stay valuable even when the tools change.”
        <cite>Fundamentals first. Systems thinking second. Tools last.</cite>
      </blockquote>
    </section>

    <section id="contact" class="section">
      <div class="contact-card">
        <div>
          <span class="tag" style="margin-bottom:14px"><span class="amber">$</span> connect --to emad</span>
          <h2>Have an idea? Let's build.</h2>
          <p>I'm always interested in technology, projects, learning and building useful things.</p>
        </div>
        <div class="contact-actions">
          <a class="contact-btn" href="https://github.com/EmadYad" target="_blank" rel="noopener">GitHub</a>
          <a class="contact-btn" href="#top">Back to top</a>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <span>© 2026 Emad Yad</span>
    <span>Built with curiosity. Tested in production.</span>
  </footer>

  <script>
    // mobile nav toggle
    var navToggle = document.getElementById('navToggle');
    var navMobile = document.getElementById('navMobile');
    navToggle.addEventListener('click', function () {
      var open = navMobile.classList.toggle('open');
      navToggle.setAttribute('aria-expanded', open);
    });
    navMobile.querySelectorAll('a').forEach(function (a) {
      a.addEventListener('click', function () {
        navMobile.classList.remove('open');
        navToggle.setAttribute('aria-expanded', 'false');
      });
    });

    // smooth anchor scroll
    document.querySelectorAll('a[href^="#"]').forEach(function (link) {
      link.addEventListener('click', function (e) {
        var target = document.querySelector(link.getAttribute('href'));
        if (target) {
          e.preventDefault();
          target.scrollIntoView({ behavior: 'smooth', block: 'start' });
        }
      });
    });

    // one orchestrated hero terminal typing sequence
    (function () {
      var body = document.getElementById('termBody');
      var reduceMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

      var lines = [
        { type: 'cmd', text: 'whoami' },
        { type: 'out', text: 'emad_yad — technology learner &amp; builder' },
        { type: 'cmd', text: 'cat status.txt' },
        { type: 'out', text: 'learning: linux, python, networking (ccna)<br>shipping: small tools, network labs, this site' },
        { type: 'cmd', text: 'echo $GOAL' },
        { type: 'out', text: 'cloud + devops + security + ai infrastructure' }
      ];

      function render(full) {
        body.innerHTML = '';
        lines.forEach(function (l) {
          var row = document.createElement('div');
          if (l.type === 'cmd') {
            row.className = 'row';
            row.innerHTML = '<span class="sym">$</span><span>' + l.text + '</span>';
          } else {
            row.className = 'out';
            row.innerHTML = l.text;
          }
          body.appendChild(row);
        });
        var caret = document.createElement('span');
        caret.className = 'caret';
        body.appendChild(caret);
      }

      if (reduceMotion) {
        render(true);
        return;
      }

      var i = 0;
      function typeNext() {
        if (i >= lines.length) return;
        var l = lines[i];
        var row = document.createElement('div');
        row.className = l.type === 'cmd' ? 'row' : 'out';
        if (l.type === 'cmd') {
          row.innerHTML = '<span class="sym">$</span><span class="txt"></span><span class="caret"></span>';
        } else {
          row.innerHTML = '<span class="txt"></span>';
        }
        body.appendChild(row);
        var txtEl = row.querySelector('.txt');
        var caretEl = row.querySelector('.caret');
        var plain = l.text.replace(/<br>/g, '\n');
        var chars = plain.split('');
        var idx = 0;
        var speed = l.type === 'cmd' ? 32 : 6;
        (function step() {
          if (idx < chars.length) {
            txtEl.innerHTML += chars[idx] === '\n' ? '<br>' : chars[idx];
            idx++;
            setTimeout(step, speed);
          } else {
            if (caretEl) caretEl.remove();
            i++;
            setTimeout(typeNext, l.type === 'cmd' ? 260 : 380);
          }
        })();
      }
      typeNext();
    })();
  </script>
</body>
</html>
