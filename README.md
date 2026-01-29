 <!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>D4 HACKERTYPE</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Share+Tech+Mono&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Share Tech Mono', monospace;
            background-color: #0a0a0a;
            color: #00ff00;
            line-height: 1.6;
            overflow-x: hidden;
            position: relative;
        }
        
        /* Animações de fundo - códigos caindo */
        #matrix-bg {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -2;
            opacity: 0.1;
        }
        
        /* Container principal */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            padding: 20px 0;
            border-bottom: 1px solid #00ff00;
            position: relative;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }
        
        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }
        
        .logo-symbol {
            font-size: 2.5rem;
            color: #ff0000;
            font-weight: bold;
            text-shadow: 0 0 10px rgba(255, 0, 0, 0.7);
        }
        
        .logo-text {
            font-size: 1.8rem;
            letter-spacing: 3px;
            color: #00ff00;
            text-shadow: 0 0 10px rgba(0, 255, 0, 0.7);
        }
        
        .tagline {
            color: #ff0000;
            font-size: 0.9rem;
            letter-spacing: 1px;
            margin-top: 5px;
        }
        
        /* Menu de navegação */
        nav ul {
            display: flex;
            list-style: none;
            gap: 30px;
        }
        
        nav a {
            color: #00ff00;
            text-decoration: none;
            font-size: 0.9rem;
            letter-spacing: 1px;
            transition: all 0.3s;
            position: relative;
            padding: 5px 0;
        }
        
        nav a:hover {
            color: #ff0000;
            text-shadow: 0 0 10px rgba(255, 0, 0, 0.7);
        }
        
        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 1px;
            background-color: #ff0000;
            transition: width 0.3s;
        }
        
        nav a:hover::after {
            width: 100%;
        }
        
        /* Seção hero */
        .hero {
            padding: 60px 0;
            text-align: center;
            border-bottom: 1px solid #333;
            position: relative;
        }
        
        .hero h1 {
            font-size: 3rem;
            letter-spacing: 5px;
            margin-bottom: 20px;
            color: #ff0000;
            text-shadow: 0 0 15px rgba(255, 0, 0, 0.7);
        }
        
        .hero h2 {
            font-size: 1.8rem;
            color: #00ff00;
            margin-bottom: 30px;
            letter-spacing: 3px;
        }
        
        .hero-text {
            font-size: 1.2rem;
            max-width: 800px;
            margin: 0 auto 40px;
            color: #cccccc;
        }
        
        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 40px;
        }
        
        .btn {
            padding: 15px 30px;
            font-family: 'Share Tech Mono', monospace;
            font-size: 1rem;
            border: 1px solid #00ff00;
            background-color: transparent;
            color: #00ff00;
            cursor: pointer;
            transition: all 0.3s;
            letter-spacing: 1px;
            text-transform: uppercase;
        }
        
        .btn-primary {
            background-color: rgba(0, 255, 0, 0.1);
            border-color: #00ff00;
        }
        
        .btn-primary:hover {
            background-color: rgba(0, 255, 0, 0.3);
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.5);
        }
        
        .btn-secondary {
            border-color: #ff0000;
            color: #ff0000;
        }
        
        .btn-secondary:hover {
            background-color: rgba(255, 0, 0, 0.1);
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.5);
        }
        
        /* Seção serviços */
        .services {
            padding: 80px 0;
            border-bottom: 1px solid #333;
        }
        
        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 60px;
            color: #00ff00;
            letter-spacing: 3px;
            text-transform: uppercase;
        }
        
        .services-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
        }
        
        .service-card {
            background-color: rgba(20, 20, 20, 0.8);
            border: 1px solid #333;
            padding: 30px;
            transition: all 0.3s;
            position: relative;
            overflow: hidden;
        }
        
        .service-card:hover {
            border-color: #00ff00;
            box-shadow: 0 0 20px rgba(0, 255, 0, 0.3);
            transform: translateY(-5px);
        }
        
        .service-icon {
            font-size: 2.5rem;
            margin-bottom: 20px;
            color: #ff0000;
        }
        
        .service-title {
            font-size: 1.5rem;
            margin-bottom: 15px;
            color: #00ff00;
        }
        
        .service-desc {
            color: #cccccc;
            font-size: 0.95rem;
            margin-bottom: 20px;
        }
        
        .service-link {
            color: #ff0000;
            text-decoration: none;
            font-size: 0.9rem;
            display: inline-block;
            margin-top: 10px;
        }
        
        .service-link:hover {
            text-decoration: underline;
        }
        
        /* Seção quem somos */
        .about {
            padding: 80px 0;
            border-bottom: 1px solid #333;
        }
        
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 50px;
            align-items: center;
        }
        
        .about-text {
            color: #cccccc;
            font-size: 1.1rem;
        }
        
        .about-text p {
            margin-bottom: 20px;
        }
        
        .about-image {
            text-align: center;
        }
        
        .d4-symbol {
            font-size: 15rem;
            color: rgba(255, 0, 0, 0.7);
            text-shadow: 0 0 30px rgba(255, 0, 0, 0.9);
            position: relative;
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { opacity: 0.7; }
            50% { opacity: 1; }
            100% { opacity: 0.7; }
        }
        
        /* Seção contato */
        .contact {
            padding: 80px 0;
            text-align: center;
        }
        
        .contact-form {
            max-width: 600px;
            margin: 0 auto;
            background-color: rgba(20, 20, 20, 0.8);
            padding: 40px;
            border: 1px solid #333;
        }
        
        .form-group {
            margin-bottom: 25px;
            text-align: left;
        }
        
        .form-group label {
            display: block;
            margin-bottom: 8px;
            color: #00ff00;
        }
        
        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            background-color: rgba(10, 10, 10, 0.8);
            border: 1px solid #333;
            color: #00ff00;
            font-family: 'Share Tech Mono', monospace;
            font-size: 0.9rem;
        }
        
        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #00ff00;
            box-shadow: 0 0 10px rgba(0, 255, 0, 0.3);
        }
        
        /* Footer */
        footer {
            padding: 30px 0;
            text-align: center;
            border-top: 1px solid #333;
            color: #666;
            font-size: 0.9rem;
        }
        
        .footer-text {
            margin-bottom: 10px;
        }
        
        /* Efeitos especiais */
        .terminal-cursor {
            display: inline-block;
            width: 10px;
            height: 20px;
            background-color: #00ff00;
            margin-left: 5px;
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            0%, 100% { opacity: 1; }
            50% { opacity: 0; }
        }
        
        .glitch {
            position: relative;
            display: inline-block;
        }
        
        .glitch::before,
        .glitch::after {
            content: attr(data-text);
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        
        .glitch::before {
            left: 2px;
            text-shadow: -2px 0 #ff0000;
            clip: rect(44px, 450px, 56px, 0);
            animation: glitch-anim 5s infinite linear alternate-reverse;
        }
        
        .glitch::after {
            left: -2px;
            text-shadow: -2px 0 #00ff00;
            clip: rect(44px, 450px, 56px, 0);
            animation: glitch-anim2 5s infinite linear alternate-reverse;
        }
        
        @keyframes glitch-anim {
            0% { clip: rect(31px, 9999px, 94px, 0); }
            5% { clip: rect(112px, 9999px, 76px, 0); }
            10% { clip: rect(85px, 9999px, 77px, 0); }
            15% { clip: rect(27px, 9999px, 97px, 0); }
            20% { clip: rect(64px, 9999px, 98px, 0); }
            25% { clip: rect(61px, 9999px, 85px, 0); }
            30% { clip: rect(99px, 9999px, 114px, 0); }
            35% { clip: rect(1px, 9999px, 13px, 0); }
            40% { clip: rect(16px, 9999px, 39px, 0); }
            45% { clip: rect(53px, 9999px, 68px, 0); }
            50% { clip: rect(35px, 9999px, 88px, 0); }
            55% { clip: rect(2px, 9999px, 36px, 0); }
            60% { clip: rect(66px, 9999px, 70px, 0); }
            65% { clip: rect(91px, 9999px, 103px, 0); }
            70% { clip: rect(17px, 9999px, 84px, 0); }
            75% { clip: rect(23px, 9999px, 54px, 0); }
            80% { clip: rect(80px, 9999px, 110px, 0); }
            85% { clip: rect(43px, 9999px, 72px, 0); }
            90% { clip: rect(46px, 9999px, 107px, 0); }
            95% { clip: rect(67px, 9999px, 119px, 0); }
            100% { clip: rect(14px, 9999px, 100px, 0); }
        }
        
        @keyframes glitch-anim2 {
            0% { clip: rect(65px, 9999px, 100px, 0); }
            5% { clip: rect(52px, 9999px, 74px, 0); }
            10% { clip: rect(79px, 9999px, 63px, 0); }
            15% { clip: rect(101px, 9999px, 39px, 0); }
            20% { clip: rect(114px, 9999px, 98px, 0); }
            25% { clip: rect(10px, 9999px, 2px, 0); }
            30% { clip: rect(34px, 9999px, 115px, 0); }
            35% { clip: rect(95px, 9999px, 11px, 0); }
            40% { clip: rect(8px, 9999px, 78px, 0); }
            45% { clip: rect(51px, 9999px, 46px, 0); }
            50% { clip: rect(92px, 9999px, 72px, 0); }
            55% { clip: rect(18px, 9999px, 71px, 0); }
            60% { clip: rect(109px, 9999px, 102px, 0); }
            65% { clip: rect(87px, 9999px, 113px, 0); }
            70% { clip: rect(66px, 9999px, 41px, 0); }
            75% { clip: rect(29px, 9999px, 89px, 0); }
            80% { clip: rect(11px, 9999px, 72px, 0); }
            85% { clip: rect(80px, 9999px, 9px, 0); }
            90% { clip: rect(78px, 9999px, 5px, 0); }
            95% { clip: rect(80px, 9999px, 76px, 0); }
            100% { clip: rect(16px, 9999px, 30px, 0); }
        }
        
        /* Responsividade */
        @media (max-width: 992px) {
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .d4-symbol {
                font-size: 10rem;
            }
            
            nav ul {
                gap: 15px;
            }
        }
        
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.2rem;
            }
            
            .hero h2 {
                font-size: 1.4rem;
            }
            
            .cta-buttons {
                flex-direction: column;
                align-items: center;
                gap: 20px;
            }
            
            .btn {
                width: 100%;
                max-width: 300px;
            }
            
            header {
                flex-direction: column;
                gap: 20px;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }
        
        @media (max-width: 576px) {
            .services-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-form {
                padding: 30px 20px;
            }
            
            .logo-text {
                font-size: 1.4rem;
            }
        }
    </style>
