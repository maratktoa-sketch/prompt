<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Prompt — Доставка из Санты</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600;800&display=swap" rel="stylesheet">
<style>
  /* Сброс и базовые настройки */
  * { box-sizing: border-box; margin: 0; padding: 0; }
  
  body {
    font-family: 'Montserrat', sans-serif;
    background-color: #121826; /* Простой темный фон, без градиентов */
    color: #e2e8f0;
    line-height: 1.5;
  }

  /* Шапка без размытий */
  header {
    background-color: #1a2235;
    padding: 40px 20px;
    text-align: center;
    border-bottom: 2px solid #2a3752;
  }
  header h1 {
    font-size: 36px;
    font-weight: 800;
    color: #60a5fa;
    margin-bottom: 5px;
  }
  header p { font-size: 16px; color: #94a3b8; }

  /* Контейнер */
  .container {
    max-width: 600px;
    margin: 20px auto;
    padding: 0 15px;
  }

  /* Легкие карточки без тяжелых теней и блюра */
  .card {
    background-color: #1a2235;
    border-radius: 16px;
    padding: 20px;
    margin-bottom: 15px;
    border: 1px solid #2a3752;
  }

  h2 {
    font-size: 20px;
    color: #f8fafc;
    margin-bottom: 15px;
    font-weight: 800;
  }

  ul { list-style: none; }
  ul li {
    padding-left: 25px;
    position: relative;
    margin-bottom: 8px;
    font-weight: 600;
    color: #cbd5e1;
  }
  ul li::before {
    content: "⚡";
    position: absolute;
    left: 0;
  }

  /* НОВАЯ СЕТКА ТАРИФОВ (Вместо таблицы) */
  .tariffs-grid {
    display: grid;
    grid-template-columns: 1fr 1fr; /* Две колонки */
    gap: 10px;
  }
  .tariff-item {
    background-color: #232f4b;
    padding: 15px;
    border-radius: 12px;
    text-align: center;
    border: 1px solid #33446b;
  }
  .tariff-item.full-width {
    grid-column: span 2; /* Экстренный тариф на всю ширину */
    background-color: #3b1a24; /* Красноватый фон для срочности */
    border-color: #7f1d1d;
  }
  .tariff-weight {
    font-size: 14px;
    color: #94a3b8;
    margin-bottom: 5px;
    font-weight: 600;
  }
  .tariff-price {
    font-size: 20px;
    font-weight: 800;
    color: #60a5fa;
  }
  .full-width .tariff-price {
    color: #f87171;
  }

  /* Кнопки без анимаций и свечений */
  .btn-group {
    display: flex;
    flex-direction: column;
    gap: 10px;
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
  
  /* Цвета кнопок */
  .btn-normal { background-color: #2563eb; }
  .btn-normal:hover { background-color: #1d4ed8; }
  
  .btn-urgent { background-color: #dc2626; }
  .btn-urgent:hover { background-color: #b91c1c; }
  
  .btn-call { background-color: #059669; }
  .btn-call:hover { background-color: #047857; }

  /* Команда */
  .team {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
  }
  .team-member {
    background-color: #232f4b;
    color: #93c5fd;
    padding: 8px 16px;
    border-radius: 20px;
    font-size: 14px;
    font-weight: 600;
    border: 1px solid #33446b;
  }

  footer {
    text-align: center;
    padding: 20px;
    color: #64748b;
    font-size: 14px;
  }
</style>
</head>
<body>

<header>
  <h1>⚡ Prompt</h1>
  <p>Быстрая доставка из «Санта»</p>
</header>

<div class="container">

  <div class="card">
    <h2>🚀 Как это работает</h2>
    <ul>
      <li>Скидываешь нам список продуктов</li>
      <li>Мы идем в «Санта» (150 м)</li>
      <li>Приносим пакет прямо к двери</li>
      <li>Оплата: чек + доставка</li>
    </ul>
  </div>

  <div class="card">
    <h2>💎 Тарифы</h2>
    <!-- Заменили таблицу на красивые плитки -->
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

  <div class="card">
    <h2>💬 Сделать заказ</h2>
    <div class="btn-group">
      
      <!-- Обычный заказ -->
      <a href="https://t.me/maratik_hall666?text=Здраствуйте!%20Хочу%20купить%20у%20Вас:%20%5Bнапишите%20свои%20продукты%5D.%20Подъезд%20X.%20Квартира%20X-XXX." class="btn btn-normal" target="_blank">
        🛒 Обычный заказ
      </a>

      <!-- Экстренный заказ -->
      <a href="https://t.me/maratik_hall666?text=Здраствуйте!%20Экстренный%20заказ!%20Список:%20%5Bпродукты%5D.%20Подъезд:%20X.%20Квартира:%20X-XXX." class="btn btn-urgent" target="_blank">
        🚨 Экстренный заказ
      </a>
      
      <!-- Позвонить -->
      <a href="tel:+375295594383" class="btn btn-call">
        📞 Позвонить
      </a>
    </div>
  </div>

  <div class="card">
    <h2>😎 Наша команда</h2>
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
