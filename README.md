<!DOCTYPE html>
<html lang="pt-br">
<head>
  <meta charset="UTF-8">
  <title>Calculadora Simples</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f4f4f4;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
    }
    .calculadora {
      background: #fff;
      padding: 20px;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.2);
    }
    input[type="text"] {
      width: 100%;
      font-size: 24px;
      text-align: right;
      margin-bottom: 10px;
      padding: 10px;
    }
    .botoes {
      display: grid;
      grid-template-columns: repeat(4, 60px);
      gap: 10px;
    }
    button {
      font-size: 20px;
      padding: 10px;
      cursor: pointer;
    }
  </style>
</head>
<body>
  <div class="calculadora">
    <input type="text" id="display" disabled>
    <div class="botoes">
      <button onclick="limpar()">C</button>
      <button onclick="adicionar('/')">/</button>
      <button onclick="adicionar('*')">*</button>
      <button onclick="adicionar('-')">-</button>

      <button onclick="adicionar('7')">7</button>
      <button onclick="adicionar('8')">8</button>
      <button onclick="adicionar('9')">9</button>
      <button onclick="adicionar('+')">+</button>

      <button onclick="adicionar('4')">4</button>
      <button onclick="adicionar('5')">5</button>
      <button onclick="adicionar('6')">6</button>
      <button onclick="calcular()">=</button>

      <button onclick="adicionar('1')">1</button>
      <button onclick="adicionar('2')">2</button>
      <button onclick="adicionar('3')">3</button>
      <button onclick="adicionar('.')">.</button>

      <button onclick="adicionar('0')" style="grid-column: span 2;">0</button>
    </div>
  </div>

  <script>
    function adicionar(valor) {
      document.getElementById('display').value += valor;
    }

    function limpar() {
      document.getElementById('display').value = '';
    }

    function calcular() {
      try {
        const resultado = eval(document.getElementById('display').value);
        document.getElementById('display').value = resultado;
      } catch (e) {
        document.getElementById('display').value = 'Erro';
      }
    }
  </script>
</body>
</html>
