з<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>WoT Community Hub</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Arial', sans-serif;
        }
        body {
            background: linear-gradient(to bottom, #2c3e50, #1a2530);
            color: #ecf0f1;
            min-height: 100vh;
            background-image:
                radial-gradient(#34495e 15%, transparent 16%),
                radial-gradient(#2c3e50 15%, transparent 16%);
            background-size: 20px 20px;
            background-position: 0 0, 10px 10px;
        }
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        header {
            text-align: center;
            padding: 30px 0;
        }
        h1 {
            font-size: 3.5rem;
            color: #e74c3c;
            text-shadow: 0 0 10px rgba(231, 76, 60, 0.8);
            letter-spacing: 2px;
            animation: glow 1.5s infinite alternate;
        }
        @keyframes glow {
            from { text-shadow: 0 0 5px #e74c3c; }
            to { text-shadow: 0 0 20px #c0392b, 0 0 30px #e74c3c; }
        }
        .subtitle {
            color: #f39c12;
            font-size: 1.2rem;
            margin-top: 10px;
            text-shadow: 0 0 5px rgba(243, 156, 18, 0.7);
        }
        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        .card {
            background: rgba(0, 0, 0, 0.6);
            border: 2px solid #e74c3c;
            border-radius: 12px;
            overflow: hidden;
            position: relative;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(231, 76, 60, 0.4);
        }
        .card-img {
            width: 100%;
            height: 200px;
            object-fit: cover;
            transition: filter 0.3s;
        }
        .card:hover .card-img {
            filter: brightness(1.2) saturate(1.3);
        }
        .card-content {
            padding: 20px;
            position: relative;
        }
        .card-title {
            font-size: 1.4rem;
            color: #f39c12;
            margin-bottom: 10px;
        }
        .card-text {
            color: #bdc3c7;
            line-height: 1.6;
            margin-bottom: 15px;
        }
        .btn {
            display: inline-block;
            padding: 10px 20px;
            background: #e74c3c;
            color: white;
            text-decoration: none;
            border-radius: 6px;
            font-weight: bold;
            text-transform: uppercase;
            letter-spacing: 1px;
            transition: background 0.3s;
        }
        .btn:hover {
            background: #c0392b;
        }
        .like-btn {
            position: absolute;
            top: 15px;
            right: 15px;
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.2);
            border: none;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: background 0.3s, transform 0.2s;
            z-index: 10;
        }
        .like-btn:hover {
            background: rgba(255, 255, 255, 0.4);
            transform: scale(1.1);
        }
        .like-icon {
            color: #e74c3c;
            font-size: 1.2rem;
        }
        footer {
            text-align: center;
            padding: 40px 0;
            margin-top: 50px;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
        .social-link {
            display: inline-block;
            margin: 0 15px;
            color: #f39c12;
            font-size: 1.1rem;
            text-decoration: none;
            transition: color 0.3s;
        }
        .social-link:hover {
            color: #e74c3c;
        }
        .firework {
            position: absolute;
            pointer-events: none;
            z-index: 100;
            width: 0;
            height: 0;
            left: 0;
            top: 0;
        }
        .battle-results {
            background: rgba(0, 0, 0, 0.7);
            border: 2px solid #f39c12;
            border-radius: 12px;
            padding: 20px;
            margin: 30px auto;
            max-width: 800px;
            text-align: center;
        }
        .battle-results img {
            max-width: 100%;
            border-radius: 8px;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.5);
            margin-bottom: 20px;
        }
        .battle-stats {
            text-align: left;
            color: #ecf0f1;
            line-height: 1.8;
        }
        .battle-stats strong {
            color: #e74c3c;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>WoT Community Hub</h1>
            <p class="subtitle">Место для настоящих танкистов!</p>
        </header>

        <div class="grid">
            <div class="card" onmouseover="launchFirework(event)">
                <img src="ВАША_ССЫЛКА_НА_ФОТО_1" alt="Фото 1" class="card-img">
                <div class="card-content">
                    <h3 class="card-title">Заголовок 1</h3>
                    <p class="card-text">Описание карточки 1.</p>
                    <a href="#" class="btn">Подробнее</a>
                </div>
                <button class="like-btn" onclick="likeCard(this)">
                    <span class="like-icon">♥
