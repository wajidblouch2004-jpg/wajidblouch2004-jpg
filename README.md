<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wajid Hussain | Full Stack Developer</title>
    <!-- Google Fonts for Modern Typography -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;600;700&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        /* --- CSS Variables & Reset --- */
        :root {
            --bg-color: #0f172a;
            --card-bg: rgba(30, 41, 59, 0.7);
            --text-primary: #f8fafc;
            --text-secondary: #94a3b8;
            --accent-color: #38bdf8; /* Cyan */
            --accent-gradient: linear-gradient(135deg, #38bdf8 0%, #818cf8 100%);
            --border-color: rgba(255, 255, 255, 0.1);
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-primary);
            line-height: 1.6;
            min-height: 100vh;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            /* Subtle background pattern */
            background-image: 
                radial-gradient(at 0% 0%, hsla(253,16%,7%,1) 0, transparent 50%), 
                radial-gradient(at 50% 0%, hsla(225,39%,30%,1) 0, transparent 50%), 
                radial-gradient(at 100% 0%, hsla(339,49%,30%,1) 0, transparent 50%);
            padding: 2rem;
        }

        /* --- Layout Container --- */
        .container {
            width: 100%;
            max-width: 800px;
            text-align: center;
            animation: fadeIn 1s ease-out;
        }

        /* --- Profile Section --- */
        .profile-header {
            margin-bottom: 3rem;
        }

        .avatar-container {
            position: relative;
            width: 140px;
            height: 140px;
            margin: 0 auto 1.5rem;
        }

        .avatar {
            width: 100%;
            height: 100%;
            border-radius: 50%;
            object-fit: cover;
            border: 4px solid var(--bg-color);
            box-shadow: 0 0 20px rgba(56, 189, 248, 0.5);
            transition: transform 0.3s ease;
        }

        .avatar:hover {
            transform: scale(1.05);
        }

        .greeting {
            color: var(--accent-color);
            font-weight: 600;
            font-size: 1.1rem;
            margin-bottom: 0.5rem;
            display: block;
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            background: var(--accent-gradient);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -0.5px;
        }

        .role {
            color: var(--text-secondary);
            font-size: 1.1rem;
            font-weight: 300;
        }

        /* --- Value Props / Highlights --- */
        .highlights {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
            margin: 2rem 0;
        }

        .badge {
            background: rgba(56, 189, 248, 0.1);
            color: var(--accent-color);
            padding: 0.5rem 1rem;
            border-radius: 50px;
            font-size: 0.9rem;
            font-weight: 500;
            border: 1px solid rgba(56, 189, 248, 0.2);
            transition: all 0.3s ease;
        }

        .badge:hover {
            background: rgba(56, 189, 248, 0.2);
            transform: translateY(-2px);
        }

        /* --- Tech Stack Section --- */
        .section-title {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            width: 50%;
            height: 3px;
            background: var(--accent-gradient);
            bottom: -10px;
            left: 25%;
            border-radius: 2px;
        }

        .tech-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .tech-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            color: var(--text-secondary);
            transition: transform 0.3s ease, color 0.3s ease;
            cursor: default;
        }

        .tech-item i {
            font-size: 3rem;
            margin-bottom: 0.8rem;
            transition: all 0.3s ease;
        }

        /* Tech Specific Colors */
        .fa-html5 { color: #e34c26; }
        .fa-css3-alt { color: #264de4; }
        .fa-js { color: #f0db4f; }
        .fa-react { color: #61dbfb; }
        .fa-laravel { color: #ff2d20; }
        .fa-wordpress { color: #21759b; }
        .fa-database { color: #fff; } /* Generic DB icon */

        .tech-item:hover {
            color: var(--text-primary);
            transform: translateY(-5px);
        }

        .tech-item:hover i {
            filter: drop-shadow(0 0 10px rgba(255, 255, 255, 0.3));
        }

        /* --- Contact Section --- */
        .contact-card {
            background: var(--card-bg);
            backdrop-filter: blur(10px);
            -webkit-backdrop-filter: blur(10px);
            border: 1px solid var(--border-color);
            border-radius: 16px;
            padding: 2.5rem;
            box-shadow: var(--shadow);
            margin-top: 1rem;
            animation: slideUp 1s ease-out 0.3s backwards;
        }

        .status-indicator {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            color: #4ade80; /* Green */
            font-weight: 500;
            margin-bottom: 1.5rem;
            font-size: 0.9rem;
            background: rgba(74, 222, 128, 0.1);
            padding: 0.3rem 0.8rem;
            border-radius: 6px;
        }

        .dot {
            width: 8px;
            height: 8px;
            background-color: #4ade80;
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        .btn-contact {
            display: inline-flex;
            align-items: center;
            gap: 0.8rem;
            background: var(--accent-gradient);
            color: white;
            text-decoration: none;
            padding: 0.8rem 2rem;
            border-radius: 8px;
            font-weight: 600;
            transition: transform 0.2s, box-shadow 0.2s;
        }

        .btn-contact:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 20px -10px rgba(56, 189, 248, 0.5);
        }

        /* --- Footer --- */
        footer {
            margin-top: 3rem;
            color: var(--text-secondary);
            font-size: 0.85rem;
        }

        /* --- Animations --- */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes slideUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(74, 222, 128, 0.4); }
            70% { box-shadow: 0 0 0 6px rgba(74, 222, 128, 0); }
            100% { box-shadow: 0 0 0 0 rgba(74, 222, 128, 0); }
        }

        /* --- Responsive Adjustments --- */
        @media (max-width: 600px) {
            h1 { font-size: 2rem; }
            .tech-grid { gap: 1.5rem; }
            .tech-item i { font-size: 2.5rem; }
            .contact-card { padding: 1.5rem; }
        }
    </style>
</head>
<body>

    <div class="container">
        
        <!-- Profile Header -->
        <header class="profile-header">
            <div class="avatar-container">
                <!-- Using a high quality placeholder seed for consistency -->
                <img src="https://picsum.photos/seed/wajidhussain/200/200" alt="Wajid Hussain" class="avatar">
            </div>
            <span class="greeting">Hi there 👋, I'm</span>
            <h1>Wajid Hussain</h1>
            <p class="role">Full Stack Web Developer | React.js, Laravel & WordPress Expert</p>
        </header>

        <!-- Highlights / Value Prop -->
        <section class="highlights">
            <span class="badge">⚡ High-Performance</span>
            <span class="badge">🚀 Dynamic</span>
            <span class="badge">📈 Scalable</span>
        </section>

        <!-- Tech Stack -->
        <section>
            <h2 class="section-title">🛠 Tech Stack</h2>
            <div class="tech-grid">
                <!-- HTML5 -->
                <div class="tech-item" title="HTML5">
                    <i class="fab fa-html5"></i>
                    <span>HTML5</span>
                </div>
                <!-- CSS3 -->
                <div class="tech-item" title="CSS3">
                    <i class="fab fa-css3-alt"></i>
                    <span>CSS3</span>
                </div>
                <!-- JavaScript -->
                <div class="tech-item" title="JavaScript">
                    <i class="fab fa-js"></i>
                    <span>JavaScript</span>
                </div>
                <!-- React -->
                <div class="tech-item" title="React.js">
                    <i class="fab fa-react"></i>
                    <span>React.js</span>
                </div>
                <!-- Laravel -->
                <div class="tech-item" title="Laravel">
                    <i class="fab fa-laravel"></i>
                    <span>Laravel</span>
                </div>
                <!-- WordPress -->
                <div class="tech-item" title="WordPress">
                    <i class="fab fa-wordpress"></i>
                    <span>WordPress</span>
                </div>
                <!-- MySQL -->
                <div class="tech-item" title="MySQL">
                    <i class="fas fa-database"></i>
                    <span>MySQL</span>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section class="contact-card">
            <div class="status-indicator">
                <span class="dot"></span>
                <span>Currently Open for Projects</span>
            </div>
            <h3 style="margin-bottom: 1.5rem; font-size: 1.2rem;">Let's build something amazing together.</h3>
            <a href="https://linkedin.com/in/wajid-khan-b3ab97407" target="_blank" class="btn-contact">
                <i class="fab fa-linkedin"></i>
                Connect on LinkedIn
            </a>
        </section>

        <!-- Footer -->
        <footer>
            <p>© 2023 Wajid Hussain. Crafted with ❤️ and Code.</p>
        </footer>

    </div>

</body>
</html>
