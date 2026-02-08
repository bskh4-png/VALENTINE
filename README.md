<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Ma question très importante ❤️</title>

  <style>
    body {
      margin: 0;
      height: 100vh;
      font-family: system-ui, -apple-system, sans-serif;
      background: linear-gradient(135deg, #ff9a9e 0%, #fad0c4 100%);
      color: #333;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      position: relative;
    }

    h1 {
      font-size: 3.8rem;
      margin: 0 20px 60px;
      text-align: center;
      text-shadow: 0 4px 10px rgba(255,105,180,0.5);
      color: #fff;
      animation: float 3s ease-in-out infinite;
    }

    .buttons {
      display: flex;
      gap: 80px;
      align-items: center;
    }

    button {
      font-size: 2.2rem;
      padding: 20px 60px;
      border: none;
      border-radius: 50px;
      cursor: pointer;
      font-weight: bold;
      box-shadow: 0 8px 25px rgba(0,0,0,0.2);
      transition: transform 0.15s ease;
    }

    #yes {
      background: #ff4757;
      color: white;
    }

    #no {
      background: #57606f;
      color: white;
      position: relative;
    }

    .heart {
      position: absolute;
      font-size: 2.5rem;
      pointer-events: none;
      animation: fadeOut 1.2s forwards;
    }

    @keyframes float {
      0%,100% { transform: translateY(0); }
      50% { transform: translateY(-20px); }
    }

    @keyframes fadeOut {
      from { opacity: 1; transform: translateY(0) scale(1); }
      to { opacity: 0; transform: translateY(-80px) scale(1.4); }
    }
  </style>
</head>

<body>

  <h1>Veux-tu être ma Valentine ? ❤️</h1>

  <div class="buttons">
    <button id="yes">OUI 😍</button>
    <button id="no">Non… 😔</button>
  </div>

  <script>
    const yesBtn = document.getElementById('yes');
    const noBtn = document.getElementById('no');
    let scale = 1;

    noBtn.addEventListener('mouseenter', (event) => {
      scale += 0.35;
      yesBtn.style.transform = `scale(${scale})`;

      const maxX = window.innerWidth - noBtn.offsetWidth;
      const maxY = window.innerHeight - noBtn.offsetHeight;

      noBtn.style.position = 'absolute';
      noBtn.style.left = Math.random() * maxX + 'px';
      noBtn.style.top = Math.random() * maxY + 'px';

      const heart = document.createElement('div');
      heart.className = 'heart';
      heart.textContent = '❤️';
      heart.style.left = event.clientX + 'px';
      heart.style.top = event.clientY + 'px';
      document.body.appendChild(heart);

      setTimeout(() => heart.remove(), 1200);
    });

    yesBtn.addEventListener('click', () => {
      document.body.innerHTML = `
        <div style="
          height:100vh;
          display:flex;
          flex-direction:column;
          align-items:center;
          justify-content:center;
          background: linear-gradient(135deg, #f093fb 0%, #f5576c 100%);
          color:white;
          text-align:center;
          font-size:4rem;
        ">
          <div>YAAAAAAY 🎉❤️</div>
          <div style="font-size:2rem;margin-top:30px;">
            Tu es ma Valentine 😍
          </div>
        </div>
      `;
    });
  </script>

</body>
</html>

