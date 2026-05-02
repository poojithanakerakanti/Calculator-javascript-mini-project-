<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Stylish Calculator</title>

<style>
body {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;

    /* 🔥 Gradient Background */
    background: linear-gradient(135deg, #667eea, #764ba2);

    font-family: Arial;
}

.calculator {
    /* Glass effect */
    background: rgba(255, 255, 255, 0.1);
    backdrop-filter: blur(10px);
    padding: 20px;
    border-radius: 15px;
    width: 260px;
    box-shadow: 0 8px 30px rgba(0,0,0,0.2);
}

#display {
    width: 100%;
    height: 50px;
    margin-bottom: 15px;
    font-size: 22px;
    text-align: right;
    padding: 10px;
    border: none;
    border-radius: 8px;
}

.buttons {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 10px;
}

button {
    padding: 15px;
    font-size: 18px;
    border: none;
    border-radius: 8px;
    cursor: pointer;
    transition: 0.2s;
}

button:hover {
    transform: scale(1.05);
}

/* Button Colors */
.operator {
    background: #ff9f43;
    color: white;
}

.equal {
    background: #28c76f;
    color: white;
    grid-column: span 2;
}

.clear {
    background: #ea5455;
    color: white;
}

button:not(.operator):not(.equal):not(.clear) {
    background: white;
}
</style>

</head>
<body>

<div class="calculator">
    <input type="text" id="display" disabled>

    <div class="buttons">
        <button onclick="clearDisplay()" class="clear">C</button>
        <button onclick="appendValue('/')">/</button>
        <button onclick="appendValue('*')">*</button>
        <button onclick="appendValue('-')">-</button>

        <button onclick="appendValue('7')">7</button>
        <button onclick="appendValue('8')">8</button>
        <button onclick="appendValue('9')">9</button>
        <button onclick="appendValue('+')" class="operator">+</button>

        <button onclick="appendValue('4')">4</button>
        <button onclick="appendValue('5')">5</button>
        <button onclick="appendValue('6')">6</button>
        <button onclick="calculate()" class="equal">=</button>

        <button onclick="appendValue('1')">1</button>
        <button onclick="appendValue('2')">2</button>
        <button onclick="appendValue('3')">3</button>
        <button onclick="appendValue('0')">0</button>
    </div>
</div>

<script>
function appendValue(value) {
    document.getElementById("display").value += value;
}

function clearDisplay() {
    document.getElementById("display").value = "";
}

function calculate() {
    try {
        let result = eval(document.getElementById("display").value);
        document.getElementById("display").value = result;
    } catch {
        alert("Invalid Expression");
    }
}
</script>

</body>
</html>
