<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Adapter Temniy Legion</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Courier New', monospace;
            background: #0a0a0a;
            color: #e0e0e0;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow-x: hidden;
        }

        /* Анимированный фон с неоновыми эффектами */
        .bg-animation {
            position: fixed;
            top: 0;
            left: 0;
            width: 50%;
            height: 50%;
            z-index: -1;
            opacity: 0.5;
            background: 
                radial-gradient(circle at 20% 30%, rgba(255, 0, 0, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 80% 70%, rgba(255, 0, 0, 0.1) 0%, transparent 50%),
                radial-gradient(circle at 40% 80%, rgba(255, 0, 0, 0.05) 0%, transparent 50%);
        }

        .particle {
            position: absolute;
            background: rgba(255, 0, 0, 0.3);
            border-radius: 50%;
            animation: float 15s infinite linear;
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.5);
        }

        @keyframes float {
            0% {
                transform: translateY(0) translateX(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-100vh) translateX(100px);
                opacity: 0;
            }
        }
        
        .container {
            max-width: 800px;
            margin: 40px auto;
            padding: 30px;
            border: 2px solid #ff0000;
            border-radius: 10px;
            background: rgba(25, 25, 25, 0.95);
            box-shadow: 0 0 30px rgba(255, 0, 0, 0.3);
            position: relative;
            overflow: hidden;
            text-align: center;
            opacity: 0;
            transform: translateY(30px);
            animation: fadeInUp 1s forwards;
        }
        
        .container::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 3px;
            background: linear-gradient(90deg, #ff0000, #ff3333, #ff0000);
        }
        
        h1 {
            color: #ff0000;
            font-size: 2.5em;
            text-align: center;
            margin-bottom: 10px;
            text-shadow: 0 0 10px rgba(255, 0, 0, 0.5);
            letter-spacing: 2px;
        }
        
        h2 {
            color: #ff6666;
            font-size: 1.8em;
            text-align: center;
            margin-bottom: 30px;
            font-weight: 300;
        }
        
        h3 {
            color: #ff0000;
            font-size: 1.3em;
            margin: 20px 0 10px 0;
            border-left: 3px solid #ff0000;
            padding-left: 15px;
            text-align: left;
        }

        /* Часы */
        .clock-container {
            margin: 30px 0;
            padding: 20px;
            background: rgba(0, 0, 0, 0.7);
            border-radius: 15px;
            border: 1px solid rgba(255, 0, 0, 0.3);
            box-shadow: 0 0 15px rgba(255, 0, 0, 0.3);
            backdrop-filter: blur(5px);
        }

        .clock-label {
            font-size: 1.2rem;
            color: #ff6666;
            margin-bottom: 10px;
            text-shadow: 0 0 5px rgba(255, 0, 0, 0.5);
        }

        .clock {
            font-size: 2.5rem;
            font-weight: bold;
            color: #ff0000;
            text-shadow: 0 0 10px rgba(255, 0, 0, 0.7);
            font-family: 'Courier New', monospace;
            letter-spacing: 2px;
        }
        
        .divider {
            height: 2px;
            background: linear-gradient(90deg, transparent, #ff0000, transparent);
            margin: 25px 0;
            border: none;
        }
        
        p {
            line-height: 1.6;
            margin: 15px 0;
            font-size: 1.1em;
            text-shadow: 0 0 5px rgba(255, 0, 0, 0.2);
        }
        
        a {
            color: #ff0000;
            text-decoration: none;
            transition: all 0.3s ease;
            border-bottom: 1px dotted transparent;
            padding: 2px 0;
            text-shadow: 0 0 5px rgba(255, 0, 0, 0.3);
        }
        
        a:hover {
            color: #ff6666;
            border-bottom-color: #ff6666;
            text-shadow: 0 0 8px rgba(255, 0, 0, 0.8);
        }
        
        .telegram-links {
            display: grid;
            gap: 15px;
            margin: 20px 0;
        }
        
        .telegram-item {
            background: rgba(255, 0, 0, 0.1);
            padding: 12px 20px;
            border-radius: 5px;
            border-left: 3px solid #ff0000;
            transition: transform 0.3s ease;
            text-align: left;
        }
        
        .telegram-item:hover {
            transform: translateX(5px);
            background: rgba(255, 0, 0, 0.15);
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.3);
        }
        
        .project-highlight {
            background: rgba(255, 0, 0, 0.1);
            padding: 15px;
            border-radius: 5px;
            border: 1px solid #ff0000;
            text-align: center;
            font-size: 1.2em;
            margin: 20px 0;
            box-shadow: 0 0 10px rgba(255, 0, 0, 0.2);
        }
        
        .owner-info {
            background: rgba(255, 0, 0, 0.05);
            padding: 15px;
            border-radius: 5px;
            margin-top: 20px;
            border: 1px solid rgba(255, 0, 0, 0.3);
        }

        /* Кнопки */
        .buttons-container {
            display: flex;
            gap: 25px;
            justify-content: center;
            flex-wrap: wrap;
            margin: 40px 0;
        }

        .telegram-btn {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
            padding: 18px 35px;
            border: none;
            border-radius: 12px;
            font-size: 1.2rem;
            font-weight: bold;
            text-decoration: none;
            cursor: pointer;
            transition: all 0.4s ease;
            min-width: 220px;
            position: relative;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.3);
            border: 2px solid #000000;
            text-shadow: 1px 1px 2px rgba(0, 0, 0, 0.8);
            background: linear-gradient(135deg, #0088ff 0%, #0055cc 100%);
            color: white;
        }

        .telegram-btn::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: 0.5s;
        }

        .telegram-btn:hover::before {
            left: 100%;
        }

        .telegram-btn:hover {
            transform: translateY(-5px) scale(1.05);
            box-shadow: 0 10px 25px rgba(0, 0, 0, 0.5), 0 0 20px rgba(0, 136, 255, 0.9);
            border: 2px solid #000000;
            background: linear-gradient(135deg, #00aaff 0%, #0077ff 100%);
        }

        .telegram-btn:active {
            transform: translateY(0) scale(1);
        }

        .telegram-icon {
            font-size: 1.5rem;
        }
        
        @media (max-width: 600px) {
            .container {
                margin: 20px auto;
                padding: 20px;
            }
            
            h1 {
                font-size: 2em;
            }
            
            h2 {
                font-size: 1.5em;
            }

            .clock {
                font-size: 2rem;
            }

            .telegram-btn {
                padding: 15px 25px;
                font-size: 1rem;
                min-width: 200px;
            }
        }
        
        /* Анимация появления */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(20px); }
            to { opacity: 1; transform: translateY(0); }
        }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .container > * {
            animation: fadeIn 0.6s ease-out;
        }
    </style>
