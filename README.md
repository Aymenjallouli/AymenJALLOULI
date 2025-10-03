<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aymen Jallouli - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #0a0e27 0%, #1a1f3a 100%);
            color: #e0e0e0;
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Animated Background */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            opacity: 0.1;
        }

        .bg-animation span {
            position: absolute;
            display: block;
            width: 20px;
            height: 20px;
            background: rgba(99, 102, 241, 0.5);
            animation: float 15s infinite;
        }

        .bg-animation span:nth-child(1) { left: 10%; animation-delay: 0s; }
        .bg-animation span:nth-child(2) { left: 20%; animation-delay: 2s; animation-duration: 12s; }
        .bg-animation span:nth-child(3) { left: 30%; animation-delay: 4s; }
        .bg-animation span:nth-child(4) { left: 40%; animation-delay: 6s; animation-duration: 18s; }
        .bg-animation span:nth-child(5) { left: 50%; animation-delay: 8s; }
        .bg-animation span:nth-child(6) { left: 60%; animation-delay: 10s; animation-duration: 14s; }
        .bg-animation span:nth-child(7) { left: 70%; animation-delay: 12s; }
        .bg-animation span:nth-child(8) { left: 80%; animation-delay: 14s; animation-duration: 20s; }

        @keyframes float {
            0%, 100% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) rotate(360deg);
            }
        }

        /* Header Section */
        .header {
            text-align: center;
            padding: 80px 20px;
            animation: fadeInDown 1s ease-out;
        }

        .header h1 {
            font-size: 4rem;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 10px rgba(102, 126, 234, 0.5)); }
            to { filter: drop-shadow(0 0 20px rgba(118, 75, 162, 0.8)); }
        }

        .subtitle {
            font-size: 1.5rem;
            color: #a0aec0;
            margin-bottom: 30px;
        }

        .social-links {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .social-btn {
            padding: 12px 30px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-block;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.3);
        }

        .social-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(102, 126, 234, 0.5);
        }

        /* Section Styling */
        .section {
            margin: 60px 0;
            animation: fadeIn 1s ease-out;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            position: relative;
            color: #fff;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            margin: 20px auto;
            border-radius: 2px;
        }

        /* Skills Grid */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 30px;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
            animation: slideUp 0.6s ease-out;
        }

        .skill-category:hover {
            transform: translateY(-10px);
            border-color: rgba(102, 126, 234, 0.5);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
        }

        .skill-category h3 {
            color: #667eea;
            font-size: 1.5rem;
            margin-bottom: 25px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(140px, 1fr));
            gap: 15px;
        }

        .tech-item {
            background: rgba(255, 255, 255, 0.03);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 12px;
            padding: 15px;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-item:hover {
            background: rgba(102, 126, 234, 0.1);
            border-color: #667eea;
            transform: scale(1.05);
        }

        .tech-item img {
            width: 40px;
            height: 40px;
            margin-bottom: 10px;
            filter: brightness(0.9);
            transition: all 0.3s ease;
        }

        .tech-item:hover img {
            filter: brightness(1.2);
            transform: rotateY(360deg);
        }

        .tech-item span {
            display: block;
            font-size: 0.85rem;
            color: #a0aec0;
        }

        /* Progress Bars */
        .language-bars {
            max-width: 800px;
            margin: 0 auto 60px;
        }

        .language-bar {
            margin-bottom: 30px;
        }

        .language-label {
            display: flex;
            justify-content: space-between;
            margin-bottom: 10px;
            font-weight: 600;
        }

        .progress-container {
            width: 100%;
            height: 12px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
            overflow: hidden;
            position: relative;
        }

        .progress-bar {
            height: 100%;
            background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
            border-radius: 10px;
            transition: width 2s ease;
            position: relative;
            overflow: hidden;
        }

        .progress-bar::after {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            bottom: 0;
            right: 0;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: shimmer 2s infinite;
        }

        @keyframes shimmer {
            0% { transform: translateX(-100%); }
            100% { transform: translateX(100%); }
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(400px, 1fr));
            gap: 40px;
            margin-top: 50px;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.4s ease;
            position: relative;
        }

        .project-card:hover {
            transform: translateY(-15px);
            box-shadow: 0 20px 60px rgba(102, 126, 234, 0.3);
            border-color: rgba(102, 126, 234, 0.5);
        }

        .project-header {
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            padding: 30px;
            position: relative;
            overflow: hidden;
        }

        .project-header::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -50%;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 0%, transparent 70%);
            animation: rotate 20s linear infinite;
        }

        @keyframes rotate {
            from { transform: rotate(0deg); }
            to { transform: rotate(360deg); }
        }

        .project-header h3 {
            font-size: 1.8rem;
            color: white;
            margin-bottom: 10px;
            position: relative;
            z-index: 1;
        }

        .project-tags {
            display: flex;
            gap: 10px;
            flex-wrap: wrap;
            position: relative;
            z-index: 1;
        }

        .tag {
            background: rgba(255, 255, 255, 0.2);
            padding: 5px 15px;
            border-radius: 20px;
            font-size: 0.85rem;
            color: white;
        }

        .project-body {
            padding: 30px;
        }

        .project-description {
            color: #a0aec0;
            margin-bottom: 20px;
            line-height: 1.8;
        }

        .project-links {
            display: flex;
            gap: 15px;
            margin-top: 20px;
        }

        .project-link {
            padding: 10px 25px;
            background: rgba(102, 126, 234, 0.2);
            color: #667eea;
            text-decoration: none;
            border-radius: 10px;
            border: 1px solid #667eea;
            transition: all 0.3s ease;
            font-weight: 600;
        }

        .project-link:hover {
            background: #667eea;
            color: white;
            transform: translateX(5px);
        }

        /* Stats Section */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 50px;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            padding: 40px;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            border-color: rgba(102, 126, 234, 0.5);
            box-shadow: 0 15px 40px rgba(102, 126, 234, 0.2);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: bold;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 10px;
        }

        .stat-label {
            color: #a0aec0;
            font-size: 1.1rem;
        }

        /* Animations */
        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .projects-grid,
            .tech-grid {
                grid-template-columns: 1fr;
            }
        }

        /* Footer */
        .footer {
            text-align: center;
            padding: 50px 20px;
            margin-top: 100px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }

        .footer-quote {
            font-style: italic;
            color: #a0aec0;
            font-size: 1.2rem;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="bg-animation">
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
        <span></span>
    </div>

    <div class="container">
        <!-- Header -->
        <header class="header">
            <h1>👨‍💻 Aymen Jallouli</h1>
            <p class="subtitle">Full-Stack Software Engineer | DevOps Enthusiast | Cloud Architecture</p>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/aymen-jallouli-713534254/" class="social-btn" target="_blank">
                    💼 LinkedIn
                </a>
                <a href="mailto:aymen.jallouli@esprit.tn" class="social-btn">
                    📧 Email
                </a>
                <a href="https://github.com/Aymenjallouli" class="social-btn" target="_blank">
                    🔗 GitHub
                </a>
            </div>
        </header>

        <!-- About Section -->
        <section class="section">
            <h2 class="section-title">🎯 Professional Summary</h2>
            <div style="max-width: 900px; margin: 0 auto; text-align: center; font-size: 1.2rem; color: #a0aec0; line-height: 2;">
                Passionate full-stack developer with expertise in building <strong style="color: #667eea;">scalable</strong>, 
                <strong style="color: #667eea;">resilient</strong>, and <strong style="color: #667eea;">high-performance</strong> applications. 
                Specialized in modern web technologies, microservices architecture, and DevOps practices.
            </div>
        </section>

        <!-- Programming Languages -->
        <section class="section">
            <h2 class="section-title">💻 Programming Languages</h2>
            <div class="language-bars">
                <div class="language-bar">
                    <div class="language-label">
                        <span>☕ Java</span>
                        <span>95%</span>
                    </div>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 95%;"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-label">
                        <span>🟨 JavaScript/TypeScript</span>
                        <span>90%</span>
                    </div>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 90%;"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-label">
                        <span>🔷 C/C++</span>
                        <span>80%</span>
                    </div>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 80%;"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-label">
                        <span>🐍 Python</span>
                        <span>75%</span>
                    </div>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 75%;"></div>
                    </div>
                </div>
                <div class="language-bar">
                    <div class="language-label">
                        <span>🐘 PHP</span>
                        <span>70%</span>
                    </div>
                    <div class="progress-container">
                        <div class="progress-bar" style="width: 70%;"></div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Skills Section -->
        <section class="section">
            <h2 class="section-title">🛠️ Technical Skills</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>🎨 Frontend Development</h3>
                    <div class="tech-grid">
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React">
                            <span>React</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/angularjs/angularjs-original.svg" alt="Angular">
                            <span>Angular</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg" alt="Vue">
                            <span>Vue.js</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nextjs/nextjs-original.svg" alt="Next.js" style="filter: invert(1);">
                            <span>Next.js</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-plain.svg" alt="Tailwind">
                            <span>Tailwind</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg" alt="Bootstrap">
                            <span>Bootstrap</span>
                        </div>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>⚙️ Backend Development</h3>
                    <div class="tech-grid">
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/spring/spring-original.svg" alt="Spring">
                            <span>Spring Boot</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="Node.js">
                            <span>Node.js</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" alt="Express" style="filter: invert(1);">
                            <span>Express</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/django/django-plain.svg" alt="Django" style="filter: invert(1);">
                            <span>Django</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/laravel/laravel-plain.svg" alt="Laravel">
                            <span>Laravel</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/symfony/symfony-original.svg" alt="Symfony">
                            <span>Symfony</span>
                        </div>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>🗄️ Databases</h3>
                    <div class="tech-grid">
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mysql/mysql-original.svg" alt="MySQL">
                            <span>MySQL</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/postgresql/postgresql-original.svg" alt="PostgreSQL">
                            <span>PostgreSQL</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" alt="MongoDB">
                            <span>MongoDB</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/redis/redis-original.svg" alt="Redis">
                            <span>Redis</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/oracle/oracle-original.svg" alt="Oracle">
                            <span>Oracle</span>
                        </div>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>🚀 DevOps & Cloud</h3>
                    <div class="tech-grid">
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/docker/docker-original.svg" alt="Docker">
                            <span>Docker</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/kubernetes/kubernetes-plain.svg" alt="Kubernetes">
                            <span>Kubernetes</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/jenkins/jenkins-original.svg" alt="Jenkins">
                            <span>Jenkins</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git">
                            <span>Git</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/prometheus/prometheus-original.svg" alt="Prometheus">
                            <span>Prometheus</span>
                        </div>
                        <div class="tech-item">
                            <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/grafana/grafana-original.svg" alt="Grafana">
                            <span>Grafana</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Projects Section -->
        <section class="section">
            <h2 class="section-title">🚀 Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-header">
                        <h3>🤖 AI Smart Dashboard</h3>
                        <div class="project-tags">
                            <span class="tag">Flask</span>
                            <span class="tag">React</span>
                            <span class="tag">ML</span>
                            <span class="tag">XGBoost</span>
                        </div>
                    </div>
                    <div class="project-body">
                        <p class="project-description">
                            Intelligent parking prediction system using machine learning for real-time occupancy forecasting 
                            and duration prediction with interactive data visualization.
                        </p>
                        <div class="project-links">
                            <a href="https://github.com/Aymenjallouli/Ai-Dashboard-Ml" class="project-link" target="_blank">📂 Code</a>
                            <a href="https://parkini-smart-dashboard.onrender.com" class="project-link" target="_blank">🌐 Live Demo</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>🅿️ Parkini System</h3>
                        <div class="project-tags">
                            <span class="tag">Express.js</span>
                            <span class="tag">React</span>
                            <span class="tag">CI/CD</span>
                            <span class="tag">Docker</span>
                        </div>
                    </div>
                    <div class="project-body">
                        <p class="project-description">
                            Complete intelligent parking management solution with automated CI/CD pipeline, 
                            containerized microservices, and real-time monitoring infrastructure.
                        </p>
                        <div class="project-links">
                            <a href="https://github.com/PiDev-2025/Parkini" class="project-link" target="_blank">📂 Code</a>
                            <a href="https://front-end-front-office.vercel.app" class="project-link" target="_blank">🌐 Live Demo</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>🍽️ Restaurant Management</h3>
                        <div class="project-tags">
                            <span class="tag">Spring Boot</span>
                            <span class="tag">Angular</span>
                            <span class="tag">Microservices</span>
                            <span class="tag">Eureka</span>
                        </div>
                    </div>
                    <div class="project-body">
                        <p class="project-description">
                            Scalable microservices architecture for restaurant order management with service discovery, 
                            API Gateway routing, and distributed transaction handling.
                        </p>
                        <div class="project-links">
                            <a href="https://github.com/Application-Web-Distribution-Project/Application_Web_Distibue" class="project-link" target="_blank">📂 Code</a>
                        </div>
                    </div>
                </div>

                <div class="project-card">
                    <div class="project-header">
                        <h3>🔧 Enterprise DevOps</h3>
                        <div class="project-tags">
                            <span class="tag">Jenkins</span>
                            <span class="tag">SonarQube</span>
                            <span class="tag">Nexus</span>
                            <span class="tag">Monitoring</span>
                        </div>
                    </div>
                    <div class="project-body">
                        <p class="project-description">
                            Production-ready CI/CD infrastructure with automated workflows, security scanning, 
                            artifact management, and comprehensive application monitoring.
                        </p>
                        <div class="project-links">
                            <a href="https://github.com/marwaniiwael18/DEVOPS-Project/tree/Aymenjallouli_4twin3_thunder" class="project-link" target="_blank">📂 Code</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Stats Section -->
        <section class="section">
            <h2 class="section-title">📊 GitHub Statistics</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-number">500+</div>
                    <div class="stat-label">Commits This Year</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">5+</div>
                    <div class="stat-label">Years Experience</div>
                </div>
            </div>
        </section>

        <!-- Learning Section -->
        <section class="section">
            <h2 class="section-title">🎓 Continuous Learning</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>🔐 Advanced Kubernetes</h3>
                    <p style="color: #a0aec0; line-height: 1.8;">
                        Exploring container orchestration, scaling strategies, and cloud-native architectures.
                    </p>
                </div>
                <div class="skill-category">
                    <h3>☁️ Cloud Architectures</h3>
                    <p style="color: #a0aec0; line-height: 1.8;">
                        Deepening knowledge in AWS/Azure services, serverless computing, and infrastructure automation.
                    </p>
                </div>
                <div class="skill-category">
                    <h3>🧠 MLOps</h3>
                    <p style="color: #a0aec0; line-height: 1.8;">
                        Learning machine learning deployment, monitoring, and lifecycle management practices.
                    </p>
                </div>
                <div class="skill-category">
                    <h3>🔄 GraphQL & Apollo</h3>
                    <p style="color: #a0aec0; line-height: 1.8;">
                        Studying modern API architectures and federated graph implementations.
                    </p>
                </div>
            </div>
        </section>

        <!-- Footer -->
        <footer class="footer">
            <p class="footer-quote">
                "Code is like humor. When you have to explain it, it's bad." - Cory House
            </p>
            <p style="color: #667eea; font-weight: 600; margin-top: 30px;">
                ⚡ Open to collaboration on innovative projects and exciting opportunities!
            </p>
            <div class="social-links" style="margin-top: 30px;">
                <a href="https://www.linkedin.com/in/aymen-jallouli-713534254/" class="social-btn" target="_blank">
                    Connect on LinkedIn
                </a>
                <a href="mailto:aymen.jallouli@esprit.tn" class="social-btn">
                    Send an Email
                </a>
            </div>
        </footer>
    </div>

    <script>
        // Animate progress bars on scroll
        const observerOptions = {
            threshold: 0.5,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.width = entry.target.getAttribute('data-width') || entry.target.style.width;
                }
            });
        }, observerOptions);

        document.querySelectorAll('.progress-bar').forEach(bar => {
            const width = bar.style.width;
            bar.setAttribute('data-width', width);
            bar.style.width = '0%';
            observer.observe(bar);
        });

        // Add stagger animation to skill categories
        const skillCategories = document.querySelectorAll('.skill-category');
        skillCategories.forEach((category, index) => {
            category.style.animationDelay = `${index * 0.1}s`;
        });

        // Add stagger animation to project cards
        const projectCards = document.querySelectorAll('.project-card');
        projectCards.forEach((card, index) => {
            card.style.animation = 'slideUp 0.6s ease-out';
            card.style.animationDelay = `${index * 0.15}s`;
            card.style.animationFillMode = 'both';
        });

        // Tech item hover effect with 3D rotation
        const techItems = document.querySelectorAll('.tech-item');
        techItems.forEach(item => {
            item.addEventListener('mouseenter', function() {
                const img = this.querySelector('img');
                img.style.transition = 'transform 0.6s ease';
            });
        });

        // Smooth scroll for anchors
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

        // Add parallax effect to header
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const header = document.querySelector('.header');
            if (header) {
                header.style.transform = `translateY(${scrolled * 0.5}px)`;
                header.style.opacity = 1 - (scrolled / 500);
            }
        });

        // Animate stats on scroll
        const statCards = document.querySelectorAll('.stat-card');
        const statsObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const statNumber = entry.target.querySelector('.stat-number');
                    const finalNumber = parseInt(statNumber.textContent);
                    let currentNumber = 0;
                    const increment = finalNumber / 50;
                    
                    const counter = setInterval(() => {
                        currentNumber += increment;
                        if (currentNumber >= finalNumber) {
                            statNumber.textContent = finalNumber + '+';
                            clearInterval(counter);
                        } else {
                            statNumber.textContent = Math.floor(currentNumber) + '+';
                        }
                    }, 30);
                    
                    statsObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.5 });

        statCards.forEach(card => statsObserver.observe(card));
    </script>
</body>
</html>-number">15+</div>
                    <div class="stat-label">Projects Completed</div>
                </div>
                <div class="stat-card">
                    <div class="stat-number">10+</div>
                    <div class="stat-label">Technologies Mastered</div>
                </div>
                <div class="stat-card">
                    <div class="stat
