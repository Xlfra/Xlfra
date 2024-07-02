- 👋 Hi, I’m @Xlfra
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...

<!---
Xlfra/Xlfra is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tulipán Infinito</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f0f0f0;
        }

        .tulip-container {
            position: relative;
            width: 200px;
            height: 300px;
            perspective: 1000px;
        }

        .tulip {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            height: 100%;
            transform-style: preserve-3d;
            animation: fall 5s infinite linear;
        }

        .petal {
            position: absolute;
            width: 100px;
            height: 100px;
            border-radius: 50%;
            background-color: #f44336; /* Rojo */
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.3);
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 10px;
            color: white;
        }

        .petal:nth-child(odd) {
            transform: rotateY(45deg);
        }

        .petal:nth-child(even) {
            transform: rotateY(-45deg);
        }

        @keyframes fall {
            0% {
                transform: translateY(0) rotateY(0deg);
            }
            100% {
                transform: translateY(200px) rotateY(360deg);
            }
        }
    </style>
</head>
<body>
    <div class="tulip-container">
        <div class="tulip">
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
            <div class="petal"></div>
        </div>
    </div>

    <script>
        // Array con las frases para cada pétalo
        const phrases = [
            "Te", "voy", "a", "querer", "hasta", "que", "el", "último", "pétalo", "que", "caiga,", "Aisha."
        ];

        // Asignar las frases a cada pétalo
        const petals = document.querySelectorAll('.petal');
        petals.forEach((petal, index) => {
            petal.textContent = phrases[index % phrases.length]; // Repetir el ciclo de frases
        });

        // Añadir evento para el efecto de "primer pétalo que cae"
        petals.forEach((petal, index) => {
            if (index === 0) {
                setTimeout(() => {
                    petal.style.animation = 'none'; // Detener la animación del primer pétalo
                    petal.classList.add('fallen'); // Marcar como caído
                }, 5000); // 5000ms (5s) después de la animación inicial
            }
        });
    </script>
</body>
</html>
