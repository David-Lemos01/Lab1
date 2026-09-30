# Lab1<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Marina Costa - Desenvolvedora Front-End</title>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
    <style>
        /* Reset e Configurações Globais */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --bg-cream: #FCF9F6;
            --bg-white: #FFFFFF;
            --bg-dark: #2B2B2B;
            --text-main: #333333;
            --text-light: #666666;
            --accent-coral: #D16B54;
            --accent-green: #487A58;
            --pill-bg: #F0EBE6;
            --border-light: #EAEAEA;
        }

        body {
            font-family: 'Inter', sans-serif;
            color: var(--text-main);
            line-height: 1.6;
            background-color: var(--bg-cream);
        }

        a {
            text-decoration: none;
            color: inherit;
        }

        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* --- Header --- */
        header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 30px 0;
        }

        .logo {
            font-weight: 700;
            font-size: 16px;
        }

        nav {
            display: flex;
            gap: 30px;
            font-size: 14px;
            color: var(--text-light);
        }

        nav a:hover {
            color: var(--text-main);
        }

        /* --- Hero Section --- */
        .hero {
            text-align: center;
            padding: 50px 0 80px;
        }

        /* CSS Art: Avatar */
        .avatar {
            width: 110px;
            height: 110px;
            background-color: #F1E2D3;
            border-radius: 50%;
            margin: 0 auto 20px;
            position: relative;
            overflow: hidden;
        }
        .avatar-body {
            width: 70px;
            height: 35px;
            background-color: var(--accent-green);
            border-radius: 35px 35px 0 0;
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        .avatar-head {
            width: 36px;
            height: 40px;
            background-color: #F5CBA7;
            border-radius: 18px 18px 15px 15px;
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
        }
        .avatar-hair {
            width: 42px;
            height: 20px;
            background-color: #2D2D2D;
            border-radius: 21px 21px 0 0;
            position: absolute;
            top: -2px;
            left: -3px;
        }
        .avatar-smile {
            width: 10px;
            height: 5px;
            border-bottom: 2px solid #333;
            border-radius: 0 0 10px 10px;
            position: absolute;
            bottom: 10px;
            left: 13px;
        }
        .avatar-eye {
            width: 4px;
            height: 4px;
            background-color: #333;
            border-radius: 50%;
            position: absolute;
            top: 18px;
        }
        .avatar-eye.left { left: 8px; }
        .avatar-eye.right { right: 8px; }

        .hero h1 {
            font-size: 32px;
            font-weight: 700;
            margin-bottom: 5px;
        }

        .hero h2 {
            font-size: 15px;
            font-weight: 500;
            color: var(--accent-coral);
            margin-bottom: 20px;
        }

        .hero p {
            color: var(--text-light);
            max-width: 600px;
            margin: 0 auto 30px;
            font-size: 14px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 15px;
        }

        .btn {
            padding: 10px 24px;
            border-radius: 30px;
            font-size: 14px;
            font-weight: 500;
            cursor: pointer;
            transition: all 0.2s;
        }

        .btn-primary {
            background-color: var(--accent-green);
            color: white;
            border: none;
        }

        .btn-primary:hover {
            background-color: #3B6649;
        }

        .btn-secondary {
            background-color: transparent;
            color: var(--text-main);
            border: 1px solid #CCC;
        }

        .btn-secondary:hover {
            border-color: var(--text-main);
        }

        /* --- Sobre Mim Section --- */
        .about-section {
            background-color: var(--bg-white);
            padding: 80px 0;
        }

        .about-grid {
            display: grid;
            grid-template-columns: 3fr 2fr;
            gap: 60px;
        }

        .section-title {
            font-size: 18px;
            font-weight: 700;
            margin-bottom: 20px;
        }

        .about-text {
            color: var(--text-light);
            font-size: 14px;
        }

        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-pill {
            background-color: var(--pill-bg);
            color: #555;
            padding: 6px 16px;
            border-radius: 20px;
            font-size: 12px;
            font-weight: 500;
        }

        /* --- Projetos Section --- */
        .projects-section {
            background-color: var(--bg-cream);
            padding: 80px 0;
            text-align: center;
        }

        .projects-header p {
            color: var(--text-light);
            font-size: 14px;
            margin-bottom: 40px;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 30px;
            text-align: left;
        }

        .project-card {
            background-color: var(--bg-white);
            border-radius: 12px;
            overflow: hidden;
            box-shadow: 0 4px 20px rgba(0,0,0,0.03);
            display: flex;
            flex-direction: column;
        }

        .project-image {
            background-color: #F8F9FA;
            padding: 20px;
            height: 220px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-bottom: 1px solid var(--border-light);
        }

        /* CSS Art: Telas de Projetos (Mockups) */
        .mockup-window {
            width: 100%;
            height: 100%;
            background: white;
            border-radius: 8px;
            box-shadow: 0 4px 10px rgba(0,0,0,0.05);
            overflow: hidden;
            border: 1px solid #EAEAEA;
            display: flex;
            flex-direction: column;
        }
        
        .mockup-header {
            height: 24px;
            display: flex;
            align-items: center;
            padding: 0 10px;
            gap: 4px;
        }

        .mockup-header.green { background-color: #487A58; }
        .mockup-header.blue { background-color: #5584B0; }
        
        .mockup-dot {
            width: 6px;
            height: 6px;
            border-radius: 50%;
            background-color: rgba(255,255,255,0.7);
        }

        /* Mockup: Painel Financeiro */
        .mockup-body-finance {
            padding: 15px;
            display: flex;
            flex-direction: column;
            gap: 15px;
            flex: 1;
        }
        .finance-top {
            display: flex;
            gap: 10px;
            height: 50px;
        }
        .f-box {
            background: #F8F8F8;
            border: 1px solid #EEE;
            border-radius: 4px;
            flex: 1;
            display: flex;
            align-items: center;
            justify-content: center;
        }
        .chart-line {
            width: 30px; height: 20px;
            border-bottom: 2px solid #CCC;
            border-left: 2px solid #CCC;
            position: relative;
        }
        .chart-line::after {
            content: ''; position: absolute;
            width: 25px; height: 15px;
            border-top: 2px solid var(--accent-green);
            border-right: 2px solid var(--accent-green);
            transform: skewY(-20deg);
            top: 5px; left: 2px;
        }
        .chart-bars {
            display: flex; align-items: flex-end; gap: 4px; height: 20px;
        }
        .chart-bars div { width: 6px; background: var(--accent-coral); border-radius: 1px; }
        .chart-bars div:nth-child(1) { height: 10px; background: var(--accent-green); }
        .chart-bars div:nth-child(2) { height: 20px; }
        .chart-bars div:nth-child(3) { height: 14px; background: #E0E0E0; }
        .chart-donut {
            width: 24px; height: 24px;
            border: 4px solid #F0F0F0;
            border-top-color: var(--accent-coral);
            border-right-color: var(--accent-coral);
            border-radius: 50%;
        }
        .finance-bottom {
            flex: 1;
            background: #F8F8F8;
            border: 1px solid #EEE;
            border-radius: 4px;
            padding: 10px;
            display: flex;
            flex-direction: column;
            gap: 8px;
        }
        .finance-line { height: 6px; background: #EAEAEA; border-radius: 3px; }
        .finance-line:nth-child(1) { width: 100%; }
        .finance-line:nth-child(2) { width: 80%; }
        .finance-line:nth-child(3) { width: 90%; }

        /* Mockup: App Clima Agora */
        .mockup-body-weather {
            padding: 15px;
            display: flex;
            flex-direction: column;
            gap: 15px;
            flex: 1;
        }
        .weather-top {
            display: flex;
            justify-content: space-between;
            align-items: center;
            background: #F8F8F8;
            border-radius: 4px;
            padding: 10px 15px;
        }
        .w-temp { font-size: 20px; font-weight: 700; color: #5584B0; }
        .w-icon {
            width: 24px; height: 24px;
            background: #FFD166;
            border-radius: 50%;
            position: relative;
        }
        .w-icon::after {
            content: ''; position: absolute;
            width: 20px; height: 12px;
            background: white; border-radius: 10px;
            bottom: -2px; right: -8px;
        }
        .w-temp-small { font-size: 14px; font-weight: 600; color: #333; }
        
        .weather-bottom {
            display: flex;
            justify-content: space-between;
            padding: 10px 15px;
            background: #F8F8F8;
            border-radius: 4px;
        }
        .w-day {
            display: flex; flex-direction: column; align-items: center; gap: 6px;
        }
        .w-day .w-dot { width: 4px; height: 4px; background: #FFD166; border-radius: 50%; }
        .w-day .w-dot.cloud { background: #5584B0; }
        .w-day span { width: 10px; height: 4px; background: #EAEAEA; border-radius: 2px; }

        /* Estilos do conteúdo dos cards de projeto */
        .project-content {
            padding: 25px;
        }

        .project-content h3 {
            font-size: 16px;
            margin-bottom: 8px;
            color: #222;
        }

        .project-content p {
            color: var(--text-light);
            font-size: 13px;
            margin-bottom: 20px;
            line-height: 1.5;
        }

        .project-tags {
            display: flex;
            gap: 10px;
        }

        .project-tags span {
            background-color: var(--pill-bg);
            color: var(--accent-coral);
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 11px;
            font-weight: 600;
        }

        /* --- Footer --- */
        footer {
            background-color: var(--bg-dark);
            color: white;
            text-align: center;
            padding: 80px 20px 40px;
        }

        .footer-title {
            font-size: 20px;
            font-weight: 600;
            margin-bottom: 15px;
        }

        .footer-text {
            color: #AAAAAA;
            font-size: 14px;
            max-width: 400px;
            margin: 0 auto 30px;
        }

        .contact-links {
            display: flex;
            flex-direction: column;
            gap: 15px;
            align-items: center;
            margin-bottom: 50px;
        }

        .contact-link {
            display: flex;
            align-items: center;
            gap: 10px;
            color: #CCCCCC;
            font-size: 13px;
            transition: color 0.2s;
        }

        .contact-link:hover {
            color: white;
        }

        .contact-link svg {
            width: 18px;
            height: 18px;
            fill: currentColor;
        }

        .copyright {
            color: #777777;
            font-size: 12px;
            border-top: 1px solid #444;
            padding-top: 30px;
            max-width: 800px;
            margin: 0 auto;
        }

        /* --- Responsividade --- */
        @media (max-width: 768px) {
            .about-grid {
                grid-template-columns: 1fr;
                gap: 40px;
            }
            .projects-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>

    <div class="container">
        <header>
            <div class="logo">Marina Costa</div>
            <nav>
                <a href="#">Sobre</a>
                <a href="#">Projetos</a>
                <a href="#">Contato</a>
            </nav>
        </header>
    </div>

    <section class="hero container">
        <div class="avatar">
            <div class="avatar-head">
                <div class="avatar-hair"></div>
                <div class="avatar-eye left"></div>
                <div class="avatar-eye right"></div>
                <div class="avatar-smile"></div>
            </div>
            <div class="avatar-body"></div>
        </div>
        <h1>Marina Costa</h1>
        <h2>Desenvolvedora Front-End</h2>
        <p>Crio interfaces web rápidas, acessíveis e agradáveis de usar. Nos últimos 4 anos, trabalhei com startups e agências para transformar protótipos em produtos reais.</p>
        <div class="buttons">
            <button class="btn btn-primary">Ver projetos</button>
            <button class="btn btn-secondary">Entrar em contato</button>
        </div>
    </section>

    <section class="about-section">
        <div class="container about-grid">
            <div>
                <h3 class="section-title">Sobre mim</h3>
                <p class="about-text">
                    Sou formada em Sistemas de Informação e me especializei em desenvolvimento front-end. Gosto de transformar ideias complexas em telas simples de usar, sempre prestando atenção em performance e acessibilidade. Fora do código, gosto de fotografia e trilhas.
                </p>
            </div>
            <div>
                <h3 class="section-title" style="font-size: 16px;">Habilidades</h3>
                <div class="skills-container">
                    <span class="skill-pill">HTML5</span>
                    <span class="skill-pill">CSS3</span>
                    <span class="skill-pill">JavaScript</span>
                    <span class="skill-pill">React</span>
                    <span class="skill-pill">Figma</span>
                    <span class="skill-pill">Git</span>
                </div>
            </div>
        </div>
    </section>

    <section class="projects-section">
        <div class="container projects-header">
            <h3 class="section-title">Projetos</h3>
            <p>Uma seleção de trabalhos recentes.</p>
            
            <div class="projects-grid">
                <!-- Projeto 1: Painel Financeiro -->
                <div class="project-card">
                    <div class="project-image">
                        <div class="mockup-window">
                            <div class="mockup-header green">
                                <div class="mockup-dot"></div><div class="mockup-dot"></div><div class="mockup-dot"></div>
                            </div>
                            <div class="mockup-body-finance">
                                <div class="finance-top">
                                    <div class="f-box"><div class="chart-line"></div></div>
                                    <div class="f-box"><div class="chart-bars"><div></div><div></div><div></div></div></div>
                                    <div class="f-box"><div class="chart-donut"></div></div>
                                </div>
                                <div class="finance-bottom">
                                    <div class="finance-line"></div>
                                    <div class="finance-line"></div>
                                    <div class="finance-line"></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3>Painel Financeiro</h3>
                        <p>Painel de controle financeiro com gráficos interativos e modo escuro.</p>
                        <div class="project-tags">
                            <span>React</span>
                            <span>Chart.js</span>
                        </div>
                    </div>
                </div>

                <!-- Projeto 2: App Clima Agora -->
                <div class="project-card">
                    <div class="project-image">
                        <div class="mockup-window">
                            <div class="mockup-header blue">
                                <div class="mockup-dot"></div><div class="mockup-dot"></div><div class="mockup-dot"></div>
                            </div>
                            <div class="mockup-body-weather">
                                <div class="weather-top">
                                    <div class="w-temp">23°C</div>
                                    <div class="w-icon"></div>
                                    <div class="w-temp-small">19°C</div>
                                </div>
                                <div class="weather-bottom">
                                    <div class="w-day"><div class="w-dot"></div><span></span></div>
                                    <div class="w-day"><div class="w-dot cloud"></div><span></span></div>
                                    <div class="w-day"><div class="w-dot"></div><span></span></div>
                                    <div class="w-day"><div class="w-dot cloud"></div><span></span></div>
                                    <div class="w-day"><div class="w-dot cloud"></div><span></span></div>
                                    <div class="w-day"><div class="w-dot"></div><span></span></div>
                                </div>
                            </div>
                        </div>
                    </div>
                    <div class="project-content">
                        <h3>App Clima Agora</h3>
                        <p>Aplicativo de previsão do tempo com busca por cidade e animações suaves.</p>
                        <div class="project-tags">
                            <span>JavaScript</span>
                            <span>API REST</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <h3 class="footer-title">Vamos conversar?</h3>
        <p class="footer-text">Estou disponível para novos projetos e oportunidades. Me mande uma mensagem!</p>
        
        <div class="contact-links">
            <a href="#" class="contact-link">
                <!-- Ícone de Email (SVG) -->
                <svg viewBox="0 0 24 24"><path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/></svg>
                marina.costa@email.com
            </a>
            <a href="#" class="contact-link">
                <!-- Ícone do GitHub (SVG) -->
                <svg viewBox="0 0 24 24"><path d="M12 2C6.48 2 2 6.48 2 12c0 4.42 2.87 8.17 6.84 9.5.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34-.45-1.15-1.11-1.46-1.11-1.46-.9-.62.07-.6.07-.6 1 .07 1.53 1.03 1.53 1.03.87 1.52 2.34 1.07 2.91.83.09-.65.35-1.09.63-1.34-2.22-.25-4.55-1.11-4.55-4.92 0-1.11.38-2 1.03-2.71-.1-.25-.45-1.29.1-2.64 0 0 .84-.27 2.75 1.02.79-.22 1.65-.33 2.5-.33.85 0 1.71.11 2.5.33 1.91-1.29 2.75-1.02 2.75-1.02.55 1.35.2 2.39.1 2.64.65.71 1.03 1.6 1.03 2.71 0 3.82-2.34 4.66-4.57 4.91.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0012 2z"/></svg>
                github.com/marinacosta
            </a>
            <a href="#" class="contact-link">
                <!-- Ícone do LinkedIn (SVG) -->
                <svg viewBox="0 0 24 24"><path d="M19 3a2 2 0 012 2v14a2 2 0 01-2 2H5a2 2 0 01-2-2V5a2 2 0 012-2h14zm-3.85 14v-4.14c0-1.05-.38-1.77-1.31-1.77-.72 0-1.15.48-1.34.95-.07.17-.09.4-.09.63V17h-2.91s.04-7.85 0-8.66h2.91v1.23h.04c.39-.6 1.09-1.46 2.64-1.46 1.93 0 3.38 1.26 3.38 3.97V17H15.15zM7.22 7.02c-1.01 0-1.67.66-1.67 1.53 0 .85.64 1.52 1.63 1.52h.02c1.03 0 1.67-.67 1.67-1.52-.02-.87-.64-1.53-1.65-1.53zM5.76 17h2.91V8.34H5.76V17z"/></svg>
                linkedin.com/in/marinacosta
            </a>
        </div>
        
        <div class="copyright">
            © 2026 Marina Costa. Todos os direitos reservados.
        </div>
    </footer>

</body>
</html>
