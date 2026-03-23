<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>DarkPixel Gaming - Latest News, Reviews & Top Games</title>
    <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@400;700;900&family=Rajdhani:wght@300;400;600;700&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Rajdhani', sans-serif;
            background: linear-gradient(135deg, #0a0a0a 0%, #1a0d2e 50%, #16213e 100%);
            color: #e0e0e0;
            overflow-x: hidden;
        }

        /* Header & Navigation */
        header {
            background: rgba(0, 0, 0, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            padding: 1rem 0;
            box-shadow: 0 2px 20px rgba(255, 0, 150, 0.3);
        }

        nav {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-family: 'Orbitron', monospace;
            font-size: 2rem;
            font-weight: 900;
            background: linear-gradient(45deg, #ff00ff, #00ffff, #ff0080);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            text-shadow: 0 0 30px rgba(255, 0, 255, 0.5);
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #e0e0e0;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a:hover {
            color: #ff00ff;
            text-shadow: 0 0 10px #ff00ff;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: linear-gradient(90deg, #ff00ff, #00ffff);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            background: 
                radial-gradient(circle at 20% 80%, rgba(120, 119, 198, 0.3) 0%, transparent 50%),
                radial-gradient(circle at 80% 20%, rgba(255, 0, 255, 0.3) 0%, transparent 50%),
                linear-gradient(135deg, #0a0a0a 0%, #1a0d2e 100%);
            display: flex;
            align-items: center;
            justify-content: center;
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
            background: url('data:image/svg+xml,<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"><defs><pattern id="grid" width="10" height="10" patternUnits="userSpaceOnUse"><path d="M 10 0 L 0 0 0 10" fill="none" stroke="rgba(255,255,255,0.05)" stroke-width="0.5"/></pattern></defs><rect width="100" height="100" fill="url(%23grid)"/></svg>');
            animation: float 20s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .hero-content h1 {
            font-family: 'Orbitron', monospace;
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, #ff00ff, #00ffff, #ffffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 1rem;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 20px #ff00ff); }
            to { filter: drop-shadow(0 0 30px #00ffff); }
        }

        .hero-content p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .cta-button {
            display: inline-block;
            padding: 1rem 2rem;
            background: linear-gradient(45deg, #ff00ff, #00ffff);
            color: #000;
            text-decoration: none;
            font-weight: 700;
            font-size: 1.1rem;
            border-radius: 50px;
            transition: all 0.3s ease;
            box-shadow: 0 10px 30px rgba(255, 0, 255, 0.4);
        }

        .cta-button:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(255, 0, 255, 0.6);
        }

        /* Sections */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 4rem 2rem;
        }

        section {
            margin-bottom: 5rem;
        }

        h2 {
            font-family: 'Orbitron', monospace;
            font-size: 3rem;
            text-align: center;
            margin-bottom: 3rem;
            background: linear-gradient(45deg, #ff00ff, #00ffff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        /* News Grid */
        .news-grid, .reviews-grid, .top-games-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .card:hover::before {
            left: 100%;
        }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(255, 0, 255, 0.3);
            border-color: rgba(255, 0, 255, 0.5);
        }

        .card h3 {
            font-family: 'Orbitron', monospace;
            font-size: 1.5rem;
            margin-bottom: 1rem;
            color: #fff;
        }

        .card-meta {
            color: #888;
            font-size: 0.9rem;
            margin-bottom: 1rem;
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .rating {
            color: #ffd700;
            font-weight: bold;
        }

        /* Top Games - Special styling */
        .top-game-card {
            text-align: center;
        }

        .top-game-card img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            border-radius: 15px;
            margin-bottom: 1rem;
            filter: grayscale(50%);
            transition: filter 0.3s ease;
        }

        .top-game-card:hover img {
            filter: grayscale(0%);
        }

        .rank {
            position: absolute;
            top: 1rem;
            right: 1rem;
            background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
            color: white;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-weight: bold;
            font-size: 1.2rem;
            box-shadow: 0 5px 15px rgba(255, 107, 107, 0.4);
        }

        /* Contact Form */
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 1rem;
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 10px;
            color: #fff;
            font-family: inherit;
            transition: all 0.3s ease;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #ff00ff;
            box-shadow: 0 0 20px rgba(255, 0, 255, 0.3);
        }

        .form-group input::placeholder,
        .form-group textarea::placeholder {
            color: #888;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .container {
                padding: 2rem 1rem;
            }
        }

        /* Scroll to top */
        .scroll-top {
            position: fixed;
            bottom: 2rem;
            right: 2rem;
            background: linear-gradient(45deg, #ff00ff, #00ffff);
            color: #000;
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            opacity: 0;
            transition: all 0.3s ease;
            z-index: 1000;
        }

        .scroll-top.show {
            opacity: 1;
        }
    </style>
</head>
<body>
    <!-- Header -->
    <header>
        <nav>
            <div class="logo">DarkPixel</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#news">News</a></li>
                <li><a href="#reviews">Reviews</a></li>
                <li><a href="#top-games">Top Games</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section id="home" class="hero">
        <div class="hero-content">
            <h1>DarkPixel Gaming</h1>
            <p>Latest News • In-Depth Reviews • Top Games of All Time</p>
            <a href="#news" class="cta-button">Explore Latest News</a>
        </div>
    </section>

    <!-- Latest News -->
    <section id="news" class="container">
        <h2><i class="fas fa-newspaper"></i> Latest Game News</h2>
        <div class="news-grid">
            <div class="card">
                <div class="card-meta">
                    <i class="fas fa-clock"></i> 2 hours ago
                    <i class="fas fa-user"></i> By Alex R.
                </div>
                <h3>Cyberpunk 2077: Phantom Liberty Wins GOTY 2023</h3>
                <p>CD Projekt RED's expansion takes home Game of the Year, proving that redemption arcs are real in gaming.</p>
            </div>
            <div class="card">
                <div class="card-meta">
                    <i class="fas fa-clock"></i> 5 hours ago
                    <i class="fas fa-user"></i> By Sarah K.
                </div>
                <h3>Nintendo Switch 2 Rumors: 12GB RAM Confirmed?</h3>
                <p>Leaked specs suggest the successor will finally compete with modern hardware.</p>
            </div>
            <div class="card">
                <div class="card-meta">
                    <i class="fas fa-clock"></i> 1 day ago
                    <i class="fas fa-user"></i> By Mike D.
                </div>
                <h3>Valve Announces New Source 2 Game Engine Features</h3>
                <p>Ray tracing, DLSS support, and better modding tools coming to Steam's powerhouse engine.</p>
            </div>
        </div>
    </section>

    <!-- Reviews -->
    <section id="reviews" class="container">
        <h2><i class="fas fa-star"></i> Latest Reviews</h2>
        <div class="reviews-grid">
            <div class="card">
                <div class="card-meta">
                    <span class="rating">9.5/10</span>
                    <i class="fas fa-clock"></i> Dec 15, 2023
                </div>
                <h3>Alan Wake 2</h3>
                <p>A masterful blend of psychological horror and narrative brilliance. Remedy's best work yet.</p>
            </div>
            <div class="card">
                <div class="card-meta">
                    <span class="rating">8.7/10</span>
                    <i class="fas fa-clock"></i> Dec 14, 2023
                </div>
                <h3>Super Mario Bros. Wonder</h3>
                <p>2D platforming perfection with innovative Wonder Flowers and co-op chaos.</p>
            </div>
            <div class="card">
                <div class="card-meta">
                    <span class="rating">9.2/10</span>
                    <i class="fas fa-clock"></i> Dec 13, 2023
                </div>
                <h3>Spider-Man 2</h3>
                <p>Insomniac delivers the ultimate web-slinging experience with emotional storytelling.</p>
            </div>
        </div>
    </section>

    <!-- Top Games -->
    <section id="top-games" class="container">
        <h2><i class="fas fa-trophy"></i> Top Games of All Time</h2>
        <div class="top-games-grid">
            <div class="card top-game-card">
                <div class="rank">#1</div>
                <img src="https://images.unsplash.com/photo-1542751371-adc38448a05e?w=400&h=200&fit=crop" alt="The Legend of Zelda: Breath of the Wild">
                <h3>The Legend of Zelda: Breath of the Wild</h3>
                <p>9.8/10 - The open-world masterpiece that redefined gaming.</p>
            </div>
            <div class="card top-game-card">
                <div class="rank">#2</div>
                <img src="https://images.unsplash.com/photo-1600585154340-be6161a56a0c?w=400&h=200&fit=crop" alt="The Witcher 3">
                <h3>The Witcher 3: Wild Hunt</h3>
                <p>9.7/10 - Epic storytelling in a breathtaking world.</p>
            </div>
            <div class="card top-game-card">
                <div class="rank">#3</div>
                <img src="https://images.unsplash.com/photo-1570549717069-33bed1b2d717?w=400&h=200&fit=crop" alt="Half-Life 2">
                <h3>Half-Life 2</h3>
                <p>9.6/10 - The pinnacle of FPS storytelling and physics.</p>
            </div>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact" class="container">
        <h2><i class="fas fa-envelope"></i> Get In Touch</h2>
        <form class="contact-form">
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" name="name" placeholder="Your name" required>
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" name="email" placeholder="your@email.com" required>
            </div>
            <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" name="message" rows="6" placeholder="Tell us what you think..." required></textarea>
            </div>
            <button type="submit" class="cta-button" style="width: 100%; margin-top: 1rem;">Send Message</button>
        </form>
    </section>

    <!-- Scroll to Top -->
    <
