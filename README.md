<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Valentine 💘</title>
  <style>
    body {
      height: 100vh;
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      font-family: 'Poppins', sans-serif;
      overflow: hidden;
    }

    .card {
      background: white;
      padding: 40px;
      border-radius: 20px;
      text-align: center;
      box-shadow: 0 15px 30px rgba(0,0,0,0.2);
      z-index: 2;
    }

    h1 {
      color: #ff3f6c;
      margin-bottom: 30px;
    }

    button {
      padding: 12px 30px;
      font-size: 18px;
      border: none;
      border-radius: 30px;
      cursor: pointer;
      position: relative;
    }

    #yes {
      background: #ff3f6c;
      color: white;
      margin-right: 20px;
    }

    #no {
      background: #ddd;
      color: #333;
      position: absolute;
    }

    /* 💖 Heart Animation */
    .heart {
      position: absolute;
      color: rgba(255, 255, 255, 0.8);
      font-size: 20px;
      animation: floatUp 6s linear infinite;
    }

    @keyframes floatUp {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }
  </style>
</head>
<body>

  <!-- 🎵 Romantic Music -->
  <audio id="music" autoplay loop>
    <source src="https://files.freemusicarchive.org/storage-freemusicarchive-org/music/no_curator/Scott_Holmes_Music/Happy_Music/Scott_Holmes_Music_-_03_-_Our_Big_Adventure.mp3" type="audio/mpeg">
  </audio>

  <div class="card">
    <h1>Priyanka 💖<br>Will you be my Valentine?</h1>
    <button id="yes" onclick="yesClick()">Yes 💕</button>
    <button id="no">No 😜</button>
  </div>

  <script>
    const noBtn = document.getElementById("no");

    noBtn.addEventListener("mouseover", moveButton);
    noBtn.addEventListener("touchstart", moveButton);

    function moveButton() {
      const x = Math.random() * (window.innerWidth - 100);
      const y = Math.random() * (window.innerHeight - 100);
      noBtn.style.left = x + "px";
      noBtn.style.top = y + "px";
    }

    function yesClick() {
      document.body.innerHTML = `
        <div style="
          height:100vh;
          display:flex;
          justify-content:center;
          align-items:center;
          background:linear-gradient(135deg,#ff758c,#ff7eb3);
          font-family:Poppins;
          text-align:center;
          color:white;
        ">
          <h1>Yayyy! 💕<br>Priyanka is my Valentine 😍💖</h1>
        </div>
      `;
    }

    /* 💗 Create floating hearts */
    setInterval(() => {
      const heart = document.createElement("div");
      heart.className = "heart";
      heart.innerHTML = "💖";
      heart.style.left = Math.random() * 100 + "vw";
      heart.style.fontSize = Math.random() * 20 + 20 + "px";
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 6000);
    }, 300);
  </script>

</body>
</html>
