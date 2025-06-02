<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Datos4GExpress - Internet Móvil de Alta Velocidad</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #e53e3e;
            --primary-dark: #c53030;
            --secondary: #f56565;
            --accent: #9b2c2c;
            --light: #fef2f2;
            --dark: #1a202c;
            --gray: #718096;
            --light-gray: #f8d7da;
            --dark-gray: #4a5568;
            --success: #38a169;
            --border-radius: 12px;
            --shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -1px rgba(0, 0, 0, 0.06);
            --shadow-lg: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -2px rgba(0, 0, 0, 0.05);
            --transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: white;
            color: var(--dark);
            line-height: 1.6;
            min-height: 100vh;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header estilo moderno */
        header {
            background-color: white;
            box-shadow: var(--shadow);
            position: sticky;
            top: 0;
            z-index: 100;
            padding: 15px 0;
            border-bottom: 2px solid var(--primary);
        }

        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 10px;
            text-decoration: none;
        }

        .logo-icon {
            font-size: 1.8rem;
            color: var(--primary);
        }

        .logo-text {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--dark);
        }

        .logo-highlight {
            color: var(--primary);
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 25px;
        }

        nav a {
            text-decoration: none;
            color: var(--gray);
            font-weight: 500;
            font-size: 1rem;
            transition: var(--transition);
            padding: 8px 0;
            position: relative;
        }

        nav a:hover {
            color: var(--primary);
        }

        nav a::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 0;
            height: 2px;
            background-color: var(--primary);
            transition: var(--transition);
        }

        nav a:hover::after {
            width: 100%;
        }

        /* Hero section estilo moderno */
        .hero {
            background: linear-gradient(135deg, #fff5f5 0%, #fed7d7 100%);
            padding: 80px 0;
            text-align: center;
            margin-bottom: 60px;
            border-bottom: 1px solid var(--light-gray);
        }

        .hero-content {
            max-width: 800px;
            margin: 0 auto;
        }

        .hero-title {
            font-size: 2.8rem;
            font-weight: 700;
            margin-bottom: 20px;
            line-height: 1.2;
            color: var(--dark);
        }

        .hero-title span {
            color: var(--primary);
        }

        .hero-subtitle {
            font-size: 1.2rem;
            color: var(--gray);
            margin-bottom: 30px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .cta-button {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            background-color: var(--primary);
            color: white;
            padding: 12px 28px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            box-shadow: var(--shadow);
            border: none;
            cursor: pointer;
            gap: 8px;
        }

        .cta-button:hover {
            background-color: var(--primary-dark);
            transform: translateY(-2px);
            box-shadow: var(--shadow-lg);
        }

        .cta-button.secondary {
            background-color: white;
            color: var(--primary);
            border: 1px solid var(--light-gray);
        }

        .cta-button.secondary:hover {
            background-color: #fef2f2;
            border-color: var(--primary);
        }

        /* Sección de paquetes */
        .section-title {
            text-align: center;
            margin-bottom: 50px;
        }

        .section-title h2 {
            font-size: 2rem;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 15px;
            position: relative;
            display: inline-block;
            padding-bottom: 10px;
        }

        .section-title h2::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 80px;
            height: 3px;
            background: var(--primary);
            border-radius: 2px;
        }

        .section-title p {
            color: var(--gray);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        .packages {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }

        .package-card {
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            padding: 30px;
            transition: var(--transition);
            border: 1px solid var(--light-gray);
            position: relative;
            overflow: hidden;
        }

        .package-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .package-card.popular {
            border-color: var(--primary);
            box-shadow: 0 0 0 1px var(--primary), var(--shadow-lg);
        }

        .package-card.popular::before {
            content: 'MÁS POPULAR';
            position: absolute;
            top: 15px;
            right: -35px;
            background-color: var(--primary);
            color: white;
            padding: 4px 35px;
            transform: rotate(45deg);
            font-size: 0.75rem;
            font-weight: 600;
            width: 150px;
            text-align: center;
        }

        .package-header {
            margin-bottom: 20px;
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
        }

        .package-icon {
            font-size: 2.5rem;
            color: var(--primary);
        }

        .package-title {
            font-size: 1.5rem;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 5px;
        }

        .package-features {
            list-style: none;
            margin: 25px 0;
        }

        .package-features li {
            padding: 10px 0;
            display: flex;
            align-items: flex-start;
            gap: 10px;
            font-size: 0.95rem;
            color: var(--dark-gray);
            border-bottom: 1px solid var(--light-gray);
        }

        .package-features li i {
            color: var(--success);
            font-size: 1rem;
            margin-top: 3px;
        }

        .price-container {
            margin: 25px 0;
        }

        .original-price {
            text-decoration: line-through;
            color: var(--gray);
            font-size: 0.9rem;
        }

        .price {
            font-size: 2rem;
            font-weight: 700;
            color: var(--primary);
            margin: 5px 0;
        }

        .price-info {
            color: var(--gray);
            font-size: 0.9rem;
        }

        .buy-button {
            display: flex;
            width: 100%;
            align-items: center;
            justify-content: center;
            background-color: var(--primary);
            color: white;
            padding: 12px;
            border-radius: 8px;
            text-decoration: none;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            gap: 8px;
        }

        .buy-button:hover {
            background-color: var(--primary-dark);
        }

        /* Sección de beneficios */
        .benefits {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-bottom: 80px;
        }

        .benefit-card {
            background-color: white;
            border-radius: var(--border-radius);
            box-shadow: var(--shadow);
            padding: 30px;
            text-align: center;
            transition: var(--transition);
            border-top: 3px solid var(--primary);
        }

        .benefit-card:hover {
            transform: translateY(-5px);
            box-shadow: var(--shadow-lg);
        }

        .benefit-icon {
            font-size: 2.5rem;
            color: var(--primary);
            margin-bottom: 20px;
        }

        .benefit-title {
            font-size: 1.3rem;
            font-weight: 700;
            color: var(--dark);
            margin-bottom: 15px;
        }

        .benefit-description {
            color: var(--gray);
            font-size: 0.95rem;
        }

        /* Footer estilo moderno */
        footer {
            background-color: var(--dark);
            color: white;
            padding: 60px 0 30px;
        }

        .footer-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 40px;
            margin-bottom: 40px;
        }

        .footer-logo {
            display: flex;
            align-items: center;
            gap: 10px;
            margin-bottom: 20px;
            text-decoration: none;
        }

        .footer-logo-icon {
            font-size: 1.8rem;
            color: white;
        }

        .footer-logo-text {
            font-size: 1.5rem;
            font-weight: 700;
            color: white;
        }

        .footer-about {
            max-width: 300px;
        }

        .footer-about p {
            color: var(--light-gray);
            font-size: 0.95rem;
            margin-bottom: 20px;
        }

        .footer-social {
            display: flex;
            gap: 15px;
        }

        .footer-social a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background-color: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            color: white;
            font-size: 1.1rem;
            transition: var(--transition);
        }

        .footer-social a:hover {
            background-color: var(--primary);
            transform: translateY(-3px);
        }

        .footer-links h3 {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: white;
        }

        .footer-links ul {
            list-style: none;
        }

        .footer-links li {
            margin-bottom: 12px;
        }

        .footer-links a {
            color: var(--light-gray);
            text-decoration: none;
            font-size: 0.95rem;
            transition: var(--transition);
        }

        .footer-links a:hover {
            color: white;
        }

        .footer-contact h3 {
            font-size: 1.1rem;
            font-weight: 600;
            margin-bottom: 20px;
            color: white;
        }

        .footer-contact p {
            color: var(--light-gray);
            font-size: 0.95rem;
            margin-bottom: 15px;
            display: flex;
            align-items: flex-start;
            gap: 10px;
        }

        .footer-contact i {
            margin-top: 3px;
            color: var(--primary);
        }

        .footer-bottom {
            border-top: 1px solid var(--dark-gray);
            padding-top: 30px;
            text-align: center;
        }

        .copyright {
            color: var(--light-gray);
            font-size: 0.9rem;
        }

        /* Modal de pago moderno */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal-content {
            background-color: white;
            border-radius: var(--border-radius);
            padding: 30px;
            width: 100%;
            max-width: 450px;
            box-shadow: var(--shadow-lg);
            position: relative;
            animation: modalFadeIn 0.3s ease-out;
            border-top: 4px solid var(--primary);
        }

        @keyframes modalFadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .close-modal {
            position: absolute;
            top: 20px;
            right: 20px;
            font-size: 1.5rem;
            cursor: pointer;
            color: var(--gray);
            transition: var(--transition);
            background: none;
            border: none;
        }

        .close-modal:hover {
            color: var(--primary);
        }

        .modal-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: var(--dark);
            text-align: center;
        }

        .ticket-form {
            margin-bottom: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--dark);
            font-size: 0.95rem;
        }

        .form-group input {
            width: 100%;
            padding: 12px;
            border: 1px solid var(--light-gray);
            border-radius: 8px;
            font-size: 1rem;
            transition: var(--transition);
        }

        .form-group input:focus {
            border-color: var(--primary);
            outline: none;
            box-shadow: 0 0 0 3px rgba(229, 62, 62, 0.1);
        }

        .payment-info {
            background-color: #fef2f2;
            border-radius: var(--border-radius);
            padding: 15px;
            margin: 20px 0;
            font-size: 0.9rem;
            border-left: 3px solid var(--primary);
        }

        .payment-info p {
            margin-bottom: 8px;
            color: var(--dark-gray);
        }

        .info-highlight {
            font-weight: 600;
            color: var(--primary);
        }

        .email-button {
            display: flex;
            width: 100%;
            align-items: center;
            justify-content: center;
            background-color: var(--primary);
            color: white;
            padding: 12px;
            border-radius: 8px;
            font-weight: 600;
            font-size: 1rem;
            transition: var(--transition);
            margin-top: 15px;
            cursor: pointer;
            border: none;
            gap: 8px;
        }

        .email-button:hover {
            background-color: var(--primary-dark);
        }

        .ticket-confirmation {
            display: none;
            text-align: center;
            padding: 20px;
        }

        .ticket-confirmation i {
            font-size: 3rem;
            color: var(--success);
            margin-bottom: 15px;
        }

        .ticket-confirmation h3 {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--dark);
        }

        .ticket-confirmation p {
            margin-bottom: 8px;
            color: var(--gray);
            font-size: 0.95rem;
        }

        /* Responsive design */
        @media (max-width: 768px) {
            .header-container {
                flex-direction: column;
                gap: 20px;
            }

            nav ul {
                flex-wrap: wrap;
                justify-content: center;
            }

            .hero-title {
                font-size: 2.2rem;
            }

            .hero-subtitle {
                font-size: 1rem;
            }

            .packages {
                grid-template-columns: 1fr;
            }
        }

        @media (max-width: 480px) {
            .hero {
                padding: 60px 0;
            }

            .hero-title {
                font-size: 1.8rem;
            }

            .package-card.popular::before {
                right: -45px;
                padding: 4px 45px;
                width: 180px;
                font-size: 0.7rem;
            }

            .modal-content {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container header-container">
            <a href="#" class="logo">
                <i class="fas fa-bolt logo-icon"></i>
                <span class="logo-text">Datos<span class="logo-highlight">4G</span>Express</span>
            </a>
            <nav>
                <ul>
                    <li><a href="#paquetes">Paquetes</a></li>
                    <li><a href="#beneficios">Beneficios</a></li>
                    <li><a href="#contacto">Contacto</a></li>
                </ul>
            </nav>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <div class="hero-content">
                <h1 class="hero-title">Internet móvil de <span>alta velocidad</span></h1>
                <p class="hero-subtitle">Los mejores paquetes de datos 4G/3G/2G con cobertura nacional y soporte técnico avanzado</p>
                <div style="display: flex; gap: 15px; justify-content: center;">
                    <a href="#paquetes" class="cta-button">Ver paquetes</a>
                    <a href="#contacto" class="cta-button secondary">Contactar soporte</a>
                </div>
            </div>
        </div>
    </section>

    <section id="paquetes" class="container">
        <div class="section-title">
            <h2>Paquetes de datos móviles</h2>
            <p>Elige el paquete que mejor se adapte a tus necesidades de conexión</p>
        </div>
        
        <div class="packages">
            <div class="package-card">
                <div class="package-header">
                    <div>
                        <h3 class="package-title">Básico</h3>
                        <p style="color: var(--gray); font-size: 0.9rem;">Ideal para uso ocasional</p>
                    </div>
                    <i class="fas fa-mobile-alt package-icon"></i>
                </div>
                <ul class="package-features">
                    <li><i class="fas fa-check"></i> 2 GB de datos + 15 min + 20 SMS</li>
                    <li><i class="fas fa-check"></i> Velocidad máxima de 10 Mbps</li>
                    <li><i class="fas fa-check"></i> Todo en tus manos</li>
                    <li><i class="fas fa-check"></i> Soporte técnico 24/7</li>
                </ul>
                <div class="price-container">
                    <div class="original-price">Precio normal: 500 CUP</div>
                    <div class="price">500 CUP</div>
                    <div class="price-info">Precio especial de lanzamiento</div>
                </div>
                <button class="buy-button" onclick="openPaymentModal('Paquete Básico', 500)">
                    <i class="fas fa-shopping-cart"></i> Comprar ahora
                </button>
            </div>

            <div class="package-card popular">
                <div class="package-header">
                    <div>
                        <h3 class="package-title">Estándar</h3>
                        <p style="color: var(--gray); font-size: 0.9rem;">El más popular</p>
                    </div>
                    <i class="fas fa-rocket package-icon"></i>
                </div>
                <ul class="package-features">
                    <li><i class="fas fa-check"></i> 4 GB de datos + 35 min + 40 SMS</li>
                    <li><i class="fas fa-check"></i> Velocidad máxima de 20 Mbps</li>
                    <li><i class="fas fa-check"></i> Tu mejor oferta</li>
                    <li><i class="fas fa-check"></i> Soporte técnico 24/7</li>
                    <li><i class="fas fa-check"></i> Conectado con el mundo</li>
                </ul>
                <div class="price-container">
                    <div class="original-price">Precio normal: 1250 CUP</div>
                    <div class="price">1250 CUP</div>
                    <div class="price-info">Depositar la cantidad exacta</div>
                </div>
                <button class="buy-button" onclick="openPaymentModal('Paquete Estándar', 1250)">
                    <i class="fas fa-shopping-cart"></i> Comprar ahora
                </button>
            </div>

            <div class="package-card">
                <div class="package-header">
                    <div>
                        <h3 class="package-title">Premium</h3>
                        <p style="color: var(--gray); font-size: 0.9rem;">Para usuarios intensivos</p>
                    </div>
                    <i class="fas fa-crown package-icon"></i>
                </div>
                <ul class="package-features">
                    <li><i class="fas fa-check"></i> 6 GB de datos + 60 min + 70 SMS</li>
                    <li><i class="fas fa-check"></i> Velocidad máxima garantizada</li>
                    <li><i class="fas fa-check"></i> Válido por 30 días</li>
                    <li><i class="fas fa-check"></i> Soporte técnico 24/7</li>
                    <li><i class="fas fa-check"></i> Conexión fácil y segura</li>
                    <li><i class="fas fa-check"></i> 60 min de llamadas</li>
                </ul>
                <div class="price-container">
                    <div class="original-price">Precio normal: 2000 CUP</div>
                    <div class="price">2000 CUP</div>
                    <div class="price-info">Compra por transferencia</div>
                </div>
                <button class="buy-button" onclick="openPaymentModal('Paquete Premium', 2000)">
                    <i class="fas fa-shopping-cart"></i> Comprar ahora
                </button>
            </div>
        </div>
    </section>

    <section id="beneficios" class="container">
        <div class="section-title">
            <h2>Beneficios exclusivos</h2>
            <p>Descubre todo lo que ofrecemos además de nuestros paquetes de datos</p>
        </div>
        
        <div class="benefits">
            <div class="benefit-card">
                <i class="fas fa-tachometer-alt benefit-icon"></i>
                <h3 class="benefit-title">Velocidad garantizada</h3>
                <p class="benefit-description">Disfruta de conexiones ultrarrápidas con nuestra red 4G de última generación.</p>
            </div>
            
            <div class="benefit-card">
                <i class="fas fa-globe-americas benefit-icon"></i>
                <h3 class="benefit-title">Cobertura nacional</h3>
                <p class="benefit-description">Conéctate en cualquier parte del país con nuestra amplia cobertura.</p>
            </div>
            
            <div class="benefit-card">
                <i class="fas fa-headset benefit-icon"></i>
                <h3 class="benefit-title">Soporte 24/7</h3>
                <p class="benefit-description">Nuestro equipo de soporte está disponible en todo momento para ayudarte.</p>
            </div>
            
            <div class="benefit-card">
                <i class="fas fa-shield-alt benefit-icon"></i>
                <h3 class="benefit-title">Seguridad avanzada</h3>
                <p class="benefit-description">Tus datos siempre protegidos con nuestros protocolos de seguridad.</p>
            </div>
        </div>
    </section>

    <footer id="contacto">
        <div class="container">
            <div class="footer-container">
                <div class="footer-about">
                    <a href="#" class="footer-logo">
                        <i class="fas fa-bolt footer-logo-icon"></i>
                        <span class="footer-logo-text">Datos4GExpress</span>
                    </a>
                    <p>Ofreciendo los mejores paquetes de datos 4G con tecnología de punta y servicio premium.</p>
                    <div class="footer-social">
                        <a href="#"><i class="fab fa-whatsapp"></i></a>
                        <a href="#"><i class="fab fa-telegram"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                    </div>
                </div>
                
                <div class="footer-links">
                    <h3>Enlaces rápidos</h3>
                    <ul>
                        <li><a href="#paquetes">Paquetes</a></li>
                        <li><a href="#beneficios">Beneficios</a></li>
                        <li><a href="#">Preguntas frecuentes</a></li>
                        <li><a href="#">Términos y condiciones</a></li>
                        <li><a href="#">Política de privacidad</a></li>
                    </ul>
                </div>
                
                <div class="footer-contact">
                    <h3>Contacto</h3>
                    <p><i class="fas fa-envelope"></i> info@datos4gexpress.com</p>
                    <p><i class="fas fa-phone-alt"></i> +53 555 1234</p>
                    <p><i class="fas fa-clock"></i> Lunes a Viernes: 8:00 AM - 6:00 PM</p>
                    <p><i class="fas fa-map-marker-alt"></i> La Habana, Cuba</p>
                </div>
            </div>
            
            <div class="footer-bottom">
                <p class="copyright">&copy; 2023 Datos4GExpress. Todos los derechos reservados.</p>
            </div>
        </div>
    </footer>

    <!-- Modal de pago moderno -->
    <div id="paymentModal" class="modal">
        <div class="modal-content">
            <button class="close-modal" onclick="closePaymentModal()">&times;</button>
            <h2 class="modal-title">Completar compra</h2>
            
            <div class="ticket-form">
                <div class="form-group">
                    <label for="customer-name">Nombre completo</label>
                    <input type="text" id="customer-name" placeholder="Ingresa tu nombre completo">
                </div>
                
                <div class="form-group">
                    <label for="customer-phone">Teléfono</label>
                    <input type="tel" id="customer-phone" placeholder="Tu número de teléfono">
                </div>
                
                <div class="form-group">
                    <label for="transfer-number">Número de transferencia</label>
                    <input type="text" id="transfer-number" placeholder="Número de transferencia bancaria">
                </div>
            </div>
            
            <div class="payment-info">
                <p><strong>Paquete seleccionado:</strong> <span id="package-name" class="info-highlight"></span></p>
                <p><strong>Precio total:</strong> <span id="package-price" class="info-highlight"></span> CUP</p>
                <p><strong>Transferir a:</strong> <span class="info-highlight">Tarjeta 93939388338</span></p>
                <p><strong>Confirmar pago al:</strong> <span class="info-highlight">63868677</span></p>
                <p><strong>Enviar comprobante a:</strong> <span class="info-highlight">ocarmenate429@gmail.com</span></p>
            </div>
            
            <button id="createTicketBtn" class="email-button" onclick="createTicket()">
                <i class="fas fa-paper-plane"></i> Enviar solicitud
            </button>
            
            <div id="ticketConfirmation" class="ticket-confirmation">
                <i class="fas fa-check-circle"></i>
                <h3>¡Solicitud enviada!</h3>
                <p>Tu pedido ha sido procesado correctamente.</p>
                <p>Recibirás confirmación en breve.</p>
            </div>
        </div>
    </div>

    <script>
        // Funciones para el modal de pago
        function openPaymentModal(packageName, packagePrice) {
            const modal = document.getElementById('paymentModal');
            const packageNameElement = document.getElementById('package-name');
            const packagePriceElement = document.getElementById('package-price');
            
            packageNameElement.textContent = packageName;
            packagePriceElement.textContent = packagePrice.toFixed(0);
            
            // Reiniciar el formulario
            document.getElementById('customer-name').value = '';
            document.getElementById('customer-phone').value = '';
            document.getElementById('transfer-number').value = '';
            
            // Mostrar formulario y ocultar confirmación
            document.querySelector('.ticket-form').style.display = 'block';
            document.querySelector('.payment-info').style.display = 'block';
            document.getElementById('createTicketBtn').style.display = 'flex';
            document.getElementById('ticketConfirmation').style.display = 'none';
            
            modal.style.display = 'flex';
            document.body.style.overflow = 'hidden';
        }
        
        function closePaymentModal() {
            document.getElementById('paymentModal').style.display = 'none';
            document.body.style.overflow = 'auto';
        }
        
        // Función para crear y enviar el ticket
        function createTicket() {
            const name = document.getElementById('customer-name').value;
            const phone = document.getElementById('customer-phone').value;
            const transfer = document.getElementById('transfer-number').value;
            const packageName = document.getElementById('package-name').textContent;
            const packagePrice = document.getElementById('package-price').textContent;
            
            // Validar campos
            if (!name || !phone || !transfer) {
                alert('Por favor complete todos los campos');
                return;
            }
            
            // Crear el mensaje del ticket
            const subject = `Solicitud de compra: ${packageName}`;
            const body = `Detalles de la compra:\n\n` +
                          `- Nombre: ${name}\n` +
                          `- Teléfono: ${phone}\n` +
                          `- Paquete: ${packageName}\n` +
                          `- Precio: ${packagePrice} CUP\n` +
                          `- Número de transferencia: ${transfer}\n\n` +
                          `He realizado el pago a la tarjeta 93939388338 y confirmaré la transacción al 63868677.\n\n` +
                          `Por favor activar mi paquete lo antes posible.`;
            
            // Crear enlace de correo
            const mailtoLink = `mailto:ocarmenate429@gmail.com?subject=${encodeURIComponent(subject)}&body=${encodeURIComponent(body)}`;
            
            // Abrir cliente de correo
            window.open(mailtoLink, '_blank');
            
            // Mostrar mensaje de confirmación
            document.querySelector('.ticket-form').style.display = 'none';
            document.querySelector('.payment-info').style.display = 'none';
            document.getElementById('createTicketBtn').style.display = 'none';
            document.getElementById('ticketConfirmation').style.display = 'block';
            
            // Cerrar automáticamente después de 3 segundos
            setTimeout(closePaymentModal, 3000);
        }
        
        // Cerrar modal al hacer clic fuera del contenido
        window.addEventListener('click', function(event) {
            const modal = document.getElementById('paymentModal');
            if (event.target === modal) {
                closePaymentModal();
            }
        });
        
        // Smooth scrolling para enlaces internos
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                
                const targetId = this.getAttribute('href');
                const targetElement = document.querySelector(targetId);
                
                if (targetElement) {
                    window.scrollTo({
                        top: targetElement.offsetTop - 80,
                        behavior: 'smooth'
                    });
                }
            });
        });
    </script>
</body>
</html>
        
        .
