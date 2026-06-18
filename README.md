<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>KLOVIY VPN — Безопасный интернет</title>
    <!-- Шрифты и иконки -->
    <link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* ===== Базовые сбросы и переменные ===== */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #6C3CE1;
            --primary-dark: #4B1F9E;
            --secondary: #00D4FF;
            --bg-dark: #0A0A1A;
            --bg-card: rgba(255, 255, 255, 0.05);
            --text-light: #F0F0FF;
            --text-muted: #AAB;
            --border-glow: rgba(108, 60, 225, 0.3);
            --radius: 16px;
            --shadow: 0 20px 60px rgba(0, 0, 0, 0.6);
        }

        body {
            font-family: 'Inter', sans-serif;
            background: var(--bg-dark);
            color: var(--text-light);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 24px;
        }

        /* ===== Шапка ===== */
        header {
            padding: 20px 0;
            border-bottom: 1px solid rgba(255, 255, 255, 0.05);
            position: sticky;
            top: 0;
            background: rgba(10, 10, 26, 0.85);
            backdrop-filter: blur(12px);
            z-index: 100;
        }

        .header-inner {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
        }

        .logo {
            font-size: 28px;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            letter-spacing: -0.5px;
        }
        .logo i {
            -webkit-text-fill-color: var(--secondary);
            margin-right: 8px;
        }

        nav a {
            color: var(--text-muted);
            text-decoration: none;
            margin-left: 32px;
            font-weight: 500;
            transition: 0.3s;
            position: relative;
        }
        nav a:hover {
            color: #fff;
        }
        nav a::after {
            content: '';
            position: absolute;
            bottom: -4px;
            left: 0;
            width: 0;
            height: 2px;
            background: var(--secondary);
            transition: 0.3s;
        }
        nav a:hover::after {
            width: 100%;
        }
        .btn-outline {
            border: 2px solid var(--primary);
            padding: 8px 20px;
            border-radius: 30px;
            color: #fff !important;
            transition: 0.3s;
        }
        .btn-outline:hover {
            background: var(--primary);
            border-color: var(--primary);
        }

        /* ===== Герой ===== */
        .hero {
            padding: 80px 0 60px;
            display: flex;
            align-items: center;
            gap: 40px;
            flex-wrap: wrap;
        }
        .hero-content {
            flex: 1 1 500px;
        }
        .hero-content h1 {
            font-size: 56px;
            font-weight: 800;
            line-height: 1.1;
            margin-bottom: 20px;
        }
        .hero-content h1 span {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }
        .hero-content p {
            font-size: 20px;
            color: var(--text-muted);
            max-width: 500px;
            margin-bottom: 30px;
        }
        .btn-primary {
            display: inline-block;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: #fff;
            padding: 14px 40px;
            border-radius: 50px;
            font-weight: 600;
            text-decoration: none;
            transition: 0.3s;
            box-shadow: 0 0 30px var(--border-glow);
        }
        .btn-primary:hover {
            transform: scale(1.04);
            box-shadow: 0 0 50px var(--border-glow);
        }
        .hero-stats {
            display: flex;
            gap: 40px;
            margin-top: 40px;
        }
        .hero-stats div {
            text-align: center;
        }
        .hero-stats .number {
            font-size: 32px;
            font-weight: 700;
            color: #fff;
        }
        .hero-stats .label {
            color: var(--text-muted);
            font-size: 14px;
        }

        .hero-image {
            flex: 1 1 400px;
            display: flex;
            justify-content: center;
        }
        .hero-image .globe {
            font-size: 200px;
            color: var(--primary);
            opacity: 0.3;
            animation: pulse 6s infinite alternate;
        }
        @keyframes pulse {
            0% { opacity: 0.2; transform: scale(0.95); }
            100% { opacity: 0.6; transform: scale(1.05); }
        }

        /* ===== Общие секции ===== */
        section {
            padding: 80px 0;
        }
        .section-title {
            font-size: 40px;
            font-weight: 700;
            text-align: center;
            margin-bottom: 12px;
        }
        .section-subtitle {
            text-align: center;
            color: var(--text-muted);
            max-width: 600px;
            margin: 0 auto 60px;
            font-size: 18px;
        }

        /* ===== Преимущества ===== */
        .features-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
            gap: 30px;
        }
        .feature-card {
            background: var(--bg-card);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: var(--radius);
            padding: 30px 24px;
            text-align: center;
            backdrop-filter: blur(4px);
            transition: 0.4s;
        }
        .feature-card:hover {
            transform: translateY(-8px);
            border-color: var(--primary);
            box-shadow: 0 12px 40px rgba(108, 60, 225, 0.15);
        }
        .feature-card i {
            font-size: 48px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 16px;
        }
        .feature-card h3 {
            font-size: 22px;
            margin-bottom: 10px;
        }
        .feature-card p {
            color: var(--text-muted);
            font-size: 15px;
        }

        /* ===== Тарифы ===== */
        .pricing-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
            gap: 20px;
            align-items: stretch;
        }
        .pricing-card {
            background: var(--bg-card);
            border: 1px solid rgba(255, 255, 255, 0.06);
            border-radius: var(--radius);
            padding: 30px 24px;
            text-align: center;
            transition: 0.4s;
            backdrop-filter: blur(4px);
            display: flex;
            flex-direction: column;
            position: relative;
        }
        .pricing-card:hover {
            border-color: var(--secondary);
            transform: translateY(-4px);
        }
        .pricing-card.best {
            border-color: var(--primary);
            box-shadow: 0 0 40px var(--border-glow);
            transform: scale(1.05);
        }
        .pricing-card.best:hover {
            transform: scale(1.05) translateY(-4px);
        }
        .pricing-card .plan-name {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 12px;
        }
        .pricing-card .price {
            font-size: 36px;
            font-weight: 800;
            margin: 12px 0;
        }
        .pricing-card .price small {
            font-size: 14px;
            font-weight: 400;
            color: var(--text-muted);
            display: block;
        }
        .pricing-card .duration {
            color: var(--text-muted);
            font-size: 14px;
            margin-bottom: 16px;
        }
        .btn-plan {
            background: transparent;
            border: 2px solid var(--primary);
            color: #fff;
            padding: 12px 24px;
            border-radius: 50px;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
            text-decoration: none;
            display: inline-block;
        }
        .btn-plan:hover {
            background: var(--primary);
        }
        .pricing-card.best .btn-plan {
            background: var(--primary);
            border-color: var(--primary);
        }
        .pricing-card.best .btn-plan:hover {
            background: var(--secondary);
            border-color: var(--secondary);
        }
        .badge {
            background: var(--secondary);
            color: #000;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 11px;
            font-weight: 700;
            display: inline-block;
            margin-bottom: 8px;
            position: absolute;
            top: 12px;
            right: 12px;
        }

        /* ===== Отзывы ===== */
        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
        }
        .testimonial-card {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 28px;
            border: 1px solid rgba(255, 255, 255, 0.06);
        }
        .testimonial-card .stars {
            color: #FFD700;
            margin-bottom: 12px;
        }
        .testimonial-card p {
            font-style: italic;
            color: var(--text-muted);
        }
        .testimonial-card .author {
            margin-top: 16px;
            font-weight: 600;
        }

        /* ===== Форма подписки ===== */
        .subscribe-box {
            background: var(--bg-card);
            border-radius: var(--radius);
            padding: 50px 40px;
            text-align: center;
            border: 1px solid rgba(255, 255, 255, 0.06);
            max-width: 600px;
            margin: 0 auto;
        }
        .subscribe-box h3 {
            font-size: 28px;
            margin-bottom: 12px;
        }
        .subscribe-box p {
            color: var(--text-muted);
            margin-bottom: 24px;
        }
        .subscribe-box form {
            display: flex;
            gap: 12px;
            flex-wrap: wrap;
            justify-content: center;
        }
        .subscribe-box input {
            flex: 1 1 250px;
            padding: 14px 20px;
            border-radius: 50px;
            border: none;
            background: rgba(255, 255, 255, 0.08);
            color: #fff;
            font-size: 16px;
            outline: none;
            transition: 0.3s;
        }
        .subscribe-box input:focus {
            background: rgba(255, 255, 255, 0.12);
            box-shadow: 0 0 0 2px var(--primary);
        }
        .subscribe-box button {
            padding: 14px 36px;
            border: none;
            border-radius: 50px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: #fff;
            font-weight: 600;
            cursor: pointer;
            transition: 0.3s;
        }
        .subscribe-box button:hover {
            transform: scale(1.05);
        }

        /* ===== Футер ===== */
        footer {
            border-top: 1px solid rgba(255, 255, 255, 0.05);
            padding: 40px 0 30px;
            text-align: center;
            color: var(--text-muted);
            font-size: 14px;
        }
        footer .socials {
            margin-bottom: 16px;
        }
        footer .socials a {
            color: var(--text-muted);
            margin: 0 12px;
            font-size: 20px;
            transition: 0.3s;
        }
        footer .socials a:hover {
            color: #fff;
        }

        /* ===== Адаптив ===== */
        @media (max-width: 768px) {
            .hero-content h1 {
                font-size: 36px;
            }
            .hero-stats {
                flex-wrap: wrap;
                gap: 20px;
            }
            .header-inner {
                flex-direction: column;
                gap: 12px;
            }
            nav a {
                margin: 0 12px;
            }
            .section-title {
                font-size: 30px;
            }
            .pricing-grid {
                grid-template-columns: 1fr;
            }
            .pricing-card.best {
                transform: scale(1);
            }
            .pricing-card.best:hover {
                transform: scale(1) translateY(-4px);
            }
            .subscribe-box {
                padding: 30px 20px;
            }
        }
    </style>
