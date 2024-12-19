<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Proposal for Shilpa</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background-color: #ffe4e1;
            color: #333;
            overflow: hidden;
        }
        .container {
            margin-top: 50px;
        }
        h1 {
            font-size: 2.5rem;
            color: #ff1493;
            animation: bounce 1.5s infinite;
        }
        .buttons {
            margin-top: 30px;
        }
        button {
            font-size: 18px;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            border-radius: 5px;
            margin: 10px;
            transition: 0.3s;
        }
        .yes {
            background-color: #32cd32;
            color: white;
        }
        .no {
            background-color: #ff6347;
            color: white;
            position: absolute;
        }
        @keyframes bounce {
            0%, 100% {
                transform: translateY(0);
            }
            50% {
                transform: translateY(-15px);
            }
        }
        .hidden {
            display: none;
        }
        .question {
            font-size: 1.5rem;
            margin-bottom: 20px;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Shilpa, Kya Tum Mujhse Shaadi Karogi? 💍</h1>
        <div class="question hidden" id="question1">1. Tumhe pata hai mujhe tum kyu pasand ho? 😍</div>
        <div class="question hidden" id="question2">2. Tumhare bina zindagi adhoori lagti hai! Tumhe bhi lagta hai? ❤️</div>
        <div class="question hidden" id="question3">3. Kya hum ek saath duniya ghoom sakte hain? 🌏</div>
        <div class="question hidden" id="question4">4. Agar main tumhe "I Love You" bolu to tum kya kahogi? 🥰</div>
        <div class="buttons">
            <button class="yes" onclick="nextQuestion()">Haan 😘</button>
            <button class="no" id="noButton" onmouseover="moveButton()">Nahi 😂</button>
        </div>
    </div>

    <script>
        let currentQuestion = 0;
        const totalQuestions = 4;

        function nextQuestion() {
            if (currentQuestion < totalQuestions) {
                currentQuestion++;
                document.getElementById(`question${currentQuestion}`).classList.remove('hidden');
                if (currentQuestion > 1) {
                    document.getElementById(`question${currentQuestion - 1}`).classList.add('hidden');
                }
                if (currentQuestion === totalQuestions) {
                    document.querySelector('h1').textContent = "Shilpa, Tumne 'Haan' bola! Main duniya ka sabse khush insaan ban gaya! 💖";
                    document.querySelector('.buttons').classList.add('hidden');
                }
            }
        }

        function moveButton() {
            const button = document.getElementById('noButton');
            const x = Math.random() * (window.innerWidth - button.offsetWidth);
            const y = Math.random() * (window.innerHeight - button.offsetHeight);
            button.style.left = `${x}px`;
            button.style.top = `${y}px`;
        }
    </script>
</body>
</html>
