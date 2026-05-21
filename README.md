# index.html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ajay Gaming - Free Fire</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            color: #333;
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, #ff6b00 0%, #ff8c00 100%);
            color: white;
            padding: 20px 0;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }

        nav a {
            color: white;
            text-decoration: none;
            transition: 0.3s;
        }

        nav a:hover {
            opacity: 0.8;
            text-shadow: 0 0 10px rgba(255,255,255,0.5);
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            color: white;
            padding: 150px 20px 100px;
            margin-top: 70px;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1200 600"><defs><pattern id="grid" width="40" height="40" patternUnits="userSpaceOnUse"><path d="M 40 0 L 0 0 0 40" fill="none" stroke="rgba(255,107,0,0.1)" stroke-width="1"/></pattern></defs><rect width="1200" height="600" fill="url(%23grid)"/></svg>');
            opacity: 0.5;
        }

        .hero-content {
            position: relative;
            z-index: 1;
            max-width: 800px;
            margin: 0 auto;
        }

        .hero h1 {
            font-size: 54px;
            margin-bottom: 20px;
            text-shadow: 0 4px 20px rgba(0,0,0,0.5);
            animation: slideIn 0.8s ease-out;
        }

        .hero p {
            font-size: 20px;
            margin-bottom: 30px;
            opacity: 0.9;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
        }

        .btn {
            padding: 15px 40px;
            font-size: 16px;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: 0.3s;
            font-weight: bold;
            text-decoration: none;
            display: inline-block;
        }

        .btn-primary {
            background: linear-gradient(135deg, #ff6b00 0%, #ff8c00 100%);
            color: white;
            box-shadow: 0 5px 20px rgba(255,107,0,0.4);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(255,107,0,0.6);
        }

        .btn-secondary {
            background: transparent;
            color: white;
            border: 2px solid white;
        }

        .btn-secondary:hover {
            background: white;
            color: #ff6b00;
        }

        /* Features Section */
        .features {
            padding: 80px 20px;
            background: #f5f5f5;
        }

        .features h2 {
            text-align: center;
            font-size: 36px;
            margin-bottom: 60px;
            color: #1a1a1a;
        }

        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
        }

        .feature-card {
            background: white;
            padding: 30px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: 0.3s;
        }

        .feature-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }

        .feature-icon {
            width: 60px;
            height: 60px;
            margin: 0 auto 20px;
            background: linear-gradient(135deg, #ff6b00 0%, #ff8c00 100%);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 30px;
        }

        .feature-card h3 {
            color: #ff6b00;
            margin-bottom: 10px;
        }

        .feature-card p {
            color: #666;
        }

        /* Game Modes Section */
        .game-modes {
            padding: 80px 20px;
            background: white;
        }

        .game-modes h2 {
            text-align: center;
            font-size: 36px;
            margin-bottom: 60px;
        }

        .modes-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 25px;
        }

        .mode-card {
            background: linear-gradient(135deg, #1a1a1a 0%, #2d2d2d 100%);
            color: white;
            padding: 40px 20px;
            border-radius: 10px;
            text-align: center;
            border: 2px solid #ff6b00;
        }

        .mode-card h3 {
            font-size: 24px;
            margin-bottom: 15px;
            color: #ff6b00;
        }

        /* Stats Section */
        .stats {
            background: linear-gradient(135deg, #ff6b00 0%, #ff8c00 100%);
            color: white;
            padding: 60px 20px;
            text-align: center;
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .stat-item h3 {
            font-size: 40px;
            margin-bottom: 10px;
        }

        .stat-item p {
            font-size: 16px;
            opacity: 0.9;
        }

        /* Footer */
        footer {
            background: #1a1a1a;
            color: white;
            padding: 40px 20px;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-bottom: 20px;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: #ff6b00;
            text-decoration: none;
            transition: 0.3s;
        }

        .footer-links a:hover {
            color: white;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            background: #ff6b00;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: 0.3s;
        }

        .social-links a:hover {
            background: white;
            color: #ff6b00;
            transform: scale(1.2);
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @media (max-width: 768px) {
            nav ul {
                gap: 15px;
                font-size: 14px;
            }

            .hero h1 {
                font-size: 36px;
            }

            .hero p {
                font-size: 16px;
            }

            .cta-buttons {
                flex-direction: column;
            }

            .btn {
                width: 100%;
            }

            .features h2, .game-modes h2 {
                font-size: 28px;
            }

            .stats-grid {
                grid-template-columns: 1fr;
            }

            .footer-links {
                flex-direction: column;
                gap: 15px;
            }
        }
    </style>
</head>
<body>
    <!-- Header/Navigation -->
    <header>
        <nav class="container">
            <div class="logo">🎮 AJAY GAMING</div>
            <ul>
                <li><a href="#features">Features</a></li>
                <li><a href="#modes">Game Modes</a></li>
                <li><a href="#download">Download</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>🔥 AJAY GAMING PRESENTS 🔥</h1>
            <h1 style="font-size: 48px; color: #ff6b00;">FREE FIRE</h1>
            <p>Experience the ultimate battle royale game. Land, loot, fight, and emerge as the last survivor!</p>
            <div class="cta-buttons">
                <button class="btn btn-primary">Download Now</button>
                <button class="btn btn-secondary">Watch Trailer</button>
            </div>
        </div>
    </section>

    <!-- Features Section -->
    <section class="features" id="features">
        <div class="container">
            <h2>Why Choose Free Fire?</h2>
            <div class="features-grid">
                <div class="feature-card">
                    <div class="feature-icon">⚡</div>
                    <h3>Fast-Paced Action</h3>
                    <p>10-minute matches packed with intense gameplay and non-stop action.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎨</div>
                    <h3>Stunning Graphics</h3>
                    <p>Beautiful HD graphics optimized for smooth performance on all devices.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">👥</div>
                    <h3>Play with Friends</h3>
                    <p>Team up with friends and dominate the battlefield together.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🏆</div>
                    <h3>Ranked Matches</h3>
                    <p>Climb the ranks and prove you're the best player in the world.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🎯</div>
                    <h3>Strategic Gameplay</h3>
                    <p>Land wisely, manage resources, and outplay your opponents.</p>
                </div>
                <div class="feature-card">
                    <div class="feature-icon">🌍</div>
                    <h3>Global Community</h3>
                    <p>Play with millions of players worldwide in real-time matches.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Game Modes Section -->
    <section class="game-modes" id="modes">
        <div class="container">
            <h2>Game Modes</h2>
            <div class="modes-grid">
                <div class="mode-card">
                    <h3>Battle Royale</h3>
                    <p>Classic 50v50 battle royale mode. Land on the island, fight 49 other players, and be the last one standing!</p>
                </div>
                <div class="mode-card">
                    <h3>Clash Squad</h3>
                    <p>Fast-paced 4v4 team matches. Work with your squad to eliminate the opposing team.</p>
                </div>
                <div class="mode-card">
                    <h3>Deathmatch</h3>
                    <p>Non-stop action in confined arenas. Free-for-all or team-based combat modes.</p>
                </div>
                <div class="mode-card">
                    <h3>Craftland</h3>
                    <p>Survival mode where you craft weapons, build structures, and fight zombies and players.</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <section class="stats">
        <div class="stats-grid">
            <div class="stat-item">
                <h3>500M+</h3>
                <p>Players Worldwide</p>
            </div>
            <div class="stat-item">
                <h3>150+</h3>
                <p>Countries</p>
            </div>
            <div class="stat-item">
                <h3>4.5⭐</h3>
                <p>App Rating</p>
            </div>
            <div class="stat-item">
                <h3>24/7</h3>
                <p>Live Support</p>
            </div>
        </div>
    </section>

    <!-- Download Section -->
    <section class="features" id="download">
        <div class="container">
            <h2 style="text-align: center; margin-bottom: 40px;">Download Free Fire</h2>
            <div style="text-align: center;">
                <p style="font-size: 18px; margin-bottom: 30px; color: #666;">Available on iOS, Android, and PC</p>
                <div class="cta-buttons" style="justify-content: center;">
                    <button class="btn btn-primary">📱 iOS App Store</button>
                    <button class="btn btn-primary">🤖 Google Play</button>
                    <button class="btn btn-primary">💻 PC Download</button>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <h3>🎮 AJAY GAMING 🎮</h3>
            <p style="margin: 15px 0; color: #999;">The Ultimate Battle Royale Experience</p>
            <div class="footer-links">
                <a href="#">Privacy Policy</a>
                <a href="#">Terms & Conditions</a>
                <a href="#">Support</a>
                <a href="#">Blog</a>
                <a href="#">Careers</a>
            </div>
            <div class="social-links">
                <a href="#" title="Facebook">f</a>
                <a href="#" title="Twitter">𝕏</a>
                <a href="#" title="Instagram">📷</a>
                <a href="#" title="YouTube">▶</a>
                <a href="#" title="Discord">💬</a>
            </div>
            <p style="margin-top: 30px; color: #999; font-size: 14px;">© 2026 AJAY GAMING. All rights reserved.</p>
        </div>
    </footer>
</body>
</html>
