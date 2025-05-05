<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Mobile Calculator</title>
  <style>
    body {
      margin: 0;
      background: #000;
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: flex-start;
      height: 100vh;
      padding: 20px;
      color: white;
    }

    #display {
      width: 100%;
      text-align: right;
      font-size: 2.5em;
      padding: 20px;
      box-sizing: border-box;
      border: none;
      background: black;
      color: white;
    }

    .calculator {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 10px;
      width: 100%;
      max-width: 400px;
    }

    button {
      font-size: 1.5em;
      border: none;
      border-radius: 50%;
      padding: 20px;
      background-color: #333;
      color: white;
      transition: 0.2s;
    }

    button:active {
      background-color: #444;
    }

    .orange {
      background-color: orange;
      color: white;
    }

    .wide {
      border-radius: 40px;
      grid-column: span 2;
    }
  </style>
</head>
<body>
  <input type="text" id="display" readonly />
  <div class="calculator">
    <button onclick="clearDisplay()">AC</button>
    <button onclick="append('%')">%</button>
    <button onclick="backspace()">⌫</button>
    <button onclick="append('/')">÷</button>

    <button onclick="append('7')">7</button>
    <button onclick="append('8')">8</button>
    <button onclick="append('9')">9</button>
    <button onclick="append('*')">×</button>

    <button onclick="append('4')">4</button>
    <button onclick="append('5')">5</button>
    <button onclick="append('6')">6</button>
    <button onclick="append('-')">−</button>

    <button onclick="append('1')">1</button>
    <button onclick="append('2')">2</button>
    <button onclick="append('3')">3</button>
    <button onclick="append('+')">+</button>

    <button onclick="append('00')">00</button>
    <button onclick="append('0')">0</button>
    <button onclick="append('.')">.</button>
    <button class="orange" onclick="calculate()">=</button>
  </div>

  <script>
    const display = document.getElementById('display');

    function append(char) {
      display.value += char;
    }

    function clearDisplay() {
      display.value = '';
    }

    function backspace() {
      display.value = display.value.slice(0, -1);
    }

    function calculate() {
      try {
        display.value = eval(display.value);
      } catch {
        display.value = 'Error';
      }
    }
  </script>
</body>
</html>
