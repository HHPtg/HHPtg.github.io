<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1"/>
  <title>Hanif Patel | Networking & Systems Portfolio</title>
  <meta name="description" content="Hanif Patel — IT Systems Student / Junior Software Developer. CCNA-level networking, cloud deployment, CI/CD, incident response, and hands-on projects."/>
  <style>
    :root{
      --bg:#060a12;
      --panel:rgba(255,255,255,.06);
      --panel2:rgba(255,255,255,.10);
      --text:#eaf2ff;
      --muted:#a8b3c7;
      --accent:#56d4ff;
      --accent2:#b7ff5a;
      --danger:#ff4d6d;
      --warn:#ffd166;
      --ok:#2ee59d;
      --border:rgba(255,255,255,.14);
      --shadow: 0 18px 60px rgba(0,0,0,.55);
      --radius: 18px;
      --mono: ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, "Liberation Mono", "Courier New", monospace;
      --sans: ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family:var(--sans);
      color:var(--text);
      background:
        radial-gradient(1000px 600px at 15% 10%, rgba(86,212,255,.20), transparent 55%),
        radial-gradient(900px 700px at 85% 25%, rgba(183,255,90,.12), transparent 60%),
        radial-gradient(900px 700px at 50% 100%, rgba(255,77,109,.10), transparent 55%),
        linear-gradient(180deg, #040611, #070b14 55%, #050812);
      overflow-x:hidden;
    }

    /* Subtle moving grid */
    .grid{
      position:fixed; inset:0;
      background-image:
        linear-gradient(rgba(255,255,255,.05) 1px, transparent 1px),
        linear-gradient(90deg, rgba(255,255,255,.05) 1px, transparent 1px);
      background-size: 48px 48px;
      mask-image: radial-gradient(600px 420px at 50% 0%, rgba(0,0,0,1), transparent 70%);
      opacity:.35;
      pointer-events:none;
      animation:gridFloat 18s linear infinite;
    }
    @keyframes gridFloat{
      0%{transform:translateY(0)}
      100%{transform:translateY(48px)}
    }

    /* Top nav */
    .topbar{
      position:sticky; top:0; z-index:50;
      backdrop-filter: blur(14px);
      background: rgba(6,10,18,.55);
      border-bottom:1px solid rgba(255,255,255,.10);
    }
    .wrap{max-width:1150px; margin:0 auto; padding:0 18px;}
    .nav{
      display:flex; align-items:center; justify-content:space-between;
      padding:14px 0;
      gap:14px;
    }
    .brand{
      display:flex; align-items:center; gap:12px; min-width:260px;
      text-decoration:none; color:var(--text);
    }
    .logo{
      width:44px; height:44px; border-radius:12px;
      background:
        radial-gradient(circle at 30% 30%, rgba(86,212,255,.95), rgba(86,212,255,.08) 58%),
        radial-gradient(circle at 75% 80%, rgba(183,255,90,.85), rgba(183,255,90,.08) 62%),
        rgba(255,255,255,.06);
      border:1px solid rgba(255,255,255,.18);
      box-shadow: 0 10px 30px rgba(0,0,0,.35);
      position:relative;
    }
    .logo:after{
      content:"";
      position:absolute; inset:9px;
      border-radius:10px;
      border:1px dashed rgba(255,255,255,.18);
      opacity:.85;
    }
    .brand h1{font-size:14px; margin:0; letter-spacing:.3px;}
    .brand p{margin:2px 0 0; font-size:12px; color:var(--muted);}
    .navlinks{
      display:flex; flex-wrap:wrap; gap:10px;
      justify-content:flex-end;
    }
    .navlinks a{
      font-size:12px;
      padding:8px 10px;
      border-radius:12px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      color:var(--text);
      text-decoration:none;
      transition:.18s transform, .18s background, .18s border-color;
      white-space:nowrap;
    }
    .navlinks a:hover{
      transform: translateY(-1px);
      background: rgba(255,255,255,.07);
      border-color: rgba(86,212,255,.35);
    }
    .navtools{
      display:flex; align-items:center; gap:10px;
    }
    .pill{
      font-family:var(--mono);
      font-size:11px;
      padding:8px 10px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.20);
      color: rgba(234,242,255,.92);
      display:flex; align-items:center; gap:8px;
    }
    .dot{
      width:8px; height:8px; border-radius:50%;
      background: var(--ok);
      box-shadow: 0 0 0 3px rgba(46,229,157,.18);
      animation: pulse 1.9s ease-in-out infinite;
    }
    @keyframes pulse{
      0%,100%{transform:scale(1); opacity:1}
      50%{transform:scale(1.12); opacity:.75}
    }
    .btn{
      cursor:pointer;
      border:none;
      border-radius:14px;
      padding:10px 12px;
      background: linear-gradient(135deg, rgba(86,212,255,.22), rgba(183,255,90,.10));
      border:1px solid rgba(86,212,255,.28);
      color:var(--text);
      font-size:12px;
      display:flex; align-items:center; gap:10px;
      transition:.18s transform, .18s filter;
      box-shadow: 0 10px 30px rgba(0,0,0,.22);
    }
    .btn:hover{transform:translateY(-1px); filter:brightness(1.05)}
    .btn:active{transform:translateY(0px); filter:brightness(.98)}
    .btn small{color:rgba(234,242,255,.72); font-family:var(--mono)}

    /* Hero */
    header.hero{
      padding:28px 0 14px;
      position:relative;
    }
    .heroGrid{
      display:grid;
      grid-template-columns: 1.35fr .95fr;
      gap:18px;
      align-items:stretch;
    }
    @media (max-width: 980px){
      .heroGrid{grid-template-columns:1fr}
      .brand{min-width:auto}
      .nav{flex-wrap:wrap}
      .navlinks{justify-content:flex-start}
    }
    .card{
      background: rgba(255,255,255,.06);
      border: 1px solid rgba(255,255,255,.12);
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      overflow:hidden;
      position:relative;
    }
    .card .inner{padding:18px}
    .heroLeft{
      padding:18px 18px 14px;
      overflow:hidden;
    }
    .kicker{
      display:flex; flex-wrap:wrap; gap:10px;
      align-items:center;
      margin-bottom:10px;
    }
    .tag{
      font-family:var(--mono);
      font-size:11px;
      padding:7px 10px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.18);
      color: rgba(234,242,255,.90);
    }
    .tag strong{color:var(--accent)}
    .title{
      margin:10px 0 8px;
      font-size:34px;
      line-height:1.05;
      letter-spacing:-.5px;
    }
    .subtitle{
      margin:0 0 14px;
      color: var(--muted);
      font-size:14px;
      line-height:1.5;
      max-width: 68ch;
    }
    .heroActions{
      display:flex; flex-wrap:wrap; gap:10px;
      margin-top: 14px;
      align-items:center;
    }
    .ghost{
      cursor:pointer;
      font-size:12px;
      padding:10px 12px;
      border-radius:14px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(255,255,255,.04);
      color: var(--text);
      text-decoration:none;
      display:inline-flex; align-items:center; gap:10px;
      transition:.18s transform, .18s background, .18s border-color;
    }
    .ghost:hover{transform:translateY(-1px); background: rgba(255,255,255,.07); border-color:rgba(183,255,90,.32)}
    .ghost small{font-family:var(--mono); color:rgba(234,242,255,.7)}
    .metrics{
      display:grid;
      grid-template-columns: repeat(3, 1fr);
      gap:10px;
      margin-top:14px;
    }
    @media (max-width:520px){
      .metrics{grid-template-columns:1fr}
      .title{font-size:30px}
    }
    .metric{
      padding:12px;
      border-radius:16px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.16);
    }
    .metric b{
      display:block;
      font-size:16px;
      letter-spacing:-.2px;
    }
    .metric span{
      display:block;
      margin-top:6px;
      font-size:12px;
      color:var(--muted);
      font-family:var(--mono);
      line-height:1.25;
    }

    /* Right panel: Network canvas + terminal */
    .heroRight{
      display:grid;
      grid-template-rows: 240px auto;
      gap:12px;
      padding:12px;
    }
    .viz{
      border-radius:16px;
      border:1px solid rgba(255,255,255,.12);
      background: radial-gradient(400px 220px at 15% 20%, rgba(86,212,255,.18), transparent 60%),
                  radial-gradient(380px 260px at 85% 60%, rgba(183,255,90,.12), transparent 60%),
                  rgba(0,0,0,.22);
      overflow:hidden;
      position:relative;
    }
    canvas{display:block; width:100%; height:100%}
    .vizHud{
      position:absolute; left:12px; right:12px; top:12px;
      display:flex; flex-wrap:wrap; justify-content:space-between; gap:8px;
      pointer-events:none;
    }
    .hudLeft, .hudRight{display:flex; gap:8px; flex-wrap:wrap}
    .hudChip{
      pointer-events:none;
      font-family:var(--mono);
      font-size:11px;
      padding:7px 10px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.25);
      color: rgba(234,242,255,.92);
      backdrop-filter: blur(8px);
    }
    .hudChip em{font-style:normal; color:var(--accent2)}
    .hudChip i{font-style:normal; color:var(--accent)}
    .terminal{
      border-radius:16px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.28);
      overflow:hidden;
    }
    .termTop{
      display:flex; justify-content:space-between; align-items:center;
      padding:10px 12px;
      border-bottom:1px solid rgba(255,255,255,.10);
      background: rgba(255,255,255,.04);
    }
    .termTop .dots{
      display:flex; gap:7px; align-items:center;
    }
    .termTop .dots span{
      width:10px; height:10px; border-radius:50%;
      display:inline-block;
      opacity:.9;
    }
    .termTop .dots span:nth-child(1){background: var(--danger)}
    .termTop .dots span:nth-child(2){background: var(--warn)}
    .termTop .dots span:nth-child(3){background: var(--ok)}
    .termTop .label{
      font-family:var(--mono);
      font-size:11px;
      color: rgba(234,242,255,.82);
    }
 .termBody{
  padding:12px;
  font-family:var(--mono);
  font-size:12px;
  line-height:1.45;
  color: rgba(234,242,255,.88);
  min-height:140px;
  height:160px;
  overflow:auto;
  white-space:pre-wrap;
}

    .caret{
      display:inline-block;
      width:8px; height:14px;
      border-bottom:2px solid rgba(234,242,255,.88);
      margin-left:2px;
      transform: translateY(2px);
      animation:blink 1.05s steps(2, end) infinite;
    }
    @keyframes blink{50%{opacity:0}}

    /* Section layout */
    section{padding:16px 0}
    .sectionTitle{
      display:flex; align-items:flex-end; justify-content:space-between;
      gap:14px;
      margin: 8px 0 12px;
    }
    .sectionTitle h2{
      margin:0;
      font-size:16px;
      letter-spacing:.2px;
    }
    .sectionTitle p{
      margin:0;
      color:var(--muted);
      font-size:12px;
      font-family:var(--mono);
    }
    .grid2{
      display:grid;
      grid-template-columns: 1fr 1fr;
      gap:14px;
    }
    @media (max-width: 900px){
      .grid2{grid-template-columns:1fr}
    }
    .list{
      display:flex; flex-direction:column; gap:10px;
    }
    .item{
      padding:14px;
      border-radius:16px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.05);
      position:relative;
      overflow:hidden;
    }
    .item:before{
      content:"";
      position:absolute; inset:-2px;
      background: radial-gradient(420px 200px at 10% 20%, rgba(86,212,255,.14), transparent 60%),
                  radial-gradient(420px 240px at 90% 60%, rgba(183,255,90,.08), transparent 65%);
      opacity:.55;
      pointer-events:none;
    }
    .item > *{position:relative}
    .item h3{
      margin:0 0 6px;
      font-size:14px;
      letter-spacing:.2px;
    }
    .meta{
      display:flex; flex-wrap:wrap; gap:10px;
      color:rgba(234,242,255,.70);
      font-size:12px;
      font-family:var(--mono);
      margin-bottom:8px;
    }
    .meta span{opacity:.95}
    .meta .sep{opacity:.35}
    .bullets{margin:0; padding-left:18px; color:var(--muted); font-size:13px}
    .bullets li{margin:6px 0}
    .chips{
      display:flex; flex-wrap:wrap; gap:8px; margin-top:10px;
    }
    .chip{
      font-family:var(--mono);
      font-size:11px;
      padding:7px 10px;
      border-radius:999px;
      border:1px solid rgba(255,255,255,.14);
      background: rgba(0,0,0,.18);
      color: rgba(234,242,255,.88);
    }
    .chip.accent{border-color: rgba(86,212,255,.34); color:rgba(86,212,255,.95)}
    .chip.green{border-color: rgba(183,255,90,.28); color:rgba(183,255,90,.95)}
    .chip.dim{opacity:.85}

    /* Skills panel */
    .skillGrid{
      display:grid;
      grid-template-columns: 1fr;
      gap:10px;
    }
    .skillRow{
      display:grid;
      grid-template-columns: 150px 1fr;
      gap:12px;
      align-items:center;
      padding:12px;
      border-radius:16px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(0,0,0,.18);
    }
    @media (max-width: 560px){
      .skillRow{grid-template-columns:1fr}
    }
    .skillRow b{
      font-size:12px;
      font-family:var(--mono);
      color: rgba(234,242,255,.92);
    }
    .bar{
      height:10px;
      border-radius:999px;
      background: rgba(255,255,255,.08);
      border: 1px solid rgba(255,255,255,.10);
      overflow:hidden;
      position:relative;
    }
    .fill{
      height:100%;
      width: 50%;
      border-radius:999px;
      background: linear-gradient(90deg, rgba(86,212,255,.85), rgba(183,255,90,.85));
      filter: drop-shadow(0 10px 18px rgba(0,0,0,.3));
    }
    .skillNote{
      margin-top:10px;
      color:var(--muted);
      font-size:12px;
      line-height:1.45;
    }

    /* Footer */
    footer{
      padding:26px 0 40px;
      color: rgba(234,242,255,.70);
      font-size:12px;
      font-family:var(--mono);
    }
    .footerCard{
      padding:16px;
      border-radius:18px;
      border:1px solid rgba(255,255,255,.12);
      background: rgba(255,255,255,.04);
      display:flex;
      flex-wrap:wrap;
      gap:12px;
      align-items:center;
      justify-content:space-between;
    }
    .footerCard a{color:rgba(86,212,255,.95); text-decoration:none}
    .footerCard a:hover{text-decoration:underline}

    /* Print */
    @media print{
      .topbar, .grid, .viz, .btn, .ghost{display:none !important}
      body{background:#fff; color:#111}
      .card, .item, .skillRow, .footerCard{box-shadow:none}
    }
  </style>
</head>
<body>
  <div class="grid" aria-hidden="true"></div>

  <div class="topbar">
    <div class="wrap">
      <div class="nav">
        <a class="brand" href="#top" aria-label="Home">
          <div class="logo" aria-hidden="true"></div>
          <div>
            <h1>Hanif Patel</h1>
            <p>Networking • Cloud • CI/CD • Incident Response</p>
          </div>
        </a>

        <div class="navlinks" role="navigation" aria-label="Site navigation">
          <a href="#about">About</a>
          <a href="#skills">Skills</a>
          <a href="#certs">Certifications</a>
          <a href="#experience">Experience</a>
          <a href="#projects">Projects</a>
          <a href="#leadership">Leadership</a>
          <a href="#contact">Contact</a>
        </div>

        <div class="navtools">
          <div class="pill" title="Network status (simulated)">
            <span class="dot" aria-hidden="true"></span>
            <span>Link: <span id="linkState">UP</span></span>
  
      </div>
    </div>
  </div>

  <main id="top">
    <header class="hero">
      <div class="wrap">
        <div class="heroGrid">
          <div class="card heroLeft">
            <div class="kicker">
              <span class="tag">Role: <strong>Junior Software Developer</strong> / IT Systems Student</span>
              <span class="tag">Focus: <strong>CCNA-level Networking</strong> + Cloud Deployments</span>
              <span class="tag">Ops: <strong>CI/CD</strong> + Incident/Problem Solving</span>
            </div>

            <h2 class="title">Building reliable networks — and the software that runs on them.</h2>
            <p class="subtitle">
              I’m an IT Systems student based in Toronto, Ontario with hands-on experience in Python development,
              cloud security basics, Docker deployments, CI/CD pipelines, and CCNA-level routing & switching.
              I like projects where networking and automation meet: monitoring, deployment, reliability, and secure access.
            </p>

            <div class="heroActions">
              <a class="ghost" href="#projects">View Projects <small>→</small></a>
              <a class="ghost" href="#experience">Experience <small>→</small></a>
              <a class="ghost" href="#contact">Contact <small>→</small></a>
              <a class="ghost" href="resume.pdf" target="_blank" title="Open resume as PDF" >
                Export Resume Snapshot <small>PDF</small>
              </a>
            </div>

            <div class="metrics">
              <div class="metric">
                <b>3.6 GPA</b>
                <span>George Brown College • Dean’s List</span>
              </div>
              <div class="metric">
                <b>300+ students</b>
                <span>Computer Science Club founding team</span>
              </div>
              <div class="metric">
                <b>+17% engagement</b>
                <span>Club participation growth (each semester)</span>
              </div>
            </div>
          </div>

          <div class="card heroRight">
            <div class="viz">
              <div class="vizHud">
                <div class="hudLeft">
                  <span class="hudChip">AS: <em>64512</em></span>
                  <span class="hudChip">VLAN: <i id="vlanChip">10</i></span>
                  <span class="hudChip">QoS: <em>EF</em></span>
                </div>
                <div class="hudRight">
                  <span class="hudChip">Packets: <em id="pktCount">0</em></span>
                  <span class="hudChip">Latency: <em id="latency">12ms</em></span>
                </div>
              </div>
              <canvas id="netCanvas" aria-label="Animated network topology visualization"></canvas>
            </div>

            <div class="terminal" aria-label="Terminal simulation">
              <div class="termTop">
                <div class="dots" aria-hidden="true"><span></span><span></span><span></span></div>
                <div class="label">ssh hanif@lab-router • <span id="termMode">show</span> mode</div>
              </div>
              <div class="termBody" id="termBody"></div>
            </div>
          </div>
        </div>
      </div>
    </header>

    <section id="about">
      <div class="wrap">
        <div class="sectionTitle">
          <h2>About</h2>
        </div>
        <div class="grid2">
          <div class="item">
            <h3>Snapshot</h3>
            <ul class="bullets">
              <li>IT Systems student (Expected Graduation: <b>June 2026</b>) at <b>George Brown College</b>.</li>
              <li>Hands-on with <b>Python</b>, <b>Docker</b>, <b>CI/CD</b> (GitHub Actions/Jenkins), and cloud basics (AWS IAM/S3, ACLs).</li>
              <li>Comfortable with <b>CCNA-level routing & switching</b>, network design, Packet Tracer labs, and troubleshooting.</li>
              <li>Enjoys combining <b>automation</b> + <b>network operations</b> for faster, safer deployments.</li>
            </ul>
            <div class="chips">
              <span class="chip accent">Networking</span>
              <span class="chip">Linux</span>
              <span class="chip">Windows Server</span>
              <span class="chip">Virtualization</span>
              <span class="chip green">AWS</span>
              <span class="chip">SIEM Fundamentals</span>
              <span class="chip">Incident Response</span>
            </div>
          </div>

          <div class="item">
            <h3>What I build</h3>
            <ul class="bullets">
              <li><b>Reliable services</b> with deployment pipelines and containerization.</li>
              <li><b>Network designs</b> for SOHO and enterprise scenarios, aligned to client needs.</li>
              <li><b>Monitoring & logging</b> habits—thinking in signals, incidents, and root cause.</li>
              <li><b>Security basics</b> applied pragmatically (least privilege, access control, segmentation).</li>
            </ul>
            <div class="skillNote">
              This site is intentionally “networking-themed”: animated topology, terminal readouts, and a packet counter to reflect how I think when troubleshooting—<i>visibility first</i>.
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="skills">
      <div class="wrap">
        <div class="sectionTitle">
          <h2>Skills</h2>
        </div>

        <div class="grid2">
          <div class="item">
            <h3>Networking & Systems</h3>
            <div class="skillGrid">
              <div class="skillRow">
                <b>Routing & Switching</b>
                <div class="bar"><div class="fill" style="width:78%"></div></div>
              </div>
              <div class="skillRow">
                <b>Network Design</b>
                <div class="bar"><div class="fill" style="width:74%"></div></div>
              </div>
              <div class="skillRow">
                <b>Linux Admin</b>
                <div class="bar"><div class="fill" style="width:70%"></div></div>
              </div>
              <div class="skillRow">
                <b>Windows Server</b>
                <div class="bar"><div class="fill" style="width:62%"></div></div>
              </div>
              <div class="skillRow">
                <b>Virtualization</b>
                <div class="bar"><div class="fill" style="width:66%"></div></div>
              </div>
            </div>
            <div class="chips">
              <span class="chip accent">CCNA-Level R&S</span>
              <span class="chip">Packet Tracer</span>
              <span class="chip">Server Management</span>
              <span class="chip">Hardware Troubleshooting</span>
              <span class="chip">Incident Response</span>
              <span class="chip">SIEM Fundamentals</span>
            </div>
          </div>

          <div class="item">
            <h3>Development & Cloud</h3>
            <div class="skillGrid">
              <div class="skillRow">
                <b>Python</b>
                <div class="bar"><div class="fill" style="width:80%"></div></div>
              </div>
              <div class="skillRow">
                <b>Docker + CI/CD</b>
                <div class="bar"><div class="fill" style="width:72%"></div></div>
              </div>
              <div class="skillRow">
                <b>AWS Fundamentals</b>
                <div class="bar"><div class="fill" style="width:62%"></div></div>
              </div>
              <div class="skillRow">
                <b>Web APIs</b>
                <div class="bar"><div class="fill" style="width:68%"></div></div>
              </div>
              <div class="skillRow">
                <b>Databases (SQL)</b>
                <div class="bar"><div class="fill" style="width:64%"></div></div>
              </div>
            </div>
            <div class="chips">
              <span class="chip">Java</span>
              <span class="chip">Bash</span>
              <span class="chip">JavaScript</span>
              <span class="chip">Flask</span>
              <span class="chip">SQLAlchemy</span>
              <span class="chip">React Native</span>
              <span class="chip green">Git/GitHub</span>
              <span class="chip">YAML / JSON</span>
            </div>
          </div>
        </div>
      </div>
    </section>

    <section id="certs">
      <div class="wrap">
        <div class="sectionTitle">
          <h2>Certifications</h2> 
        </div>
        <div class="item">
          <div class="chips" style="margin-top:0">
            <span class="chip accent">Cisco CCNA Enterprise</span>
            <span class="chip green">AWS Cloud Foundations</span>
            <span class="chip green">Google Cloud Essentials</span>
            <span class="chip">Java Programming</span>
            <span class="chip">Python Advanced</span>
            <span class="chip">Computer Assembly</span>
            <span class="chip">Syntax 6.1 Hackathon</span>
          </div>
          <p class="skillNote" style="margin:12px 0 0">
            Certifications support my focus by applying them in real projects: network segmentation with VLANs, role-based access control in cloud environments, automated deployments via CI/CD pipelines, and structured incident troubleshooting following ITIL-inspired workflows.
          </p>
        </div>
      </div>
    </section>

    <section id="experience">
      <div class="wrap">
        <div class="sectionTitle">
          <h2>Experience</h2>
        </div>

        <div class="list">
          <div class="item">
            <h3>Auriga Info Systems — Software Development Intern</h3>
            <div class="meta">
              <span>Remote</span><span class="sep">•</span>
              <span>Jun 2025 – Aug 2025</span>
            </div>
            <ul class="bullets">
              <li>Assisted on new base projects focusing on <b>Python-based systems</b> aligned to client needs.</li>
              <li>Deployed applications using <b>Docker</b> and <b>CI/CD</b> pipelines (GitHub Actions / Jenkins).</li>
              <li>Automated repetitive development tasks with Python scripts, reducing overall build time by <b>12%</b>.</li>
            </ul>
            <div class="chips">
              <span class="chip">Python</span>
              <span class="chip">Docker</span>
              <span class="chip">GitHub Actions</span>
              <span class="chip">Jenkins</span>
              <span class="chip green">CI/CD</span>
            </div>
          </div>

          <div class="item">
            <h3>George Brown Computer Science Club — Co-Chair</h3>
            <div class="meta">
              <span>Toronto, ON</span><span class="sep">•</span>
              <span>Jun 2024 – Present</span>
            </div>
            <ul class="bullets">
              <li>Founding team that brought together <b>300 students</b> for the club.</li>
              <li>Helped run events/meetings and increased participation, growing engagement by <b>+17% each semester</b>.</li>
              <li>Coordinated weekly executive meetings and delegated tasks to keep operations smooth.</li>
            </ul>
            <div class="chips">
              <span class="chip">Leadership</span>
              <span class="chip">Project Coordination</span>
              <span class="chip">Community Building</span>
            </div>
          </div>

          <div class="item">
            <h3>Boston World School — Student Application Lead</h3>
            <div class="meta">
              <span>Pune, IN</span><span class="sep">•</span>
              <span>Jun 2022 – Jul 2023</span>
            </div>
            <ul class="bullets">
              <li>Collaborated with system administrators to monitor and analyze application logs using <b>SIEM-based troubleshooting</b>.</li>
              <li>Built a student council <b>voting app</b> (Python/Flask stack) and deployed it for the school’s use.</li>
              <li>Implemented basic cloud security configurations in <b>AWS</b> (IAM roles, S3 policies, network ACLs).</li>
            </ul>
            <div class="chips">
              <span class="chip">SIEM Fundamentals</span>
              <span class="chip">Flask</span>
              <span class="chip">AWS IAM</span>
              <span class="chip">Access Control</span>
            </div>
          </div>
        </div>

      </div>
    </section>

    <section id="projects">
      <div class="wrap">
        <div class="sectionTitle">
          <h2>Projects</h2>
        </div>

        <div class="grid2">
          <div class="item">
            <h3>Voting Web-Based Application</h3>
            <div class="meta">
              <span>HTML • CSS • JavaScript</span><span class="sep">•</span>
              <span>Flask • SQLAlchemy</span>
            </div>
            <ul class="bullets">
              <li>Built a Student Council Voting App for Boston World School in a duo team.</li>
              <li>Handled higher traffic use cases while maintaining data security with user authentication.</li>
            </ul>
            <div class="chips">
              <span class="chip">Auth</span>
              <span class="chip">Flask</span>
              <span class="chip">SQLAlchemy</span>
              <span class="chip green">Web App</span>
            </div>
          </div>

          <div class="item">
            <h3>Weather Monitoring Application</h3>
            <div class="meta">
              <span>OpenWeather API</span><span class="sep">•</span>
              <span>Flask • Web UI</span>
            </div>
            <ul class="bullets">
              <li>Created a user-friendly app to monitor current & forecast weather using an API.</li>
              <li>Built a secondary web app for browser access; achieved <b>Top 5</b> in the Syntax 6.1 Hackathon.</li>
            </ul>
            <div class="chips">
              <span class="chip">REST APIs</span>
              <span class="chip">Flask</span>
              <span class="chip">JSON</span>
              <span class="chip accent">Top 5 Hackathon</span>
            </div>
          </div>

          <div class="item">
            <h3>SOHO & Enterprise Network Designs</h3>
            <div class="meta">
              <span>Cisco Packet Tracer</span><span class="sep">•</span>
              <span>PMI-based outline</span>
            </div>
            <ul class="bullets">
              <li>Designed SOHO and enterprise networks tailored to client needs.</li>
              <li>Provided recommended equipment list and a project outline for setup and rollout.</li>
            </ul>
            <div class="chips">
              <span class="chip accent">Network Design</span>
              <span class="chip">VLANs</span>
              <span class="chip">IP Planning</span>
              <span class="chip">Packet Tracer</span>
            </div>
          </div>

          <div class="item">
            <h3>Solar Environment Sustainability</h3>
            <div class="meta">
              <span>India Innovation Challenge 2022</span><span class="sep">•</span>
              <span>University of Sydney</span>
            </div>
            <ul class="bullets">
              <li>Designed a sustainability-focused system to optimize energy efficiency.</li>
              <li>Targeted reducing carbon footprint by <b>40%+</b> across a school system.</li>
            </ul>
            <div class="chips">
              <span class="chip">System Design</span>
              <span class="chip">Sustainability</span>
              <span class="chip green">Optimization</span>
            </div>
          </div>
        </div>

      </div>
    </section>

    <section id="leadership">
      <div class="wrap">
        <div class="sectionTitle">
          <h2>Leadership</h2>
        </div>

        <div class="grid2">
          <div class="item">
            <h3>HuskyHacks Hackathon — Vice President</h3>
            <div class="meta">
              <span>Toronto, ON</span><span class="sep">•</span>
              <span>Sep 2025 – Present</span>
            </div>
            <ul class="bullets">
              <li>Helping organize HuskyHacks to accommodate <b>300+ hackers</b>.</li>
              <li>Working with sponsors and managing allocations with <b>7+ interested sponsors</b>.</li>
              <li>Leading a team of <b>15+</b> members handling all aspects of organization.</li>
            </ul>
            <div class="chips">
              <span class="chip">Operations</span>
              <span class="chip">Sponsorship</span>
              <span class="chip">Team Leadership</span>
            </div>
          </div>

          <div class="item">
            <h3>Boston World School — Student Council President</h3>
            <div class="meta">
              <span>Pune, IN</span><span class="sep">•</span>
              <span>Apr 2022 – Jun 2023</span>
            </div>
            <ul class="bullets">
              <li>Represented 500+ students and bridged students, faculty, and administration.</li>
              <li>Led planning and execution of initiatives to build school spirit and engagement.</li>
            </ul>
            <div class="chips">
              <span class="chip">Public Speaking</span>
              <span class="chip">Stakeholder Management</span>
              <span class="chip">Initiative Ownership</span>
            </div>
          </div>
        </div>

      </div>
    </section>

    <section id="contact">
      <div class="wrap">
        <div class="sectionTitle">
          <h2>Contact</h2>
          <p>Toronto, ON • open to internships & junior roles</p>
        </div>

        <div class="item">
          <h3>Let’s connect</h3>
          <ul class="bullets">
            <li><b>Location:</b> Toronto, ON</li>
            <li><b>Phone:</b> <span id="phoneText">437-263-2403</span></li>
            <li><b>Email:</b> <a id="emailLink" href="mailto:hanifwork2403@gmail.com" style="color:rgba(86,212,255,.95); text-decoration:none;">hanifwork2403@gmail.com</a></li>
            <li><b>LinkedIn:</b> <a href="https://www.linkedin.com/in/hanif-patel/" target="_blank" rel="noopener noreferrer" style="color:rgba(86,212,255,.95); text-decoration:none;"> Hanif Patel</a></li>
          </ul>
          <div class="heroActions" style="margin-top:12px">
            <button class="btn" id="copyEmailBtn">Copy Email <small>hanifwork2403@gmail.com</small></button>
            <button class="ghost" id="copyPhoneBtn">Copy Phone <small>437-263-2403</small></button>
            <button class="ghost" id="pingBtn" title="Simulated network check">Run Ping <small>ICMP</small></button>
      </div>
    </section>

    <footer>
      <div class="wrap">
        <div class="footerCard">
          <div>© <span id="year"></span> Hanif Patel</div>
          <div>
            <a href="#top">Back to top</a> •
            <a href="mailto:hanifwork2403@gmail.com">Email</a>
          </div>
        </div>
      </div>
    </footer>
  </main>

  <script>
    /* -------------------------------
       Utilities
    -------------------------------- */
    const $ = (sel) => document.querySelector(sel);
    const sleep = (ms) => new Promise(r => setTimeout(r, ms));

    function clamp(v, a, b){ return Math.max(a, Math.min(b, v)); }
    function rand(min, max){ return Math.random()*(max-min)+min; }

    function copyToClipboard(text){
      if (navigator.clipboard && window.isSecureContext){
        return navigator.clipboard.writeText(text);
      }
      // fallback
      const ta = document.createElement('textarea');
      ta.value = text;
      ta.style.position = 'fixed';
      ta.style.top = '-9999px';
      ta.style.left = '-9999px';
      document.body.appendChild(ta);
      ta.focus();
      ta.select();
      try { document.execCommand('copy'); } catch(e){}
      document.body.removeChild(ta);
      return Promise.resolve();
    }

    /* -------------------------------
       Topbar actions
    -------------------------------- */
    const EMAIL = "hanifwork2403@gmail.com";
    const PHONE = "437-263-2403";

    $("#copyEmailBtn").addEventListener("click", async () => {
      await copyToClipboard(EMAIL);
      toast("Copied email.");
    });
    $("#copyPhoneBtn").addEventListener("click", async () => {
      await copyToClipboard(PHONE);
      toast("Copied phone number.");
    });
    /* -------------------------------
       Toast
    -------------------------------- */
    let toastEl;
    function toast(msg){
      if(!toastEl){
        toastEl = document.createElement("div");
        toastEl.style.position = "fixed";
        toastEl.style.left = "50%";
        toastEl.style.bottom = "22px";
        toastEl.style.transform = "translateX(-50%)";
        toastEl.style.padding = "10px 12px";
        toastEl.style.borderRadius = "14px";
        toastEl.style.border = "1px solid rgba(255,255,255,.14)";
        toastEl.style.background = "rgba(0,0,0,.55)";
        toastEl.style.backdropFilter = "blur(10px)";
        toastEl.style.color = "rgba(234,242,255,.92)";
        toastEl.style.fontFamily = "ui-monospace, SFMono-Regular, Menlo, Monaco, Consolas, 'Liberation Mono', 'Courier New', monospace";
        toastEl.style.fontSize = "12px";
        toastEl.style.zIndex = "9999";
        toastEl.style.boxShadow = "0 18px 50px rgba(0,0,0,.45)";
        toastEl.style.opacity = "0";
        toastEl.style.transition = "opacity .18s ease, transform .18s ease";
        document.body.appendChild(toastEl);
      }
      toastEl.textContent = msg;
      toastEl.style.opacity = "1";
      toastEl.style.transform = "translateX(-50%) translateY(-2px)";
      clearTimeout(toastEl._t);
      toastEl._t = setTimeout(() => {
        toastEl.style.opacity = "0";
        toastEl.style.transform = "translateX(-50%) translateY(0px)";
      }, 1600);
    }

    /* -------------------------------
       Simulated network topology canvas
    -------------------------------- */
    const canvas = $("#netCanvas");
    const ctx = canvas.getContext("2d");
    let W=0, H=0, DPR=1;

    function resizeCanvas(){
      const rect = canvas.getBoundingClientRect();
      DPR = Math.max(1, Math.floor(window.devicePixelRatio || 1));
      W = Math.floor(rect.width * DPR);
      H = Math.floor(rect.height * DPR);
      canvas.width = W;
      canvas.height = H;
    }
    window.addEventListener("resize", resizeCanvas);

    // Nodes / links
    const nodes = [];
    const links = [];
    const nodeCount = 12;

    function initGraph(){
      nodes.length = 0;
      links.length = 0;

      // Place nodes in a loose ring + a few interior nodes.
      for(let i=0;i<nodeCount;i++){
        const t = (i/nodeCount) * Math.PI*2;
        const ring = i < 8 ? 0.40 : 0.22;
        const x = (0.5 + Math.cos(t)*ring + rand(-0.05,0.05)) * W;
        const y = (0.55 + Math.sin(t)*ring + rand(-0.05,0.05)) * H;
        nodes.push({
          x, y,
          vx: rand(-0.12,0.12),
          vy: rand(-0.12,0.12),
          r: i===0 ? 10 : (i<3 ? 7 : 6),
          role: (i===0 ? "core" : (i<3 ? "dist" : "access"))
        });
      }

      // Create links: core to dist, dist to access, plus a couple cross links
      const core = 0;
      for(let i=1;i<3;i++) links.push([core, i]);
      for(let i=3;i<nodeCount;i++){
        const parent = (i%2===0) ? 1 : 2;
        links.push([parent, i]);
      }
      links.push([1,2]);
      links.push([4,7]);
      links.push([6,9]);
    }

    const packets = [];
    let pktCounter = 0;

    function spawnPacket(){
      const L = links[Math.floor(Math.random()*links.length)];
      const a = nodes[L[0]], b = nodes[L[1]];
      packets.push({
        ax:a.x, ay:a.y, bx:b.x, by:b.y,
        t:0,
        speed: rand(0.006, 0.012),
        size: rand(2.0, 3.0)
      });
      pktCounter++;
      $("#pktCount").textContent = pktCounter.toString();
    }

    function draw(){
      ctx.clearRect(0,0,W,H);

      // background glow
      ctx.save();
      ctx.globalAlpha = 0.75;
      const grd = ctx.createRadialGradient(W*0.2,H*0.15, 0, W*0.2,H*0.15, Math.max(W,H)*0.75);
      grd.addColorStop(0, "rgba(86,212,255,0.10)");
      grd.addColorStop(1, "rgba(0,0,0,0)");
      ctx.fillStyle = grd;
      ctx.fillRect(0,0,W,H);
      ctx.restore();

      // Move nodes slightly
      for(const n of nodes){
        n.x += n.vx;
        n.y += n.vy;

        // boundary bounce
        const pad = 18*DPR;
        if(n.x < pad || n.x > W-pad) n.vx *= -1;
        if(n.y < pad || n.y > H-pad) n.vy *= -1;
        n.x = clamp(n.x, pad, W-pad);
        n.y = clamp(n.y, pad, H-pad);
      }

      // Draw links
      ctx.save();
      ctx.lineWidth = 1.2*DPR;
      for(const [i,j] of links){
        const a = nodes[i], b = nodes[j];
        ctx.strokeStyle = "rgba(234,242,255,0.16)";
        ctx.beginPath();
        ctx.moveTo(a.x,a.y);
        ctx.lineTo(b.x,b.y);
        ctx.stroke();

        // subtle bright pass
        ctx.strokeStyle = "rgba(86,212,255,0.12)";
        ctx.beginPath();
        ctx.moveTo(a.x,a.y);
        ctx.lineTo(b.x,b.y);
        ctx.stroke();
      }
      ctx.restore();

      // Update & draw packets
      for(let k=packets.length-1;k>=0;k--){
        const p = packets[k];
        p.t += p.speed;
        const tt = p.t;
        const x = p.ax + (p.bx - p.ax) * tt;
        const y = p.ay + (p.by - p.ay) * tt;

        ctx.save();
        ctx.globalAlpha = 0.9;
        ctx.fillStyle = "rgba(183,255,90,0.85)";
        ctx.beginPath();
        ctx.arc(x, y, p.size*DPR, 0, Math.PI*2);
        ctx.fill();
        ctx.restore();

        if(p.t >= 1){
          packets.splice(k,1);
        }
      }

      // Draw nodes
      for(const n of nodes){
        ctx.save();
        const glow = ctx.createRadialGradient(n.x,n.y, 0, n.x,n.y, (n.r*6)*DPR);
        if(n.role==="core"){
          glow.addColorStop(0, "rgba(86,212,255,0.34)");
          glow.addColorStop(1, "rgba(86,212,255,0)");
        } else if(n.role==="dist"){
          glow.addColorStop(0, "rgba(183,255,90,0.22)");
          glow.addColorStop(1, "rgba(183,255,90,0)");
        } else {
          glow.addColorStop(0, "rgba(234,242,255,0.16)");
          glow.addColorStop(1, "rgba(234,242,255,0)");
        }
        ctx.fillStyle = glow;
        ctx.beginPath();
        ctx.arc(n.x,n.y, (n.r*6)*DPR, 0, Math.PI*2);
        ctx.fill();

        // node body
        ctx.fillStyle = "rgba(0,0,0,0.35)";
        ctx.strokeStyle = "rgba(255,255,255,0.18)";
        ctx.lineWidth = 1.2*DPR;
        ctx.beginPath();
        ctx.arc(n.x,n.y, n.r*DPR, 0, Math.PI*2);
        ctx.fill();
        ctx.stroke();

        // node center
        ctx.fillStyle = n.role==="core" ? "rgba(86,212,255,0.95)"
                        : n.role==="dist" ? "rgba(183,255,90,0.90)"
                        : "rgba(234,242,255,0.78)";
        ctx.beginPath();
        ctx.arc(n.x,n.y, (n.r*0.45)*DPR, 0, Math.PI*2);
        ctx.fill();
        ctx.restore();
      }

      requestAnimationFrame(draw);
    }

    function startViz(){
      resizeCanvas();
      initGraph();
      // packet spawner
      setInterval(() => {
        const burst = Math.random() < 0.25 ? 2 : 1;
        for(let i=0;i<burst;i++) spawnPacket();
        // fake latency + VLAN rotation
        const lat = Math.round(rand(6, 22));
        $("#latency").textContent = `${lat}ms`;
      }, 320);
      // VLAN ticker
      let vlan = 10;
      setInterval(() => {
        vlan = vlan === 10 ? 20 : vlan === 20 ? 30 : 10;
        $("#vlanChip").textContent = vlan.toString();
      }, 2600);

      draw();
    }

    /* -------------------------------
       Terminal simulation
    -------------------------------- */
    const term = $("#termBody");
    const termMode = $("#termMode");
    const commands = [
      { cmd: "show ip interface brief", out: [
        "Interface              IP-Address      OK? Method Status                Protocol",
        "Gi0/0                  10.10.10.1      YES manual up                    up",
        "Gi0/1                  10.20.20.1      YES manual up                    up",
        "Vlan10                 10.10.10.254    YES manual up                    up",
        "Vlan20                 10.20.20.254    YES manual up                    up",
        "Lo0                    172.16.0.1      YES manual up                    up",
      ]},
      { cmd: "show vlan brief", out: [
        "VLAN Name                             Status    Ports",
        "---- -------------------------------- --------- -------------------------------",
        "1    default                          active    Gi0/2, Gi0/3",
        "10   USERS                            active    Gi0/10, Gi0/11",
        "20   SERVERS                          active    Gi0/12, Gi0/13",
        "30   MGMT                             active    Gi0/14",
      ]},
      { cmd: "show ip route | include 10.", out: [
        "C    10.10.10.0/24 is directly connected, Gi0/0",
        "C    10.20.20.0/24 is directly connected, Gi0/1",
        "S    10.30.30.0/24 [1/0] via 10.20.20.2",
      ]},
      { cmd: "show interfaces counters errors", out: [
        "Port        Align-Err  FCS-Err  Xmit-Err  Rcv-Err  UnderSize  OutDiscards",
        "Gi0/0       0          0        0         0        0          0",
        "Gi0/1       0          0        0         0        0          0",
        "Gi0/10      0          0        0         0        0          0",
      ]},
      { cmd: "show logging | tail 5", out: [
        "%LINK-3-UPDOWN: Interface GigabitEthernet0/0, changed state to up",
        "%LINEPROTO-5-UPDOWN: Line protocol on Interface GigabitEthernet0/0, changed state to up",
        "%SEC-6-IPACCESSLOGP: list ACL-MGMT permitted tcp 10.30.30.10 -> 10.30.30.1(22), 1 packet",
        "%SYS-5-CONFIG_I: Configured from console by hanif on vty0 (lab)",
        "%PKT-5-TRACE: Packet capture enabled on Gi0/1 (monitoring)",
      ]},
    ];

    async function typeLine(text, speed=12){
      for(const ch of text){
        term.textContent += ch;
        await sleep(speed);
      }
      term.textContent += "\n";
      term.scrollTop = term.scrollHeight;
    }

    async function terminalLoop(){
      term.textContent = "";
      const prompt = "hanif@lab-router# ";
      let idx = 0;

      while(true){
        const entry = commands[idx % commands.length];

        termMode.textContent = entry.cmd.startsWith("show") ? "show" : "exec";
        await typeLine(prompt + entry.cmd, 10);
        for(const line of entry.out){
          await typeLine(line, 2);
        }
        term.textContent += "\n";
        term.scrollTop = term.scrollHeight;

        // small pause
        await sleep(900);

        idx++;
        // occasionally flip link state
        if(Math.random() < 0.12){
          const state = $("#linkState");
          state.textContent = "UP";
        }
      }
    }

    /* -------------------------------
       Ping button (simulated)
    -------------------------------- */
    $("#pingBtn").addEventListener("click", async () => {
      toast("Running ping (simulated)...");
      const prompt = "hanif@lab-router# ";
      await typeLine(prompt + "ping 8.8.8.8 repeat 4", 10);
      const base = rand(8, 20);
      for(let i=1;i<=4;i++){
        const ms = (base + rand(-2, 4)).toFixed(1);
        await typeLine(`!!!!  Reply from 8.8.8.8: icmp_seq=${i} time=${ms} ms`, 3);
      }
      await typeLine("---- 8.8.8.8 ping statistics ----", 2);
      await typeLine("4 packets transmitted, 4 received, 0% packet loss", 2);
      term.textContent += "\n";
      term.scrollTop = term.scrollHeight;
    });

    /* -------------------------------
       Boot
    -------------------------------- */
    $("#year").textContent = new Date().getFullYear();
    startViz();
    terminalLoop();

    /* Keyboard shortcut hint: Ctrl+C copies contact if focused on page */
    document.addEventListener("keydown", (e) => {
      if((e.ctrlKey || e.metaKey) && e.key.toLowerCase() === "c"){
        // don't override if user is selecting text
        const sel = window.getSelection()?.toString();
        if(sel && sel.length > 0) return;
        copyToClipboard(`Hanif Patel • ${EMAIL} • ${PHONE} • Toronto, ON`);
        toast("Copied contact (quick).");
      }
    });
  </script>
</body>
</html>
