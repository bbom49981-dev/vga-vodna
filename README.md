# vga-vodna

<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>VGA Vodna | Game Top Up</title>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  background: #090b12;
  color: white;
  font-family: Arial, sans-serif;
}

header {
  background: #111522;
  padding: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  border-bottom: 1px solid #242a3a;
}

.logo {
  color: #00e5ff;
  font-size: 23px;
  font-weight: bold;
}

nav a {
  color: white;
  text-decoration: none;
  margin-left: 12px;
  font-size: 13px;
}

.hero {
  text-align: center;
  padding: 55px 15px;
  background: linear-gradient(135deg,#101d35,#090b12);
}

.hero h1 {
  font-size: 35px;
  color: #00e5ff;
  margin-bottom: 12px;
}

.hero p {
  color: #b8c2d5;
}

.container {
  max-width: 950px;
  margin: auto;
  padding: 25px 15px;
}

.heading {
  font-size: 23px;
  margin-bottom: 20px;
}

.games {
  display: grid;
  grid-template-columns: repeat(2,1fr);
  gap: 15px;
}

.game {
  background: #151b2a;
  padding: 22px 10px;
  border: 1px solid #29354b;
  border-radius: 13px;
  text-align: center;
  cursor: pointer;
  transition: .2s;
}

.game:hover, .game.active {
  border-color: #00e5ff;
  background: #19283a;
}

.game .emoji {
  font-size: 35px;
  margin-bottom: 10px;
}

.game h3 {
  font-size: 15px;
}

.panel {
  background: #151b2a;
  padding: 22px;
  margin-top: 25px;
  border-radius: 13px;
  border: 1px solid #29354b;
}

input {
  width: 100%;
  padding: 14px;
  margin-top: 12px;
  background: #090e19;
  border: 1px solid #34415a;
  border-radius: 8px;
  color: white;
  outline: none;
}

button {
  background: #00cce8;
  color: #06121b;
  border: none;
  padding: 13px;
  border-radius: 8px;
  width: 100%;
  margin-top: 15px;
  font-size: 15px;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  background: #00aeca;
}

footer {
  text-align: center;
  padding: 25px;
  margin-top: 30px;
  background: #111522;
  color: #8290a8;
  font-size: 13px;
}
</style>
</head>

<body>

<header>
  <div class="logo">VGA VODNA</div>
  <nav>
    <a href="#home">หน้าแรก</a>
    <a href="#games">เติมเกม</a>
  </nav>
</header>

<section class="hero" id="home">
  <h1>VGA VODNA</h1>
  <p>WELCOME TO VGA VODNA TOP UP</p>
  <p>เว็บไซต์เติมเกมออนไลน์ของคุณ</p>
</section>

<main class="container">

  <h2 class="heading" id="games">
    เลือกเกมที่ต้องการเติม
  </h2>

  <div class="games">

    <div class="game" onclick="selectGame('Free Fire',this)">
      <div class="emoji">🔥</div>
      <h3>Free Fire</h3>
    </div>

    <div class="game" onclick="selectGame('PUBG Mobile',this)">
      <div class="emoji">🎯</div>
      <h3>PUBG Mobile</h3>
    </div>

    <div class="game" onclick="selectGame('Mobile Legends',this)">
      <div class="emoji">⚔️</div>
      <h3>Mobile Legends</h3>
    </div>

    <div class="game" onclick="selectGame('Roblox',this)">
      <div class="emoji">🟩</div>
      <h3>Roblox</h3>
    </div>

  </div>

  <div class="panel">
    <h2>รายละเอียดการเติมเกม</h2>

    <p style="margin-top:15px;color:#00e5ff">
      เกมที่เลือก:
      <span id="selected">ยังไม่ได้เลือกเกม</span>
    </p>

    <input
      type="text"
      id="playerID"
      placeholder="กรอก ID ผู้เล่น"
    >

    <input
      type="text"
      id="package"
      placeholder="แพ็กเกจที่ต้องการ (เพิ่มภายหลัง)"
    >

    <button onclick="showMessage()">
      ส่งรายละเอียด
    </button>

    <p id="message"
       style="margin-top:15px;color:#00e5ff">
    </p>
  </div>

</main>

<footer>
  <h3>VGA VODNA</h3>
  <p>© 2026 VGA Vodna. All Rights Reserved.</p>
  <p>Game Top Up Website</p>
</footer>

<script>
let currentGame = "";

function selectGame(name, element) {
  currentGame = name;

  document.getElementById("selected")
    .innerText = name;

  document.querySelectorAll(".game")
    .forEach(game => game.classList.remove("active"));

  element.classList.add("active");
}

function showMessage() {
  const id = document.getElementById("playerID").value;
  const pack = document.getElementById("package").value;

  if (!currentGame || !id || !pack) {
    alert("กรุณาเลือกเกมและกรอกข้อมูลให้ครบ");
    return;
  }

  document.getElementById("message").innerText =
    "บันทึกรายละเอียดตัวอย่างแล้ว: " +
    currentGame + " | ID: " + id +
    " | แพ็กเกจ: " + pack;
}
</script>

</body>
</html>
