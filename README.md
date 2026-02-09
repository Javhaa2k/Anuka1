<!DOCTYPE html>
<html lang="mn">
<head>
  <meta charset="UTF-8" />
  <title>My Valentine ❤️</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      color: #fff;
      overflow: hidden;
    }

    .page {
      text-align: center;
      max-width: 600px;
      padding: 40px 20px;
      animation: fadeIn 1s ease;
    }

    h1 {
      font-size: 2.2rem;
      margin-bottom: 30px;
      line-height: 1.4;
    }

    .buttons {
      display: flex;
      gap: 20px;
      justify-content: center;
      flex-wrap: wrap;
    }

    button {
      padding: 14px 32px;
      font-size: 1.1rem;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      transition: transform 0.2s, box-shadow 0.2s;
    }

    button:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 20px rgba(0,0,0,0.25);
    }

    .yes {
      background: #fff;
      color: #ff4f81;
      font-weight: bold;
    }

    .no {
      background: rgba(255,255,255,0.3);
      color: #fff;
    }

    /* YES PAGE */
    .yes-page {
      background: #000;
      width: 100vw;
      height: 100vh;
      display: none;
      align-items: center;
      justify-content: center;
      position: relative;
      overflow: hidden;
    }

    .yes-text {
      color: #fff;
      text-align: center;
      font-size: 1.4rem;
      max-width: 700px;
      line-height: 1.7;
      z-index: 2;
      animation: fadeIn 1.5s ease;
    }

    .heart {
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      transform: rotate(45deg);
      animation: float 4s linear infinite;
    }

    .heart::before,
    .heart::after {
      content: '';
      position: absolute;
      width: 20px;
      height: 20px;
      background: red;
      border-radius: 50%;
    }

    .heart::before { left: -10px; }
    .heart::after { top: -10px; }

    /* NO PAGE */
    .no-page {
      display: none;
      font-size: 1.5rem;
      color: #fff;
      animation: typing 2s steps(20), blink 0.7s infinite;
      white-space: nowrap;
      border-right: 3px solid #fff;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    @keyframes float {
      0% { transform: translateY(100vh) rotate(45deg); opacity: 1; }
      100% { transform: translateY(-10vh) rotate(45deg); opacity: 0; }
    }

    @keyframes typing {
      from { width: 0; }
      to { width: 100%; }
    }

    @keyframes blink {
      50% { border-color: transparent; }
    }
  </style>
</head>
<body>

  <!-- MAIN PAGE -->
  <div class="page" id="mainPage">
    <h1>Хайраа, миний Valentine болох уу? 💖</h1>
    <div class="buttons">
      <button class="yes" onclick="showYes()">Тийм 💕</button>
      <button class="no" onclick="showNo()">Үгүй😢 </button>
    </div>
  </div>

  <!-- YES PAGE -->
  <div class="yes-page" id="yesPage">
    <div class="yes-text">
      ✨ Баярлалаа миний хайр хөөрхөн шүү ✨<br><br>
      Хайр нь хязгааргүй их хайртай шүү ❤️<br><br>
      Энэ хөөрхөн охиныг насан туршдаа хайрланаа 💍
    </div>
  </div>

  <!-- NO PAGE -->
  <div class="no-page" id="noPage">No Internet</div>

  <script>
    function showYes() {
      document.getElementById('mainPage').style.display = 'none';
      document.getElementById('yesPage').style.display = 'flex';
      createHearts();
    }

    function showNo() {
      document.getElementById('mainPage').style.display = 'none';
      const noPage = document.getElementById('noPage');
      noPage.style.display = 'block';

      setTimeout(() => {
        noPage.style.display = 'none';
        document.getElementById('mainPage').style.display = 'block';
      }, 3000);
    }

    function createHearts() {
      for (let i = 0; i < 40; i++) {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = 3 + Math.random() * 3 + 's';
        document.getElementById('yesPage').appendChild(heart);
      }
    }
  </script>

</body>
</html>

