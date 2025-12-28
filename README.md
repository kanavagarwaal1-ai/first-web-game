<!DOCTYPE html>
<html>
<head>
    <title>Guess the Number Game</title>
    <style>
        body {
            font-family: Arial;
            text-align: center;
            background-color: #f0f8ff;
        }

        input {
            padding: 8px;
            font-size: 16px;
        }

        button {
            padding: 8px 12px;
            margin: 5px;
            font-size: 16px;
            cursor: pointer;
        }

        #result {
            font-weight: bold;
            margin-top: 10px;
        }
    </style>
</head>
<body>

    <h2>Guess the Number (1–10)</h2>

    <input id="guess" type="number" placeholder="Enter number">
    <button onclick="checkGuess()">Guess</button>
    <button onclick="resetGame()">Reset</button>

    <p id="result"></p>
    <p id="attempts"></p>

    <script>
        let secret = Math.floor(Math.random() * 10) + 1;
        let tries = 0;

        function checkGuess() {
            let userGuess = document.getElementById("guess").value;
            tries++;

            if (userGuess == secret) {
                document.getElementById("result").innerHTML = "🎉 You win!";
            } else {
                document.getElementById("result").innerHTML = "❌ Wrong! Try again.";
            }

            document.getElementById("attempts").innerHTML = "Attempts: " + tries;
        }

        function resetGame() {
            secret = Math.floor(Math.random() * 10) + 1;
            tries = 0;
            document.getElementById("result").innerHTML = "";
            document.getElementById("attempts").innerHTML = "";
            document.getElementById("guess").value = "";
        }
    </script>

</body>
</html>
