<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ayush Kumar Jha | Creative Developer</title>
    <!-- Google Fonts -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;700&family=Space+Grotesk:wght@500;700&display=swap" rel="stylesheet">
    <!-- Font Awesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    
    <style>
        /* --- CSS Variables & Reset --- */
        :root {
            --primary: #64ffda;
            --primary-dim: rgba(100, 255, 218, 0.1);
            --bg-dark: #0a192f;
            --bg-light: #112240;
            --bg-card: #233554;
            --text-main: #ccd6f6;
            --text-secondary: #8892b0;
            --white: #e6f1ff;
            --font-main: 'Inter', sans-serif;
            --font-heading: 'Space Grotesk', sans-serif;
            --nav-height: 80px;
            --transition: all 0.3s ease; /* Simplified transition */
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        html {
            scroll-behavior: smooth;
            font-size: 16px;
        }

        body {
            background-color: var(--bg-dark);
            color: var(--text-main);
            font-family: var(--font-main);
            line-height: 1.6;
            overflow-x: hidden;
        }

        h1, h2, h3, h4 {
            font-family: var(--font-heading);
            color: var(--white);
            margin-bottom: 1.5rem;
        }

        a {
            text-decoration: none;
            color: inherit;
            transition: var(--transition);
        }

        ul {
            list-style: none;
        }

        section {
            padding: 5rem 1.5rem;
            max-width: 1200px;
            margin: 0 auto;
        }

        /* --- Components --- */
        .btn {
            display: inline-block;
            padding: 0.8rem 1.75rem;
            border: 1px solid var(--primary);
            border-radius: 4px;
            color: var(--primary);
            font-family: var(--font-heading);
            font-size: 0.9rem;
            cursor: pointer;
            background: transparent;
            transition: var(--transition);
        }

        .btn:hover {
            background: var(--primary-dim);
        }

        .section-title {
            font-size: 2rem;
            display: flex;
            align-items: center;
            white-space: nowrap;
        }

        .section-title::after {
            content: "";
            display: block;
            width: 100%;
            height: 1px;
            background-color: var(--bg-card);
            margin-left: 1.5rem;
        }

        /* --- Navigation (Flexbox) --- */
        header {
            height: var(--nav-height);
            background-color: #0a192f;
            position: fixed;
            width: 100%;
            top: 0;
            z-index: 1000;
            box-shadow: 0 2px 20px rgba(0,0,0,0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 100%;
            padding: 0 2rem;
            max-width: 1400px;
            margin: 0 auto;
        }

        .logo {
            font-family: var(--font-heading);
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--primary);
            z-index: 1001;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
        }

        .nav-links a {
            font-size: 0.9rem;
            font-weight: 500;
        }

        .nav-links a:hover {
            color: var(--primary);
        }

        .hamburger {
            display: none;
            cursor: pointer;
            z-index: 1001;
        }

        .bar {
            width: 25px;
            height: 3px;
            background-color: var(--primary);
            margin: 5px 0;
            transition: var(--transition);
        }

        /* --- Hero Section --- */
        #hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            padding-top: var(--nav-height);
        }

        .hero-content {
            width: 100%;
            max-width: 1000px;
        }

        .overline {
            color: var(--primary);
            font-family: var(--font-heading);
            font-size: 1rem;
            margin-bottom: 1rem;
            display: block;
        }

        .hero-title {
            font-size: clamp(2.5rem, 8vw, 5rem);
            line-height: 1.1;
            color: var(--white);
            margin-bottom: 1rem;
        }

        .hero-subtitle {
            font-size: clamp(2rem, 5vw, 4rem);
            line-height: 1.1;
            color: var(--text-secondary);
            margin-bottom: 2rem;
        }

        .hero-desc {
            max-width: 540px;
            font-size: 1.1rem;
            color: var(--text-secondary);
            margin-bottom: 3rem;
        }

        /* --- About Section --- */
        .about-content {
            display: flex;
            gap: 3rem;
            align-items: flex-start;
        }

        .about-text {
            flex: 2;
        }

        .about-text p {
            margin-bottom: 1rem;
            color: var(--text-secondary);
        }

        .tech-list {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 10px;
            margin-top: 20px;
            font-family: var(--font-heading);
            font-size: 0.9rem;
        }

        .tech-list li {
            position: relative;
            padding-left: 20px;
        }

        .tech-list li::before {
            content: "▹";
            position: absolute;
            left: 0;
            color: var(--primary);
        }

        /* --- Projects Section (CSS GRID) --- */
        #projects {
            padding: 6rem 1.5rem;
        }

        .project-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin-top: 3rem;
        }

        .project-card {
            background-color: var(--bg-light);
            padding: 2rem;
            border-radius: 8px;
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-5px);
        }

        .project-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 2rem;
        }

        .folder-icon {
            color: var(--primary);
            font-size: 2.5rem;
        }

        .project-links a {
            color: var(--text-main);
            font-size: 1.25rem;
            margin-left: 10px;
        }

        .project-links a:hover {
            color: var(--primary);
        }

        .project-title {
            color: var(--white);
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .project-desc {
            color: var(--text-secondary);
            font-size: 0.9rem;
            margin-bottom: 2rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 1rem;
            font-size: 0.8rem;
            font-family: var(--font-heading);
            color: var(--text-secondary);
        }

        /* --- Contact Section --- */
        #contact {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
            padding: 8rem 1.5rem;
        }

        #contact h2 {
            font-size: 3rem;
            color: var(--white);
        }

        #contact p {
            color: var(--text-secondary);
            margin-bottom: 3rem;
            font-size: 1.1rem;
        }

        /* --- Footer --- */
        footer {
            padding: 2rem;
            text-align: center;
            color: var(--text-secondary);
            font-size: 0.8rem;
            font-family: var(--font-heading);
        }

        .social-icons {
            display: none;
            justify-content: center;
            gap: 2rem;
            margin-bottom: 1rem;
            font-size: 1.5rem;
        }

        /* --- Media Queries (Responsiveness) --- */
        
        @media (max-width: 768px) {
            .hamburger {
                display: block;
            }

            .nav-links {
                position: fixed;
                top: 0;
                right: 0;
                height: 100vh;
                width: 70%;
                background-color: var(--bg-light);
                flex-direction: column;
                justify-content: center;
                align-items: center;
                transform: translateX(100%);
                transition: transform 0.3s ease-in-out;
                box-shadow: -10px 0 30px -10px rgba(2, 12, 27, 0.7);
            }

            .nav-links.active {
                transform: translateX(0);
            }

            .social-icons {
                display: flex;
            }
        }

        @media (min-width: 769px) {
            .about-content {
                flex-direction: row;
            }
        }

        .hamburger.active .bar:nth-child(1) {
            transform: translateY(8px) rotate(45deg);
        }
        .hamburger.active .bar:nth-child(2) {
            opacity: 0;
        }
        .hamburger.active .bar:nth-child(3) {
            transform: translateY(-8px) rotate(-45deg);
        }

    </style>
