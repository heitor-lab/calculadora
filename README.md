<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Calculadora</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #f4f4f4;
        }

        .calculator {
            background: #fff;
            border-radius: 10px;
            box-shadow: 0 4px 10px rgba(0, 0, 0, 0.2);
            overflow: hidden;
            width: 300px;
        }

        .display {
            background: #222;
            color: #fff;
            font-size: 2rem;
            padding: 20px;
            text-align: right;
            overflow-x: auto;
        }

        .buttons {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 1px;
            background: #ccc;
        }

        .btn {
            background: #f4f4f4;
            border: none;
            font-size: 1.5rem;
            padding: 20px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .btn:hover {
            background: #ddd;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <div class="display" id="display">0</div>
        <div class="buttons">
            <button class="btn" onclick="clearDisplay()">C</button>
            <button class="btn" onclick="appendToDisplay('/')">/</button>
            <button class="btn" onclick="appendToDisplay('*')">*</button>
            <button class="btn" onclick="appendToDisplay('-')">-</button>
            <button class="btn" onclick="appendToDisplay('7')">7</button>
            <button class="btn" onclick="appendToDisplay('8')">8</button>
            <button class="btn" onclick="appendToDisplay('9')">9</button>
            <button class="btn" onclick="appendToDisplay('+')">+</button>
            <button class="btn" onclick="appendToDisplay('4')">4</button>
            <button class="btn" onclick="appendToDisplay('5')">5</button>
            <button class="btn" onclick="appendToDisplay('6')">6</button>
            <button class="btn" onclick="calculate()">=</button>
            <button class="btn" onclick="appendToDisplay('1')">1</button>
            <button class="btn" onclick="appendToDisplay('2')">2</button>
            <button class="btn" onclick="appendToDisplay('3')">3</button>
            <button class="btn" onclick="appendToDisplay('0')">0</button>
            <button class="btn" onclick="appendToDisplay('.')">.</button>
        </div>
    </div>
    <script>
        const display = document.getElementById('display');

        // Adiciona texto ao visor
        function appendToDisplay(value) {
            if (display.innerText === "0") {
                display.innerText = value;
            } else {
                display.innerText += value;
            }
        }

        // Limpa o visor
        function clearDisplay() {
            display.innerText = "0";
        }

        // Realiza o cálculo
        function calculate() {
            try {
                display.innerText = eval(display.innerText);
            } catch (error) {
                display.innerText = "Erro";
            }
        }
    </script>
</body>
</html>
