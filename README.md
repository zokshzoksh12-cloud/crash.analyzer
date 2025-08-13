<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>أداة تحليل الأنماط</title>
<style>
    body {
        background-color: #111;
        color: #fff;
        font-family: Arial, sans-serif;
        text-align: center;
        padding: 20px;
    }
    h1 {
        color: #00bfff;
    }
    textarea {
        width: 90%;
        height: 150px;
        background-color: #222;
        color: #fff;
        border: 2px solid #00bfff;
        border-radius: 8px;
        padding: 10px;
        font-size: 16px;
    }
    button {
        background-color: #00ff88;
        color: #000;
        padding: 12px 24px;
        border: none;
        border-radius: 8px;
        font-size: 18px;
        cursor: pointer;
        margin-top: 15px;
        transition: 0.3s;
    }
    button:hover {
        background-color: #00cc6f;
    }
    .result {
        margin-top: 20px;
        padding: 15px;
        border-radius: 8px;
        background-color: #222;
        border: 2px solid #00ff88;
        font-size: 20px;
        min-height: 40px;
    }
</style>
</head>
<body>

<h1>📊 أداة تحليل الأنماط</h1>
<p>أدخل النتائج السابقة (كل رقم في سطر جديد):</p>
<textarea id="data" placeholder="مثال:
1.25
3.50
2.10"></textarea>
<br>
<button onclick="analyze()">تحليل</button>

<div class="result" id="result">💡 النتيجة ستظهر هنا</div>

<script>
function analyze() {
    let input = document.getElementById("data").value.trim();
    if (!input) {
        document.getElementById("result").innerHTML = "⚠️ من فضلك أدخل بيانات أولا";
        return;
    }
    let numbers = input.split(/\s+/).map(Number).filter(n => !isNaN(n));
    let sum = numbers.reduce((a, b) => a + b, 0);
    let avg = (sum / numbers.length).toFixed(2);
    let min = Math.min(...numbers);
    let max = Math.max(...numbers);
    
    document.getElementById("result").innerHTML = 
        `📈 المتوسط: ${avg}<br>⬆️ أعلى قيمة: ${max}<br>⬇️ أقل قيمة: ${min}`;
}
</script>

</body>
</html>
