<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Daily Budget Calculator</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            line-height: 1.6;
            margin: 0;
            padding: 20px;
            background: #f0f2f5;
        }

        .container {
            max-width: 600px;
            margin: 0 auto;
            background: white;
            padding: 30px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0,0,0,0.1);
        }

        h1 {
            color: #2c3e50;
            text-align: center;
            margin-bottom: 30px;
        }

        .input-group {
            margin-bottom: 20px;
        }

        label {
            display: block;
            margin-bottom: 5px;
            color: #34495e;
            font-weight: bold;
        }

        input {
            width: 100%;
            padding: 10px;
            border: 1px solid #ddd;
            border-radius: 5px;
            font-size: 16px;
            box-sizing: border-box;
        }

        button {
            background: #3498db;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            width: 100%;
            font-size: 16px;
            transition: background 0.3s;
        }

        button:hover {
            background: #2980b9;
        }

        .result {
            margin-top: 20px;
            padding: 20px;
            background: #f8f9fa;
            border-radius: 5px;
            text-align: center;
        }

        .result h2 {
            color: #2c3e50;
            margin-bottom: 10px;
        }

        .result p {
            font-size: 24px;
            color: #27ae60;
            font-weight: bold;
            margin: 0;
        }

        @media (max-width: 480px) {
            .container {
                padding: 20px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Daily Budget Calculator</h1>
        <div class="input-group">
            <label for="income">Monthly Income (£):</label>
            <input type="number" id="income" placeholder="Enter your monthly income">
        </div>
        <div class="input-group">
            <label for="expenses">Monthly Expenses (£):</label>
            <input type="number" id="expenses" placeholder="Enter your monthly expenses">
        </div>
        <div class="input-group">
            <label for="savings">Desired Monthly Savings (£):</label>
            <input type="number" id="savings" placeholder="Enter your desired monthly savings">
        </div>
        <button onclick="calculateBudget()">Calculate Daily Budget</button>
        <div class="result">
            <h2>Your Daily Budget:</h2>
            <p id="dailyBudget">£0.00</p>
        </div>
    </div>

    <script>
        function calculateBudget() {
            // Get input values
            const income = parseFloat(document.getElementById('income').value) || 0;
            const expenses = parseFloat(document.getElementById('expenses').value) || 0;
            const savings = parseFloat(document.getElementById('savings').value) || 0;

            // Calculate daily budget
            const monthlyBudget = income - expenses - savings;
            const dailyBudget = monthlyBudget / 30; // Using 30 days for simplicity

            // Display result with 2 decimal places
            document.getElementById('dailyBudget').textContent = 
                `£${Math.max(0, dailyBudget).toFixed(2)}`;
        }
    </script>
</body>
</html>
