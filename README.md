# Bmi-calculator-
This is My first project about BMI calculator 
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BMI Calculator</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }

        .calculator {
            width: 300px;
            margin: 50px auto;
            padding: 20px;
            background-color: #fff;
            border: 1px solid #ddd;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        label {
            display: block;
            margin-bottom: 10px;
        }

        input[type="number"] {
            width: 100%;
            height: 40px;
            margin-bottom: 20px;
            padding: 10px;
            border: 1px solid #ccc;
        }

        button {
            width: 100%;
            height: 40px;
            background-color: #4CAF50;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
        }

        button:hover {
            background-color: #3e8e41;
        }

        #result {
            margin-top: 20px;
            font-size: 24px;
            font-weight: bold;
        }
    </style>
</head>
<body>
    <div class="calculator">
        <h1>BMI Calculator</h1>
        <label for="weight">Weight (kg):</label>
        <input type="number" id="weight" required>
        <label for="height">Height (cm):</label>
        <input type="number" id="height" required>
        <button id="calculate">Calculate BMI</button>
        <p id="result"></p>
    </div>
    <script>
        document.getElementById('calculate').addEventListener('click', () => {
            const weight = parseFloat(document.getElementById('weight').value);
            const height = parseFloat(document.getElementById('height').value);
            const bmi = weight / ((height / 100) ** 2);
            const resultElement = document.getElementById('result');
            if (isNaN(bmi)) {
                resultElement.textContent = 'Please enter valid values';
            } else {
                resultElement.textContent = `Your BMI is: ${bmi.toFixed(2)}`;
                if (bmi < 18.5) {
                    resultElement.textContent += ' (Underweight)';
                } else if (bmi < 25) {
                    resultElement.textContent += ' (Normal)';
                } else if (bmi < 30) {
                    resultElement.textContent += ' (Overweight)';
                } else {
                    resultElement.textContent += ' (Obese)';
                }
            }
        });
    </script>
</body>
</html>
