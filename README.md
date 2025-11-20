<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Help</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background-color: #000;
            color: #00ffff;
            font-family: 'Courier New', monospace;
            overflow-x: hidden;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            position: relative;
            padding: 20px;
        }

        .container {
            text-align: center;
            z-index: 10;
            position: relative;
            animation: float 3s ease-in-out infinite;
            width: 100%;
            max-width: 800px;
            padding: 0 15px;
        }

        @keyframes float {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-20px);
            }
        }

        .neon-text {
            font-size: 5rem;
            font-weight: bold;
            color: #00ffff;
            text-shadow: 
                0 0 10px #00ffff,
                0 0 20px #00ffff,
                0 0 30px #00ffff,
                0 0 40px #0080ff,
                0 0 70px #0080ff,
                0 0 80px #0080ff;
            margin-bottom: 2rem;
            letter-spacing: 5px;
        }

        .info-section {
            background: rgba(0, 255, 255, 0.1);
            border: 1px solid #00ffff;
            padding: 2rem;
            margin: 1rem 0;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(0, 255, 255, 0.3);
            width: 100%;
        }

        .separator {
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ffff, transparent);
            margin: 1.5rem 0;
        }

        .links {
            margin-top: 2rem;
            display: flex;
            flex-direction: column;
            gap: 1rem;
            align-items: center;
            width: 100%;
        }

        .link {
            color: #00ffff;
            text-decoration: none;
            padding: 0.8rem 2rem;
            border: 1px solid #00ffff;
            border-radius: 5px;
            transition: all 0.3s ease;
            text-shadow: 0 0 10px #00ffff;
            width: 250px;
            display: block;
        }

        .link:hover {
            background: #00ffff;
            color: #000;
            box-shadow: 0 0 20px #00ffff;
            transform: scale(1.05);
        }

        .telegram-links {
            display: flex;
            flex-direction: column;
            gap: 0.5rem;
            margin: 1rem 0;
        }

        .telegram-link {
            color: #00ffff;
            text-decoration: none;
            padding: 0.5rem 1rem;
            border: 1px solid #00ffff;
            border-radius: 3px;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .telegram-link:hover {
            background: #00ffff;
            color: #000;
            box-shadow: 0 0 10px #00ffff;
        }

        .owner-buttons {
            margin-top: 1.5rem;
            display: flex;
            flex-direction: column;
            gap: 0.8rem;
            align-items: center;
            width: 100%;
        }

        .owner-button {
            padding: 0.8rem 2rem;
            background: rgba(0, 255, 255, 0.1);
            border: 1px solid #00ffff;
            border-radius: 5px;
            color: #00ffff;
            text-decoration: none;
            transition: all 0.3s ease;
            display: inline-block;
            font-size: 1rem;
            width: 250px;
        }

        .owner-button:hover {
            background: #00ffff;
            color: #000;
            box-shadow: 0 0 20px #00ffff;
            transform: scale(1.05);
        }

        .owner-link {
            color: #00ffff;
            text-decoration: none;
        }

        .owner-link:hover {
            text-decoration: underline;
        }

        .channel-text {
            font-size: 1.1em;
            font-weight: bold;
            margin-bottom: 0.3rem;
        }

        .chat-text {
            font-size: 1em;
            opacity: 0.9;
        }

        .glitch-effect {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(45deg, transparent 49%, rgba(0, 255, 255, 0.1) 50%, transparent 51%);
            background-size: 10px 10px;
            animation: glitch 0.5s infinite;
            pointer-events: none;
            opacity: 0.1;
        }

        @keyframes glitch {
            0% { transform: translateX(0); }
            100% { transform: translateX(-10px); }
        }

        .scan-line {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 2px;
            background: linear-gradient(90deg, transparent, #00ffff, transparent);
            animation: scan 3s linear infinite;
            box-shadow: 0 0 10px #00ffff;
        }

        @keyframes scan {
            0% { top: 0; }
            100% { top: 100%; }
        }

        /* Медиа-запросы для адаптивности */
        @media (max-width: 768px) {
            .neon-text {
                font-size: 3.5rem;
                letter-spacing: 3px;
                margin-bottom: 1.5rem;
            }
            
            .info-section {
                padding: 1.5rem;
            }
            
            .link, .owner-button {
                width: 220px;
                padding: 0.7rem 1.5rem;
            }
        }

        @media (max-width: 480px) {
            .neon-text {
                font-size: 2.5rem;
                letter-spacing: 2px;
                margin-bottom: 1rem;
            }
            
            .info-section {
                padding: 1rem;
            }
            
            .link, .owner-button {
                width: 200px;
                padding: 0.6rem 1.2rem;
                font-size: 0.9rem;
            }
            
            .telegram-link {
                font-size: 0.8rem;
            }
            
            .channel-text, .chat-text {
                font-size: 0.9rem;
            }
        }

        @media (max-width: 320px) {
            .neon-text {
                font-size: 2rem;
            }
            
            .link, .owner-button {
                width: 180px;
            }
        }
    </style>
</head>
<body>
    <div class="scan-line"></div>
    <div class="glitch-effect"></div>
    
    <div class="container">
        <div class="neon-text">Help</div>
        
        <div class="info-section">
            <p>Adapter Help project</p>
            <div class="separator"></div>
            <div class="separator"></div>
            <div class="channel-text">CHANNEL › HELP</div>
            <div class="chat-text">ЧАТ › HELP</div>
            
            <div class="telegram-links">
                <a href="https://t.me/+IHya0C6SfUphMjgy" class="telegram-link" target="_blank"> CHANNEL › HELP</a>
                <a href="https://t.me/+u6tSoAYTMQdmNWQy" class="telegram-link" target="_blank"> ЧАТ › HELP</a>
            </div>
            
            <div class="separator"></div>
            <p>We came here to bring order to this platform, we have no equal, we are the only ones.</p>
        </div>

        <div class="links">
            <a href="https://t.me/+IHya0C6SfUphMjgy" class="link" target="_blank">JOIN CHANNEL</a>
            <a href="https://t.me/+u6tSoAYTMQdmNWQy" class="link" target="_blank">JOIN CHAT</a>
        </div>

        <div class="owner-buttons">
            <a href="Https://t.me/alisaflankova" class="owner-button" target="_blank">OWNER</a>
            <a href="Https://t.me/AlOsint" class="owner-button" target="_blank">CO OWNER</a>
        </div>
    </div>

    <script>
        // Дополнительные эффекты
        document.addEventListener('mousemove', (e) => {
            const container = document.querySelector('.container');
            const x = (e.clientX / window.innerWidth - 0.5) * 20;
            const y = (e.clientY / window.innerHeight - 0.5) * 20;
            container.style.transform = `translateY(${y}px)`;
        });

        // Эффект мерцания неона
        setInterval(() => {
            const neon = document.querySelector('.neon-text');
            const intensity = 0.8 + Math.random() * 0.4;
            neon.style.textShadow = `
                0 0 ${10 * intensity}px #00ffff,
                0 0 ${20 * intensity}px #00ffff,
                0 0 ${30 * intensity}px #00ffff,
                0 0 ${40 * intensity}px #0080ff,
                0 0 ${70 * intensity}px #0080ff,
                0 0 ${80 * intensity}px #0080ff
            `;
        }, 100);

        // Эффект ввода текста
        window.addEventListener('load', () => {
            const texts = document.querySelectorAll('.info-section p, .channel-text, .chat-text');
            texts.forEach((text, index) => {
                const originalText = text.textContent;
                text.textContent = '';
                let i = 0;
                
                setTimeout(() => {
                    const typeWriter = setInterval(() => {
                        if (i < originalText.length) {
                            text.textContent += originalText.charAt(i);
                            i++;
                        } else {
                            clearInterval(typeWriter);
                        }
                    }, 50);
                }, index * 500);
            });
        });

        // Случайное мерцание элементов
        setInterval(() => {
            const elements = document.querySelectorAll('.link, .telegram-link, .owner-button');
            elements.forEach(element => {
                if (Math.random() > 0.7) {
                    element.style.opacity = '0.7';
                    setTimeout(() => {
                        element.style.opacity = '1';
                    }, 100);
                }
            });
        }, 300);
    </script>
</body>
</html>