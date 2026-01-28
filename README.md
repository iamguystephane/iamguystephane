<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Guy Stephane - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
            position: relative;
        }

        /* Animated background particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            overflow: hidden;
            z-index: 0;
            pointer-events: none;
        }

        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: rgba(255, 255, 255, 0.5);
            border-radius: 50%;
            animation: float 15s infinite;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0) translateX(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) translateX(100px);
                opacity: 0;
            }
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            position: relative;
            z-index: 1;
        }

        /* Hero Section */
        .hero {
            text-align: center;
            padding: 60px 20px;
            animation: fadeInDown 1s ease-out;
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .avatar-container {
            position: relative;
            display: inline-block;
            margin-bottom: 30px;
        }

        .avatar {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 5px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.3);
            animation: float-avatar 3s ease-in-out infinite;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        }

        @keyframes float-avatar {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        .glow-ring {
            position: absolute;
            top: -10px;
            left: -10px;
            right: -10px;
            bottom: -10px;
            border-radius: 50%;
            background: linear-gradient(45deg, #f093fb 0%, #f5576c 100%);
            opacity: 0.5;
            filter: blur(20px);
            animation: pulse 2s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% {
                transform: scale(1);
                opacity: 0.5;
            }
            50% {
                transform: scale(1.1);
                opacity: 0.8;
            }
        }

        h1 {
            font-size: 3.5em;
            margin-bottom: 15px;
            background: linear-gradient(45deg, #fff, #f093fb);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: fadeIn 1.5s ease-out;
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        .subtitle {
            font-size: 1.5em;
            margin-bottom: 30px;
            opacity: 0.9;
            animation: fadeIn 2s ease-out;
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin: 30px 0;
            animation: fadeIn 2.5s ease-out;
        }

        .social-link {
            display: inline-block;
            padding: 12px 30px;
            background: rgba(255, 255, 255, 0.1);
            border: 2px solid rgba(255, 255, 255, 0.2);
            border-radius: 50px;
            color: #fff;
            text-decoration: none;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            font-weight: 600;
        }

        .social-link:hover {
            background: rgba(255, 255, 255, 0.2);
            border-color: rgba(255, 255, 255, 0.5);
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .visitor-badge {
            margin-top: 20px;
            animation: fadeIn 3s ease-out;
        }

        /* About Section */
        .section {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 30px;
            padding: 50px;
            margin: 40px 0;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: slideInUp 1s ease-out;
            box-shadow: 0 20px 60px rgba(0, 0, 0, 0.2);
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section-title {
            font-size: 2.5em;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .section-title::before {
            content: '';
            width: 50px;
            height: 5px;
            background: linear-gradient(45deg, #f093fb, #f5576c);
            border-radius: 5px;
        }

        .about-content {
            font-size: 1.2em;
            line-height: 2;
            opacity: 0.95;
        }

        .about-item {
            margin: 15px 0;
            padding-left: 30px;
            position: relative;
        }

        .about-item::before {
            content: '▸';
            position: absolute;
            left: 0;
            color: #f093fb;
            font-size: 1.3em;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(100px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px 20px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            cursor: pointer;
        }

        .skill-card:hover {
            transform: translateY(-10px) scale(1.05);
            background: rgba(255, 255, 255, 0.2);
            border-color: rgba(255, 255, 255, 0.4);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .skill-icon {
            width: 60px;
            height: 60px;
            margin: 0 auto 15px;
            filter: drop-shadow(0 5px 15px rgba(0, 0, 0, 0.3));
            transition: all 0.3s ease;
        }

        .skill-card:hover .skill-icon {
            transform: rotateY(360deg);
        }

        .skill-name {
            font-weight: 600;
            font-size: 1.1em;
            margin-top: 10px;
        }

        /* Floating animation for skills */
        .skill-card:nth-child(1) { animation: floatSkill 3s ease-in-out infinite; }
        .skill-card:nth-child(2) { animation: floatSkill 3.2s ease-in-out infinite; }
        .skill-card:nth-child(3) { animation: floatSkill 3.4s ease-in-out infinite; }
        .skill-card:nth-child(4) { animation: floatSkill 3.6s ease-in-out infinite; }
        .skill-card:nth-child(5) { animation: floatSkill 3.8s ease-in-out infinite; }
        .skill-card:nth-child(6) { animation: floatSkill 4s ease-in-out infinite; }
        .skill-card:nth-child(7) { animation: floatSkill 4.2s ease-in-out infinite; }
        .skill-card:nth-child(8) { animation: floatSkill 4.4s ease-in-out infinite; }
        .skill-card:nth-child(9) { animation: floatSkill 4.6s ease-in-out infinite; }
        .skill-card:nth-child(10) { animation: floatSkill 4.8s ease-in-out infinite; }

        @keyframes floatSkill {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-10px);
            }
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 40px 20px;
            opacity: 0.8;
            font-size: 1.1em;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5em;
            }

            .subtitle {
                font-size: 1.2em;
            }

            .section {
                padding: 30px 20px;
            }

            .section-title {
                font-size: 2em;
            }

            .social-links {
                flex-direction: column;
                align-items: center;
            }

            .skills-grid {
                grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
                gap: 20px;
            }
        }
    </style>
</head>
<body>
    <!-- Animated particles background -->
    <div class="particles" id="particles"></div>

    <div class="container">
        <!-- Hero Section -->
        <div class="hero">
            <div class="avatar-container">
                <div class="glow-ring"></div>
                <img class="avatar" src="https://media.giphy.com/media/M9gbBd9nbDrOTu1Mqx/giphy.gif" alt="Guy Stephane">
            </div>
            
            <h1>Hey There 👋</h1>
            <p class="subtitle">I'm Guy Stephane</p>
            
            <div class="social-links">
                <a href="https://www.linkedin.com/in/guy-stephane-489555259/" class="social-link">
                    💼 LinkedIn
                </a>
                <a href="https://www.youtube.com/@Iamstephane" class="social-link">
                    🎥 YouTube
                </a>
                <a href="https://x.com/iamguystephane" class="social-link">
                    🐦 Twitter
                </a>
            </div>

            <div class="visitor-badge">
                <img src="https://visitor-badge.laobi.icu/badge?page_id=guystephane.portfolio" alt="Visitors">
            </div>
        </div>

        <!-- About Section -->
        <div class="section">
            <h2 class="section-title">👨‍💻 About Me</h2>
            <div class="about-content">
                <p style="margin-bottom: 25px;">I'm <strong>Guy Stephane</strong> from Cameroon 🇨🇲</p>
                
                <div class="about-item">
                    🔭 I'm a <strong>full-stack software developer</strong>, specializing in building stunning websites and cross-platform mobile applications
                </div>
                
                <div class="about-item">
                    📚 Currently expanding my skills by learning <strong>Java</strong>
                </div>
                
                <div class="about-item">
                    ⚡ In my free time, I code, game, listen to music, and watch anime
                </div>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="section">
            <h2 class="section-title">🛠️ Technologies & Tools</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/nextjs-dark.svg" class="skill-icon" alt="Next.js">
                    <div class="skill-name">Next.js</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/react.svg" class="skill-icon" alt="React">
                    <div class="skill-name">React</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/nodejs.svg" class="skill-icon" alt="Node.js">
                    <div class="skill-name">Node.js</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/mongodb.svg" class="skill-icon" alt="MongoDB">
                    <div class="skill-name">MongoDB</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/php.svg" class="skill-icon" alt="PHP">
                    <div class="skill-name">PHP</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/java.svg" class="skill-icon" alt="Java">
                    <div class="skill-name">Java</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://static.cdnlogo.com/logos/t/58/tailwind-css.svg" class="skill-icon" alt="Tailwind">
                    <div class="skill-name">Tailwind</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/cplusplus.png" class="skill-icon" alt="C++">
                    <div class="skill-name">C++</div>
                </div>
                
                <div class="skill-card">
                    <img src="https://devicons.railway.com/i/c.svg" class="skill-icon" alt="C">
                    <div class="skill-name">C</div>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <footer>
            <p>✨ Made with passion by Guy Stephane ✨</p>
            <p style="margin-top: 10px; font-size: 0.9em; opacity: 0.7;">Full Stack Developer | Cameroon 🇨🇲</p>
        </footer>
    </div>

    <script>
        // Create animated particles
        const particlesContainer = document.getElementById('particles');
        const particleCount = 50;

        for (let i = 0; i < particleCount; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particlesContainer.appendChild(particle);
        }

        // Add scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'slideInUp 1s ease-out';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.section').forEach(section => {
            observer.observe(section);
        });
    </script>
</body>
</html>