</head>
<body>

    <!-- Header / Navigation -->
    <header>
        <nav>
            <a href="#" class="logo">AYUSH.DEV</a>
            
            <div class="hamburger" id="hamburger">
                <span class="bar"></span>
                <span class="bar"></span>
                <span class="bar"></span>
            </div>

            <ul class="nav-links" id="nav-links">
                <li><a href="#about" class="nav-item"><span style="color:var(--primary)">01.</span> About</a></li>
                <li><a href="#projects" class="nav-item"><span style="color:var(--primary)">02.</span> Work</a></li>
                <li><a href="#contact" class="nav-item"><span style="color:var(--primary)">03.</span> Contact</a></li>
                <li><a href="#" class="btn" style="margin-left: 15px;">Resume</a></li>
            </ul>
        </nav>
    </header>

    <!-- Main Content -->
    <main>
        <!-- Hero Section -->
        <section id="hero">
            <div class="hero-content">
                <span class="overline">Hi, my name is</span>
                <h1 class="hero-title">Ayush Kumar Jha.</h1>
                <h2 class="hero-subtitle">I build things for the web.</h2>
                <p class="hero-desc">
                    I'm a software engineer specializing in building (and occasionally designing) exceptional digital experiences. Currently, I'm focused on building accessible, human-centered products.
                </p>
                <div class="hero-btn-wrapper">
                    <a href="#projects" class="btn">Check out my work!</a>
                </div>
            </div>
        </section>

        <!-- About Section -->
        <section id="about">
            <h2 class="section-title"><span style="color:var(--primary); margin-right: 10px; font-size: 1.5rem;">01.</span> About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Hello! My name is Ayush and I enjoy creating things that live on the internet. My interest in web development started back in 2018 when I decided to try editing custom Tumblr themes — turns out hacking together HTML & CSS was exciting!</p>
                    <p>Fast-forward to today, and I've had the privilege of working at an advertising agency, a start-up, and a huge corporation. My main focus these days is building accessible, inclusive products and digital experiences.</p>
                    <p>Here are a few technologies I've been working with recently:</p>
                    <ul class="tech-list">
                        <li>JavaScript (ES6+)</li>
                        <li>TypeScript</li>
                        <li>React</li>
                        <li>Node.js</li>
                        <li>Tailwind CSS</li>
                        <li>WordPress</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Projects Section (CSS Grid) -->
        <section id="projects">
            <h2 class="section-title"><span style="color:var(--primary); margin-right: 10px; font-size: 1.5rem;">02.</span> Some Things I've Built</h2>
            
            <div class="project-grid">
                <!-- Project 1 -->
                <div class="project-card">
                    <div class="project-top">
                        <i class="far fa-folder folder-icon"></i>
                        <div class="project-links">
                            <a href="#"><i class="fab fa-github"></i></a>
                            <a href="#"><i class="fas fa-external-link-alt"></i></a>
                        </div>
                    </div>
                    <h3 class="project-title">Halcyon Theme</h3>
                    <p class="project-desc">
                        A minimal, dark blue theme for VS Code, Sublime Text, and more. Includes 25+ language syntax highlights and is optimized for eye comfort.
                    </p>
                    <div class="project-tech">
                        <span>VS Code</span>
                        <span>JSON</span>
                        <span>Design</span>
                    </div>
                </div>

                <!-- Project 2 -->
                <div class="project-card">
                    <div class="project-top">
                        <i class="far fa-folder folder-icon"></i>
                        <div class="project-links">
                            <a href="#"><i class="fab fa-github"></i></a>
                            <a href="#"><i class="fas fa-external-link-alt"></i></a>
                        </div>
                    </div>
                    <h3 class="project-title">Time Tracker App</h3>
                    <p class="project-desc">
                        A web application for tracking time spent on various projects. Features dashboard visualization, export to CSV, and dark mode toggle.
                    </p>
                    <div class="project-tech">
                        <span>React</span>
                        <span>Firebase</span>
                        <span>Chart.js</span>
                    </div>
                </div>

                <!-- Project 3 -->
                <div class="project-card">
                    <div class="project-top">
                        <i class="far fa-folder folder-icon"></i>
                        <div class="project-links">
                            <a href="#"><i class="fab fa-github"></i></a>
                            <a href="#"><i class="fas fa-external-link-alt"></i></a>
                        </div>
                    </div>
                    <h3 class="project-title">Spotify Profile</h3>
                    <p class="project-desc">
                        A web app for visualizing personalized Spotify data. View your top artists, top tracks, recently played tracks, and detailed audio information.
                    </p>
                    <div class="project-tech">
                        <span>Node.js</span>
                        <span>Express</span>
                        <span>Spotify API</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Contact Section -->
        <section id="contact">
            <p style="color: var(--primary); font-family: var(--font-heading);">03. What's Next?</p>
            <h2>Get In Touch</h2>
            <p>
                Although I'm not currently looking for any new opportunities, my inbox is always open. Whether you have a question or just want to say hi, I'll try my best to get back to you!
            </p>
            <a href="mailto:ayush@example.com" class="btn">Say Hello</a>
        </section>
    </main>

    <!-- Footer -->
    <footer>
        <div class="social-icons">
            <a href="#"><i class="fab fa-github"></i></a>
            <a href="#"><i class="fab fa-instagram"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-linkedin-in"></i></a>
        </div>
        <p>Designed & Built by Ayush Kumar Jha</p>
    </footer>

    <!-- JavaScript for Interactivity -->
    <script>
        // DOM Elements
        const hamburger = document.getElementById('hamburger');
        const navLinks = document.getElementById('nav-links');
        const navItems = document.querySelectorAll('.nav-item');

        // Toggle Mobile Menu
        hamburger.addEventListener('click', () => {
            navLinks.classList.toggle('active');
            hamburger.classList.toggle('active');
        });

        // Close Mobile Menu when a link is clicked
        navItems.forEach(item => {
            item.addEventListener('click', () => {
                navLinks.classList.remove('active');
                hamburger.classList.remove('active');
            });
        });
    </script>
</body>
</html>
