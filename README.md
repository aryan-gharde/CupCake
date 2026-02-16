<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tiny Treats - Homemade Baking | Premium Artisan Cupcakes</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:wght@300;400;600;700&family=Playfair+Display:wght@400;600;700;900&family=Quicksand:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            /* Color Palette from Logo */
            --pink-primary: #f4c4c4;
            --pink-light: #fde8e8;
            --pink-accent: #e89bb8;
            --mint-bg: #d4f4e8;
            --lavender-bg: #c4d4f4;
            --cream: #fff8f0;
            --chocolate: #8b6f5f;
            --gold: #d4af37;
            --white: #ffffff;
            --shadow: rgba(244, 196, 196, 0.3);
            
            /* Typography */
            --font-display: 'Playfair Display', serif;
            --font-script: 'Cormorant Garamond', serif;
            --font-body: 'Quicksand', sans-serif;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: var(--font-body);
            background: linear-gradient(135deg, var(--mint-bg) 0%, var(--pink-light) 50%, var(--lavender-bg) 100%);
            overflow-x: hidden;
            position: relative;
        }

        /* Floating Sprinkles Animation */
        .sprinkles-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            overflow: hidden;
        }

        .sprinkle {
            position: absolute;
            width: 8px;
            height: 8px;
            border-radius: 50%;
            opacity: 0;
            animation: float-down 8s infinite;
        }

        @keyframes float-down {
            0% {
                transform: translateY(-100px) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 0.8;
            }
            90% {
                opacity: 0.5;
            }
            100% {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }

        /* Header */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 1rem 5%;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            z-index: 100;
            box-shadow: 0 4px 20px var(--shadow);
            animation: slide-down 0.8s ease-out;
        }

        @keyframes slide-down {
            from {
                transform: translateY(-100%);
            }
            to {
                transform: translateY(0);
            }
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo-container {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .logo-text {
            font-family: var(--font-display);
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--chocolate);
            letter-spacing: 2px;
        }

        .nav-links {
            display: flex;
            gap: 2.5rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: var(--chocolate);
            font-weight: 500;
            font-size: 1rem;
            transition: all 0.3s ease;
            position: relative;
        }

        .nav-links a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--pink-accent);
            transition: width 0.3s ease;
        }

        .nav-links a:hover::after {
            width: 100%;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            padding: 120px 5% 60px;
            overflow: hidden;
        }

        .hero-content {
            max-width: 1400px;
            width: 100%;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 4rem;
            align-items: center;
            z-index: 2;
        }

        .hero-text {
            animation: fade-slide-up 1s ease-out 0.3s both;
        }

        @keyframes fade-slide-up {
            from {
                opacity: 0;
                transform: translateY(40px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero-subtitle {
            font-family: var(--font-script);
            font-size: 1.5rem;
            color: var(--pink-accent);
            margin-bottom: 1rem;
            font-style: italic;
            animation: fade-in 1s ease-out 0.5s both;
        }

        .hero-title {
            font-family: var(--font-display);
            font-size: 5rem;
            font-weight: 900;
            line-height: 1.1;
            color: var(--chocolate);
            margin-bottom: 1.5rem;
            animation: fade-slide-up 1s ease-out 0.6s both;
        }

        .hero-title .highlight {
            color: var(--pink-accent);
            position: relative;
            display: inline-block;
            animation: bounce-word 2s ease-in-out infinite;
        }

        @keyframes bounce-word {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        .hero-description {
            font-size: 1.2rem;
            color: var(--chocolate);
            margin-bottom: 2.5rem;
            line-height: 1.8;
            opacity: 0.9;
            animation: fade-slide-up 1s ease-out 0.8s both;
        }

        /* Unboxing Effect */
        .hero-visual {
            position: relative;
            perspective: 1000px;
            animation: fade-slide-up 1s ease-out 0.4s both;
        }

        .cupcake-box {
            width: 100%;
            max-width: 500px;
            margin: 0 auto;
            position: relative;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .box-lid {
            width: 100%;
            height: 400px;
            background: linear-gradient(135deg, var(--pink-primary), var(--pink-light));
            border-radius: 20px;
            box-shadow: 0 20px 60px var(--shadow);
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
            transform-origin: top;
            transition: all 0.8s cubic-bezier(0.68, -0.55, 0.265, 1.55);
        }

        .cupcake-box:hover .box-lid {
            transform: rotateX(-120deg);
            opacity: 0;
        }

        .box-ribbon {
            position: absolute;
            width: 120%;
            height: 60px;
            background: var(--gold);
            transform: rotate(-45deg);
            opacity: 0.3;
        }

        .box-label {
            font-family: var(--font-display);
            font-size: 3rem;
            color: var(--chocolate);
            z-index: 2;
            text-align: center;
            font-weight: 700;
        }

        .cupcake-reveal {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            opacity: 0;
            transition: opacity 0.8s ease 0.4s;
            pointer-events: none;
        }

        .cupcake-box:hover .cupcake-reveal {
            opacity: 1;
        }

        .cupcake-image {
            width: 300px;
            height: 300px;
            background: radial-gradient(circle, var(--cream), var(--pink-light));
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 8rem;
            box-shadow: 0 30px 80px rgba(0,0,0,0.2);
            animation: cupcake-float 3s ease-in-out infinite;
        }

        @keyframes cupcake-float {
            0%, 100% {
                transform: translateY(0) scale(1);
            }
            50% {
                transform: translateY(-20px) scale(1.05);
            }
        }

        /* CTA Button with Sound */
        .cta-button {
            display: inline-flex;
            align-items: center;
            gap: 1rem;
            padding: 1.2rem 3rem;
            background: linear-gradient(135deg, var(--pink-accent), var(--pink-primary));
            color: white;
            font-family: var(--font-body);
            font-size: 1.1rem;
            font-weight: 600;
            text-decoration: none;
            border-radius: 50px;
            border: none;
            cursor: pointer;
            box-shadow: 0 10px 30px var(--shadow);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .cta-button::before {
            content: '';
            position: absolute;
            top: 50%;
            left: 50%;
            width: 0;
            height: 0;
            border-radius: 50%;
            background: rgba(255, 255, 255, 0.3);
            transform: translate(-50%, -50%);
            transition: width 0.6s ease, height 0.6s ease;
        }

        .cta-button:hover::before {
            width: 300px;
            height: 300px;
        }

        .cta-button:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 15px 40px var(--shadow);
        }

        .cta-icon {
            font-size: 1.5rem;
            animation: pulse-icon 2s ease-in-out infinite;
        }

        @keyframes pulse-icon {
            0%, 100% {
                transform: scale(1);
            }
            50% {
                transform: scale(1.2);
            }
        }

        /* Sweet Sound Section */
        .sweet-sound {
            padding: 6rem 5%;
            background: var(--white);
            position: relative;
            overflow: hidden;
        }

        .sweet-sound::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: repeating-linear-gradient(
                45deg,
                transparent,
                transparent 10px,
                var(--pink-light) 10px,
                var(--pink-light) 20px
            );
            opacity: 0.1;
        }

        .sweet-sound-content {
            max-width: 900px;
            margin: 0 auto;
            text-align: center;
            position: relative;
            z-index: 2;
        }

        .section-title {
            font-family: var(--font-display);
            font-size: 3.5rem;
            color: var(--chocolate);
            margin-bottom: 2rem;
            font-weight: 700;
        }

        .slogan {
            font-family: var(--font-script);
            font-size: 2.5rem;
            color: var(--pink-accent);
            margin: 2rem 0;
            font-style: italic;
            line-height: 1.4;
        }

        .slogan-animated {
            display: inline-block;
            animation: bounce-text 1s ease-in-out infinite;
        }

        @keyframes bounce-text {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-8px);
            }
        }

        /* Flavor Gallery */
        .flavor-gallery {
            padding: 6rem 5%;
            background: linear-gradient(135deg, var(--cream), var(--pink-light));
            position: relative;
        }

        .gallery-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .carousel-container {
            max-width: 1400px;
            margin: 0 auto;
            position: relative;
            overflow: hidden;
        }

        .carousel-wrapper {
            display: flex;
            gap: 2rem;
            overflow-x: auto;
            scroll-behavior: smooth;
            padding: 2rem 0;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }

        .carousel-wrapper::-webkit-scrollbar {
            display: none;
        }

        .flavor-card {
            min-width: 350px;
            background: white;
            border-radius: 20px;
            padding: 2rem;
            box-shadow: 0 10px 40px var(--shadow);
            transition: all 0.4s ease;
            cursor: pointer;
            position: relative;
            overflow: hidden;
        }

        .flavor-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, var(--pink-light), var(--lavender-bg));
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .flavor-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 60px rgba(0,0,0,0.15);
        }

        .flavor-card:hover::before {
            opacity: 0.3;
        }

        .flavor-icon {
            font-size: 5rem;
            text-align: center;
            margin-bottom: 1.5rem;
            display: block;
            transition: transform 0.4s ease;
            position: relative;
            z-index: 2;
        }

        .flavor-card:hover .flavor-icon {
            transform: scale(1.15) rotate(10deg);
        }

        .flavor-name {
            font-family: var(--font-display);
            font-size: 1.8rem;
            color: var(--chocolate);
            margin-bottom: 1rem;
            text-align: center;
            font-weight: 600;
            position: relative;
            z-index: 2;
        }

        .flavor-description {
            font-family: var(--font-script);
            font-size: 1.1rem;
            color: var(--chocolate);
            text-align: center;
            line-height: 1.6;
            opacity: 0;
            max-height: 0;
            transition: all 0.4s ease;
            position: relative;
            z-index: 2;
            font-style: italic;
        }

        .flavor-card:hover .flavor-description {
            opacity: 1;
            max-height: 200px;
            margin-top: 1rem;
        }

        /* Philosophy Section */
        .philosophy {
            padding: 8rem 5%;
            background: var(--white);
            position: relative;
        }

        .philosophy-content {
            max-width: 1200px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 5rem;
            align-items: center;
        }

        .philosophy-text h2 {
            font-family: var(--font-display);
            font-size: 3.5rem;
            color: var(--chocolate);
            margin-bottom: 2rem;
            font-weight: 700;
        }

        .philosophy-text p {
            font-size: 1.2rem;
            line-height: 1.8;
            color: var(--chocolate);
            margin-bottom: 1.5rem;
            opacity: 0.9;
        }

        .philosophy-visual {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 2rem;
        }

        .philosophy-card {
            background: linear-gradient(135deg, var(--pink-light), var(--cream));
            padding: 2.5rem;
            border-radius: 20px;
            text-align: center;
            box-shadow: 0 10px 30px var(--shadow);
            transition: transform 0.3s ease;
        }

        .philosophy-card:hover {
            transform: translateY(-10px);
        }

        .philosophy-card-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .philosophy-card h3 {
            font-family: var(--font-display);
            font-size: 1.5rem;
            color: var(--chocolate);
            margin-bottom: 0.5rem;
        }

        .philosophy-card p {
            font-size: 1rem;
            color: var(--chocolate);
            opacity: 0.8;
        }

        /* Social Proof Section */
        .social-proof {
            padding: 6rem 5%;
            background: linear-gradient(135deg, var(--lavender-bg), var(--mint-bg));
            position: relative;
        }

        .social-proof-header {
            text-align: center;
            margin-bottom: 4rem;
        }

        .testimonials {
            max-width: 1400px;
            margin: 0 auto;
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .testimonial-card {
            background: white;
            padding: 2.5rem;
            border-radius: 15px;
            box-shadow: 0 10px 30px var(--shadow);
            position: relative;
            transition: transform 0.3s ease;
            border-left: 5px solid var(--pink-accent);
        }

        .testimonial-card:hover {
            transform: translateY(-5px);
        }

        .testimonial-card::before {
            content: '"';
            position: absolute;
            top: 20px;
            left: 20px;
            font-size: 5rem;
            font-family: var(--font-display);
            color: var(--pink-light);
            line-height: 1;
        }

        .testimonial-text {
            font-family: var(--font-script);
            font-size: 1.2rem;
            line-height: 1.6;
            color: var(--chocolate);
            margin-bottom: 1.5rem;
            position: relative;
            z-index: 2;
            font-style: italic;
        }

        .testimonial-author {
            font-family: var(--font-body);
            font-weight: 600;
            color: var(--pink-accent);
            font-size: 1rem;
        }

        .testimonial-rating {
            color: var(--gold);
            font-size: 1.2rem;
            margin-top: 0.5rem;
        }

        /* Footer */
        footer {
            background: var(--chocolate);
            color: var(--cream);
            padding: 3rem 5%;
            text-align: center;
        }

        .footer-content {
            max-width: 1200px;
            margin: 0 auto;
        }

        .footer-logo {
            font-family: var(--font-display);
            font-size: 2rem;
            margin-bottom: 1rem;
        }

        .footer-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 2rem 0;
            flex-wrap: wrap;
        }

        .footer-links a {
            color: var(--cream);
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .footer-links a:hover {
            color: var(--pink-accent);
        }

        /* Mobile Responsive */
        @media (max-width: 968px) {
            .hero-content {
                grid-template-columns: 1fr;
                gap: 3rem;
                text-align: center;
            }

            .hero-title {
                font-size: 3.5rem;
            }

            .nav-links {
                display: none;
            }

            .philosophy-content {
                grid-template-columns: 1fr;
                gap: 3rem;
            }

            .philosophy-visual {
                grid-template-columns: 1fr;
            }

            .section-title {
                font-size: 2.5rem;
            }

            .flavor-card {
                min-width: 280px;
            }
        }

        @media (max-width: 640px) {
            .hero-title {
                font-size: 2.5rem;
            }

            .logo-text {
                font-size: 1.3rem;
            }
        }

        /* Scroll Triggered Animation */
        .fade-in-up {
            opacity: 0;
            transform: translateY(60px);
            transition: all 0.8s ease;
        }

        .fade-in-up.visible {
            opacity: 1;
            transform: translateY(0);
        }
    </style>
</head>
<body>
    <!-- Floating Sprinkles -->
    <div class="sprinkles-container" id="sprinkles"></div>

    <!-- Header -->
    <header>
        <nav>
            <div class="logo-container">
                <span class="logo-text">TINY TREATS</span>
            </div>
            <ul class="nav-links">
                <li><a href="#flavors">Flavors</a></li>
                <li><a href="#philosophy">Our Story</a></li>
                <li><a href="#reviews">Reviews</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <div class="hero-text">
                <p class="hero-subtitle">Artisan Cupcakes, Crafted with Love</p>
                <h1 class="hero-title">
                    Tiny Treats,<br>
                    <span class="highlight">Big</span> Emotions
                </h1>
                <p class="hero-description">
                    Every bite is a celebration. Handcrafted with premium ingredients, 
                    baked fresh daily, and designed to make your moments unforgettable.
                </p>
                <button class="cta-button" id="orderBtn">
                    <span class="cta-icon">🧁</span>
                    <span>Order Your Joy</span>
                </button>
            </div>
            <div class="hero-visual">
                <div class="cupcake-box">
                    <div class="box-lid">
                        <div class="box-ribbon"></div>
                        <div class="box-label">Open Me ✨</div>
                    </div>
                    <div class="cupcake-reveal">
                        <div class="cupcake-image">🧁</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Sweet Sound Section -->
    <section class="sweet-sound">
        <div class="sweet-sound-content">
            <h2 class="section-title">The Sweet Sound of Joy</h2>
            <p class="slogan">
                <span class="slogan-animated" style="animation-delay: 0s;">"Every</span>
                <span class="slogan-animated" style="animation-delay: 0.1s;"> cupcake</span>
                <span class="slogan-animated" style="animation-delay: 0.2s;"> tells</span>
                <span class="slogan-animated" style="animation-delay: 0.3s;"> a</span>
                <span class="slogan-animated" style="animation-delay: 0.4s;"> story,</span><br>
                <span class="slogan-animated" style="animation-delay: 0.5s;">soft,</span>
                <span class="slogan-animated" style="animation-delay: 0.6s;"> sweet,</span>
                <span class="slogan-animated" style="animation-delay: 0.7s;"> and</span>
                <span class="slogan-animated" style="animation-delay: 0.8s;"> delicious"</span>
            </p>
        </div>
    </section>

    <!-- Flavor Gallery -->
    <section class="flavor-gallery" id="flavors">
        <div class="gallery-header fade-in-up">
            <h2 class="section-title">The Flavor Gallery</h2>
            <p style="font-family: var(--font-script); font-size: 1.5rem; color: var(--chocolate); font-style: italic;">
                Swipe through our signature collection
            </p>
        </div>
        <div class="carousel-container">
            <div class="carousel-wrapper">
                <div class="flavor-card">
                    <span class="flavor-icon">🍦</span>
                    <h3 class="flavor-name">Ivory Silk Vanilla</h3>
                    <p class="flavor-description">
                        Pure Madagascar vanilla bean infused into silky buttercream, 
                        atop a tender vanilla sponge. Elegance in its simplest form.
                    </p>
                </div>
                <div class="flavor-card">
                    <span class="flavor-icon">💙</span>
                    <h3 class="flavor-name">Sapphire Berry</h3>
                    <p class="flavor-description">
                        Luscious blueberry compote swirled with cream cheese frosting, 
                        crowned with fresh berries. A burst of summer in every bite.
                    </p>
                </div>
                <div class="flavor-card">
                    <span class="flavor-icon">🍮</span>
                    <h3 class="flavor-name">Caramel Biscotti</h3>
                    <p class="flavor-description">
                        Salted caramel drizzle over Italian biscotti-infused cupcake, 
                        finished with crunchy almond pieces. Sweet sophistication.
                    </p>
                </div>
                <div class="flavor-card">
                    <span class="flavor-icon">🍫</span>
                    <h3 class="flavor-name">Royal Chocolate</h3>
                    <p class="flavor-description">
                        Triple chocolate indulgence with Belgian dark chocolate ganache, 
                        cocoa sponge, and chocolate shavings. For the true connoisseur.
                    </p>
                </div>
                <div class="flavor-card">
                    <span class="flavor-icon">🌈</span>
                    <h3 class="flavor-name">The Curated Four</h3>
                    <p class="flavor-description">
                        Can't decide? Our signature box features one of each flavor, 
                        beautifully presented in our custom gift box.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Philosophy Section -->
    <section class="philosophy" id="philosophy">
        <div class="philosophy-content">
            <div class="philosophy-text fade-in-up">
                <h2>The "Tiny" Philosophy</h2>
                <p>
                    We believe that the best things in life come in small packages. 
                    Each cupcake is a miniature masterpiece, handcrafted with precision 
                    and passion.
                </p>
                <p>
                    From sourcing the finest ingredients to perfecting each swirl of 
                    buttercream, we obsess over every detail. Because when something 
                    is truly tiny, it has to be perfect.
                </p>
                <p>
                    Our kitchen is a place of joy, creativity, and love. Every batch 
                    is baked fresh daily, ensuring you receive cupcakes at their peak 
                    of flavor and freshness.
                </p>
            </div>
            <div class="philosophy-visual fade-in-up">
                <div class="philosophy-card">
                    <div class="philosophy-card-icon">🌾</div>
                    <h3>Premium Ingredients</h3>
                    <p>Only the finest, locally-sourced ingredients</p>
                </div>
                <div class="philosophy-card">
                    <div class="philosophy-card-icon">👩‍🍳</div>
                    <h3>Artisan Craft</h3>
                    <p>Handcrafted with precision and care</p>
                </div>
                <div class="philosophy-card">
                    <div class="philosophy-card-icon">🎨</div>
                    <h3>Creative Design</h3>
                    <p>Each cupcake is a work of edible art</p>
                </div>
                <div class="philosophy-card">
                    <div class="philosophy-card-icon">💝</div>
                    <h3>Made with Love</h3>
                    <p>Every batch baked with passion</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Social Proof -->
    <section class="social-proof" id="reviews">
        <div class="social-proof-header fade-in-up">
            <h2 class="section-title">Sweet Talk</h2>
            <p style="font-family: var(--font-script); font-size: 1.5rem; color: var(--chocolate); font-style: italic;">
                What our customers are saying
            </p>
        </div>
        <div class="testimonials">
            <div class="testimonial-card fade-in-up">
                <p class="testimonial-text">
                    These aren't just cupcakes, they're edible poetry. The Sapphire Berry 
                    transported me to a Parisian café. Absolutely divine!
                </p>
                <p class="testimonial-author">— Sarah M.</p>
                <div class="testimonial-rating">★★★★★</div>
            </div>
            <div class="testimonial-card fade-in-up">
                <p class="testimonial-text">
                    I ordered The Curated Four for my daughter's birthday and the presentation 
                    alone was worth it. The taste? Out of this world!
                </p>
                <p class="testimonial-author">— James L.</p>
                <div class="testimonial-rating">★★★★★</div>
            </div>
            <div class="testimonial-card fade-in-up">
                <p class="testimonial-text">
                    The Royal Chocolate is dangerously good. I keep telling myself 
                    "just one more" but I can never stop at one!
                </p>
                <p class="testimonial-author">— Priya K.</p>
                <div class="testimonial-rating">★★★★★</div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer id="contact">
        <div class="footer-content">
            <h3 class="footer-logo">TINY TREATS</h3>
            <p>Homemade Baking | Est. 2024</p>
            <div class="footer-links">
                <a href="#flavors">Our Flavors</a>
                <a href="#philosophy">Our Story</a>
                <a href="mailto:hello@tinytreats.com">Contact Us</a>
                <a href="#">Instagram</a>
                <a href="#">Facebook</a>
            </div>
            <p style="margin-top: 2rem; opacity: 0.7; font-size: 0.9rem;">
                © 2026 Tiny Treats. Soft, Sweet, and Delicious. ♥
            </p>
        </div>
    </footer>

    <script>
        // Floating Sprinkles Animation
        function createSprinkles() {
            const container = document.getElementById('sprinkles');
            const colors = ['#f4c4c4', '#e89bb8', '#d4af37', '#fde8e8', '#c4d4f4'];
            let sprinklesActive = false;

            function addSprinkle() {
                if (!sprinklesActive) return;
                
                const sprinkle = document.createElement('div');
                sprinkle.className = 'sprinkle';
                sprinkle.style.left = Math.random() * 100 + '%';
                sprinkle.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
                sprinkle.style.animationDelay = Math.random() * 2 + 's';
                sprinkle.style.animationDuration = (Math.random() * 4 + 6) + 's';
                
                container.appendChild(sprinkle);
                
                setTimeout(() => {
                    sprinkle.remove();
                }, 8000);
            }

            // Start sprinkles on scroll
            let scrolled = false;
            window.addEventListener('scroll', () => {
                if (!scrolled && window.scrollY > 100) {
                    scrolled = true;
                    sprinklesActive = true;
                    setInterval(addSprinkle, 300);
                }
            });
        }

        // Sound Effect for CTA Button
        const orderBtn = document.getElementById('orderBtn');
        let audioContext;
        
        orderBtn.addEventListener('mouseenter', () => {
            // Create Web Audio API context for chime sound
            if (!audioContext) {
                audioContext = new (window.AudioContext || window.webkitAudioContext)();
            }
            
            // Create a pleasant chime sound
            const oscillator = audioContext.createOscillator();
            const gainNode = audioContext.createGain();
            
            oscillator.connect(gainNode);
            gainNode.connect(audioContext.destination);
            
            oscillator.frequency.setValueAtTime(800, audioContext.currentTime);
            oscillator.frequency.exponentialRampToValueAtTime(1200, audioContext.currentTime + 0.1);
            
            gainNode.gain.setValueAtTime(0.3, audioContext.currentTime);
            gainNode.gain.exponentialRampToValueAtTime(0.01, audioContext.currentTime + 0.3);
            
            oscillator.start(audioContext.currentTime);
            oscillator.stop(audioContext.currentTime + 0.3);
        });

        // Smooth horizontal scroll for carousel
        const carousel = document.querySelector('.carousel-wrapper');
        let isDown = false;
        let startX;
        let scrollLeft;

        carousel.addEventListener('mousedown', (e) => {
            isDown = true;
            startX = e.pageX - carousel.offsetLeft;
            scrollLeft = carousel.scrollLeft;
        });

        carousel.addEventListener('mouseleave', () => {
            isDown = false;
        });

        carousel.addEventListener('mouseup', () => {
            isDown = false;
        });

        carousel.addEventListener('mousemove', (e) => {
            if (!isDown) return;
            e.preventDefault();
            const x = e.pageX - carousel.offsetLeft;
            const walk = (x - startX) * 2;
            carousel.scrollLeft = scrollLeft - walk;
        });

        // Scroll-triggered animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.classList.add('visible');
                }
            });
        }, observerOptions);

        document.querySelectorAll('.fade-in-up').forEach((el) => {
            observer.observe(el);
        });

        // Initialize
        createSprinkles();

        // Auto-scroll carousel
        let scrollInterval;
        function autoScroll() {
            scrollInterval = setInterval(() => {
                if (carousel.scrollLeft >= carousel.scrollWidth - carousel.clientWidth - 50) {
                    carousel.scrollTo({ left: 0, behavior: 'smooth' });
                } else {
                    carousel.scrollBy({ left: 370, behavior: 'smooth' });
                }
            }, 4000);
        }

        autoScroll();

        carousel.addEventListener('mouseenter', () => {
            clearInterval(scrollInterval);
        });

        carousel.addEventListener('mouseleave', () => {
            autoScroll();
        });
    </script>
</body>
</html>
