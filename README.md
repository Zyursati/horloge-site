<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Horloge Précise</title>
  <style>
    body {
      background-color: #0e0e0e;
      display: flex;
      align-items: center;
      justify-content: center;
      height: 100vh;
      margin: 0;
      overflow: hidden;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      cursor: none;
    }

    /* HORLOGE avec LUEUR FORTEMENT PULSANTE */
    .clock-container {
      position: relative;
      z-index: 1;
      border: 2px solid #ffffff88;
      background-color: #000000;
      color: white;
      padding: 40px 60px;
      border-radius: 16px;
      font-size: 4em;
      font-weight: bold;
      text-align: center;
      box-shadow: 0 0 30px rgba(255, 255, 255, 0.3);
      animation: pulseGlow 3s infinite ease-in-out;
    }

    @keyframes pulseGlow {
      0%, 100% {
        box-shadow: 0 0 30px rgba(255, 255, 255, 0.3);
      }
      50% {
        box-shadow: 0 0 60px rgba(255, 255, 255, 0.6);
      }
    }

    /* PARTICULES */
    .particles-container {
      position: absolute;
      width: 100%;
      height: 100%;
      top: 0; left: 0;
      overflow: hidden;
      z-index: 0;
      pointer-events: none;
    }

    .particle {
      position: absolute;
      width: 6px;
      height: 6px;
      border-radius: 50%;
      background-color: #ffffff;
      opacity: 0;
      animation: blink 1.2s infinite;
      box-shadow: 0 0 8px rgba(255, 255, 255, 0.8);
    }

    @keyframes blink {
      0% { opacity: 0; }
      20% { opacity: 1; }
      80% { opacity: 0; }
      100% { opacity: 0; }
    }
  </style>
</head>
<body>
  <div class="particles-container" id="particles-container"></div>
  <div class="clock-container" id="clock">--:--:--.---</div>

  <script>
    function updateClock() {
      const now = new Date();
      const hours = String(now.getHours()).padStart(2, '0');
      const minutes = String(now.getMinutes()).padStart(2, '0');
      const seconds = String(now.getSeconds()).padStart(2, '0');
      const milliseconds = String(now.getMilliseconds()).padStart(3, '0');
      const timeString = `${hours}:${minutes}:${seconds}.${milliseconds}`;
      document.getElementById('clock').textContent = timeString;
      requestAnimationFrame(updateClock);
    }

    // Création de particules dynamiquement
    const container = document.getElementById('particles-container');
    const particleCount = 150;

    for (let i = 0; i < particleCount; i++) {
      const p = document.createElement('div');
      p.classList.add('particle');
      p.style.top = `${Math.random() * 100}%`;
      p.style.left = `${Math.random() * 100}%`;
      p.style.animationDelay = `${Math.random()}s`;
      container.appendChild(p);
    }

    // Gestion du curseur
    document.body.style.cursor = 'none';

    document.addEventListener('mousedown', (e) => {
      if (e.button === 0) {
        document.body.style.cursor = 'default';
      }
    });

    document.addEventListener('mouseup', (e) => {
      if (e.button === 0) {
        document.body.style.cursor = 'none';
      }
    });

    updateClock();
  </script>
</body>
</html>