</head>
<body>

<!-- ===== ШАПКА ===== -->
<header>
    <div class="container header-inner">
        <div class="logo">
            <i class="fas fa-shield-alt"></i> KLOVIY_VPN
        </div>
        <nav>
            <a href="#features">Возможности</a>
            <a href="#pricing">Тарифы</a>
            <a href="#testimonials">Отзывы</a>
            <a href="#subscribe" class="btn-outline">Подключиться</a>
        </nav>
    </div>
</header>

<!-- ===== ГЕРОЙ ===== -->
<section class="hero container">
    <div class="hero-content">
        <h1>Безопасный интернет <br><span>с KLOVIY_VPN</span></h1>
        <p>Мгновенное шифрование, безлимитная скорость и полная анонимность. Ваши данные — под надёжной защитой.</p>
        <a href="#subscribe" class="btn-primary"><i class="fas fa-rocket"></i> Начать сейчас</a>
        <div class="hero-stats">
            <div><div class="number">4.9</div><div class="label">★ Рейтинг</div></div>
            <div><div class="number">12M+</div><div class="label">Пользователей</div></div>
            <div><div class="number">90+</div><div class="label">Стран</div></div>
        </div>
    </div>
    <div class="hero-image">
        <div class="globe"><i class="fas fa-globe-americas"></i></div>
    </div>
