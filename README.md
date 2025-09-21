<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>!!! SISTEM TERKUNCI !!!</title>
  <style>
    body {
      background-color: black;
      color: white;
      font-family: 'Courier New', monospace;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      flex-direction: column;
      text-align: center;
      animation: colorFlash 0.1s infinite alternate;
      overflow: hidden;
    }

    @keyframes colorFlash {
      0% {background-color: red; color: yellow;}
      25% {background-color: orange; color: white;}
      50% {background-color: yellow; color: red;}
      75% {background-color: lime; color: cyan;}
      100% {background-color: cyan; color: magenta;}
    }

    h1, p {
      font-size: 2em;
      animation: textFlash 0.08s infinite alternate;
    }

    @keyframes textFlash {
      0% {opacity: 1;}
      50% {opacity: 0.1;}
      100% {opacity: 1;}
    }

    #timer {
      font-size: 3em;
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      animation: moveTimer 1s infinite alternate;
    }

    @keyframes moveTimer {
      0% {transform: translate(-50%, -50%) rotate(0deg);}
      25% {transform: translate(-40%, -55%) rotate(10deg);}
      50% {transform: translate(-60%, -45%) rotate(-10deg);}
      75% {transform: translate(-50%, -50%) rotate(10deg);}
      100% {transform: translate(-50%, -50%) rotate(0deg);}
    }

    .smoke {
      position: absolute;
      width: 100%;
      height: 100%;
      background: url('https://www.transparenttextures.com/patterns/asfalt-dark.png');
      opacity: 0.2;
      pointer-events: none;
      animation: smokeEffect 5s infinite;
    }

    @keyframes smokeEffect {
      0% {transform: translate(0, 0);}
      100% {transform: translate(0, -100%);}
    }
  </style>
</head>
<body>
  <div class="smoke"></div>
  <h1>!!! SISTEM TERKUNCI !!!</h1>
  <p>Semua file di perangkatmu telah dienkripsi!</p>
  <p>Transfer 100.000 rupiah sekarang atau perangkatmu akan restart sendiri!</p>
  <div id="timer">00:10</div>

  <audio autoplay loop>
    <source src="https://www.soundjay.com/button/beep-10.wav" type="audio/wav">
  </audio>

  <script>
    let time = 10;
    const timer = document.getElementById('timer');

    function randomPopup() {
      const messages = [
        "PERINGATAN! Perangkatmu dalam bahaya!",
        "File sedang dienkripsi!",
        "Bayar jaminan 100.000 sekarang!",
        "Kesalahan sistem kritis!"
      ];
      if (Math.random() < 0.3) {
        alert(messages[Math.floor(Math.random() * messages.length)]);
      }
    }

    function updateTimer() {
      timer.textContent = `00:${time.toString().padStart(2, '0')}`;
      if (time > 0) {
        time--;
        randomPopup();
      } else {
        clearInterval(countdown);
        alert("Perangkatmu sekarang 'restart'! Santai bro 😎 – cuma prank kok");
      }
    }

    const countdown = setInterval(updateTimer, 1000);
  </script>
</body>
</html># cara_membuat_web
