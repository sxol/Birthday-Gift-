<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Happy Birthday!</title>
  <style>
    body {
      background: #fff0f6;
      overflow: hidden;
      margin: 0;
      height: 100vh;
      width: 100vw;
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      font-family: 'Comic Sans MS', cursive, sans-serif;
    }

    h1 {
      color: #d72660;
      font-size: 3em;
      margin-bottom: 0.5em;
      text-shadow: 0 4px 10px #fff0f6;
    }

    .heart {
      position: absolute;
      width: 40px;
      height: 40px;
      background: #ff6f91;
      left: 50%;
      top: 80%;
      transform: translate(-50%, 0) scale(1);
      animation: float 3s linear forwards;
      opacity: 0.8;
      pointer-events: none;
    }
    .heart:before,
    .heart:after {
      content: '';
      position: absolute;
      width: 40px;
      height: 40px;
      background: #ff6f91;
      border-radius: 50%;
    }
    .heart:before {
      top: -20px;
      left: 0;
    }
    .heart:after {
      left: 20px;
      top: 0;
    }

    @keyframes float {
      0% {
        transform: translate(-50%, 0) scale(1);
        opacity: 0.8;
      }
      80% {
        opacity: 1;
      }
      100% {
        transform: translate(var(--x), -80vh) scale(var(--scale));
        opacity: 0;
      }
    }
  </style>
</head>
<body>
  <h1>Happy Birthday, Love! 💖</h1>
  <script>
    function createHeart() {
      const heart = document.createElement('div');
      heart.className = 'heart';
      // Randomize horizontal movement
      const x = (Math.random() - 0.5) * 60 + 'vw';
      // Randomize scale
      const scale = Math.random() * 0.8 + 0.6;
      heart.style.setProperty('--x', x);
      heart.style.setProperty('--scale', scale);
      heart.style.left = Math.random() * 100 + 'vw';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 3000);
    }

    setInterval(createHeart, 300);

    // Optional: Extra burst when the page loads
    for (let i = 0; i < 15; i++) {
      setTimeout(createHeart, i * 100);
    }
  </script>
</body>
</html>