</section>

<!-- ===== ПРЕИМУЩЕСТВА ===== -->
<section id="features">
    <div class="container">
        <h2 class="section-title">Почему KLOVIY_VPN?</h2>
        <p class="section-subtitle">Мы создали VPN, которому можно доверять — без компромиссов в скорости и безопасности.</p>
        <div class="features-grid">
            <div class="feature-card">
                <i class="fas fa-lock"></i>
                <h3>Военное шифрование</h3>
                <p>Используем протоколы AES-256 и ChaCha20 — ваши данные не перехватить даже суперкомпьютеру.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-bolt"></i>
                <h3>Максимальная скорость</h3>
                <p>Собственная сеть серверов с оптимизацией для стриминга, игр и загрузок без потери пинга.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-user-secret"></i>
                <h3>Полная анонимность</h3>
                <p>Никаких логов, никаких следов. Даже мы не знаем, чем вы занимаетесь в сети.</p>
            </div>
            <div class="feature-card">
                <i class="fas fa-globe"></i>
                <h3>Доступ к контенту</h3>
                <p>Обходите географические блокировки и наслаждайтесь любимыми сервисами из любой точки мира.</p>
            </div>
        </div>
    </div>
</section>

<!-- ===== ТАРИФЫ ===== -->
<section id="pricing" style="background: rgba(255,255,255,0.02);">
    <div class="container">
        <h2 class="section-title">Выберите свой план</h2>
        <p class="section-subtitle">Гибкие тарифы на любой срок. Попробуйте прямо сейчас!</p>
        <div class="pricing-grid">
            <!-- 1 месяц -->
            <div class="pricing-card">
                <div class="plan-name">1 месяц</div>
                <div class="price">80<small>₽</small></div>
                <div class="duration">Одноразовая покупка</div>
                <a href="#subscribe" class="btn-plan">Купить</a>
            </div>

            <!-- 2 месяца -->
            <div class="pricing-card">
                <div class="plan-name">2 месяца</div>
                <div class="price">160<small>₽</small></div>
                <div class="duration">80₽ за месяц</div>
                <a href="#subscribe" class="btn-plan">Купить</a>
            </div>

            <!-- 3 месяца -->
            <div class="pricing-card">
                <div class="plan-name">3 месяца</div>
                <div class="price">240<small>₽</small></div>
                <div class="duration">80₽ за месяц</div>
                <a href="#subscribe" class="btn-plan">Купить</a>
            </div>

            <!-- 4 месяца -->
            <div class="pricing-card">
                <div class="plan-name">4 месяца</div>
                <div class="price">320<small>₽</small></div>
                <div class="duration">80₽ за месяц</div>
                <a href="#subscribe" class="btn-plan">Купить</a>
            </div>

            <!-- 1 год (ЛУЧШИЙ) -->
            <div class="pricing-card best">
                <span class="badge">🔥 ЛУЧШИЙ</span>
                <div class="plan-name">1 год</div>
                <div class="price">960<small>₽</small></div>
                <div class="duration">80₽ за месяц</div>
                <a href="#subscribe" class="btn-plan">Купить</a>
            </div>
        </div>
    </div>
