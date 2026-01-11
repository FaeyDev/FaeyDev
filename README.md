<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Profil Pengembang - Tema Merah Gelap</title>
    <style>
        /* --- CSS VARIABLES & RESET --- */
        :root {
            /* Warna Tema: Merah Seram & Gelap */
            --bg-body: #050505;
            --bg-container: #0d0d0d;
            --bg-card: #161616;
            --border-color: #333;
            --border-highlight: #4d0000; /* Merah sangat gelap */
            
            /* Tipografi */
            --text-main: #e0e0e0;
            --text-muted: #8b8b8b;
            --text-red: #ff1f1f; /* Merah neon/seram */
            --text-red-dim: #990000;
            
            /* Efek */
            --glow: 0 0 10px rgba(255, 31, 31, 0.3);
            --font-main: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica, Arial, sans-serif;
            --font-mono: "SFMono-Regular", Consolas, "Liberation Mono", Menlo, Courier, monospace;
        }

        * {
            box-sizing: border-box;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: var(--bg-body);
            color: var(--text-main);
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        a {
            text-decoration: none;
            color: var(--text-red);
            transition: color 0.2s, text-shadow 0.2s;
        }

        a:hover {
            color: #ff4d4d;
            text-shadow: var(--glow);
        }

        /* --- LAYOUT UTAMA --- */
        .container {
            max-width: 1100px;
            margin: 0 auto;
            padding: 40px 20px;
        }

        /* --- HEADER PROFIL --- */
        header {
            display: flex;
            gap: 24px;
            align-items: flex-start;
            margin-bottom: 48px;
            flex-wrap: wrap;
        }

        .avatar-wrapper {
            position: relative;
        }

        .avatar {
            width: 290px;
            height: 290px;
            border-radius: 50%;
            border: 2px solid var(--border-highlight);
            box-shadow: 0 0 20px rgba(255, 0, 0, 0.1);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .avatar:hover {
            transform: scale(1.02);
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.3);
            border-color: var(--text-red);
        }

        .profile-info {
            flex: 1;
            min-width: 300px;
        }

        h1 {
            font-size: 2rem;
            font-weight: 700;
            color: var(--text-main);
            margin-bottom: 8px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .status-badge {
            font-size: 0.8rem;
            background: rgba(255, 31, 31, 0.1);
            color: var(--text-red);
            padding: 4px 12px;
            border-radius: 20px;
            border: 1px solid var(--border-highlight);
            text-transform: uppercase;
            letter-spacing: 1px;
            font-weight: 600;
        }

        .username {
            font-size: 1.5rem;
            color: var(--text-muted);
            font-weight: 300;
            margin-bottom: 16px;
        }

        .bio {
            font-size: 1rem;
            max-width: 600px;
            margin-bottom: 24px;
        }

        .highlight {
            color: var(--text-red);
            font-weight: 600;
        }

        /* --- TOMBOL & STATISTIK --- */
        .actions {
            display: flex;
            gap: 12px;
            margin-bottom: 24px;
            flex-wrap: wrap;
        }

        .btn {
            padding: 6px 16px;
            border-radius: 6px;
            font-size: 0.9rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.2s;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background-color: var(--text-red);
            color: white;
            border: 1px solid var(--text-red);
        }

        .btn-primary:hover {
            background-color: #cc0000;
            box-shadow: var(--glow);
        }

        .btn-secondary {
            background-color: var(--bg-card);
            color: var(--text-main);
            border: 1px solid var(--border-color);
        }

        .btn-secondary:hover {
            border-color: var(--text-muted);
            background-color: #222;
        }

        .stats-container {
            display: flex;
            gap: 24px;
            font-size: 0.9rem;
            color: var(--text-muted);
            border-bottom: 1px solid var(--border-color);
            padding-bottom: 24px;
            margin-bottom: 32px;
        }

        .stat-item strong {
            color: var(--text-main);
            margin-right: 4px;
        }

        /* --- BAGIAN KETERAMPILAN (SKILLS) --- */
        .section-title {
            font-size: 1.2rem;
            border-bottom: 1px solid var(--border-highlight);
            padding-bottom: 8px;
            margin-bottom: 16px;
            color: var(--text-main);
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .section-title svg {
            width: 20px;
            height: 20px;
            stroke: var(--text-red);
        }

        .tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
            margin-bottom: 40px;
        }

        .tag {
            background-color: #1a0505;
            color: #ff6b6b;
            border: 1px solid var(--border-highlight);
            padding: 4px 12px;
            border-radius: 4px;
            font-size: 0.85rem;
            font-family: var(--font-mono);
            transition: 0.2s;
        }

        .tag:hover {
            border-color: var(--text-red);
            color: var(--text-red);
            box-shadow: var(--glow);
        }

        /* --- GRID REPOSITORI --- */
        .repo-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 16px;
        }

        .repo-card {
            background-color: var(--bg-card);
            border: 1px solid var(--border-color);
            border-radius: 6px;
            padding: 16px;
            transition: transform 0.2s, border-color 0.2s;
            position: relative;
            overflow: hidden;
        }

        .repo-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 4px;
            height: 100%;
            background: var(--border-highlight);
            transition: background 0.3s;
        }

        .repo-card:hover {
            border-color: var(--text-red);
            transform: translateY(-3px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.5);
        }

        .repo-card:hover::before {
            background: var(--text-red);
            box-shadow: 2px 0 10px var(--text-red);
        }

        .repo-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 8px;
        }

        .repo-name {
            font-weight: 700;
            color: var(--text-main);
            font-size: 1rem;
        }

        .repo-visibility {
            font-size: 0.75rem;
            border: 1px solid var(--border-color);
            border-radius: 10px;
            padding: 2px 8px;
            color: var(--text-muted);
        }

        .repo-desc {
            font-size: 0.85rem;
            color: var(--text-muted);
            margin-bottom: 16px;
            min-height: 40px;
        }

        .repo-meta {
            display: flex;
            gap: 16px;
            font-size: 0.8rem;
            color: var(--text-muted);
            align-items: center;
        }

        .repo-meta span {
            display: flex;
            align-items: center;
            gap: 4px;
        }

        .language-dot {
            width: 10px;
            height: 10px;
            border-radius: 50%;
            display: inline-block;
        }
        .lang-html { background-color: #e34c26; box-shadow: 0 0 5px #e34c26; }
        .lang-js { background-color: #f1e05a; }
        .lang-css { background-color: #563d7c; }
        .lang-py { background-color: #3572A5; }

        /* --- KONTRIBUSI VISUAL (SIMULASI) --- */
        .contribution-graph {
            margin-top: 40px;
            width: 100%;
            overflow-x: auto;
            padding-bottom: 10px;
        }
        
        .graph-title {
            font-size: 0.9rem;
            color: var(--text-muted);
            margin-bottom: 8px;
        }

        .squares {
            display: flex;
            gap: 4px;
            min-width: 600px;
        }

        .col {
            display: flex;
            flex-direction: column;
            gap: 4px;
        }

        .sq {
            width: 12px;
            height: 12px;
            border-radius: 2px;
            background-color: #161616;
        }

        /* Variasi warna merah untuk grafik */
        .l1 { background-color: #3d0b0b; }
        .l2 { background-color: #661111; }
        .l3 { background-color: #9e1818; box-shadow: 0 0 5px rgba(158, 24, 24, 0.4); }
        .l4 { background-color: #ff1f1f; box-shadow: 0 0 8px rgba(255, 31, 31, 0.6); }

        /* --- FOOTER --- */
        footer {
            margin-top: 60px;
            text-align: center;
            font-size: 0.8rem;
            color: var(--text-muted);
            padding-top: 20px;
            border-top: 1px dashed var(--border-highlight);
        }

        /* --- RESPONSIVE --- */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                align-items: center;
                text-align: center;
            }
            
            .profile-info {
                display: flex;
                flex-direction: column;
                align-items: center;
            }

            h1 {
                flex-direction: column;
                gap: 5px;
            }

            .stats-container {
                justify-content: center;
            }

            .repo-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <!-- Header Profil -->
        <header>
            <div class="avatar-wrapper">
                <!-- Menggunakan seed 'red' untuk mendapatkan gambar acak yang konsisten -->
                <img src="https://picsum.photos/seed/redghost/300/300" alt="Foto Profil" class="avatar">
            </div>
            
            <div class="profile-info">
                <h1>
                    Ghost Developer 
                    <span class="status-badge">Open to work</span>
                </h1>
                <p class="username">@nightcoder_id</p>
                
                <p class="bio">
                    Pengembang Frontend yang obsesif dengan detail. Menciptakan pengalaman web yang imersif dengan sentuhan <span class="highlight">estetika gelap</span>. Spesialisasi dalam membangun antarmuka modern yang cepat, responsif, dan "menakutkan" baiknya.
                </p>

                <div class="actions">
                    <button class="btn btn-primary">Ikuti</button>
                    <button class="btn btn-secondary">Sponsor</button>
                    <a href="#" class="btn btn-secondary" style="color:var(--text-muted); border-color:transparent;">▼ Drop Down</a>
                </div>

                <div class="stats-container">
                    <div class="stat-item"><strong>54</strong> repositori</div>
                    <div class="stat-item"><strong>1.2k</strong> pengikut</div>
                    <div class="stat-item"><strong>89</strong> mengikuti</div>
                    <div class="stat-item"><strong>⭐</strong> 4.5k total stars</div>
                </div>
            </div>
        </header>

        <!-- Bagian Keterampilan -->
        <section>
            <div class="section-title">
                <!-- Ikon Chip SVG -->
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="4" y="4" width="16" height="16" rx="2" ry="2"></rect><rect x="9" y="9" width="6" height="6"></rect><line x1="9" y1="1" x2="9" y2="4"></line><line x1="15" y1="1" x2="15" y2="4"></line><line x1="9" y1="20" x2="9" y2="23"></line><line x1="15" y1="20" x2="15" y2="23"></line><line x1="20" y1="9" x2="23" y2="9"></line><line x1="20" y1="14" x2="23" y2="14"></line><line x1="1" y1="9" x2="4" y2="9"></line><line x1="1" y1="14" x2="4" y2="14"></line></svg>
                Tech Stack & Bahasa
            </div>
            <div class="tags">
                <span class="tag">JavaScript (ES6+)</span>
                <span class="tag">TypeScript</span>
                <span class="tag">React.js</span>
                <span class="tag">Tailwind CSS</span>
                <span class="tag">Next.js</span>
                <span class="tag">Node.js</span>
                <span class="tag">Cybersecurity</span>
                <span class="tag">UI/UX Design</span>
                <span class="tag">Git & GitHub</span>
                <span class="tag">Dark Mode Architecture</span>
            </div>
        </section>

        <!-- Grid Repositori (Pinned) -->
        <section>
            <div class="section-title">
                <!-- Ikon Buku SVG -->
                <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M4 19.5A2.5 2.5 0 0 1 6.5 17H20"></path><path d="M6.5 2H20v20H6.5A2.5 2.5 0 0 1 4 19.5v-15A2.5 2.5 0 0 1 6.5 2z"></path></svg>
                Repositori Populer
            </div>
            
            <div class="repo-grid">
                <!-- Repo 1 -->
                <article class="repo-card">
                    <div class="repo-header">
                        <a href="#" class="repo-name">red-ui-kit</a>
                        <span class="repo-visibility">Public</span>
                    </div>
                    <p class="repo-desc">Komponen UI modular dengan tema merah gelap, cocok untuk dashboard admin dan aplikasi cybersecurity.</p>
                    <div class="repo-meta">
                        <span><span class="language-dot lang-js"></span> JavaScript</span>
                        <span>★ 845</span>
                        <span>⑂ 120</span>
                    </div>
                </article>

                <!-- Repo 2 -->
                <article class="repo-card">
                    <div class="repo-header">
                        <a href="#" class="repo-name">dark-portfolio-v1</a>
                        <span class="repo-visibility">Public</span>
                    </div>
                    <p class="repo-desc">Template portofolio statis berkinerja tinggi tanpa framework, hanya HTML dan CSS murni.</p>
                    <div class="repo-meta">
                        <span><span class="language-dot lang-html"></span> HTML</span>
                        <span>★ 320</span>
                        <span>⑂ 45</span>
                    </div>
                </article>

                <!-- Repo 3 -->
                <article class="repo-card">
                    <div class="repo-header">
                        <a href="#" class="repo-name">security-scanner</a>
                        <span class="repo-visibility">Public</span>
                    </div>
                    <p class="repo-desc">Script otomatisasi sederhana untuk memindai kerentanan dasar pada aplikasi web statis.</p>
                    <div class="repo-meta">
                        <span><span class="language-dot lang-py"></span> Python</span>
                        <span>★ 512</span>
                        <span>⑂ 89</span>
                    </div>
                </article>

                <!-- Repo 4 -->
                <article class="repo-card">
                    <div class="repo-header">
                        <a href="#" class="repo-name">cyber-glitch-effects</a>
                        <span class="repo-visibility">Public</span>
                    </div>
                    <p class="repo-desc">Kumpulan efek glitch CSS dan SVG untuk memberikan nuansa futuristik yang kacau pada website.</p>
                    <div class="repo-meta">
                        <span><span class="language-dot lang-css"></span> CSS</span>
                        <span>★ 1.1k</span>
                        <span>⑂ 230</span>
                    </div>
                </article>
                 <!-- Repo 5 -->
                 <article class="repo-card">
                    <div class="repo-header">
                        <a href="#" class="repo-name">terminal-manager</a>
                        <span class="repo-visibility">Public</span>
                    </div>
                    <p class="repo-desc">Manajer berkas berbasis terminal (TUI) dengan kustomisasi tema warna mendalam.</p>
                    <div class="repo-meta">
                        <span><span class="language-dot lang-py"></span> Python</span>
                        <span>★ 156</span>
                        <span>⑂ 12</span>
                    </div>
                </article>

                 <!-- Repo 6 -->
                 <article class="repo-card">
                    <div class="repo-header">
                        <a href="#" class="repo-name">api-gateway-red</a>
                        <span class="repo-visibility">Public</span>
                    </div>
                    <p class="repo-desc">Microservices gateway ringan dengan logging visual berwarna merah untuk error tracking.</p>
                    <div class="repo-meta">
                        <span><span class="language-dot lang-js"></span> Node.js</span>
                        <span>★ 210</span>
                        <span>⑂ 34</span>
                    </div>
                </article>
            </div>
        </section>

        <!-- Grafik Kontribusi (Visual) -->
        <section class="contribution-graph">
            <div class="graph-title">2,493 kontribusi pada tahun terakhir</div>
            <div class="squares" id="graphGrid">
                <!-- Kotak-kotak akan digenerate oleh JS agar kode lebih bersih, tapi saya tulis manual di sini agar tanpa JS dependency -->
                <!-- Menggunakan loop inline sedikit untuk mensimulasikan banyak kotak -->
                <script>
                    for(let i=0; i<30; i++) {
                        document.write(`<div class="col">`);
                        for(let j=0; j<7; j++) {
                            // Random level warna
                            const level = Math.floor(Math.random() * 5); 
                            let cls = 'sq';
                            if(level === 1) cls += ' l1';
                            if(level === 2) cls += ' l2';
                            if(level === 3) cls += ' l3';
                            if(level === 4) cls += ' l4';
                            document.write(`<div class="${cls}" title="Activity"></div>`);
                        }
                        document.write(`</div>`);
                    }
                </script>
            </div>
        </section>

        <footer>
            <p>❤️ Dibuat dengan kode dan darah. <a href="#" style="text-decoration: underline;">GitHub</a> &copy; 2023</p>
        </footer>
    </div>

</body>
</html>
