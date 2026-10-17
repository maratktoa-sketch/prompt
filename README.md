<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Prompt — Доставка нового уровня</title>
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;600;800&display=swap" rel="stylesheet">
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  
  body {
    font-family: 'Montserrat', sans-serif;
    background: #0b0f19;
    background-image: radial-gradient(circle at top right, #1e1b4b, #0b0f19 60%);
    color: #e2e8f0;
    line-height: 1.6;
    min-height: 100vh;
  }

  header {
    background: linear-gradient(135deg, rgba(59, 130, 246, 0.2), rgba(139, 92, 246, 0.2));
    border-bottom: 1px solid rgba(255, 255, 255, 0.1);
    padding: 60px 20px;
    text-align: center;
    backdrop-filter: blur(10px);
    border-bottom-left-radius: 40px;
    border-bottom-right-radius: 40px;
    position: relative;
    overflow: hidden;
  }
  header::before {
    content: '';
    position: absolute;
    top: -50%; left: -50%;
    width: 200%; height: 200%;
    background: radial-gradient(circle, rgba(59, 130, 246, 0.4) 0%, transparent 60%);
    z-index: -1;
  }
  header h1 {
    font-size: 42px;
    font-weight: 800;
    margin-bottom: 10px;
    background: linear-gradient(to right, #60a5fa, #c084fc);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    text-shadow: 0 0 30px rgba(96, 165, 250, 0.3);
  }
  header p { font-size: 18px; color: #94a3b8; font-weight: 600; }

  .container {
    max-width: 600px;
    margin: -40px auto 40px;
    padding: 0 20px;
    position: relative;
    z-index: 10;
  }

  .card {
    background: rgba(30, 41, 59, 0.6);
    border: 1px solid rgba(255, 255, 255, 0.05);
    border-radius: 24px;
    padding: 30px;
    margin-bottom: 20px;
    backdrop-filter: blur(16px);
    box-shadow: 0 10px 30px rgba(0, 0, 0, 0.3);
    transition: transform 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275), box-shadow 0.4s ease, border-color 0.4s ease;
  }
  .card:hover {
    transform: translateY(-8px);
    box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5), 0 0 20px rgba(59, 130, 246, 0.2);
    border-color: rgba(59, 130, 246, 0.3);
  }

  h2 {
    font-size: 22px;
    color: #f8fafc;
    margin-bottom: 15px;
    font-weight: 800;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  ul { list-style: none; }
  ul li {
    padding-left: 30px;
    position: relative;
    margin-bottom: 12px;
    font-weight: 600;
    color: #cbd5e1;
  }
  ul li::before { content: "✨"; position: absolute; left: 0; top: 0; }

  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 15px;
    background: rgba(15, 23, 42, 0.4);
    border-radius: 12px;
    overflow: hidden;
  }
  th, td { padding: 14px; text-align: left; border-bottom: 1px solid rgba(255, 255, 255, 0.05); }
  th { color: #94a3b8; font-weight: 600; font-size: 14px; text-transform: uppercase; letter-spacing: 1px; }
  td { font-weight: 600; color: #f1f5f9; }
  tr:last-child td { border-bottom: none; }

  .btn-group {
    display: flex;
    flex-direction: column;
    gap: 15px;
    margin-top: 20px;
  }
  .btn {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 10px;
    padding: 18px;
    border-radius: 16px;
    text-decoration: none;
    font-weight: 800;
    font-size: 16px;
    color: white;
    transition: transform 0.2s, filter 0.2s, box-shadow 0.2s;
    cursor: pointer;
    border: none;
    width: 100%;
    letter-spacing: 0.5px;
  }
  .btn:active { transform: scale(0.97); }
  
  /* Кнопка Обычного заказа (синяя) */
  .btn-normal {
    background: linear-gradient(135deg, #0088cc, #00aaff);
    box-shadow: 0 6px 20px rgba(0, 136, 204, 0.4);
  }
  .btn-normal:hover { filter: brightness(1.15); box-shadow: 0 8px 25px rgba(0, 136, 204, 0.6); }

  /* Кнопка Экстренного заказа (красная/оранжевая) */
  .btn-urgent {
    background: linear-gradient(135deg, #ef4444, #f97316);
    box-shadow: 0 6px 20px rgba(239, 68, 68, 0.4);
  }
  .btn-urgent:hover { filter: brightness(1.15); box-shadow: 0 8px 25px rgba(239, 68, 68, 0.6); }
  
  /* Кнопка звонка (зеленая) */
  .btn-call {
    background: linear-gradient(135deg, #10b981, #34d399);
    box-shadow: 0 6px 20px rgba(16, 185, 129, 0.4);
  }
  .btn-call:hover { filter: brightness(1.15); box-shadow: 0 8px 25px rgba(16, 185, 129, 0.6); }

  .team { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 15px; }
  .team-member {
    background: rgba(59, 130, 246, 0.15);
    color: #93c5fd;
    padding: 10px 20px;
    border-radius: 30px;
    font-size: 14px;
    font-weight: 800;
    border: 1px solid rgba(59, 130, 246, 0.3);
    transition: background 0.3s, transform 0.3s;
  }
  .team-member:hover { background: rgba(59, 130, 246, 0.3); transform: scale(1.05); }

  footer { text-align: center; padding: 30px; color: #64748b; font-size: 14px; font-weight: 600; }

  .fade-in { animation: fadeIn 0.8s ease forwards; opacity: 0; }
  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(30px); }
    to { opacity: 1; transform: translateY(0); }
  }
</style>
</head>
<body>

<header>
  <h1>⚡ Prompt</h1>
  <p>Быстрая доставка из «Санта»</p>
</header>

<div class="container">

  <div class="card fade-in" style="animation-delay: 0.1s;">
    <h2>🚀 Как это работает</h2>
    <ul>
      <li>Скидываешь нам список продуктов</li>
      <li>Мы пулей летим в «Санта» (150 м)</li>
      <li>Приносим пакет прямо к двери</li>
      <li>Оплата: чек + доставка</li>
    </ul>
  </div>

  <div class="card fade-in" style="animation-delay: 0.2s;">
    <h2>💎 Тарифы</h2>
    <table>
      <tr><th>Вес</th><th>Цена</th></tr>
      <tr><td>до 2 кг</td><td>1 руб.</td></tr>
      <tr><td>до 5 кг</td><td>2 руб.</td></tr>
      <tr><td>до 10 кг</td><td>3 руб.</td></tr>
      <tr><td>Срочно</td><td>+1 руб.</td></tr>
    </table>
  </div>

  <div class="card fade-in" style="animation-delay: 0.3s;">
    <h2>💬 Сделать заказ</h2>
    <p style="margin-bottom: 15px; font-weight: 600; color: #94a3b8;">Выбирай тип заказа:</p>
    <div class="btn-group">
      
      <!-- 1. ОБЫЧНЫЙ ЗАКАЗ -->
      <!-- Текст: Здраствуйте! Хочу купить у Вас: [напишите свои продукты]. Подъезд X. Квартира X-XXX. -->
      <a href="https://t.me/maratik_hall666?text=Здраствуйте!%20Хочу%20купить%20у%20Вас:%20%5Bнапишите%20свои%20продукты%5D.%20Подъезд%20X.%20Квартира%20X-XXX." class="btn btn-normal" target="_blank">
        <span>🛒</span> Обычный заказ
      </a>

      <!-- 2. ЭКСТРЕННЫЙ ЗАКАЗ -->
      <!-- Текст: Здраствуйте! Экстренный заказ! Список: [продукты]. Подъезд: X. Квартира: X-XXX. -->
      <a href="https://t.me/maratik_hall666?text=Здраствуйте!%20Экстренный%20заказ!%20Список:%20%5Bпродукты%5D.%20Подъезд:%20X.%20Квартира:%20X-XXX." class="btn btn-urgent" target="_blank">
        <span>🚨</span> Экстренный заказ
      </a>
      
      <!-- 3. ПОЗВОНИТЬ -->
      <a href="tel:+375295594383" class="btn btn-call">
        <span>📞</span> Позвонить
      </a>
    </div>
  </div>

  <div class="card fade-in" style="animation-delay: 0.4s;">
    <h2>😎 Наша команда</h2>
    <p style="margin-bottom: 15px; font-weight: 600; color: #94a3b8;">Три друга из твоего дома:</p>
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

<script>
  document.addEventListener("DOMContentLoaded", () => {
    const cards = document.querySelectorAll('.card');
    cards.forEach((card, index) => {
      setTimeout(() => {
        card.style.opacity = 1;
        card.style.transform = 'translateY(0)';
      }, index * 150);
    });
  });
</script>

</body>
</html>