</section>

<!-- ===== ОТЗЫВЫ ===== -->
<section id="testimonials">
    <div class="container">
        <h2 class="section-title">Что говорят пользователи</h2>
        <p class="section-subtitle">Более 12 миллионов человек уже доверили нам свою безопасность.</p>
        <div class="testimonials-grid">
            <div class="testimonial-card">
                <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                <p>«С KLOVIY_VPN я забыл о блокировках. Скорость даже выше, чем у моего обычного интернета!»</p>
                <div class="author">— Александр, Москва</div>
            </div>
            <div class="testimonial-card">
                <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                <p>«Использую для работы с конфиденциальными данными. Интерфейс простой, а защита — надёжная.»</p>
                <div class="author">— Екатерина, Санкт-Петербург</div>
            </div>
            <div class="testimonial-card">
                <div class="stars"><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i><i class="fas fa-star"></i></div>
                <p>«Лучший VPN, который я пробовал. Поддержка отвечает за 5 минут, а тарифы очень доступные.»</p>
                <div class="author">— Дмитрий, Киев</div>
            </div>
        </div>
    </div>
</section>

<!-- ===== ПОДПИСКА ===== -->
<section id="subscribe">
    <div class="container">
        <div class="subscribe-box">
            <h3>🚀 Готовы к безопасному интернету?</h3>
            <p>Оставьте почту, и мы пришлём вам персональную скидку 20% на первый месяц.</p>
            <form onsubmit="event.preventDefault(); alert('Спасибо! Мы свяжемся с вами.');">
                <input type="email" placeholder="Ваш email" required>
                <button type="submit">Получить скидку</button>
            </form>
            <small style="display: block; margin-top: 16px; color: var(--text-muted);">Никакого спама, только полезны�� предложения.</small>
        </div>
    </div>
</section>

<!-- ===== ФУТЕР ===== -->
<footer>
    <div class="container">
        <div class="socials">
            <a href="#"><i class="fab fa-telegram"></i></a>
            <a href="#"><i class="fab fa-youtube"></i></a>
            <a href="#"><i class="fab fa-twitter"></i></a>
            <a href="#"><i class="fab fa-github"></i></a>
        </div>
        <p>© 2026 KLOVIY_VPN. Все права защищены. <br> Работает по всему миру без логов.</p>
    </div>
</footer>

<script>
    // Плавный скролл для якорных ссылок
    document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
            e.preventDefault();
            const target = document.querySelector(this.getAttribute('href'));
            if (target) {
                target.scrollIntoView({ behavior: 'smooth', block: 'start' });
            }
        });
    });
</script>

</body>
</html>
