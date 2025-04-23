# discount-calculatorrrr
<!DOCTYPE html>
<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Калькулятор скидок</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 500px;
      margin: 50px auto;
      padding: 20px;
      background: #f7f7f7;
      border-radius: 10px;
      box-shadow: 0 0 10px rgba(0,0,0,0.1);
    }
    h2 {
      text-align: center;
    }
    label {
      display: block;
      margin-top: 15px;
    }
    input {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      box-sizing: border-box;
    }
    button {
      margin-top: 20px;
      padding: 10px;
      width: 100%;
      background-color: #4CAF50;
      color: white;
      border: none;
      cursor: pointer;
      font-size: 16px;
      border-radius: 5px;
    }
    #result {
      margin-top: 20px;
      font-size: 18px;
      font-weight: bold;
      text-align: center;
    }
  </style>
</head>
<body>

  <h2>Калькулятор скидок</h2>
  <label>Цена товара (₽):
    <input type="number" id="price" placeholder="Введите цену">
  </label>
  <label>Скидка (%):
    <input type="number" id="discount" placeholder="Введите скидку">
  </label>
  <button onclick="calculateDiscount()">Рассчитать</button>

  <div id="result"></div>

  <script>
    function calculateDiscount() {
      const price = parseFloat(document.getElementById('price').value);
      const discount = parseFloat(document.getElementById('discount').value);

      if (isNaN(price) || isNaN(discount)) {
        document.getElementById('result').textContent = 'Введите корректные значения.';
        return;
      }

      const discountedPrice = price * (1 - discount / 100);
      const saved = price - discountedPrice;

      document.getElementById('result').textContent =
        `Цена со скидкой: ${discountedPrice.toFixed(2)} ₽ (вы сэкономили ${saved.toFixed(2)} ₽)`;
    }
  </script>

</body>
</html>
