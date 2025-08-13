<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>تحليل أنماط اللعبة</title>
    <style>
        body {
            background-color: #121212;
            color: #ffffff;
            font-family: Arial, sans-serif;
            text-align: center;
            padding: 20px;
        }
        h1 {
            color: #00e676;
        }
        textarea {
            width: 90%;
            height: 150px;
            margin: 10px 0;
            background-color: #1e1e1e;
            color: #fff;
            border: none;
            padding: 10px;
            font-size: 16px;
        }
        button {
            background-color: #00e676;
            color: #000;
            border: none;
            padding: 10px 20px;
            font-size: 16px;
            cursor: pointer;
            margin: 10px;
            border-radius: 5px;
        }
        .result {
            margin-top: 20px;
            font-size: 18px;
            background-color: #1e1e1e;
            padding: 10px;
            border-radius: 5px;
        }
    </style>
</head>
<body>

    <h1>📊 أداة تحليل الأنماط</h1>
    <p>أدخل النتائج السابقة (كل رقم في سطر جديد):</p>
    <textarea id="inputData" placeholder="مثال:
1.25
3.50
2.10
..."></textarea><br>
    <button onclick="analyze()">تحليل</button>

    <div class="result" id="output">💡 النتيجة ستظهر هنا</div>

    <script>
        function analyze() {
            let input = document.getElementById("inputData").value.trim().split("\n").map(Number);
            if (input.length < 5) {
                document.getElementById("output").innerHTML = "⚠️ أدخل على الأقل 5 قيم.";
                return;
            }

            let avg = input.reduce((a, b) => a + b, 0) / input.length;
            let last = input[input.length - 1];
            let prediction = "";

            if (last < avg) {
                prediction = "🔼 التوقع: أعلى من المتوسط";
            } else {
                prediction = "🔽 التوقع: أقل من المتوسط";
            }

            document.getElementById("output").innerHTML = 
                `📈 المتوسط: ${avg.toFixed(2)}<br>${prediction}`;
        }
    </script>

</body>
</html>
