<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Mini Quiz Game</title>

<style>
body {
  font-family: Arial;
  text-align: center;
  background: #f4f6ff;
  padding: 40px;
}

.card {
  background: white;
  padding: 20px;
  margin: auto;
  width: 300px;
  border-radius: 15px;
  box-shadow: 0 4px 10px rgba(0,0,0,0.1);
}

button {
  padding: 10px 20px;
  margin-top: 10px;
  border: none;
  border-radius: 10px;
  cursor: pointer;
  background: #4a6cf7;
  color: white;
}

input {
  padding: 10px;
  width: 80%;
  margin-top: 10px;
}

.score {
  font-size: 20px;
  margin-top: 20px;
}
</style>
</head>

<body>

<h1>🎮 Mini Gimkit Style Quiz</h1>

<div class="card">

  <div id="question">Press Start!</div>

  <input id="answer" placeholder="Type answer here">

  <br>

  <button onclick="checkAnswer()">Submit</button>
  <button onclick="nextQuestion()">Next</button>

  <div class="score">Score: <span id="score">0</span></div>

</div>

<script>
let score = 0;

let questions = [
  {q: "What is 2 + 2?", a: "4"},
  {q: "What is capital of USA?", a: "washington"},
  {q: "What color is the sky?", a: "blue"},
  {q: "What is 5 x 3?", a: "15"},
  {q: "What planet do we live on?", a: "earth"}
];

let current = 0;

document.getElementById("question").innerText = questions[current].q;

function checkAnswer() {
  let user = document.getElementById("answer").value.toLowerCase();
  let correct = questions[current].a.toLowerCase();

  if (user === correct) {
    score += 10;
    alert("Correct! +10 points 🎉");
  } else {
    alert("Wrong 😅 Answer: " + correct);
  }

  document.getElementById("score").innerText = score;
}

function nextQuestion() {
  current++;

  if (current >= questions.length) {
    current = 0;
    alert("Game finished! Restarting 🔁");
  }

  document.getElementById("question").innerText = questions[current].q;
  document.getElementById("answer").value = "";
}
</script>

</body>
</html>