</head>
<body>
    <div class="bg-animation" id="bgAnimation"></div>

    <div class="container">
        <h1>Adapter Temniy Legion</h1>
        <h2>Temniy Legion</h2>
        
        <div class="clock-container">
            <div class="clock-label">Московское время:</div>
            <div class="clock" id="clock">00:00:00</div>
        </div>
        
        <div class="divider"></div>
        
        <h3>Our Project:</h3>
        <div class="project-highlight">
            Temniy Legion
        </div>
        
        <div class="divider"></div>
        
        <div class="buttons-container">
            <a href="https://t.me/+IXJCximp63UwMzAy" class="telegram-btn" target="_blank">
                <i class="fab fa-telegram-plane telegram-icon"></i>
                CHANNEL › Temniy Legion
            </a>
            
            <a href="https://t.me/+u6tSoAYTMQdmNWQy" class="telegram-btn" target="_blank">
                <i class="fas fa-comments telegram-icon"></i>
                ЧАТ › Temniy Legion
            </a>
        </div>
        
        <div class="divider"></div>
        
        <p>We came here to bring order and good cybersecurity to this messenger.</p>
        
        <div class="owner-info">
            <p>Owner channel Temniy Legion: <a href="https://t.me/Krosh_garant" target="_blank">@krosh_garant</a></p>
        </div>
    </div>

    <script>
        // Создание анимированного фона с частицами
        function createParticles() {
            const bgAnimation = document.getElementById('bgAnimation');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Случайные параметры для частицы
                const size = Math.random() * 10 + 5;
                const left = Math.random() * 100;
                const animationDuration = Math.random() * 20 + 10;
                const animationDelay = Math.random() * 10;
                
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${left}%`;
                particle.style.top = '100vh';
                particle.style.animationDuration = `${animationDuration}s`;
                particle.style.animationDelay = `${animationDelay}s`;
                
                bgAnimation.appendChild(particle);
            }
        }

        // Функция для обновления времени (Московское время UTC+3)
        function updateClock() {
            const now = new Date();
            // Московское время UTC+3
            const moscowTime = new Date(now.getTime() + (3 * 60 * 60 * 1000));
            
            const hours = String(moscowTime.getUTCHours()).padStart(2, '0');
            const minutes = String(moscowTime.getUTCMinutes()).padStart(2, '0');
            const seconds = String(moscowTime.getUTCSeconds()).padStart(2, '0');
            
            document.getElementById('clock').textContent = `${hours}:${minutes}:${seconds}`;
        }

        // Инициализация при загрузке страницы
        document.addEventListener('DOMContentLoaded', function() {
            createParticles();
            
            // Обновляем время сразу и затем каждую секунду
            updateClock();
            setInterval(updateClock, 1000);
            
            // Добавляем эффект при наведении на кнопки
            const buttons = document.querySelectorAll('.telegram-btn');
            
            buttons.forEach(button => {
                button.addEventListener('mouseenter', function() {
                    this.style.transform = 'translateY(-5px) scale(1.05)';
                });
                
                button.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0) scale(1)';
                });
            });
        });
    </script>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"
