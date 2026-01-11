<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>GitHub Profile Preview - Red Cyber Theme</title>
    <style>
        /* =========================================
           CSS VARIABLES & RESET
           ========================================= */
        :root {
            --bg-dark: #050505;
            --bg-card: #0f0f0f;
            --bg-card-hover: #161616;
            --text-main: #e0e0e0;
            --text-muted: #858585;
            --accent-red: #ff0f39; /* Blood Red / Cyber Red */
            --accent-dim: #590816;
            --border-color: #333;
            --font-mono: 'Courier New', Courier, monospace; /* Fallback */
            --font-sans: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        /* Import Fonts via @import for standalone file */
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;700&family=Inter:wght@400;600;800&display=swap');

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: 'Inter', var(--font-sans);
            line-height: 1.6;
            overflow-x: hidden;
            background-image: 
                radial-gradient(circle at 10% 20%, rgba(255, 15, 57, 0.05) 0%, transparent 20%),
                linear-gradient(rgba(18, 18, 18, 0.9) 1px, transparent 1px),
                linear-gradient(90deg, rgba(18, 18, 18, 0.9) 1px, transparent 1px);
            background-size: 100% 100%, 40px 40px, 40px 40px;
        }

        /* Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: var(--bg-dark);
        }
        ::-webkit-scrollbar-thumb {
            background: var(--accent-dim);
            border-radius: 4px;
        }
        ::-webkit-scrollbar-thumb:hover {
            background: var(--accent-red);
        }

        /* =========================================
           LAYOUT UTILITIES
           ========================================= */
        .container {
            max-width: 900px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        .text-center { text-align: center; }
        .text-accent { color: var(--accent-red); }
        .text-muted { color: var(--text-muted); }
        
        /* Glitch Effect on Hover */
        .glitch-wrapper {
            display: inline-block;
            position: relative;
        }
        .glitch-wrapper:hover {
            animation: glitch-anim 0.3s cubic-bezier(.25, .46, .45, .94) both infinite;
            color: var(--accent-red);
        }

        @keyframes glitch-anim {
            0% { transform: translate(0); }
            20% { transform: translate(-2px, 2px); }
            40% { transform: translate(-2px, -2px); }
            60% { transform: translate(2px, 2px); }
            80% { transform: translate(2px, -2px); }
            100% { transform: translate(0); }
        }

        /* =========================================
           HEADER SECTION
           ========================================= */
        header {
            display: flex;
            flex-direction: column;
            align-items: center;
            margin-bottom: 60px;
            position: relative;
        }

        .avatar-container {
            position: relative;
            width: 120px;
            height: 120px;
            margin-bottom: 20px;
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            border: 2px solid var(--border-color);
            object-fit: cover;
            position: relative;
            z-index: 2;
            background-color: #222;
        }

        .avatar-glow {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            width: 100%;
            height: 100%;
            border-radius: 50%;
            box-shadow: 0 0 20px var(--accent-red);
            opacity: 0.6;
            z-index: 1;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 15px var(--accent-dim); }
            50% { box-shadow: 0 0 30px var(--accent-red); }
            100% { box-shadow: 0 0 15px var(--accent-dim); }
        }

        h1 {
            font-size: 2.5rem;
            margin-bottom: 10px;
            font-family: 'JetBrains Mono', var(--font-mono);
            font-weight: 700;
            letter-spacing: -1px;
        }

        .tagline {
            font-size: 1.1rem;
            color: var(--text-muted);
            margin-bottom: 20px;
            max-width: 600px;
        }

        /* Typing cursor simulation */
        .typing-cursor::after {
            content: '|';
            animation: blink 1s step-end infinite;
            color: var(--accent-red);
        }
        @keyframes blink { 50% { opacity: 0; } }

        .social-links {
            display: flex;
            gap: 15px;
        }

        .social-btn {
            text-decoration: none;
            color: var(--text-main);
            border: 1px solid var(--border-color);
            padding: 8px 16px;
            border-radius: 4px;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .social-btn:hover {
            border-color: var(--accent-red);
            background: rgba(255, 15, 57, 0.1);
            color: var(--accent-red);
            transform: translateY(-2px);
            box-shadow: 0 4px 12px rgba(255, 15, 57, 0.2);
        }

        /* =========================================
           SKILLS SECTION
           ========================================= */
        .section-title {
            font-size: 1.5rem;
            margin-bottom: 25px;
            border-left: 4px solid var(--accent-red);
            padding-left: 15px;
            font-family: 'JetBrains Mono', var(--font-mono);
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .skills-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 60px;
        }

        .skill-tag {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 8px 14px;
            border-radius: 4px;
            font-size: 0.9rem;
            font-family: 'JetBrains Mono', var(--font-mono);
            transition: 0.3s;
            color: var(--text-muted);
        }

        .skill-tag:hover {
            border-color: var(--accent-red);
            color: var(--accent-red);
            background: var(--bg-card-hover);
        }

        .skill-tag span {
            color: var(--accent-red);
            margin-right: 5px;
        }

        /* =========================================
           GITHUB STATS (CARDS)
           ========================================= */
        .stats-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 20px;
            margin-bottom: 60px;
        }

        .stat-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            padding: 20px;
            border-radius: 6px;
            transition: transform 0.3s ease, border-color 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-red);
        }

        .stat-header {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-weight: 600;
            color: var(--text-main);
        }

        .stat-value {
            font-size: 2rem;
            font-weight: 800;
            color: var(--accent-red);
            font-family: 'JetBrains Mono', var(--font-mono);
        }

        .stat-desc {
            font-size: 0.85rem;
            color: var(--text-muted);
        }

        /* =========================================
           PROJECTS SECTION
           ========================================= */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 80px;
        }

        .project-card {
            background: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            overflow: hidden;
            transition: 0.3s;
            position: relative;
        }

        .project-card:hover {
            border-color: var(--accent-red);
            box-shadow: 0 10px 30px -10px rgba(0,0,0,0.5);
        }

        .project-content {
            padding: 20px;
        }

        .project-title {
            font-size: 1.1rem;
            font-weight: 700;
            margin-bottom: 8px;
            color: var(--text-main);
            display: flex;
            justify-content: space-between;
        }

        .folder-icon { color: var(--accent-red); }

        .project-desc {
            font-size: 0.9rem;
            color: var(--text-muted);
            margin-bottom: 15px;
        }

        .project-tech {
            font-family: 'JetBrains Mono', var(--font-mono);
            font-size: 0.75rem;
            color: var(--accent-red);
        }

        /* =========================================
           MARKDOWN CODE BLOCK (COPY AREA)
           ========================================= */
        .code-section {
            background: #111;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 20px;
            position: relative;
        }

        .code-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 15px;
            border-bottom: 1px solid #333;
            padding-bottom: 10px;
        }

        .copy-btn {
            background: var(--accent-dim);
            color: white;
            border: none;
            padding: 5px 12px;
            border-radius: 4px;
            cursor: pointer;
            font-size: 0.8rem;
            transition: 0.2s;
        }

        .copy-btn:hover { background: var(--accent-red); }

        pre {
            overflow-x: auto;
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.85rem;
            color: #a8b3c1;
        }

        code {
            font-family: inherit;
        }

        /* Syntax Highlighting Simulation */
        .md-h1 { color: #ff7b72; } /* Red */
        .md-special { color: #79c0ff; } /* Blue */
        .md-comment { color: #8b949e; font-style: italic; }
        .md-link { color: #d2a8ff; } /* Purple */

        /* =========================================
           FOOTER
           ========================================= */
        footer {
            border-top: 1px solid var(--border-color);
            padding-top: 20px;
            text-align: center;
            color: var(--text-muted);
            font-size: 0.9rem;
            font-family: 'JetBrains Mono', var(--font-mono);
        }

    </style>
</head>
<body>

    <div class="container">
        
        <!-- HEADER -->
        <header>
            <div class="avatar-container">
                <div class="avatar-glow"></div>
                <!-- Placeholder avatar using picsum with a dark seed -->
                <img src="https://picsum.photos/seed/cyberred/200/200" alt="Profile Avatar" class="avatar">
            </div>
            
            <h1>
                <span class="text-accent">&lt;</span> 
                <span class="glitch-wrapper">NamaAnda</span> 
                <span class="text-accent">/&gt;</span>
            </h1>
            
            <p class="tagline typing-cursor">
                Full Stack Developer | Security Enthusiast | Building the void.
            </p>

            <div class="social-links">
                <a href="#" class="social-btn">
                    <span>★</span> GitHub
                </a>
                <a href="#" class="social-btn">
                    <span>in</span> LinkedIn
                </a>
                <a href="#" class="social-btn">
                    <span>✉</span> Email
                </a>
            </div>
        </header>

        <!-- MAIN CONTENT -->
        <main>
            <!-- SKILLS -->
            <section>
                <h2 class="section-title">01. Tech Arsenal</h2>
                <div class="skills-grid">
                    <div class="skill-tag"><span>#</span>JavaScript</div>
                    <div class="skill-tag"><span>#</span>TypeScript</div>
                    <div class="skill-tag"><span>#</span>React.js</div>
                    <div class="skill-tag"><span>#</span>Node.js</div>
                    <div class="skill-tag"><span>#</span>Python</div>
                    <div class="skill-tag"><span>#</span>Rust</div>
                    <div class="skill-tag"><span>#</span>Docker</div>
                    <div class="skill-tag"><span>#</span>Kubernetes</div>
                    <div class="skill-tag"><span>#</span>Penetration Testing</div>
                </div>
            </section>

            <!-- STATS -->
            <section>
                <h2 class="section-title">02. System Metrics</h2>
                <div class="stats-container">
                    <div class="stat-card">
                        <div class="stat-header">Total Stars</div>
                        <div class="stat-value">1,337</div>
                        <div class="stat-desc">Contributions across repositories</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-header">Commits (2023)</div>
                        <div class="stat-value">842</div>
                        <div class="stat-desc">Lines of code pushed</div>
                    </div>
                    <div class="stat-card">
                        <div class="stat-header">Current Streak</div>
                        <div class="stat-value">42 Days</div>
                        <div class="stat-desc">Consistency is key</div>
                    </div>
                </div>
            </section>

            <!-- PROJECTS -->
            <section>
                <h2 class="section-title">03. Deployed Units</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-content">
                            <div class="project-title">
                                Project Void <span class="folder-icon">📂</span>
                            </div>
                            <p class="project-desc">A secure, decentralized messaging platform using Rust and WebSockets.</p>
                            <div class="project-tech">Rust • WebSockets • Actix</div>
                        </div>
                    </div>
                    <div class="project-card">
                        <div class="project-content">
                            <div class="project-title">
                                Red Eye UI <span class="folder-icon">📂</span>
                            </div>
                            <p class="project-desc">Dark mode component library built for React applications focusing on accessibility.</p>
                            <div class="project-tech">React • CSS Modules • Storybook</div>
                        </div>
                    </div>
                    <div class="project-card">
                        <div class="project-content">
                            <div class="project-title">
                                Net Sentinel <span class="folder-icon">📂</span>
                            </div>
                            <p class="project-desc">Python-based network scanner that detects vulnerabilities in real-time.</p>
                            <div class="project-tech">Python • Scapy • Flask</div>
                        </div>
                    </div>
                </div>
            </section>
        </main>

        <!-- FOOTER -->
        <footer>
            <p>Designed & Built by NamaAnda © 2023</p>
            <p class="text-muted" style="font-size: 0.8rem; margin-top: 5px;">System Status: Online</p>
        </footer>

        <!-- MARKDOWN CODE TO COPY -->
        <div style="margin-top: 80px; margin-bottom: 40px;">
            <h2 class="section-title">04. Implementation Code</h2>
            <p style="margin-bottom: 20px; color: var(--text-muted);">
                Salin kode di bawah ini dan tempel ke dalam file <code>README.md</code> di repository GitHub Anda.
            </p>
            
            <div class="code-section">
                <div class="code-header">
                    <span>README.md</span>
                    <button class="copy-btn" onclick="copyCode()">Copy Code</button>
                </div>
                <pre><code id="markdownCode">
<!-- 
  GITHUB PROFILE README - RED CYBER THEME
  Instructions: 
  1. Ganti 'NamaAnda' dengan nama asli Anda.
  2. Ganti link gambar (img src) dengan link avatar asli Anda.
  3. Ganti link social media href.
-->

<div align="center">

  <!-- Avatar dengan efek glow menggunakan HTML border trick -->
  <img src="https://picsum.photos/seed/cyberred/200/200" alt="Avatar" style="width: 120px; height: 120px; border-radius: 50%; border: 2px solid #333; box-shadow: 0 0 20px #ff0f39;">

  <!-- Judul Utama -->
  <h1 align="center" style="font-family: monospace; font-size: 2.5em;">
    <span style="color:#ff0f39">&lt;</span> NamaAnda <span style="color:#ff0f39">/&gt;</span>
  </h1>

  <!-- Tagline / Role -->
  <p align="center" style="color: #858585; font-family: monospace;">
    Full Stack Developer | Security Enthusiast | Open Source Contributor
  </p>

  <!-- Social Links (Menggunakan Shields.io untuk ikon text-based yang rapi) -->
  <p align="center">
    <a href="https://github.com/NamaAnda" target="_blank">
      <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white&color=0d0d0d&labelColor=ff0f39" alt="GitHub">
    </a>
    <a href="https://linkedin.com/in/NamaAnda" target="_blank">
      <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white&color=0d0d0d&labelColor=ff0f39" alt="LinkedIn">
    </a>
    <a href="mailto:email@example.com">
      <img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white&color=0d0d0d&labelColor=ff0f39" alt="Email">
    </a>
  </p>
</div>

---

### &nbsp; <span style="color:#ff0f39">01.</span> Tech Arsenal

Tech stack yang saya gunakan untuk membangun sistem:

<!-- Skill Badges -->
<p>
  <img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black&labelColor=333333" alt="JS" />
  <img src="https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white&labelColor=333333" alt="TS" />
  <img src="https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB&labelColor=333333" alt="React" />
  <img src="https://img.shields.io/badge/Node.js-43853D?style=flat-square&logo=node.js&logoColor=white&labelColor=333333" alt="Node" />
  <img src="https://img.shields.io/badge/Python-14354C?style=flat-square&logo=python&logoColor=white&labelColor=333333" alt="Python" />
  <img src="https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white&labelColor=333333" alt="Rust" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white&labelColor=333333" alt="Docker" />
</p>

---

### &nbsp; <span style="color:#ff0f39">02.</span> System Metrics

Statistik kontribusi coding saya:

<p align="center">
  <img height="180em" src="https://github-readme-stats.vercel.app/api?username=NamaAnda&show_icons=true&theme=dracula&include_all_commits=true&count_private=true&hide_border=true&bg_color=0d0d0d&title_color=ff0f39&icon_color=ff0f39&text_color=e0e0e0" alt="Stats"/>
  <img height="180em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=NamaAnda&layout=compact&langs_count=7&theme=dracula&hide_border=true&bg_color=0d0d0d&title_color=ff0f39&text_color=e0e0e0" alt="Top Langs"/>
</p>

---

### &nbsp; <span style="color:#ff0f39">03.</span> Highlighted Projects

Proyek unggulan yang telah saya kerjakan:

| Project Name | Description | Tech Stack |
| :--- | :--- | :--- |
| <b>[Project Void](https://github.com/NamaAnda/project-void)</b> | Secure decentralized messaging platform. | `Rust` `WebSockets` `Actix` |
| <b>[Red Eye UI](https://github.com/NamaAnda/red-eye-ui)</b> | Accessible dark-mode component library. | `React` `CSS Modules` `Storybook` |
| <b>[Net Sentinel](https://github.com/NamaAnda/net-sentinel)</b> | Real-time network vulnerability scanner. | `Python` `Scapy` `Flask` |

---

<div align="center">
  <img src="https://komarev.com/ghpvc/?username=NamaAnda&style=flat-square&color=ff0f39" alt=""/>
</div>

<div align="center">
  <p style="color: #555; font-family: monospace; font-size: 0.8em;">
    System Status: Online | © 2023 NamaAnda
  </p>
</div>
                </code></pre>
            </div>
        </div>

    </div>

    <script>
        // Simple script to copy code content
        function copyCode() {
            const codeBlock = document.getElementById('markdownCode');
            const textToCopy = codeBlock.innerText;

            navigator.clipboard.writeText(textToCopy).then(() => {
                const btn = document.querySelector('.copy-btn');
                const originalText = btn.innerText;
                
                btn.innerText = "Copied!";
                btn.style.background = "#28a745"; // Green for success
                
                setTimeout(() => {
                    btn.innerText = originalText;
                    btn.style.background = ""; // Reset to CSS default
                }, 2000);
            }).catch(err => {
                console.error('Failed to copy: ', err);
                alert('Gagal menyalin kode, silakan blok manual.');
            });
        }
    </script>
</body>
</html>
