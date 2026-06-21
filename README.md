<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daivik Patel - Backend Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #3b82f6;
            --primary-dark: #1e40af;
            --primary-light: #dbeafe;
            --secondary: #1e293b;
            --accent: #06b6d4;
            --accent-dark: #0891b2;
            --success: #10b981;
            --warning: #f59e0b;
            --danger: #ef4444;
            --light: #f8fafc;
            --light-gray: #f1f5f9;
            --gray: #cbd5e1;
            --dark: #0f172a;
            --text-primary: #f8fafc;
            --text-secondary: #cbd5e1;
            --border: #e2e8f0;
            --shadow-sm: 0 1px 2px 0 rgba(0, 0, 0, 0.05);
            --shadow-md: 0 4px 6px -1px rgba(0, 0, 0, 0.1);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1);
            --shadow-xl: 0 20px 25px -5px rgba(0, 0, 0, 0.1);
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Roboto', 'Oxygen', 'Ubuntu', 'Cantarell', sans-serif;
            color: var(--text-primary);
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 50%, #0f172a 100%);
            min-height: 100vh;
            line-height: 1.6;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-30px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0px);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        @keyframes shimmer {
            0% {
                background-position: -1000px 0;
            }
            100% {
                background-position: 1000px 0;
            }
        }

        header {
            background: rgba(15, 23, 42, 0.95);
            backdrop-filter: blur(10px);
            padding: 1.2rem 0;
            position: sticky;
            top: 0;
            z-index: 100;
            border-bottom: 1px solid rgba(59, 130, 246, 0.2);
            box-shadow: var(--shadow-sm);
        }

        .header-content {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 2rem;
        }

        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(135deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: fadeInDown 0.6s ease-out;
            letter-spacing: -0.5px;
        }

        nav {
            display: flex;
            gap: 2.5rem;
        }

        nav a {
            text-decoration: none;
            color: #cbd5e1;
            font-weight: 500;
            font-size: 0.95rem;
            transition: all 0.3s ease;
            position: relative;
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2.5px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            transition: width 0.3s ease;
            border-radius: 2px;
        }

        nav a:hover {
            color: var(--primary);
        }

        nav a:hover::after {
            width: 100%;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 2rem;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 4rem 2rem;
        }

        .hero-content {
            animation: fadeInDown 0.8s ease-out;
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 0.5rem;
            color: #f8fafc;
            font-weight: 800;
            line-height: 1.2;
            letter-spacing: -1px;
        }

        .hero-content h1 span {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-content .subtitle {
            font-size: 1.5rem;
            color: var(--text-secondary);
            margin-bottom: 2rem;
            animation: fadeInUp 0.8s ease-out 0.2s both;
            font-weight: 500;
        }

        .typing {
            display: inline-block;
            border-right: 3px solid var(--primary);
            animation: blink 0.7s infinite;
        }

        @keyframes blink {
            0%, 50% {
                border-right-color: var(--primary);
            }
            51%, 100% {
                border-right-color: transparent;
            }
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: fadeInUp 0.8s ease-out 0.4s both;
        }

        .btn {
            padding: 0.85rem 2rem;
            border: none;
            border-radius: 8px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            box-shadow: var(--shadow-lg);
            border: none;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 15px 40px rgba(59, 130, 246, 0.4);
        }

        .btn-primary:active {
            transform: translateY(0);
        }

        .btn-secondary {
            background: white;
            color: var(--primary);
            border: 2px solid var(--primary);
            box-shadow: var(--shadow-sm);
        }

        .btn-secondary:hover {
            background: var(--primary-light);
            transform: translateY(-2px);
            box-shadow: var(--shadow-md);
        }

        .scroll-indicator {
            position: absolute;
            bottom: 2rem;
            left: 50%;
            transform: translateX(-50%);
            animation: float 3s ease-in-out infinite;
            color: var(--primary);
        }

        .scroll-indicator i {
            font-size: 2rem;
        }

        section {
            padding: 6rem 0;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            color: #f8fafc;
            position: relative;
            animation: fadeInDown 0.6s ease-out;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
            border-radius: 2px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 2rem;
            margin-bottom: 3rem;
        }

        .project-card {
            background: #1e293b;
            border-radius: 12px;
            overflow: hidden;
            box-shadow: var(--shadow-md);
            transition: all 0.4s ease;
            animation: fadeInUp 0.6s ease-out;
            position: relative;
            border: 1px solid rgba(59, 130, 246, 0.2);
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--accent));
        }

        .project-card:hover {
            transform: translateY(-8px);
            box-shadow: var(--shadow-xl);
            border-color: var(--primary-light);
        }

        .project-header {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            padding: 2rem;
            color: white;
            min-height: 120px;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .project-card h3 {
            font-size: 1.5rem;
            margin-bottom: 0.5rem;
            font-weight: 700;
            color: white;
        }

        .project-card p {
            opacity: 0.95;
            font-size: 0.95rem;
        }

        .project-content {
            padding: 1.5rem;
            color: #cbd5e1;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tech-badge {
            background: rgba(59, 130, 246, 0.15);
            color: #60a5fa;
            padding: 0.4rem 0.8rem;
            border-radius: 6px;
            font-size: 0.85rem;
            font-weight: 600;
            transition: all 0.3s ease;
            border: 1px solid rgba(59, 130, 246, 0.3);
        }

        .tech-badge:hover {
            background: var(--primary);
            color: white;
            transform: scale(1.05);
        }

        .project-link {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            gap: 1rem;
            color: var(--accent);
        }

        .skills-section {
            background: #1e293b;
            border-radius: 12px;
            padding: 3rem;
            box-shadow: var(--shadow-md);
            border: 1px solid rgba(59, 130, 246, 0.2);
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 2rem;
        }

        .skill-item {
            text-align: center;
            animation: fadeInUp 0.6s ease-out;
            transition: all 0.3s ease;
        }

        .skill-item:hover {
            transform: scale(1.1);
        }

        .skill-icon {
            width: 80px;
            height: 80px;
            margin: 0 auto 1rem;
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.15), rgba(6, 182, 212, 0.15));
            border-radius: 12px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            transition: all 0.3s ease;
            position: relative;
            color: #60a5fa;
            border: 1px solid rgba(59, 130, 246, 0.3);
        }

        .skill-item:hover .skill-icon {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            transform: rotateY(180deg);
            box-shadow: var(--shadow-lg);
        }

        .skill-item p {
            font-weight: 600;
            color: #f8fafc;
            font-size: 0.95rem;
        }

        .about-content {
            background: #1e293b;
            border-radius: 12px;
            padding: 3rem;
            box-shadow: var(--shadow-md);
            animation: fadeInUp 0.6s ease-out;
            border: 1px solid rgba(59, 130, 246, 0.2);
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
            color: #cbd5e1;
            margin-bottom: 2rem;
        }

        .highlight {
            color: #60a5fa;
            font-weight: 700;
        }

        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .stat-box {
            text-align: center;
            padding: 2rem;
            background: linear-gradient(135deg, rgba(59, 130, 246, 0.1), rgba(6, 182, 212, 0.1));
            border-radius: 10px;
            transition: all 0.3s ease;
            animation: fadeInUp 0.6s ease-out;
            border: 1px solid rgba(59, 130, 246, 0.3);
        }

        .stat-box:hover {
            transform: translateY(-5px);
            background: linear-gradient(135deg, var(--primary), var(--accent));
            color: white;
            box-shadow: var(--shadow-lg);
            border-color: var(--accent);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 800;
            margin-bottom: 0.5rem;
            color: #60a5fa;
        }

        .stat-box:hover .stat-number {
            color: #bfdbfe;
        }

        .stat-label {
            font-size: 0.95rem;
            font-weight: 600;
            color: #94a3b8;
        }

        .stat-box:hover .stat-label {
            color: rgba(255, 255, 255, 0.9);
        }

        .contact-section {
            background: linear-gradient(135deg, var(--primary), var(--accent));
            border-radius: 12px;
            padding: 4rem;
            text-align: center;
            color: white;
            animation: fadeInUp 0.6s ease-out;
            box-shadow: var(--shadow-lg);
        }

        .contact-section h2 {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            font-weight: 700;
        }

        .contact-email {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.95;
        }

        .social-links {
            display: flex;
            gap: 1.5rem;
            justify-content: center;
            flex-wrap: wrap;
        }

        .social-link {
            width: 50px;
            height: 50px;
            background: rgba(255, 255, 255, 0.2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
            font-size: 1.2rem;
            border: 2px solid rgba(255, 255, 255, 0.5);
        }

        .social-link:hover {
            background: white;
            color: var(--primary);
            transform: translateY(-5px);
            border-color: white;
            box-shadow: var(--shadow-lg);
        }

        .cert-section {
            margin-top: 4rem;
            padding: 2rem;
            text-align: center;
            background: #1e293b;
            border-radius: 12px;
            box-shadow: var(--shadow-md);
            border: 1px solid rgba(59, 130, 246, 0.2);
            animation: fadeInUp 0.6s ease-out;
        }

        .cert-section h3 {
            margin-bottom: 1.5rem;
            color: #f8fafc;
            font-size: 1.5rem;
            font-weight: 700;
        }

        .cert-badge {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 1.5rem;
            background: linear-gradient(135deg, #f97316, #fb923c);
            color: white;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            box-shadow: var(--shadow-md);
        }

        .cert-badge:hover {
            transform: translateY(-3px);
            box-shadow: var(--shadow-lg);
        }

        footer {
            background: var(--secondary);
            color: white;
            text-align: center;
            padding: 2.5rem;
            margin-top: 4rem;
        }

        footer p {
            margin: 0.5rem 0;
        }

        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 2.5rem;
            }

            .hero-content .subtitle {
                font-size: 1.2rem;
            }

            .section-title {
                font-size: 2rem;
            }

            .header-content {
                flex-direction: column;
                gap: 1rem;
            }

            nav {
                gap: 1.5rem;
                flex-wrap: wrap;
                justify-content: center;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn {
                width: 100%;
                justify-content: center;
            }

            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
                gap: 1rem;
            }

            .contact-section {
                padding: 2rem;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="header-content">
            <div class="logo">DP</div>
            <nav>
                <a href="#about">About</a>
                <a href="#projects">Projects</a>
                <a href="#skills">Skills</a>
                <a href="#contact">Contact</a>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="hero-content">
            <h1>Hi 👋, I'm <span>Daivik Patel</span></h1>
            <div class="subtitle">
                A passionate <span class="typing">Backend Developer</span> from India
            </div>
            <p style="color: var(--text-secondary); margin-bottom: 2rem; font-size: 1.1rem;">
                Building robust systems and scalable applications with modern technologies
            </p>
            <div class="cta-buttons">
                <a href="#projects" class="btn btn-primary">
                    <i class="fas fa-arrow-down"></i> View My Work
                </a>
                <a href="mailto:daivikp40@gmail.com" class="btn btn-secondary">
                    <i class="fas fa-envelope"></i> Get in Touch
                </a>
            </div>
        </div>
        <div class="scroll-indicator">
            <i class="fas fa-chevron-down"></i>
        </div>
    </section>

    <div class="container">
        <section id="about">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <p class="about-text">
                    I'm a dedicated backend developer with a passion for creating efficient, scalable solutions. 
                    Currently working on <span class="highlight">GearGuard</span> - a Computerized Maintenance Management System (CMMS). 
                    I have hands-on experience with modern web technologies and love solving complex problems with clean, maintainable code.
                </p>
                <div class="stats">
                    <div class="stat-box">
                        <div class="stat-number">2+</div>
                        <div class="stat-label">Years of Experience</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number">10+</div>
                        <div class="stat-label">Projects Completed</div>
                    </div>
                    <div class="stat-box">
                        <div class="stat-number">5+</div>
                        <div class="stat-label">Technologies Mastered</div>
                    </div>
                </div>
            </div>
        </section>

        <section id="projects">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-header">
                        <h3>🛠️ GearGuard</h3>
                        <p>Maintenance Management System</p>
                    </div>
                    <div class="project-content">
                        <p>A comprehensive CMMS platform for managing equipment maintenance, work orders, and asset lifecycle.</p>
                        <div class="project-tech">
                            <span class="tech-badge">Node.js</span>
                            <span class="tech-badge">MongoDB</span>
                            <span class="tech-badge">Express</span>
                        </div>
                        <p style="font-size: 0.9rem; color: var(--text-secondary); margin-top: 1rem;">Currently in development</p>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>✈️ Travel Bharat</h3>
                        <p>Travel Discovery Platform</p>
                    </div>
                    <div class="project-content">
                        <p>A full-stack web application for discovering travel destinations across India with interactive maps and guides.</p>
                        <div class="project-tech">
                            <span class="tech-badge">React</span>
                            <span class="tech-badge">Node.js</span>
                            <span class="tech-badge">MongoDB</span>
                        </div>
                        <a href="https://travel-bharat-tau.vercel.app/" class="project-link" target="_blank">
                            View Live <i class="fas fa-external-link-alt"></i>
                        </a>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>🚀 Backend Systems</h3>
                        <p>RESTful APIs & Microservices</p>
                    </div>
                    <div class="project-content">
                        <p>Robust backend systems with authentication, data validation, and optimized database queries.</p>
                        <div class="project-tech">
                            <span class="tech-badge">Node.js</span>
                            <span class="tech-badge">PostgreSQL</span>
                            <span class="tech-badge">Redis</span>
                        </div>
                        <p style="font-size: 0.9rem; color: var(--text-secondary); margin-top: 1rem;">Portfolio projects</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="skills">
            <h2 class="section-title">Skills & Technologies</h2>
            <div class="skills-section">
                <div class="skills-grid">
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fab fa-js-square"></i>
                        </div>
                        <p>JavaScript</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fab fa-node-js"></i>
                        </div>
                        <p>Node.js</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-database"></i>
                        </div>
                        <p>MongoDB</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fas fa-database"></i>
                        </div>
                        <p>PostgreSQL</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fab fa-react"></i>
                        </div>
                        <p>React</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fab fa-python"></i>
                        </div>
                        <p>Python</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fab fa-python"></i>
                        </div>
                        <p>Django</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fab fa-css3-alt"></i>
                        </div>
                        <p>CSS3</p>
                    </div>
                    <div class="skill-item">
                        <div class="skill-icon">
                            <i class="fab fa-html5"></i>
                        </div>
                        <p>HTML5</p>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact">
            <h2 class="section-title">Let's Connect</h2>
            <div class="contact-section">
                <h2>Get in Touch</h2>
                <p class="contact-email">daivikp40@gmail.com</p>
                <p style="margin-bottom: 2rem; opacity: 0.95;">Feel free to reach out to discuss opportunities, projects, or just to say hello!</p>
                <div class="social-links">
                    <a href="https://www.linkedin.com/in/daivik-patel-0b933836b" class="social-link" target="_blank">
                        <i class="fab fa-linkedin-in"></i>
                    </a>
                    <a href="https://github.com" class="social-link" target="_blank">
                        <i class="fab fa-github"></i>
                    </a>
                    <a href="mailto:daivikp40@gmail.com" class="social-link" target="_blank">
                        <i class="fas fa-envelope"></i>
                    </a>
                    <a href="https://twitter.com" class="social-link" target="_blank">
                        <i class="fab fa-twitter"></i>
                    </a>
                </div>
            </div>

            <div class="cert-section">
                <h3>Certifications</h3>
                <a href="https://www.credly.com/badges/d8be840b-e485-472a-b6e0-956f6413cae4/public_url" class="cert-badge" target="_blank">
                    <i class="fab fa-oracle"></i>
                    Oracle OCI DevOps Professional
                </a>
            </div>
        </section>
    </div>

    <footer>
        <p>&copy; 2024 Daivik Patel. All rights reserved.</p>
        <p style="font-size: 0.9rem;">Crafted with <i class="fas fa-heart" style="color: #ef4444;"></i> using modern web technologies</p>
    </footer>

    <script>
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });

        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = getComputedStyle(entry.target).animation;
                }
            });
        }, observerOptions);

        document.querySelectorAll('section, .project-card, .skill-item, .stat-box').forEach(el => {
            observer.observe(el);
        });

        function animateCounter(element, target) {
            let current = 0;
            const increment = target / 30;
            const interval = setInterval(() => {
                current += increment;
                if (current >= target) {
                    element.textContent = target + '+';
                    clearInterval(interval);
                } else {
                    element.textContent = Math.floor(current) + '+';
                }
            }, 30);
        }

        const statBoxes = document.querySelectorAll('.stat-box');
        const statObserver = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting && !entry.target.dataset.animated) {
                    const numberEl = entry.target.querySelector('.stat-number');
                    const number = parseInt(numberEl.textContent);
                    animateCounter(numberEl, number);
                    entry.target.dataset.animated = 'true';
                }
            });
        }, { threshold: 0.5 });

        statBoxes.forEach(box => statObserver.observe(box));
    </script>
</body>
</html>
