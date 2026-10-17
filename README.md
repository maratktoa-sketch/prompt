<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Prompt — Доставка из Санты</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  
  body {
    font-family: 'Montserrat', sans-serif;
    background-color: #0f172a;
    color: #f8fafc;
    line-height: 1.6;
  }

  /* --- ШАПКА С МЕНЮ --- */
  .navbar {
    background-color: #1e293b;
    padding: 15px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    position: fixed; /* Шапка всегда сверху */
    width: 100%;
    top: 0;
    z-index: 1000;
    border-bottom: 1px solid #334155;
  }
  .logo {
    font-size: 24px;
    font-weight: 800;
    color: #60a5fa;
    text-decoration: none;
  }
  .nav-links {
    display: none; /* На телефоне прячем меню, чтобы не мешало */
  }
  .btn-nav {
    background-color: #2563eb;
    color: white;
    padding: 8px 16px;
    border-radius: 8px;
    text-decoration: none;
    font-weight: 600;
    font-size: 14px;
  }

  /* --- ГЛАВНЫЙ БАННЕР (КАК НА СКРИНШОТЕ) --- */
  .hero {
    /* Тут мы ставим картинку на фон. Я нашел крутую картинку с продуктами в интернете */
    background-image: linear-gradient(rgba(15, 23, 42, 0.7), rgba(15, 23, 42, 0.9)), url('https://images.unsplash.com/photo-1542838132-92c53300491e?auto=format&fit=crop&w=1920&q=80');
    background-size: cover;
    background-position: center;
    min-height: 100vh; /* Баннер на весь экран */
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: 100px 20px 40px;
    text-align: center;
  }
  .hero h1 {
    font-size: 40px;
    font-weight: 800;
    margin-bottom: 20px;
    line-height: 1.2;
  }
  .hero p {
    font-size: 18px;
    color: #cbd5e1;
    margin-bottom: 30px;
    max-width: 600px;
    margin-left: auto;
    margin-right: auto;
  }
  
  /* Большая кнопка заказа */
  .btn-hero {
    display: inline-block;
    background-color: #ea580c; /* Оранжевая, как на скрине */
    color: white;
    padding: 18px 40px;
    border-radius: 12px;
    font-size: 18px;
    font-weight: 800;
    text-decoration: none;
    transition: background 0.3s;
  }
  .btn-hero:hover {
    background-color: #c2410c;
  }

  /* --- КОНТЕНТ НИЖЕ БАННЕРА --- */
  .container {
    max-width: 800px;
    margin: 0 auto;
    padding: 40px 20px;
  }

  .section-title {
    font-size: 28px;
    font-weight: 800;
    margin-bottom: 20px;
    color: #60a5fa;
    text-align: center;
  }

  /* Сетка тарифов */
  .tariffs-grid {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 15px;
    margin-bottom: 40px;
  }
  .tariff-item {
    background-color: #1e293b;
    padding: 20px;
    border-radius: 12px;
    text-align: center;
    border: 1px solid #334155;
  }
  .tariff-item.full-width {
    grid-column: span 2;
    background-color: #3b1a24;
    border-color: #7f1d1d;
  }
  .tariff-weight { font-size: 14px; color: #94a3b8; margin-bottom: 5px; font-weight: 600; }
  .tariff-price { font-size: 24px; font-weight: 800; color: #60a5fa; }
  .full-width .tariff-price { color: #f87171; }

  /* Кнопки заказа */
  .btn-group {
    display: flex;
    flex-direction: column;
    gap: 15px;
    max-width: 500px;
    margin: 0 auto;
  }
  .btn {
    display: block;
    text-align: center;
    padding: 16px;
    border-radius: 12px;
    text-decoration: none;
    font-weight: 800;
    font-size: 16px;
    color: white;
    border: none;
    cursor: pointer;
  }
  .btn-normal { background-color: #2563eb; }
  .btn-urgent { background-color: #dc2626; }
  .btn-call { background-color: #059669; }

  /* Команда */
  .team {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 10px;
    margin-bottom: 40px;
  }
  .team-member {
    background-color: #1e293b;
    color: #93c5fd;
    padding: 10px 20px;
    border-radius: 20px;
    font-size: 14px;
    font-weight: 600;
    border: 1px solid #334155;
  }

  footer {
    text-align: center;
    padding: 20px;
    color: #64748b;
    font-size: 14px;
    background-color: #0f172a;
    border-top: 1px solid #1e293b;
  }

  /* Адаптация под компьютеры */
  @media (min-width: 768px) {
    .nav-links { display: flex; gap: 20px; }
    .nav-links a { color: #cbd5e1; text-decoration: none; font-weight: 600; font-size: 15px; }
    .nav-links a:hover { color: #60a5fa; }
    .hero h1 { font-size: 56px; }
  }
</style>
</head>
<body>

<!-- Шапка сайта -->
<nav class="navbar">
  <a href="#" class="logo">⚡ Prompt</a>
  <div class="nav-links">
    <a href="#how">Как работает</a>
    <a href="#tariffs">Тарифы</a>
    <a href="#order">Заказать</a>
  </div>
  <a href="https://t.me/maratik_hall666" class="btn-nav" target="_blank">Написать в TG</a>
</nav>

<!-- Главный баннер на весь экран -->
<header class="hero">
  <h1>Быстрая доставка продуктов прямо к двери</h1>
  <p>Мы живем в твоем доме! Сбегаем в «Санта» за 150 метров и принесем пакет к твоей квартире.</p>
  <div>
    <a href="#order" class="btn-hero">Сделать заказ</a>
  </div>
</header>

<div class="container">
  
  <!-- Как работает -->
  <div id="how" style="margin-bottom: 50px;">
    <h2 class="section-title">Как это работает</h2>
    <ul style="list-style: none; font-size: 18px;">
      <li style="margin-bottom: 10px;">1. Пишешь нам список продуктов</li>
      <li style="margin-bottom: 10px;">2. Мы идем в «Санта» (150 м)</li>
      <li style="margin-bottom: 10px;">3. Приносим пакет к двери</li>
      <li style="margin-bottom: 10px;">4. Ты платишь по чеку + доставку</li>
    </ul>
  </div>

  <!-- Тарифы -->
  <div id="tariffs" style="margin-bottom: 50px;">
    <h2 class="section-title">Тарифы</h2>
    <div class="tariffs-grid">
      <div class="tariff-item">
        <div class="tariff-weight">до 2 кг</div>
        <div class="tariff-price">1 руб.</div>
      </div>
      <div class="tariff-item">
        <div class="tariff-weight">до 5 кг</div>
        <div class="tariff-price">2 руб.</div>
      </div>
      <div class="tariff-item">
        <div class="tariff-weight">до 10 кг</div>
        <div class="tariff-price">3 руб.</div>
      </div>
      <div class="tariff-item full-width">
        <div class="tariff-weight">🚨 Срочный заказ (20 мин)</div>
        <div class="tariff-price">+1 руб.</div>
      </div>
    </div>
  </div>

  <!-- Кнопки заказа -->
  <div id="order" style="margin-bottom: 50px;">
    <h2 class="section-title">Сделать заказ</h2>
    <div class="btn-group">
      <a href="https://t.me/maratik_hall666?text=Здраствуйте!%20Хочу%20купить%20у%20Вас:%20%5Bнапишите%20свои%20продукты%5D.%20Подъезд%20X.%20Квартира%20X-XXX." class="btn btn-normal" target="_blank">🛒 Обычный заказ</a>
      <a href="https://t.me/maratik_hall666?text=Здраствуйте!%20Экстренный%20заказ!%20Список:%20%5Bпродукты%5D.%20Подъезд:%20X.%20Квартира:%20X-XXX." class="btn btn-urgent" target="_blank">🚨 Экстренный заказ</a>
      <a href="tel:+375295594383" class="btn btn-call">📞 Позвонить</a>
    </div>
  </div>

  <!-- Команда -->
  <div>
    <h2 class="section-title">Наша команда</h2>
    <div class="team">
      <span class="team-member">MaratMegaladon</span>
      <span class="team-member">Kirka228</span>
      <span class="team-member">AShyrik</span>
    </div>
  </div>

</div>

<footer>
  © 2025 Prompt · Работаем с 10:00 до 20:00 · Дом 436
</footer>

</body>
</html>
