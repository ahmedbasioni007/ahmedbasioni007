<!DOCTYPE html>
<html lang="en" dir="ltr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ahmed Basioni - Full-Stack .NET Developer</title>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <style>
        :root {
            --amazon-orange: #ff9900;
            --amazon-blue: #232f3e;
            --amazon-light: #37475a;
            --amazon-dark: #131921;
            --success-green: #00853e;
            --info-blue: #0073bb;
            --warning-orange: #b12704;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: linear-gradient(135deg, #2c3e50 0%, #34495e 25%, #3498db 50%, #2980b9 75%, #1e3c72 100%);
            min-height: 100vh;
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            padding: 40px 20px;
            position: relative;
            overflow-x: hidden;
        }

        body::before {
            content: '';
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 20% 80%, rgba(52, 73, 94, 0.4) 0%, transparent 50%), 
                        radial-gradient(circle at 80% 20%, rgba(52, 152, 219, 0.3) 0%, transparent 50%);
            pointer-events: none;
            z-index: -1;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            position: relative;
            z-index: 1;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.12);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 2rem;
            margin-bottom: 2rem;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1);
            transition: all 0.3s ease;
            animation: slideUp 0.8s ease-out;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .glass-card:hover {
            box-shadow: 0 12px 40px rgba(0, 0, 0, 0.15);
            transform: translateY(-2px);
            background: rgba(255, 255, 255, 0.15);
        }

        /* Header Section */
        .header {
            text-align: center;
            margin-bottom: 30px;
        }

        .profile-avatar {
            width: 180px;
            height: 180px;
            border-radius: 50%;
            border: 4px solid var(--amazon-orange);
            box-shadow: 0 8px 32px rgba(255, 153, 0, 0.3);
            margin: 0 auto 1.5rem;
            background: linear-gradient(135deg, var(--amazon-orange), var(--info-blue));
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            color: white;
            position: relative;
            overflow: hidden;
            animation: glow 2s infinite alternate;
        }

        @keyframes glow {
            from { box-shadow: 0 0 20px rgba(255, 153, 0, 0.3); }
            to { box-shadow: 0 0 40px rgba(255, 153, 0, 0.6); }
        }

        .profile-avatar::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transform: rotate(45deg);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: rotate(45deg) translateX(-100%); }
            50% { transform: rotate(45deg) translateX(100%); }
            100% { transform: rotate(45deg) translateX(100%); }
        }

        h1 {
            color: white;
            font-size: 3em;
            margin-bottom: 10px;
            text-shadow: 2px 2px 10px rgba(0, 0, 0, 0.3);
            background: linear-gradient(135deg, white, var(--amazon-orange));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .tagline {
            color: var(--amazon-orange);
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 1rem;
        }

        .description {
            color: rgba(255, 255, 255, 0.9);
            font-size: 1.1rem;
            margin-bottom: 1.5rem;
            line-height: 1.6;
        }

        /* Social Links */
        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            flex-wrap: wrap;
        }

        .social-btn {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            color: white;
            padding: 12px 24px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
        }

        .social-btn:hover {
            background: var(--amazon-orange);
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(255, 153, 0, 0.3);
            color: white;
            text-decoration: none;
        }

        /* Section Title */
        .section-title {
            color: var(--amazon-orange);
            font-size: 2em;
            margin-bottom: 2rem;
            text-align: center;
            position: relative;
            padding-bottom: 15px;
            font-weight: 700;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: linear-gradient(90deg, transparent, var(--amazon-orange), transparent);
        }

        /* Stats Section */
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1.5rem;
            margin-bottom: 2rem;
        }

        .stat-box {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            padding: 1.5rem;
            text-align: center;
            transition: all 0.3s ease;
        }

        .stat-box:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.15);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
        }

        .stat-icon {
            font-size: 2.5rem;
            color: var(--amazon-orange);
            margin-bottom: 0.5rem;
        }

        .stat-label {
            color: rgba(255, 255, 255, 0.8);
            font-size: 1.1rem;
            font-weight: 600;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 1.5rem;
        }

        .skill-category {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 15px;
            padding: 1.5rem;
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.2);
            background: rgba(255, 255, 255, 0.15);
        }

        .skill-category h4 {
            color: var(--amazon-orange);
            margin-bottom: 1rem;
            font-weight: 600;
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .skill-tag {
            background: rgba(255, 255, 255, 0.2);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.9rem;
            font-weight: 500;
            color: white;
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: var(--amazon-orange);
            transform: scale(1.05);
        }

        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            border-radius: 20px;
            padding: 2rem;
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.6s;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: translateY(-10px);
            background: rgba(255, 255, 255, 0.15);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.25);
            border-color: var(--amazon-orange);
        }

        .project-icon {
            font-size: 3rem;
            color: var(--amazon-orange);
            margin-bottom: 1rem;
        }

        .project-title {
            color: white;
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 1rem;
        }

        .project-desc {
            color: rgba(255, 255, 255, 0.8);
            margin-bottom: 1rem;
            line-height: 1.6;
            font-size: 0.95rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            margin-bottom: 1rem;
        }

        .tech-badge {
            background: rgba(255, 255, 255, 0.2);
            padding: 5px 12px;
            border-radius: 15px;
            font-size: 0.75rem;
            color: white;
            font-weight: 600;
        }

        .project-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            background: var(--amazon-orange);
            color: white;
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
        }

        .project-link:hover {
            background: #ff7700;
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(255, 153, 0, 0.4);
            color: white;
            text-decoration: none;
        }

        /* About Section */
        .about-content {
            color: rgba(255, 255, 255, 0.9);
            font-size: 1.1rem;
            line-height: 1.8;
            margin-bottom: 1.5rem;
        }

        .quick-facts {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 15px;
            padding: 1.5rem;
            margin-top: 1rem;
        }

        .quick-facts h4 {
            color: var(--amazon-orange);
            margin-bottom: 1rem;
        }

        .fact-item {
            display: flex;
            align-items: center;
            gap: 0.5rem;
            margin-bottom: 0.7rem;
            color: rgba(255, 255, 255, 0.9);
        }

        .fact-item i {
            color: var(--amazon-orange);
            width: 20px;
        }

        @media (max-width: 768px) {
            h1 { font-size: 2em; }
            .tagline { font-size: 1.2rem; }
            .glass-card { padding: 1.5rem; }
            .skills-grid { grid-template-columns: 1fr; }
            .stats-grid { grid-template-columns: repeat(2, 1fr); }
        }
    </style>
