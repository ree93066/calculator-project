# calculator-project
This is a calculator project
<br>
by Reena
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Calculator</title>

<style>
  body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    background: #a244e0c3;
    font-family: Arial;
  }

  .calculator {
    background: #435246;
    padding: 20px;
    border-radius: 10px;
    width: 280px;
    box-shadow: 10px 10px 15px  #0a0a0a;
    outline: auto;
  }

  #display {
    width: 96%;
    height: 40px;
    font-size: 24px;
    text-align: right;
    margin-bottom:15px;
    padding: 5px;
    border-radius: 10px;
    background-color: #eae7ea;
    
  }

  .buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
  }

  button {
    padding: 10px;
    font-size: 18px;
    border: none;
    border-radius: 5px;
    cursor: pointer;
  }

  button:hover {
    background: #56d064;
  }

  .zero {
    grid-column: span 2;
  }
</style>
</head>

<body>

<div class="calculator">
  <input type="text" id="display" disabled>

  <div class="buttons">
    <button onclick="clearDisplay()">C</button>
    <button onclick="deleteLast()">DEL</button>
    <button onclick="appendValue('%')">%</button>
    <button onclick="appendValue('/')">/</button>

    <button onclick="appendValue('7')">7</button>
    <button onclick="appendValue('8')">8</button>
    <button onclick="appendValue('9')">9</button>
    <button onclick="appendValue('*')">*</button>

    <button onclick="appendValue('4')">4</button>
    <button onclick="appendValue('5')">5</button>
    <button onclick="appendValue('6')">6</button>
    <button onclick="appendValue('-')">-</button>

    <button onclick="appendValue('1')">1</button>
    <button onclick="appendValue('2')">2</button>
    <button onclick="appendValue('3')">3</button>
    <button onclick="appendValue('+')">+</button>

    <button onclick="appendValue('0')" class="zero">0</button>
    <button onclick="appendValue('.')">.</button>
    <button onclick="calculate()">=</button>
  </div>
</div>

<script>
  let display = document.getElementById("display");

  function appendValue(value) {
    display.value += value;
  }

  function clearDisplay() {
    display.value = "";
  }

  function deleteLast() {
    display.value = display.value.slice(0, -1);
  }

  function calculate() {
    try {
      display.value = eval(display.value);
    } catch {
      display.value = "Error";
    }
  }
</script>

</body>
</html>
