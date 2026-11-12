# The-world-king
The world king gaming website 

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>THE WORLD KING</title>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  background: #0b0914;
  color: white;
  font-family: Arial, sans-serif;
}

header {
  background: #171027;
  padding: 20px;
  text-align: center;
  border-bottom: 2px solid gold;
}

header h1 {
  color: gold;
  font-size: 27px;
}

nav {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  gap: 18px;
  padding: 15px;
  background: #211735;
}

nav a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}

.hero {
  text-align: center;
  padding: 65px 15px;
  background: linear-gradient(135deg,#30145c,#101020,#6a390c);
}

.hero h2 {
  color: gold;
  font-size: 34px;
  margin-bottom: 12px;
}

.hero p {
  margin-bottom: 20px;
}

button {
  background: linear-gradient(90deg,#d49a24,#ffe08a);
  border: none;
  border-radius: 8px;
  padding: 11px 17px;
  font-weight: bold;
  cursor: pointer;
  color: #171027;
}

section {
  padding: 30px 15px;
  max-width: 1000px;
  margin: auto;
}

h2.section-title {
  color: gold;
  margin-bottom: 20px;
  text-align: center;
}

.grid {
  display: grid;
  grid-template-columns: repeat(auto-fit,minmax(145px,1fr));
  gap: 15px;
}

.card {
  background: #1c1730;
  border: 1px solid #72522c;
  border-radius: 12px;
  padding: 18px;
  text-align: center;
}

.game-icon {
  font-size: 42px;
  margin-bottom: 10px;
}

.card h3 {
  color: #f4ce70;
  margin-bottom: 12px;
}

.game-area {
  margin-top: 12px;
  color: white;
}

.game-area input {
  width: 100%;
  padding: 10px;
  border-radius: 6px;
  margin: 10px 0;
}

.game-area button {
  margin: 4px;
}

.result {
  color: #ffe08a;
  margin-top: 10px;
  min-height: 25px;
}

.product {
  background: #211735;
  padding: 20px;
  border-radius: 12px;
  text-align: center;
  border: 1px solid #72522c;
}

.product-photo {
  height: 110px;
  display: grid;
  place-items: center;
  font-size: 50px;
  background: linear-gradient(135deg,#43216b,#171027);
  border-radius: 10px;
  margin-bottom: 12px;
}

footer {
  text-align: center;
  background: #171027;
  padding: 25px;
  color: #d4c7e8;
}

#admin {
  display: none;
}

</style>
</head>

<body>

<header>
  <h1>👑 THE WORLD KING</h1>
  <p>Your World. Your Rules.</p>
</header>

<nav>
  <a href="#home">Home</a>
  <a href="#games">Games</a>
  <a href="#products">Products</a>
  <a href="#admin">Admin</a>
</nav>

<div class="hero" id="home">
  <h2>WELCOME KING 👑</h2>
  <p>Enter The World Of Online Gaming</p>
  <a href="#games">
    <button>PLAY GAMES 🎮</button>
  </a>
</div>

<section id="games">
  <h2 class="section-title">🎮 ONLINE GAMES</h2>

  <div class="grid">

    <div class="card">
      <div class="game-icon">⭕</div>
      <h3>Tic Tac Toe</h3>
      <div id="board" class="game-area">
        <p id="turn">Your turn: X</p>
        <div class="grid" id="cells"></div>
        <p class="result" id="ticResult"></p>
        <button onclick="resetTic()">Restart</button>
      </div>
    </div>

    <div class="card">
      <div class="game-icon">✊</div>
      <h3>Rock Paper Scissors</h3>
      <div class="game-area">
        <button onclick="play('Rock')">✊</button>
        <button onclick="play('Paper')">✋</button>
        <button onclick="play('Scissors')">✌️</button>
        <p class="result" id="rpsResult"></p>
      </div>
    </div>

    <div class="card">
      <div class="game-icon">🔢</div>
      <h3>Number Guess</h3>
      <div class="game-area">
        <p>Guess a number from 1 to 10</p>
        <input id="guess" type="number" min="1" max="10"
        placeholder="Enter number">
        <button onclick="guessNumber()">Guess</button>
        <p class="result" id="guessResult"></p>
        <button onclick="newNumber()">New Game</button>
      </div>
    </div>

  </div>
</section>

<section>
  <h2 class="section-title">🏆 GAME CATEGORIES</h2>
  <div class="grid">
    <div class="card">🏎️<h3>Racing</h3></div>
    <div class="card">🧩<h3>Puzzle</h3></div>
    <div class="card">⚔️<h3>Action</h3></div>
    <div class="card">⚽<h3>Sports</h3></div>
    <div class="card">🕹️<h3>Arcade</h3></div>
    <div class="card">🧠<h3>Brain Games</h3></div>
  </div>
</section>

<section id="products">
  <h2 class="section-title">🛍️ MY PRODUCTS</h2>
  <div class="grid" id="productList">

    <div class="product">
      <div class="product-photo">🎮</div>
      <h3>Gaming Product</h3>
      <p>Coming Soon</p>
      <button onclick="orderProduct('Gaming Product')">
        ORDER NOW
      </button>
    </div>

    <div class="product">
      <div class="product-photo">👑</div>
      <h3>Special Collection</h3>
      <p>Coming Soon</p>
      <button onclick="orderProduct('Special Collection')">
        ORDER NOW
      </button>
    </div>

  </div>
</section>

<section id="admin">
  <h2 class="section-title">⚙️ ADMIN PANEL</h2>
  <div class="card">
    <p>This is a local demo admin panel.</p>
    <input id="newProduct" placeholder="New product name">
    <button onclick="addProduct()">ADD PRODUCT</button>
    <p class="result" id="adminResult"></p>
  </div>
</section>

<footer>
  <h3>👑 THE WORLD KING</h3>
  <p>Made with passion.</p>
  <p>© 2026 THE WORLD KING</p>
</footer>

<script>

// Tic Tac Toe
let cells = [];
let player = "X";
let finished = false;

function resetTic() {
  cells = Array(9).fill("");
  player = "X";
  finished = false;
  document.getElementById("ticResult").textContent = "";
  drawBoard();
}

function drawBoard() {
  const board = document.getElementById("cells");
  board.innerHTML = "";

  cells.forEach((value, i) => {
    let btn = document.createElement("button");
    btn.textContent = value || " ";
    btn.style.width = "100%";
    btn.style.height = "42px";
    btn.onclick = () => move(i);
    board.appendChild(btn);
  });

  document.getElementById("turn").textContent =
    "Your turn: " + player;
}

function move(i) {
  if (cells[i] || finished) return;

  cells[i] = player;

  const wins = [
    [0,1,2],[3,4,5],[6,7,8],
    [0,3,6],[1,4,7],[2,5,8],
    [0,4,8],[2,4,6]
  ];

  drawBoard();

  if (wins.some(line => line.every(n => cells[n] === player))) {
    document.getElementById("ticResult").textContent =
      player + " WINS!";
    finished = true;
  } else if (cells.every(Boolean)) {
    document.getElementById("ticResult").textContent =
      "DRAW!";
    finished = true;
  } else {
    player = player === "X" ? "O" : "X";
    document.getElementById("turn").textContent =
      "Your turn: " + player;
  }
}

resetTic();

// Rock Paper Scissors
function play(user) {
  const choices = ["Rock","Paper","Scissors"];
  const computer = choices[Math.floor(Math.random()*3)];

  let result = user === computer ? "DRAW!" :
    (user === "Rock" && computer === "Scissors") ||
    (user === "Paper" && computer === "Rock") ||
    (user === "Scissors" && computer === "Paper")
    ? "YOU WIN!" : "COMPUTER WINS!";

  document.getElementById("rpsResult").textContent =
    "You: " + user + " | Computer: " +
    computer + " | " + result;
}

// Number Guess
let secret = Math.floor(Math.random()*10)+1;

function guessNumber() {
  const value = Number(document.getElementById("guess").value);

  if (!Number.isInteger(value) || value < 1 || value > 10) {
    document.getElementById("guessResult").textContent =
      "Enter a number from 1 to 10.";
  } else if (value === secret) {
    document.getElementById("guessResult").textContent =
      "🎉 CORRECT! YOU WIN!";
  } else {
    document.getElementById("guessResult").textContent =
      value < secret ? "Try a higher number!" : "Try a lower number!";
  }
}

function newNumber() {
  secret = Math.floor(Math.random()*10)+1;
  document.getElementById("guess").value = "";
  document.getElementById("guessResult").textContent =
    "New game started!";
}

// Product order demo
function orderProduct(name) {
  alert("You selected: " + name +
    ". Contact the website owner to order.");
}

// Demo admin panel
function addProduct() {
  const name = document.getElementById("newProduct").value.trim();

  if (!name) {
    document.getElementById("adminResult").textContent =
      "Enter a product name.";
    return;
  }

  const item = document.createElement("div");
  item.className = "product";
  item.innerHTML = "<div class='product-photo'>🎁</div>";

  const title = document.createElement("h3");
  title.textContent = name;
  item.appendChild(title);

  document.getElementById("productList").appendChild(item);

  document.getElementById("adminResult").textContent =
    "Product added in this session!";
  document.getElementById("newProduct").value = "";
}

// Simple admin navigation
document.querySelector('a[href="#admin"]').onclick = function() {
  document.getElementById("admin").style.display = "block";
};

</script>

</body>
</html>
