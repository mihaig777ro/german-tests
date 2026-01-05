# german-tests
german-tests/
│
├── index.html
<!DOCTYPE html>
<html lang="de">
<head>
    <meta charset="UTF-8">
    <title>Deutsch Test – Grammatik</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<h1>Deutsch Test – Grammatik</h1>

<section>
<h2>Theorie</h2>
<p>Das Perfekt wird mit <b>haben</b> oder <b>sein</b> gebildet.</p>
</section>

<form id="quiz">

<h3>1. Multiple Choice</h3>
<p>Ich ___ nach Hause gegangen.</p>
<label><input type="radio" name="q1" value="bin"> bin</label><br>
<label><input type="radio" name="q1" value="habe"> habe</label><br>

<h3>2. Lückentext</h3>
<p>Er hat das Buch ___.</p>
<input type="text" id="q2">

<h3>3. Fehler korrigieren</h3>
<p>Sie hat gegangen.</p>
<input type="text" id="q3" placeholder="Corectează propoziția">

<br><br>
<button type="button" onclick="checkAnswers()">Testează</button>
</form>

<p id="result"></p>

<script src="script.js"></script>
</body>
</html>

├── style.css
body {
    font-family: Arial;
    padding: 20px;
    background: #f4f4f4;
}

h1 {
    color: darkblue;
}

section {
    background: white;
    padding: 15px;
    margin-bottom: 20px;
}

button {
    padding: 10px;
    background: green;
    color: white;
    border: none;
    cursor: pointer;
}

└── script.js
function checkAnswers() {
    let score = 0;

    // Grilă
    const q1 = document.querySelector('input[name="q1"]:checked');
    if (q1 && q1.value === "bin") score++;

    // Completare spațiu
    const q2 = document.getElementById("q2").value.trim().toLowerCase();
    if (q2 === "gelesen") score++;

    // Corectare greșeală
    const q3 = document.getElementById("q3").value.trim().toLowerCase();
    if (q3 === "sie ist gegangen") score++;

    document.getElementById("result").innerHTML =
        "Punktzahl: " + score + " / 3";
}

