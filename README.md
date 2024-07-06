<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Счетчик кликов</title>
    <style>
        #square {
            width: 100px;
            height: 100px;
            background-color: red;
            display: flex;
            justify-content: center;
            align-items: center;
            color: white;
            font-size: 24px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div id="square">0</div>

    <script>
        // Получаем элемент квадрата
        const square = document.getElementById('square');

        // Загружаем значение счетчика из localStorage или устанавливаем 0
        let count = localStorage.getItem('clickCount') ? parseInt(localStorage.getItem('clickCount')) : 0;
        square.textContent = count;

        // Обработчик кликов по квадрату
        square.addEventListener('click', () => {
            count++;
            square.textContent = count;
            localStorage.setItem('clickCount', count); // Сохраняем значение в localStorage
        });
    </script>
</body>
</html>
