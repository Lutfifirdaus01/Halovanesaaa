<!DOCTYPE html>

<html lang="en">

<head>

    <meta charset="UTF-8">

    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <title>iPhone Calculator</title>

    <style>

        body {

            display: flex;

            justify-content: center;

            align-items: center;

            height: 100vh;

            margin: 0;

            background-color: #f0f0f0;

            font-family: Arial, sans-serif;

        }

        .calculator {

            background-color: #000;

            border-radius: 40px;

            padding: 20px;

            width: 300px;

        }

        .screen {

            background-color: #333;

            color: #fff;

            font-size: 35px;

            text-align: right;

            padding: 10px;

            margin-bottom: 10px;

            border-radius: 10px;

        }

        .buttons {

            display: grid;

            grid-template-columns: repeat(4, 1fr);

            gap: 10px;

        }

        button {

            background-color: #333;

            color: #fff;

            border: none;

            font-size: 24px;

            padding: 20px;

            border-radius: 50%;

            cursor: pointer;

        }

        button.operator {

            background-color: #ff9500;

        }

        button.equal {

            background-color: #ff9500;

        }

    </style>

</head>

<body>

    <div class="calculator">

        <div class="screen" id="screen">0</div>

        <div class="buttons">

            <button onclick="clearScreen()">C</button>

            <button onclick="appendToScreen('+/-')">+/-</button>

            <button onclick="appendToScreen('%')">%</button>

            <button class="operator" onclick="appendToScreen('/')">/</button>

            <button onclick="appendToScreen('7')">7</button>

            <button onclick="appendToScreen('8')">8</button>

            <button onclick="appendToScreen('9')">9</button>

            <button class="operator" onclick="appendToScreen('*')">×</button>

            <button onclick="appendToScreen('4')">4</button>

            <button onclick="appendToScreen('5')">5</button>

            <button onclick="appendToScreen('6')">6</button>

            <button class="operator" onclick="appendToScreen('-')">-</button>

            <button onclick="appendToScreen('1')">1</button>

            <button onclick="appendToScreen('2')">2</button>

            <button onclick="appendToScreen('3')">3</button>

            <button class="operator" onclick="appendToScreen('+')">+</button>

            <button onclick="appendToScreen('0')">0</button>

            <button onclick="appendToScreen('.')">.</button>

            <button class="equal" onclick="calculate()">=</button>

        </div>

    </div>



    <script>

        let screenValue = '0';



        function updateScreen() {

            document.getElementById('screen').innerText = screenValue;

        }



        function appendToScreen(value) {

            if (screenValue === '0' && value !== '.') {

                screenValue = value;

            } else {

                screenValue += value;

            }

            updateScreen();

        }



        function clearScreen() {

            screenValue = '0';

            updateScreen();

        }



        function calculate() {

            try {

                if (screenValue === '9+10') {

                    screenValue = 'HALLO VANESAAAA:))';

                } else {

                    screenValue = eval(screenValue).toString();

                }

                updateScreen();

            } catch (error) {

                screenValue = 'Error';

                updateScreen();

            }

        }

    </script>

</body>

</html>