</head>
<body>
    <div class="container">
        <!-- Header Section -->
        <div class="glass-card header">
            <div class="profile-avatar">
                <i class="fas fa-user-tie"></i>
            </div>
            <h1>Ahmed Basioni EL-Khateeb</h1>
            <p class="tagline">Full-Stack .NET Developer</p>
            <p class="description">
                Building efficient, reliable solutions with passion and precision
            </p>
            
            <div class="social-links">
                <a href="tel:+201066408193" class="social-btn" target="_blank">
                    <i class="fas fa-phone"></i> Phone
                </a>
                <a href="https://mail.google.com/mail/?view=cm&fs=1&to=ahmedbasuony22322@gmail.com" class="social-btn" target="_blank">
                    <i class="fas fa-envelope"></i> Email
                </a>
                <a href="https://www.linkedin.com/in/ahmed-basioni/" class="social-btn" target="_blank">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://github.com/ahmedbasioni007" class="social-btn" target="_blank">
                    <i class="fab fa-github"></i> GitHub
                </a>
            </div>
        </div>

        <!-- About Me -->
        <div class="glass-card">
            <h2 class="section-title"><i class="fas fa-user"></i> About Me</h2>
            <p class="about-content">
                Driven and analytical professional with a passion for building efficient, reliable solutions. 
                Known for a strong work ethic, attention to detail, and a commitment to continuous improvement. 
                I enjoy learning new technologies and contributing to collaborative team environments.
            </p>
            <p class="about-content">
                With a solid foundation in .NET technologies and modern web development, 
                I specialize in creating robust, scalable applications that deliver exceptional user experiences. 
                My expertise spans both frontend and backend development, allowing me to build complete solutions from concept to deployment.
            </p>
            
            <div class="quick-facts">
                <h4>Quick Facts</h4>
                <div class="fact-item">
                    <i class="fas fa-map-marker-alt"></i>
                    <span>Cairo, Egypt</span>
                </div>
                <div class="fact-item">
                    <i class="fas fa-code"></i>
                    <span>.NET Full-Stack Developer</span>
                </div>
                <div class="fact-item">
                    <i class="fas fa-graduation-cap"></i>
                    <span>ITI Graduate - Intensive Training Program</span>
                </div>
                <div class="fact-item">
                    <i class="fas fa-language"></i>
                    <span>Arabic (Native), English (B2)</span>
                </div>
            </div>
        </div>

        <!-- GitHub Stats -->
        <div class="glass-card">
            <h2 class="section-title"><i class="fas fa-chart-line"></i> GitHub Stats</h2>
            <div class="stats-grid">
                <div class="stat-box">
                    <i class="stat-icon fas fa-project-diagram"></i>
                    <div class="stat-label">Projects</div>
                </div>
                <div class="stat-box">
                    <i class="stat-icon fas fa-code-branch"></i>
                    <div class="stat-label">Repositories</div>
                </div>
                <div class="stat-box">
                    <i class="stat-icon fas fa-star"></i>
                    <div class="stat-label">Stars</div>
                </div>
                <div class="stat-box">
                    <i class="stat-icon fas fa-users"></i>
                    <div class="stat-label">Followers</div>
                </div>
            </div>
        </div>

        <!-- Skills Section -->
        <div class="glass-card">
            <h2 class="section-title"><i class="fas fa-tools"></i> Technical Skills</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h4><i class="fas fa-code"></i>Frontend Development</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">HTML5</span>
                        <span class="skill-tag">CSS3</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">Angular</span>
                        <span class="skill-tag">React</span>
                        <span class="skill-tag">Bootstrap</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4><i class="fas fa-server"></i>Backend Development</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">C#</span>
                        <span class="skill-tag">ASP.NET Core</span>
                        <span class="skill-tag">ASP.NET MVC</span>
                        <span class="skill-tag">Entity Framework Core</span>
                        <span class="skill-tag">LINQ</span>
                        <span class="skill-tag">Web APIs</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4><i class="fas fa-database"></i>Database & Tools</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">SQL Server</span>
                        <span class="skill-tag">Entity Framework</span>
                        <span class="skill-tag">Database Design</span>
                        <span class="skill-tag">Query Optimization</span>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h4><i class="fas fa-cogs"></i>Additional Technologies</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">JWT Authentication</span>
                        <span class="skill-tag">OAuth 2.0</span>
                        <span class="skill-tag">SignalR</span>
                        <span class="skill-tag">jQuery AJAX</span>
                        <span class="skill-tag">Twilio SMS</span>
                        <span class="skill-tag">SMTP Email</span>
                    </div>
                </div>
            </div>
        </div>

        <!-- Featured Projects -->
        <div class="glass-card">
            <h2 class="section-title"><i class="fas fa-rocket"></i> Featured Projects</h2>
            <div class="projects-grid">
                
                <!-- Amazon Clone -->
                <div class="project-card">
                    <i class="project-icon fas fa-shopping-cart"></i>
                    <h3 class="project-title">Amazon Clone</h3>
                    <p class="project-desc">
                        Full-featured e-commerce platform with advanced authentication, AI-powered product recommendations, 
                        and real-time updates. Features Google OAuth 2.0, two-factor authentication, and intelligent product suggestions.
                    </p>
                    <div class="project-tech">
                        <span class="tech-badge">ASP.NET MVC</span>
                        <span class="tech-badge">EF Core</span>
                        <span class="tech-badge">OAuth 2.0</span>
                        <span class="tech-badge">SignalR</span>
                        <span class="tech-badge">AI Integration</span>
                    </div>
                    <a href="https://ahmedbasioni.runasp.net/" class="project-link" target="_blank">
                        <i class="fas fa-external-link-alt"></i> View Live
                    </a>
                </div>

                <!-- Yaomix E-Commerce -->
                <div class="project-card">
                    <i class="project-icon fas fa-store"></i>
                    <h3 class="project-title">Yaomix E-Commerce</h3>
                    <p class="project-desc">
                        Responsive e-commerce platform supporting multiple user roles with comprehensive functionality. 
                        Features customer shopping, seller dashboards, and admin management capabilities.
                    </p>
                    <div class="project-tech">
                        <span class="tech-badge">HTML5</span>
                        <span class="tech-badge">CSS3</span>
                        <span class="tech-badge">JavaScript</span>
                        <span class="tech-badge">Bootstrap</span>
                        <span class="tech-badge">Multi-Role</span>
                    </div>
                    <a href="https://yoamix.vercel.app/" class="project-link" target="_blank">
                        <i class="fas fa-external-link-alt"></i> View Live
                    </a>
                </div>

                <!-- Examination System -->
                <div class="project-card">
                    <i class="project-icon fas fa-clipboard-check"></i>
                    <h3 class="project-title">Examination System</h3>
                    <p class="project-desc">
                        Secure online examination platform with comprehensive role-based access control. Features dynamic exam creation, 
                        automated grading, and detailed result analytics with JWT authentication.
                    </p>
                    <div class="project-tech">
                        <span class="tech-badge">ASP.NET Web API</span>
                        <span class="tech-badge">Angular</span>
                        <span class="tech-badge">EF Core</span>
                        <span class="tech-badge">JWT</span>
                    </div>
                    <a href="https://github.com/ahmedbasioni007/exam-system-Angular-APi-.git" class="project-link" target="_blank">
                        <i class="fab fa-github"></i> View Code
                    </a>
                </div>

                <!-- LibraryPro -->
                <div class="project-card">
                    <i class="project-icon fas fa-book"></i>
                    <h3 class="project-title">LibraryPro Management</h3>
                    <p class="project-desc">
                        Comprehensive library management system with CRUD operations, book reservation system, 
                        automated late fee calculations, and detailed reporting capabilities.
                    </p>
                    <div class="project-tech">
                        <span class="tech-badge">ASP.NET Core MVC</span>
                        <span class="tech-badge">EF Core</span>
                        <span class="tech-badge">SQL Server</span>
                        <span class="tech-badge">Admin Dashboard</span>
                    </div>
                    <a href="https://basioni008.runasp.net/" class="project-link" target="_blank">
                        <i class="fas fa-external-link-alt"></i> View Live
                    </a>
                </div>

            </div>
        </div>

        <!-- Training -->
        <div class="glass-card">
            <h2 class="section-title"><i class="fas fa-certificate"></i> Training & Development</h2>
            <div style="background: rgba(255, 255, 255, 0.1); border-radius: 15px; padding: 2rem; border-left: 4px solid var(--amazon-orange);">
                <h4 style="color: var(--amazon-orange); font-weight: 700; margin-bottom: 0.5rem;">
                    Intensive Training Program (ITP)
                </h4>
                <h5 style="color: white; margin-bottom: 1rem;">.NET Full Stack Web Development Track</h5>
                <p style="color: rgba(255,255,255,0.8); margin-bottom: 0.5rem;">
                    <i class="fas fa-university" style="margin-right: 0.5rem;"></i>Information Technology Institute (ITI)
                </p>
                <p style="color: rgba(255,255,255,0.7); margin-bottom: 1rem;">
                    <i class="fas fa-calendar-alt" style="margin-right: 0.5rem;"></i>March 2025 – July 2025
                </p>
                <p style="color: rgba(255,255,255,0.9); line-height: 1.6;">
                    Comprehensive training in modern .NET technologies, covering both frontend and backend development 
                    with hands-on projects and real-world applications.
                </p>
            </div>
        </div>

        <!-- Contact -->
        <div class="glass-card">
            <h2 class="section-title"><i class="fas fa-envelope"></i> Get In Touch</h2>
            <p style="text-align: center; color: rgba(255,255,255,0.9); font-size: 1.1rem; margin-bottom: 2rem;">
                I'm always interested in new opportunities and exciting projects. Feel free to reach out!
            </p>
            <div class="social-links">
                <a href="https://www.linkedin.com/in/ahmed-basioni/" class="social-btn" target="_blank">
                    <i class="fab fa-linkedin"></i> LinkedIn
                </a>
                <a href="https://github.com/ahmedbasioni007" class="social-btn" target="_blank">
                    <i class="fab fa-github"></i> GitHub
                </a>
                <a href="tel:+201066408193" class="social-btn" target="_blank">
                    <i class="fas fa-phone"></i> +201066408193
                </a>
                <a href="https://mail.google.com/mail/?view=cm&fs=1&to=ahmedbasuony22322@gmail.com" class="social-btn" target="_blank">
                    <i class="fas fa-envelope"></i> Email Me
                </a>
            </div>
        </div>

        <!-- Footer -->
        <div style="text-align: center; color: rgba(255,255,255,0.7); padding: 2rem 0;">
            <p style="margin-bottom: 0.5rem;">
                <i class="fas fa-heart" style="color: var(--amazon-orange);"></i> Built with passion using .NET technologies
            </p>
            <p>&copy; 2025 Ahmed Basioni EL-Khateeb</p>
        </div>
    </div>

    <script>
        // Add particle effect on mouse move
        document.addEventListener('mousemove', (e) => {
            const particle = document.createElement('div');
            particle.style.cssText = `
                position: fixed;
                width: 5px;
                height: 5px;
                background: rgba(255, 153, 0, 0.5);
                border-radius: 50%;
                pointer-events: none;
                left: ${e.clientX}px;
                top: ${e.clientY}px;
                animation: fadeOut 1s forwards;
                z-index: 9999;
            `;
            document.body.appendChild(particle);
            setTimeout(() => particle.remove(), 1000);
        });

        const style = document.createElement('style');
        style.textContent = `
            @keyframes fadeOut {
                to {
                    opacity: 0;
                    transform: scale(2);
                }
            }
        `;
        document.head.appendChild(style);

        // Stagger card animations
        document.addEventListener('DOMContentLoaded', () => {
            const cards = document.querySelectorAll('.glass-card');
            cards.forEach((card, index) => {
                card.style.animationDelay = `${index * 0.1}s`;
            });
        });
    </script>
</body>
</html>
