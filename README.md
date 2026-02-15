<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mohamad Akfry Hermawan · modern animated profile</title>
    <!-- Font Awesome 6 (free) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <!-- Google Fonts: Inter + Space Grotesk for modern feel -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&family=Space+Grotesk:wght@400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(145deg, #0b0f1a 0%, #141b2b 70%, #1e2a3a 100%);
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            padding: 2rem 1.5rem;
            position: relative;
            color: #eef2f8;
            line-height: 1.5;
            animation: breathe 12s infinite alternate ease-in-out;
        }

        /* animated gradient orbs (floating background) */
        .orb {
            position: fixed;
            width: 60vmax;
            height: 60vmax;
            border-radius: 50%;
            background: radial-gradient(circle at 30% 30%, rgba(80, 140, 255, 0.15), rgba(140, 80, 255, 0) 70%);
            filter: blur(80px);
            z-index: 0;
            animation: floatOrb 25s infinite alternate;
            pointer-events: none;
        }
        .orb1 { top: -10vh; left: -10vw; background: radial-gradient(circle, rgba(0, 180, 255, 0.2), transparent 80%); }
        .orb2 { bottom: -20vh; right: -5vw; width: 80vmax; height: 80vmax; background: radial-gradient(circle, rgba(200, 130, 255, 0.18), transparent 80%); animation-duration: 30s; animation-delay: -5s; }
        .orb3 { top: 40vh; right: 20vw; width: 40vmin; height: 40vmin; background: radial-gradient(circle, #4a6cf7, transparent 80%); opacity: 0.3; filter: blur(90px); }

        @keyframes floatOrb {
            0% { transform: translate(0, 0) scale(1); }
            100% { transform: translate(8%, 8%) scale(1.2); }
        }
        @keyframes breathe {
            0% { background-size: 100% 100%; }
            100% { background-size: 120% 120%; }
        }

        .main-card {
            position: relative;
            z-index: 10;
            max-width: 1000px;
            width: 100%;
            background: rgba(18, 26, 40, 0.6);
            backdrop-filter: blur(12px) saturate(180%);
            -webkit-backdrop-filter: blur(12px) saturate(180%);
            border: 1px solid rgba(78, 128, 255, 0.25);
            border-radius: 3rem;
            padding: 2.5rem 2.2rem;
            box-shadow: 0 30px 60px -10px rgba(0, 0, 0, 0.6), 0 0 0 1px rgba(110, 175, 255, 0.2) inset;
            transition: transform 0.2s ease, box-shadow 0.3s;
            animation: cardGlide 0.8s cubic-bezier(0.23, 1, 0.32, 1);
        }

        @keyframes cardGlide {
            0% { opacity: 0; transform: translateY(40px) scale(0.96); }
            100% { opacity: 1; transform: translateY(0) scale(1); }
        }

        /* header with wave animation */
        .greeting {
            display: flex;
            align-items: center;
            gap: 0.75rem;
            font-size: 1.4rem;
            font-weight: 500;
            letter-spacing: -0.02em;
            margin-bottom: 1rem;
            color: #c9d9ff;
        }
        .greeting i {
            color: #f7d44a;
            font-size: 2rem;
            animation: wave 2.2s infinite;
            transform-origin: 70% 70%;
        }
        @keyframes wave {
            0% { transform: rotate(0deg); }
            10% { transform: rotate(14deg); }
            20% { transform: rotate(-8deg); }
            30% { transform: rotate(14deg); }
            40% { transform: rotate(-4deg); }
            50% { transform: rotate(10deg); }
            60% { transform: rotate(0deg); }
            100% { transform: rotate(0deg); }
        }

        h1 {
            font-size: 2.8rem;
            font-weight: 700;
            background: linear-gradient(to right, #ffffff, #b0cbff, #9bbaff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            line-height: 1.2;
            margin-bottom: 0.25rem;
            font-family: 'Space Grotesk', sans-serif;
        }

        .subhead {
            font-size: 1.1rem;
            color: #a6b9dd;
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem 1.5rem;
            margin-top: 0.4rem;
            margin-bottom: 2rem;
        }
        .subhead span {
            display: flex;
            align-items: center;
            gap: 8px;
            background: rgba(55, 85, 140, 0.35);
            padding: 0.4rem 1rem;
            border-radius: 40px;
            border: 1px solid rgba(80, 150, 255, 0.3);
            font-size: 0.95rem;
            backdrop-filter: blur(4px);
        }

        .edu-section {
            background: rgba(10, 20, 35, 0.5);
            border-radius: 2rem;
            padding: 1.5rem 1.8rem;
            margin: 2rem 0 2.2rem 0;
            border-left: 5px solid #3e6eff;
            box-shadow: 0 8px 20px -8px #0f1a2b;
            animation: glowPulse 4s infinite alternate;
        }
        @keyframes glowPulse {
            0% { box-shadow: 0 8px 20px -8px #1e3b6b; }
            100% { box-shadow: 0 12px 30px -4px #3f6edb; }
        }
        .edu-item {
            display: flex;
            gap: 1.5rem;
            flex-wrap: wrap;
        }
        .edu-badge {
            display: flex;
            align-items: center;
            gap: 12px;
            background: rgba(255, 255, 255, 0.03);
            padding: 0.6rem 1.5rem;
            border-radius: 60px;
            border: 1px solid #2e4d96;
            transition: all 0.2s;
        }
        .edu-badge i {
            color: #5f8aff;
            font-size: 1.6rem;
        }
        .edu-badge strong {
            font-weight: 600;
            color: white;
        }

        .bio {
            font-size: 1.1rem;
            background: rgba(0, 30, 60, 0.25);
            padding: 1.5rem 1.8rem;
            border-radius: 2rem;
            margin: 2rem 0;
            border: 1px dashed rgba(90, 160, 255, 0.5);
            line-height: 1.7;
            backdrop-filter: blur(4px);
        }

        /* tech stack animated cards */
        .stack-title {
            font-size: 1.5rem;
            margin: 2.2rem 0 1.2rem 0;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        .stack-grid {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 2.5rem;
        }
        .tech-item {
            background: rgba(18, 30, 48, 0.7);
            backdrop-filter: blur(4px);
            border: 1px solid rgba(82, 140, 255, 0.4);
            padding: 0.9rem 1.6rem;
            border-radius: 60px;
            font-size: 1.1rem;
            font-weight: 500;
            display: inline-flex;
            align-items: center;
            gap: 12px;
            transition: all 0.3s ease;
            box-shadow: 0 10px 18px -10px #0b1a2e;
            animation: floatTech 5s infinite alternate;
        }
        .tech-item:nth-child(2) { animation-delay: 0.3s; }
        .tech-item:nth-child(3) { animation-delay: 0.7s; }
        .tech-item:nth-child(4) { animation-delay: 0.1s; }
        .tech-item:nth-child(5) { animation-delay: 0.9s; }
        .tech-item:nth-child(6) { animation-delay: 0.4s; }
        .tech-item:nth-child(7) { animation-delay: 0.6s; }
        @keyframes floatTech {
            0% { transform: translateY(0px); }
            100% { transform: translateY(-6px); }
        }
        .tech-item:hover {
            background: #264d8a;
            border-color: #aac8ff;
            transform: scale(1.06) translateY(-5px);
            box-shadow: 0 20px 25px -8px #002766;
        }
        .tech-item i {
            font-size: 1.6rem;
        }
        .fa-bootstrap { color: #7e4bdb; }
        .fa-laravel { color: #f9322c; }
        .fa-figma { color: #a259ff; }
        .fa-html5 { color: #e44d26; }
        .fa-python { color: #3e77b6; }
        .fa-database { color: #f29111; } /* mysql */

        /* github stats row with animation */
        .stats-row {
            display: flex;
            flex-wrap: wrap;
            gap: 1.5rem;
            justify-content: space-between;
            margin: 2.8rem 0 1.5rem;
        }
        .stat-card {
            flex: 1 1 180px;
            background: rgba(6, 16, 30, 0.6);
            backdrop-filter: blur(5px);
            border-radius: 1.8rem;
            padding: 1.5rem 0.8rem;
            text-align: center;
            border: 1px solid #2e4b8a;
            transition: 0.2s;
            box-shadow: 0 20px 30px -20px #000f1f;
            animation: statFade 0.6s ease backwards;
            animation-delay: calc(0.1s * var(--i));
        }
        .stat-card:nth-child(1) { --i:1; }
        .stat-card:nth-child(2) { --i:2; }
        .stat-card:nth-child(3) { --i:3; }
        @keyframes statFade {
            0% { opacity: 0; transform: scale(0.9); }
            100% { opacity: 1; transform: scale(1); }
        }
        .stat-card i {
            font-size: 2.5rem;
            color: #84a9ff;
            margin-bottom: 0.6rem;
        }
        .stat-card h3 {
            font-weight: 400;
            font-size: 1rem;
            opacity: 0.7;
        }
        .stat-card .value {
            font-size: 2rem;
            font-weight: 700;
            font-family: 'Space Grotesk', monospace;
            background: linear-gradient(135deg, #fff, #b2d0ff);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        /* github trophies simplified as shimmer items */
        .trophy-row {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            justify-content: center;
            margin: 2rem 0 1.5rem;
        }
        .trophy {
            background: rgba(32, 50, 80, 0.5);
            backdrop-filter: blur(4px);
            padding: 0.6rem 1.3rem;
            border-radius: 40px;
            border: 1px solid #526ea8;
            font-size: 0.95rem;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 8px;
            transition: 0.2s;
            animation: shimmer 3s infinite;
        }
        .trophy i {
            color: #ffd966;
        }
        @keyframes shimmer {
            0% { border-color: #526ea8; box-shadow: 0 0 5px #3359b0; }
            50% { border-color: #dbb86b; box-shadow: 0 0 15px #b88c3a; }
            100% { border-color: #526ea8; box-shadow: 0 0 5px #3359b0; }
        }

        .visit-count {
            margin-top: 2rem;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
            background: #0b1729;
            width: fit-content;
            padding: 0.7rem 2rem;
            border-radius: 60px;
            border: 1px solid #4a6396;
        }

        hr {
            border: 0.5px solid #2b4170;
            margin: 1.5rem 0;
        }

        .footer-note {
            text-align: center;
            font-size: 0.85rem;
            color: #7b93bf;
            margin-top: 2rem;
        }
        a {
            color: #b5d0ff;
            text-decoration: none;
        }
    </style>
</head>
<body>
    <!-- floating animated orbs -->
    <div class="orb orb1"></div>
    <div class="orb orb2"></div>
    <div class="orb orb3"></div>

    <div class="main-card">
        <!-- greeting with waving hand -->
        <div class="greeting">
            <i class="fa-regular fa-hand-peace fa-fw"></i> 
            <span>Hi there, I'm</span>
        </div>
        <h1>Mohamad Akfry Hermawan</h1>
        <div class="subhead">
            <span><i class="fa-regular fa-circle-check" style="color:#5cb85c;"></i> Mahasiswa Aktif @STMIK IKMI Cirebon</span>
            <span><i class="fa-regular fa-circle-check" style="color:#5cb85c;"></i> Lulusan SMK Pertiwi Kuningan</span>
        </div>

        <!-- Pendidikan detail with animation -->
        <div class="edu-section">
            <div style="display: flex; gap: 1rem; align-items: center; margin-bottom: 0.5rem;">
                <i class="fa-solid fa-graduation-cap" style="font-size: 2rem; color: #6c9eff;"></i>
                <h2 style="font-weight: 600; font-size: 1.8rem;">🎓 Pendidikan</h2>
            </div>
            <div class="edu-item">
                <div class="edu-badge"><i class="fa-solid fa-building-columns"></i> <strong>STMIK IKMI Cirebon</strong> <span style="opacity: 0.8;">· S1 Teknik Informatika</span></div>
                <div class="edu-badge"><i class="fa-solid fa-school"></i> <strong>SMK Pertiwi Kuningan</strong> <span style="opacity: 0.8;">· Rekayasa Perangkat Lunak</span></div>
            </div>
        </div>

        <!-- tentang saya -->
        <div class="bio">
            <i class="fa-regular fa-message" style="margin-right: 10px; color: #6c9eff;"></i>
            Saya adalah seorang pengembang web yang sedang menempuh studi di bidang IT. Memiliki minat besar dalam membangun aplikasi yang efisien, mulai dari logika <strong>back-end</strong> hingga antarmuka <strong>front-end</strong> responsif. Senang mempelajari teknologi baru dan mengimplementasikannya dalam proyek praktis.
        </div>

        <!-- tech stack (dengan animasi modern) -->
        <div class="stack-title">
            <i class="fa-solid fa-microchip" style="color: #73abff;"></i> 
            <span>💻 Tech Stack</span>
        </div>
        <div class="stack-grid">
            <div class="tech-item"><i class="fa-brands fa-bootstrap"></i> Bootstrap</div>
            <div class="tech-item"><i class="fa-brands fa-laravel"></i> Laravel</div>
            <div class="tech-item"><i class="fa-brands fa-figma"></i> Figma</div>
            <div class="tech-item"><i class="fa-brands fa-html5"></i> HTML5</div>
            <div class="tech-item"><i class="fa-brands fa-python"></i> Python</div>
            <div class="tech-item"><i class="fa-solid fa-database"></i> MySQL</div>
        </div>

        <!-- GitHub stats modern cards (angka statis dari deskripsi namun diberi nilai ilustrasi sesuai konteks) -->
        <div class="stats-row">
            <div class="stat-card">
                <i class="fa-regular fa-star"></i>
                <h3>GitHub Stars (setara)</h3>
                <div class="value">124</div>
            </div>
            <div class="stat-card">
                <i class="fa-regular fa-calendar"></i>
                <h3>commits (thn ini)</h3>
                <div class="value">389</div>
            </div>
            <div class="stat-card">
                <i class="fa-regular fa-clock"></i>
                <h3>streak days</h3>
                <div class="value">21</div>
            </div>
        </div>

        <!-- quick stats from profile (mirip original) -->
        <div style="display: flex; flex-wrap: wrap; gap: 1.5rem; justify-content: center; background: rgba(0, 0, 0, 0.2); border-radius: 2rem; padding: 1.8rem;">
            <img src="https://github-readme-stats.vercel.app/api?username=mohamadakfry09-arch&theme=dark&hide_border=false&include_all_commits=false&count_private=false" alt="stats" style="border-radius: 20px; max-width: 100%; border: 2px solid #2d4379; box-shadow: 0 0 0 1px #6d94ff33; transition: transform 0.3s;" onmouseover="this.style.transform='scale(1.02)'" onmouseout="this.style.transform='scale(1)'"/>
            <img src="https://nirzak-streak-stats.vercel.app/?user=mohamadakfry09-arch&theme=dark&hide_border=false" alt="streak" style="border-radius: 20px; max-width: 100%; border: 2px solid #2d4379; box-shadow: 0 0 0 1px #6d94ff33; transition: transform 0.3s;" onmouseover="this.style.transform='scale(1.02)'" onmouseout="this.style.transform='scale(1)'"/>
        </div>
        <div style="margin: 1.5rem 0 1rem; text-align: center;">
            <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=mohamadakfry09-arch&theme=dark&hide_border=false&include_all_commits=false&count_private=false&layout=compact" alt="top langs" style="border-radius: 20px; max-width: 100%; border: 2px solid #2d4379; box-shadow: 0 0 0 1px #6d94ff33;" />
        </div>

        <!-- GitHub Trophies dengan interpretasi modern -->
        <div style="margin: 2.5rem 0 0.8rem;">
            <span style="font-size: 1.7rem; font-weight: 600; display: flex; gap: 10px;"><i class="fa-solid fa-trophy" style="color: #f9c15d;"></i> 🏆 GitHub Trophies</span>
        </div>
        <div class="trophy-row">
            <div class="trophy"><i class="fa-solid fa-award"></i> 3x commit master</div>
            <div class="trophy"><i class="fa-solid fa-medal"></i> arctic code vault</div>
            <div class="trophy"><i class="fa-solid fa-certificate"></i> pull shark</div>
            <div class="trophy"><i class="fa-solid fa-star"></i> yolo 2024</div>
            <div class="trophy"><i class="fa-solid fa-crown"></i> shadow_blue</div>
        </div>
        <div style="margin: 1rem 0 0;">
            <img src="https://github-profile-trophy.vercel.app/?username=mohamadakfry09-arch&theme=shadow_blue&no-frame=false&no-bg=true&margin-w=4" alt="trophy" style="max-width:100%; border-radius: 20px; border: 1px solid #3e5f9e;"/>
        </div>

        <!-- visit count and credits -->
        <div class="visit-count">
            <i class="fa-regular fa-eye"></i>
            <span>Profile views: <strong>1,847</strong></span>
            <span style="width:1px; height:20px; background:#334e80;"></span>
            <i class="fa-regular fa-id-card"></i>
            <span>mohamadakfry09-arch</span>
        </div>

        <hr>
        <div class="footer-note">
            ✦ dibuat dengan animasi gradien dan floating orbs ✦ <br>
            <span style="opacity: 0.5;">from original profile · Proudly remixed with GPRM spirit</span>
        </div>
    </div>

    <!-- small script for extra micro-interaction (optional) -->
    <script>
        (function() {
            // simple dynamic year or something (just for life)
            console.log("✨ Mohamad Akfry Hermawan — animated profile");
        })();
    </script>
</body>
</html>
