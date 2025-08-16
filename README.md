<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Luciano Sales - Perfil GitHub</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary-color: #0d1117;
            --secondary-color: #161b22;
            --accent-color: #58a6ff;
            --text-primary: #f0f6fc;
            --text-secondary: #8b949e;
            --border-color: #30363d;
            --gradient: linear-gradient(135deg, #0d1117 0%, #161b22 100%);
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', 'Noto Sans', Helvetica, Arial, sans-serif;
            background: var(--gradient);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .header {
            text-align: center;
            margin-bottom: 4rem;
            position: relative;
        }

        .header::before {
            content: '';
            position: absolute;
            top: -50px;
            left: 50%;
            transform: translateX(-50%);
            width: 200px;
            height: 200px;
            background: radial-gradient(circle, var(--accent-color)20, transparent 70%);
            border-radius: 50%;
            z-index: -1;
            animation: pulse 3s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { transform: translateX(-50%) scale(1); opacity: 0.3; }
            50% { transform: translateX(-50%) scale(1.1); opacity: 0.6; }
        }

        .title {
            font-size: clamp(2.5rem, 5vw, 4rem);
            font-weight: 300;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, var(--text-primary), var(--accent-color));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stats-container {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin: 3rem 0;
            flex-wrap: wrap;
        }

        .stat-card {
            background: var(--secondary-color);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 1rem;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .stat-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-color);
            box-shadow: 0 10px 30px rgba(88, 166, 255, 0.1);
        }

        .section {
            margin: 4rem 0;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 0.8s ease forwards;
        }

        .section:nth-child(2) { animation-delay: 0.2s; }
        .section:nth-child(3) { animation-delay: 0.4s; }
        .section:nth-child(4) { animation-delay: 0.6s; }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .section-title {
            font-size: 2rem;
            font-weight: 400;
            margin-bottom: 2rem;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--accent-color);
            transition: width 0.5s ease;
        }

        .section:hover .section-title::after {
            width: 100%;
        }

        .about-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1.5rem;
            margin-top: 2rem;
        }

        .about-item {
            background: var(--secondary-color);
            border: 1px solid var(--border-color);
            border-radius: 8px;
            padding: 1.5rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .about-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(88, 166, 255, 0.1), transparent);
            transition: left 0.5s ease;
        }

        .about-item:hover::before {
            left: 100%;
        }

        .about-item:hover {
            border-color: var(--accent-color);
            transform: scale(1.02);
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            margin-top: 2rem;
        }

        .tech-category {
            background: var(--secondary-color);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            cursor: pointer;
        }

        .tech-category:hover {
            transform: translateY(-10px);
            border-color: var(--accent-color);
            box-shadow: 0 15px 40px rgba(88, 166, 255, 0.15);
        }

        .tech-category h3 {
            margin-bottom: 1rem;
            color: var(--accent-color);
        }

        .tech-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
            justify-content: center;
        }

        .tech-tag {
            background: var(--primary-color);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 0.3rem 0.8rem;
            font-size: 0.8rem;
            transition: all 0.3s ease;
        }

        .tech-tag:hover {
            background: var(--accent-color);
            color: var(--primary-color);
            transform: scale(1.1);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .project-card {
            background: var(--secondary-color);
            border: 1px solid var(--border-color);
            border-radius: 12px;
            padding: 2rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, var(--accent-color), #7c3aed, #ec4899);
            transform: scaleX(0);
            transition: transform 0.3s ease;
        }

        .project-card:hover::before {
            transform: scaleX(1);
        }

        .project-card:hover {
            transform: translateY(-5px);
            border-color: var(--accent-color);
            box-shadow: 0 20px 50px rgba(88, 166, 255, 0.1);
        }

        .contact-section {
            text-align: center;
            background: var(--secondary-color);
            border: 1px solid var(--border-color);
            border-radius: 20px;
            padding: 3rem;
            margin-top: 4rem;
        }

        .contact-links {
            display: flex;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .contact-link {
            display: inline-flex;
            align-items: center;
            gap: 0.5rem;
            padding: 1rem 2rem;
            background: var(--primary-color);
            border: 1px solid var(--border-color);
            border-radius: 50px;
            color: var(--text-primary);
            text-decoration: none;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .contact-link::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: var(--accent-color);
            transition: left 0.3s ease;
            z-index: -1;
        }

        .contact-link:hover::before {
            left: 0;
        }

        .contact-link:hover {
            color: var(--primary-color);
            transform: scale(1.05);
        }

        .footer {
            text-align: center;
            margin-top: 4rem;
            padding: 2rem;
            border-top: 1px solid var(--border-color);
            color: var(--text-secondary);
        }

        @media (max-width: 768px) {
            .container {
                padding: 1rem;
            }
            
            .stats-container {
                flex-direction: column;
                align-items: center;
            }
            
            .contact-links {
                flex-direction: column;
                align-items: center;
            }
        }

        .typing-animation {
            border-right: 2px solid var(--accent-color);
            animation: blink 1s infinite;
        }

        @keyframes blink {
            0%, 50% { border-color: var(--accent-color); }
            51%, 100% { border-color: transparent; }
        }
    </style>
</head>
<body>
    <div class="container">
        <header class="header">
            <h1 class="title">Luciano Sales</h1>
            <p class="typing-animation" id="typing-text"></p>
        </header>

        <div class="stats-container">
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api?username=LucianoSales&show_icons=true&theme=dark&hide_border=true&bg_color=0d1117" alt="GitHub Stats" style="border-radius: 8px;">
            </div>
            <div class="stat-card">
                <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=LucianoSales&layout=compact&theme=dark&hide_border=true&bg_color=0d1117" alt="Top Languages" style="border-radius: 8px;">
            </div>
        </div>

        <section class="section">
            <h2 class="section-title">Sobre</h2>
            <div class="about-grid">
                <div class="about-item">
                    <h3>🎓 Formação & Especialização</h3>
                    <p>Analista de Rede e Dados<br>
                    Especialista em Segurança de Redes (Ofensiva e Defensiva)<br>
                    Graduação em Tecnologia em Inteligência Artificial (FATESG)</p>
                </div>
                <div class="about-item">
                    <h3>💼 Experiência Profissional</h3>
                    <p>Configuração e Manutenção de Redes<br>
                    Análise e Otimização de Tráfego<br>
                    Implementação de Soluções de Segurança Ofensiva e Defensiva</p>
                </div>
                <div class="about-item">
                    <h3>📊 Análise de Dados & IA</h3>
                    <p>Coleta e Processamento de Dados de Rede<br>
                    Desenvolvimento de Modelos Preditivos<br>
                    Automação com IA para Monitoramento</p>
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">Tecnologias</h2>
            <div class="tech-grid">
                <div class="tech-category">
                    <h3>Redes</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">TCP/IP</span>
                        <span class="tech-tag">Cisco</span>
                        <span class="tech-tag">Firewalls</span>
                        <span class="tech-tag">VPNs</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>Análise de Dados</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">Python</span>
                        <span class="tech-tag">SQL</span>
                        <span class="tech-tag">Pandas</span>
                        <span class="tech-tag">Power BI</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>Segurança</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">IDS/IPS</span>
                        <span class="tech-tag">SIEM</span>
                        <span class="tech-tag">Ethical Hacking</span>
                        <span class="tech-tag">Penetration Testing</span>
                        <span class="tech-tag">Security Audits</span>
                    </div>
                </div>
                <div class="tech-category">
                    <h3>Automação & IA</h3>
                    <div class="tech-tags">
                        <span class="tech-tag">Ansible</span>
                        <span class="tech-tag">Machine Learning</span>
                        <span class="tech-tag">Deep Learning</span>
                    </div>
                </div>
            </div>
        </section>

        <section class="section">
            <h2 class="section-title">Projetos Destacados</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>🛡️ Sistema de Detecção de Intrusão</h3>
                    <p>Desenvolvimento de um sistema baseado em Machine Learning para identificar anomalias e ameaças em redes.</p>
                    <a href="#" style="color: var(--accent-color); text-decoration: none;">Ver projeto →</a>
                </div>
                <div class="project-card">
                    <h3>📈 Dashboard de Monitoramento de Rede</h3>
                    <p>Criação de um dashboard interativo para visualização em tempo real de métricas de desempenho e segurança de rede.</p>
                    <a href="#" style="color: var(--accent-color); text-decoration: none;">Ver projeto →</a>
                </div>
                <div class="project-card">
                    <h3>🤖 Automação de Configuração de Redes</h3>
                    <p>Scripting e automação de tarefas de configuração e gerenciamento de dispositivos de rede com Python e Ansible.</p>
                    <a href="#" style="color: var(--accent-color); text-decoration: none;">Ver projeto →</a>
                </div>
            </div>
        </section>

        <section class="contact-section">
            <h2 class="section-title">Vamos Conectar</h2>
            <p>Interessado em segurança de redes, análise de dados ou projetos de IA?</p>
            <div class="contact-links">
                <a href="https://www.linkedin.com/in/luciano-sales-network-data-analyst" class="contact-link">
                    LinkedIn
                </a>
                <a href="mailto:luciano.sales@example.com" class="contact-link">
                    Email
                </a>
                <a href="https://github.com/LucianoSales" class="contact-link">
                    GitHub
                </a>
            </div>
        </section>

        <footer class="footer">
            <p>Desenvolvido com foco em segurança, dados e inovação</p>
        </footer>
    </div>

    <script>
        // Typing animation
        const texts = [
            "Analista de Rede",
            "Especialista em Dados",
            "Entusiasta de IA",
            "Solucionador de Problemas"
        ];
        
        let textIndex = 0;
        let charIndex = 0;
        let isDeleting = false;
        const typingElement = document.getElementById('typing-text');
        
        function typeText() {
            const currentText = texts[textIndex];
            
            if (isDeleting) {
                typingElement.textContent = currentText.substring(0, charIndex - 1);
                charIndex--;
            } else {
                typingElement.textContent = currentText.substring(0, charIndex + 1);
                charIndex++;
            }
            
            let typeSpeed = isDeleting ? 50 : 100;
            
            if (!isDeleting && charIndex === currentText.length) {
                typeSpeed = 2000;
                isDeleting = true;
            } else if (isDeleting && charIndex === 0) {
                isDeleting = false;
                textIndex = (textIndex + 1) % texts.length;
                typeSpeed = 500;
            }
            
            setTimeout(typeText, typeSpeed);
        }
        
        // Start typing animation
        typeText();
        
        // Smooth scrolling for internal links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });
        
        // Add hover effects to tech tags
        document.querySelectorAll('.tech-tag').forEach(tag => {
            tag.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.1) rotate(2deg)';
            });
            
            tag.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) rotate(0deg)';
            });
        });
        
        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);
        
        document.querySelectorAll('.section').forEach(section => {
            observer.observe(section);
        });
        
        // Add particle effect on mouse move
        document.addEventListener('mousemove', (e) => {
            const particle = document.createElement('div');
            particle.style.position = 'fixed';
            particle.style.left = e.clientX + 'px';
            particle.style.top = e.clientY + 'px';
            particle.style.width = '4px';
            particle.style.height = '4px';
            particle.style.background = 'var(--accent-color)';
            particle.style.borderRadius = '50%';
            particle.style.pointerEvents = 'none';
            particle.style.opacity = '0.6';
            particle.style.zIndex = '1000';
            particle.style.transition = 'all 0.5s ease-out';
            
            document.body.appendChild(particle);
            
            setTimeout(() => {
                particle.style.opacity = '0';
                particle.style.transform = 'scale(0)';
                setTimeout(() => {
                    document.body.removeChild(particle);
                }, 500);
            }, 100);
        });
    </script>
</body>
</html>