</head>
<body>
    <!-- Fundo com animação de códigos -->
    <canvas id="matrix-bg"></canvas>
    
    <div class="container">
        <!-- Cabeçalho -->
        <header>
            <div class="logo">
                <div class="logo-symbol">D4</div>
                <div>
                    <div class="logo-text">HACKERTYPE</div>
                    <div class="tagline">TIPO DE HACKER</div>
                </div>
            </div>
            
            <nav>
                <ul>
                    <li><a href="#services">SERVIÇOS</a></li>
                    <li><a href="#about">QUEM SOMOS</a></li>
                    <li><a href="#contact">CONTATO</a></li>
                </ul>
            </nav>
        </header>
        
        <!-- Seção principal -->
        <section class="hero">
            <h1 class="glitch" data-text="D4 HACKERTYPE">D4 HACKERTYPE</h1>
            <h2>TIPO DE HACKER</h2>
            
            <p class="hero-text">
                Nenhuma rede é segura. Nenhum sistema é impenetrável.<span class="terminal-cursor"></span>
            </p>
            
            <div class="cta-buttons">
                <button class="btn btn-primary">EXPLORAR SERVIÇOS ></button>
                <button class="btn btn-secondary">CONTRATAR AGORA</button>
            </div>
        </section>
        
        <!-- Seção de serviços -->
        <section id="services" class="services">
            <h2 class="section-title">SERVIÇOS DIGITAIS</h2>
            
            <div class="services-grid">
                <!-- Serviço 1 -->
                <div class="service-card">
                    <div class="service-icon">@</div>
                    <h3 class="service-title">Derrubada de Sites</h3>
                    <p class="service-desc">Tiramos sites e redes sociais do ar. Nenhuma rede é segura.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
                
                <!-- Serviço 2 -->
                <div class="service-card">
                    <div class="service-icon">WU</div>
                    <h3 class="service-title">Testes de Segurança</h3>
                    <p class="service-desc">Identificamos falhas críticas antes que outros hackers o façam.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
                
                <!-- Serviço 3 -->
                <div class="service-card">
                    <div class="service-icon">></div>
                    <h3 class="service-title">Clonagem Digital</h3>
                    <p class="service-desc">Clonamos sites, contatos e redes sociais com resultados perfeitos.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
                
                <!-- Serviço 4 -->
                <div class="service-card">
                    <div class="service-icon">0</div>
                    <h3 class="service-title">Distribuição de Virus</h3>
                    <p class="service-desc">Espalhamos códigos maliciosos em sistemas e infraestruturas.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
                
                <!-- Serviço 5 -->
                <div class="service-card">
                    <div class="service-icon">©</div>
                    <h3 class="service-title">Espionagem Digital</h3>
                    <p class="service-desc">Monitoramento invisível e recuperação de dados sensíveis.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
                
                <!-- Serviço 6 -->
                <div class="service-card">
                    <div class="service-icon">=</div>
                    <h3 class="service-title">Quebra de Servidores</h3>
                    <p class="service-desc">Invadimos e tomamos controle de servidores e infraestruturas.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
                
                <!-- Serviço 7 -->
                <div class="service-card">
                    <div class="service-icon">4</div>
                    <h3 class="service-title">Ataques DDoS</h3>
                    <p class="service-desc">Derrubamos qualquer rede com ataques distribuídos massivos.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
                
                <!-- Serviço 8 -->
                <div class="service-card">
                    <div class="service-icon">G</div>
                    <h3 class="service-title">Cibersegurança Avançada</h3>
                    <p class="service-desc">Proteção de alto nível contra ameaças digitais.</p>
                    <a href="#" class="service-link">EXPLORAR ></a>
                </div>
            </div>
        </section>
        
        <!-- Seção quem somos -->
        <section id="about" class="about">
            <h2 class="section-title">QUEM SOMOS D4</h2>
            
            <div class="about-content">
                <div class="about-text">
                    <p>D4 Hackertype é uma organização digital que atua nas sombras da internet.</p>
                    <p>Somos conhecidos por invadir sistemas, destruir arquivos, quebrar sites, quebrar servidores e tomar controle de infraestruturas digitais inteiras.</p>
                    <p>A D4 opera sem regras, explorando falhas, desligando sistemas, sequestrando servidores e espalhando o caos digital.</p>
                    <p>Nenhuma rede é segura. Nenhum sistema é impenetrável.</p>
                </div>
                
                <div class="about-image">
                    <div class="d4-symbol">D4</div>
                </div>
            </div>
        </section>
        
        <!-- Seção contato -->
        <section id="contact" class="contact">
            <h2 class="section-title">CONTATO</h2>
            <h3 class=""section-title"">barryyyflash@gmail.com</h3>
            <div class="contact-form">
                <p style="color: #cccccc; margin-bottom: 30px;">Se quer algum serviço, deixe seu e-mail de contato e d
