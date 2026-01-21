<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Riddhi 🌹</title>

<style>
body {
    margin: 0;
    font-family: 'Segoe UI', sans-serif;
    background: linear-gradient(135deg, #ffdde1, #ee9ca7);
    height: 100vh;
    overflow: hidden;
}

.page {
    display: none;
    height: 100vh;
    justify-content: center;
    align-items: center;
}

.page.active {
    display: flex;
}

.card {
    background: #fff;
    padding: 28px;
    border-radius: 20px;
    width: 340px;
    text-align: center;
    box-shadow: 0 12px 30px rgba(0,0,0,0.3);
    z-index: 2;
}

h1 { color: #c2185b; }
h2 { color: #d81b60; }

p {
    color: #555;
    font-size: 15px;
    line-height: 1.6;
}

.note-big {
    font-size: 18px; /* Made bigger */
    font-weight: bold;
}

.btn {
    margin-top: 15px;
    background: #c2185b;
    color: #fff;
    padding: 12px 24px;
    border-radius: 25px;
    cursor: pointer;
    display: inline-block;
    margin: 5px; /* Added for spacing between buttons */
}

.btn.no {
    background: #888; /* Different color for NO button */
}

.rose-option {
    display: inline-block;
    margin: 10px;
    padding: 10px;
    border-radius: 10px;
    cursor: pointer;
    font-size: 24px;
}

.quiz-option {
    display: block;
    margin: 10px 0;
    padding: 10px;
    background: #f0f0f0;
    border-radius: 10px;
    cursor: pointer;
    font-size: 16px;
}

.quiz-option:hover {
    background: #e0e0e0;
}

/* Falling items */
.fall {
    position: absolute;
    top: -40px;
    animation: fall linear infinite;
    opacity: 0.9;
}

@keyframes fall {
    0% { transform: translateY(0) rotate(0deg); }
    100% { transform: translateY(110vh) rotate(360deg); }
}

/* Fireworks */
.firework {
    position: absolute;
    width: 6px;
    height: 6px;
    background: red;
    border-radius: 50%;
    animation: explode 1s ease-out forwards;
}

@keyframes explode {
    0% { transform: scale(1); opacity: 1; }
    100% { transform: scale(20); opacity: 0; }
}

img {
    width: 100%;
    border-radius: 15px;
}
</style>
</head>

<body>

<!-- 🎶 Music -->
<audio id="music" loop>
    <source src="https://files.freemusicarchive.org/storage-freemusicarchive-org/music/no_curator/Komiku/Love/Komiku_-_12_-_Tenderness.mp3">
</audio>

<!-- 🌹💖 Falling Roses & Hearts -->
<script>
const items = ["🌹","💖"];
for (let i = 0; i < 40; i++) {
    const el = document.createElement("div");
    el.className = "fall";
    el.innerText = items[Math.floor(Math.random()*2)];
    el.style.left = Math.random()*100 + "vw";
    el.style.fontSize = (18 + Math.random()*20) + "px";
    el.style.animationDuration = (4 + Math.random()*6) + "s";
    document.body.appendChild(el);
}
</script>

<!-- Page 1 -->
<div class="page active" id="p1">
<div class="card">
<h1>Happy Rose Day 🌹</h1>
<h2>Dear Riddhi</h2>
<p>This is not just a rose… it’s a journey of surprises.</p>
<div class="btn" onclick="go(2)">Start 💖</div>
</div>
</div>

<!-- Page 2 -->
<div class="page" id="p2">
<div class="card">
<h1>💌 A Note</h1>
<img src="https://example.com/rose-image.jpg" alt="Beautiful Rose"> <!-- Added rose image -->
<p class="note-big">
My bachha baby,<br>
You are the reason smiles feel brighter  
and moments feel warmer.
</p>
<div class="btn" onclick="go(3)">Next 🎁</div>
</div>
</div>

<!-- Page 3 (Choose a Rose) -->
<div class="page" id="p3">
<div class="card">
<h1>🌹 Choose Your Rose</h1>
<p>Pick one that speaks to your heart!</p>
<div class="rose-option" onclick="chooseRose('Red Rose')">🌹 Red Rose</div>
<div class="rose-option" onclick="chooseRose('Pink Rose')">🌸 Pink Rose</div>
<div class="rose-option" onclick="chooseRose('White Rose')">🌷 White Rose</div>
</div>
</div>

<!-- Page 4 (Greeting Note) -->
<div class="page" id="p4">
<div class="card">
<h1>💌 A Special Greeting</h1>
<p id="greeting-text">
Dear Riddhi,<br>
Wishing you a day filled with love, joy, and beautiful roses. You are my everything! 💖
</p>
<div class="btn" onclick="go(8)">Play Quiz 🎉</div>
</div>
</div>

<!-- Page 8 (Quiz Game) -->
<div class="page" id="p8">
<div class="card">
<h1>🌹 Rose Quiz Time!</h1>
<p id="quiz-question">Question 1: What color rose symbolizes love?</p>
<div class="quiz-option" onclick="answerQuiz(0, 'Red')">Red</div>
<div class="quiz-option" onclick="answerQuiz(0, 'Blue')">Blue</div>
<div class="quiz-option" onclick="answerQuiz(0, 'Green')">Green</div>
<div class="quiz-option" onclick="answerQuiz(0, 'Yellow')">Yellow</div>
</div>
</div>

<!-- Page 5 (Surprise) -->
<div class="page" id="p5">
<div class="card">
<h1>🎆 Surprise Time</h1>
<p>Something magical is about to happen…</p>
<div class="btn" onclick="fireworks(); go(6)">Tap 🎆</div>
</div>
</div>

<!-- Page 6 (Question) -->
<div class="page" id="p6">
<div class="card">
<h1>💍 One Last Question</h1>
<p>
Riddhi,<br>
Would you like to be<br>
my forever rose? 🌹
</p>
<div class="btn" onclick="finale()">YES 💖</div>
<div class="btn no" onclick="requestYes()">NO 😢</div>
</div>
</div>

<!-- Page 7 (Final) -->
<div class="page" id="p7">
<div class="card">
<h1>Once Again, Happy Rose Day! 🌹💖</h1>
<p>Thank you for saying yes! You're my forever rose. (Returning to start in 5 seconds...)</p>
<!-- No button here; it's the end, but loops back -->
</div>
</div>

<script>
let quizScore = 0;
let currentQuestion = 0;
const questions = [
    { q: "What color rose symbolizes love?", options: ["Red", "Blue", "Green", "Yellow"], correct: "Red" },
    { q: "How many petals does a typical rose have?", options: ["5", "10", "20", "Infinite"], correct: "5" },
    { q: "What does a white rose symbolize?", options: ["Love", "Purity", "Jealousy", "Friendship"], correct: "Purity" }
];

function go(n){
    document.querySelectorAll('.page').forEach(p=>p.classList.remove('active'));
    document.getElementById('p'+n).classList.add('active');
    document.getElementById("music").play();
    
    // If reaching Page 7, auto-loop back to Page 1 after 5 seconds
    if (n === 7) {
        setTimeout(() => {
            go(1);
        }, 5000); // 5000ms = 5 seconds
    }
}

function chooseRose(roseType) {
    alert(`You chose the ${roseType}! It symbolizes love and beauty. 💖`);
    go(4); // Proceed to greeting note
}

function answerQuiz(questionIndex, selectedAnswer) {
    if (selectedAnswer === questions[questionIndex].correct) {
        quizScore++;
    }
    currentQuestion++;
    if (currentQuestion < questions.length) {
        loadQuestion(currentQuestion);
    } else {
        endQuiz();
    }
}

function loadQuestion(index) {
    const q = questions[index];
    document.getElementById('quiz-question').innerText = `Question ${index + 1}: ${q.q}`;
    const options = document.querySelectorAll('.quiz-option');
    options.forEach((opt, i) => {
        opt.innerText = q.options[i];
        opt.onclick = () => answerQuiz(index, q.options[i]);
    });
}

function endQuiz() {
    alert(`Quiz Complete! Your score: ${quizScore}/${questions.length}. Great job! 💖`);
    go(5); // Proceed to surprise
}

function fireworks(){
    for(let i=0;i<20;i++){
        const f=document.createElement("div");
        f.className="firework";
        f.style.left=Math.random()*100+"vw";
        f.style.top=Math.random()*100+"vh";
        f.style.background=["red","pink","gold"][Math.floor(Math.random()*3)];
        document.body.appendChild(f);
        setTimeout(()=>f.remove(),1000);
    }
}

function finale(){
    fireworks();
    alert("💖 She said YES! 💖\nHappy Rose Day Riddhi 🌹");
    go(7); // Go to the last page after the alert
}

function requestYes(){
    alert("Please say YES! 💖 I promise it'll be amazing.");
    // Stays on Page 6
}
</script>

</body>
</html>
