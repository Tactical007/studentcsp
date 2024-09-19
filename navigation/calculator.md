---
layout: page
title: Calculator
permalink: /calculator/
---

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
            margin: 0;
        }
        .calculator-container {
            max-width: 300px;
            margin: 0 auto;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
            background-color: #f4f4f4;
            padding: 20px;
        }
        .calculator-screen {
            width: 100%;
            height: 40px;
            text-align: right;
            padding: 10px;
            font-size: 1.2rem;
            margin-bottom: 10px;
            border: none;
            background-color: #fff;
        }
        .calculator-keys {
            display: grid;
            grid-template-columns: repeat(4, 1fr);
            gap: 10px;
        }
        button {
            padding: 15px;
            font-size: 1.2rem;
            border: none;
            cursor: pointer;
            outline: none;
        }
        button.operator {
            background-color: #ff9500;
            color: white;
        }
        button.equal-sign {
            background-color: #4caf50;
            color: white;
            grid-column: span 2;
        }
        button.all-clear {
            background-color: #d9534f;
            color: white;
            grid-column: span 2;
        }
        button:hover {
            background-color: #ccc;
        }
    </style>
</head>
<body>
    <div class="calculator-container">
        <input type="text" id="screen" class="calculator-screen" disabled />
        <div class="calculator-keys">
            <button onclick="appendValue('7')">7</button>
            <button onclick="appendValue('8')">8</button>
            <button onclick="appendValue('9')">9</button>
            <button class="operator" onclick="setOperator('+')">+</button>

            <button onclick="appendValue('4')">4</button>
            <button onclick="appendValue('5')">5</button>
            <button onclick="appendValue('6')">6</button>
            <button class="operator" onclick="setOperator('-')">-</button>

            <button onclick="appendValue('1')">1</button>
            <button onclick="appendValue('2')">2</button>
            <button onclick="appendValue('3')">3</button>
            <button class="operator" onclick="setOperator('*')">×</button>

            <button onclick="appendValue('0')">0</button>
            <button onclick="appendValue('.')">.</button>
            <button class="equal-sign" onclick="calculate()">=</button>
            <button class="operator" onclick="setOperator('/')">÷</button>

            <button class="operator" onclick="calculateSquareRoot()">√</button>
            <button class="operator" onclick="setExponent()">^</button>
            <button class="all-clear" onclick="clearScreen()">AC</button>
        </div>
    </div>

    <script>
        let currentInput = '';
        let operator = null;
        let firstOperand = null;
        let exponent = null;

        function appendValue(value) {
            currentInput += value;
            document.getElementById('screen').value = currentInput;
        }

        function setOperator(op) {
            if (currentInput !== '') {
                firstOperand = parseFloat(currentInput);
                operator = op;
                currentInput = '';
            }
        }

        function setExponent() {
            if (currentInput !== '') {
                firstOperand = parseFloat(currentInput);
                operator = '^';
                currentInput = '';
            }
        }

        function calculate() {
            if (operator && firstOperand !== null) {
                let result;
                switch (operator) {
                    case '+':
                    case '-':
                    case '*':
                    case '/':
                        result = eval(firstOperand + operator + parseFloat(currentInput));
                        break;
                    case '^':
                        result = Math.pow(firstOperand, parseFloat(currentInput));
                        break;
                }
                document.getElementById('screen').value = result;
                currentInput = result;
                operator = null;
                firstOperand = null;
            }
        }

        function calculateSquareRoot() {
            if (currentInput !== '') {
                currentInput = Math.sqrt(parseFloat(currentInput)).toString();
                document.getElementById('screen').value = currentInput;
            }
        }

        function clearScreen() {
            currentInput = '';
            operator = null;
            firstOperand = null;
            document.getElementById('screen').value = '';
        }
    </script>
</body>
</html>

<script src="https://utteranc.es/client.js"
        repo="studentcsp"
        issue-term="title"
        label="blogpost-comment"
        theme="github-light"
        crossorigin="anonymous"
        async>
</script>