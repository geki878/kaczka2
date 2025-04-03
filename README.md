<!DOCTYPE html>
<html lang="pl">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wielkanoc 2025</title>
<img src="geki co jest.jpg" alt= width="500" height="300">
    <style>
        /* Ustawienia dla całej strony */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: Arial, sans-serif;
            background-color: #ADD8E6;
            color: #fff;
            text-align: center;
            overflow: hidden;
            height: 100vh;
            position: relative;
        }

        h1 {
            font-size: 3em;
            color: #ff69b4;
            margin-top: 20%;
        }

        p {
            font-size: 1.5em;
            color: #fff;
        }

        .time {
            font-size: 2em;
            margin-top: 20px;
        }

        /* Efekt spadającego śniegu */
        .snow{
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
        }

        .snowflake {
            position: absolute;
            top: -10px;
            background-color: #ffffff;
            border-radius: 50%;
            opacity: 0.9;
            pointer-events: none;
            animation: fall 10s linear infinite;
        }

        @keyframes fall {
            0% {
                top: -10px;
            }

            100% {
                top: 100vh;
            }
        }
    </style>
</head>

<body>
    <div class="snow"></div>
    <h1>Wesołych Świąt Wielkanocnych!</h1>
    <p>Niech te Święta przyniosą Wam spokój, radość i wiele błogosławieństw.  
    Niech nadzieja, jak zmartwychwstanie, wypełnia Wasze serca!</p>
    <div class="time">
        <p id="clock"></p>
    </div>

    <script>
        // Funkcja do aktualizacji zegara
        function updateClock() {
            const now = new Date();
            const hours = now.getHours().toString().padStart(2, '0');
            const minutes = now.getMinutes().toString().padStart(2, '0');
            const seconds = now.getSeconds().toString().padStart(2, '0');
            document.getElementById('clock').textContent = `${hours}:${minutes}:${seconds}`;
        }

        // Ustawienie zegara na stronie
        setInterval(updateClock, 1000);
        updateClock();  // Inicjalizacja zegara przy ładowaniu strony

        // Generowanie płatków śniegu
        const snowContainer = document.querySelector('.snow');

        function createSnowflake() {
            const snowflake = document.createElement('div');
            snowflake.classList.add('snowflake');
            
            // Random size for snowflakes
            const size = Math.random() * 10 + 5;
            snowflake.style.width = `${size}px`;
            snowflake.style.height = `${size}px`;
            
            // Random starting position
            snowflake.style.left = Math.random() * 100 + 'vw';
            
            // Random animation duration (slow or fast)
            const duration = Math.random() * 3 + 5;
            snowflake.style.animationDuration = `${duration}s`;
            
            snowContainer.appendChild(snowflake);
            
            // Remove snowflake once it has fallen off the screen
            snowflake.addEventListener('animationiteration', () => {
                snowflake.remove();
            });
        }

        // Generowanie płatków śniegu co 100ms
        setInterval(createSnowflake, 100);
    </script>

</body>

</html>
