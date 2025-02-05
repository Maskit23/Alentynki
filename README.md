<!DOCTYPE html>
<html lang="pl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Walentynka</title>
    <style>
        body {
            background-color: pink;
            text-align: center;
            font-family: Arial, sans-serif;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            position: relative;
            overflow: hidden;
        }
        h1 {
            font-size: 2.5em;
            color: red;
        }
        .hearts {
            position: absolute;
            top: 0;
            left: 50%;
            transform: translateX(-50%);
            width: 100%;
            height: 100%;
            pointer-events: none;
        }
        .heart {
            position: absolute;
            bottom: -50px;
            font-size: 24px;
            color: red;
            animation: float 5s linear infinite;
        }
        @keyframes float {
            0% { transform: translateY(0) scale(1); opacity: 1; }
            100% { transform: translateY(-100vh) scale(1.5); opacity: 0; }
        }
        .button-container {
            margin-top: 20px;
        }
        button {
            background-color: red;
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 18px;
            cursor: pointer;
            border-radius: 20px;
            margin: 10px;
        }
        button:hover {
            background-color: darkred;
        }
    </style>
</head>
<body>
    <h1>Czy będziesz moją Walentynką? ❤️</h1>
    <div class="button-container">
        <button onclick="alert('Wiedziałem! ❤️')">Tak</button>
        <button onclick="alert('Nie było innej opcji! 😍')">Oczywiście, że tak!</button>
    </div>
    <div class="hearts"></div>
    <script>
        function createHeart() {
            const heart = document.createElement("div");
            heart.classList.add("heart");
            heart.innerHTML = "❤️";
            heart.style.left = Math.random() * 100 + "vw";
            heart.style.animationDuration = Math.random() * 2 + 3 + "s";
            document.querySelector(".hearts").appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 300);
    </script>
</body>
</html>
